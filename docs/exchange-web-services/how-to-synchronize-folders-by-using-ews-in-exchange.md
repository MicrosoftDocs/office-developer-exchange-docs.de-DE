---
title: Synchronisieren von Ordnern in Exchange mithilfe der Exchange-Webdienste
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d3bbacd1-8e4b-4fd0-8d27-4cbbc045ec3f
description: Erfahren Sie, wie die EWS Managed API oder EWS zum Abrufen einer Liste von Ordnern oder eine Liste von Ordnern, die zum Synchronisieren von Ihrem Clients geändert haben, verwenden.
ms.openlocfilehash: 4b0686134d642da34b2890a0e692e3d03e4a9fb1
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "19757008"
---
# <a name="synchronize-folders-by-using-ews-in-exchange"></a>Synchronisieren von Ordnern in Exchange mithilfe der Exchange-Webdienste

Erfahren Sie, wie die EWS Managed API oder EWS zum Abrufen einer Liste von Ordnern oder eine Liste von Ordnern, die zum Synchronisieren von Ihrem Clients geändert haben, verwenden.
  
EWS in Exchange verwendet Element Synchronisierung und Ordner der Synchronisierung der Inhalt von Postfächern Synchronisierung zwischen dem Client und Server. Ordnersynchronisation Ruft die ursprüngliche Liste der Ordner aus einer Stammordner ab und ruft dann im Laufe der Zeit Änderungen, die für diese Ordner vorgenommen wurden und ruft sowie neue Ordner.
  
Wenn Sie mithilfe der EWS Managed API, Sie zuerst [die ursprüngliche Liste der Ordner im Stammordner erhalten möchten](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_cesyncinitialewsma) , mithilfe der Methode [ExchangeService.SyncFolderHierarchy](http://msdn.microsoft.com/en-us/library/microsoft.exchange.webservices.data.exchangeservice.syncfolderhierarchy%28v=exchg.80%29.aspx) Ordnersynchronisation durchführen. Dann aktualisieren Sie den Wert des Parameters _cSyncState_ bei nachfolgenden Aufrufen, um die Liste der neuen und geänderten Ordner abzurufen. 
  
Mithilfe der Exchange-Webdienste führen Ordnersynchronisation Sie die [ursprüngliche Liste der Ordner im Stammordner](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_cesyncewsrequest) mit der [SyncFolderHierarchy](http://msdn.microsoft.com/library/b31916b1-bc6c-4451-a475-b7c5417f752d%28Office.15%29.aspx) -Operation anfordern, Verarbeiten der Antwort und anschließend zu einem bestimmten Zeitpunkt in der Zukunft [die Änderungen in den Ordnern in das Stammverzeichnis](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_cesyncrespews), und die Antwort zu analysieren. Nachdem der Client die Liste der ursprünglichen oder geänderten Ordner empfangen sie [Updates lokal macht](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_nextsteps). Wie und wann Sie Änderungen in der Zukunft abrufen, hängt von der [Synchronisierung Entwurfsmuster](mailbox-synchronization-and-ews-in-exchange.md#bk_syncpatterns) , Ihre Anwendung verwendet wird. 
  
## <a name="get-the-list-of-all-folders-or-changed-folders-by-using-the-ews-managed-api"></a>Abrufen der Liste aller Ordner oder geänderten Ordner mithilfe der EWS Managed API
<a name="bk_cesyncinitialewsma"> </a>

Im folgenden Codebeispiel wird veranschaulicht, wie die ursprüngliche Liste von Ordnern in einem Stammordner rufen und anschließend eine Liste der Änderungen auf Ordner im Stammordner gespeichert, die seit der vorherigen Synchronisierung aufgetreten sind. Während der anfänglichen Aufruf der [ExchangeService.SyncFolderHierarchy](http://msdn.microsoft.com/en-us/library/microsoft.exchange.webservices.data.exchangeservice.syncfolderhierarchy%28v=exchg.80%29.aspx) -Methode den _cSyncState_ -Wert auf null festgelegt. Wenn die Methode abgeschlossen ist, speichern Sie den _cSyncState_ Wert lokal für den nächsten Aufruf der **SyncFolderHierarchy** -Methode verwenden. In der ersten Aufruf und die nachfolgenden Aufrufen werden die Ordner in Batches von zehn mithilfe von aufeinander folgenden Aufrufen der Methode **SyncFolderHierarchy** bis keine weitere Änderungen bleiben abgerufen. In diesem Beispiel wird den Parameter _PropertySet_ IdOnly um Anrufe an die Exchange-Datenbank eine [bewährte Methode Synchronisierung ist](mailbox-synchronization-and-ews-in-exchange.md#bk_bestpractices)reduzieren. In diesem Beispiel wird davon ausgegangen, dass **-Dienst** eine gültige **ExchangeService** Objekt Bindung ist und diese _cSyncState_ stellt den Synchronisierungsstatus an, der von einem vorherigen Aufruf von **SyncFolderHierarchy**zurückgegeben wurde. 
  
```cs
// Get a list of all folders in the mailbox by calling SyncFolderHierarchy.
// The folderId parameter must be set to the root folder to synchronize. 
// The propertySet parameter is set to IdOnly to reduce calls to the Exchange database
// because any additional properties result in additional calls to the Exchange database. 
// The syncState parameter is set to cSyncState, which should be null in the initial call, 
// and should be set to the sync state returned by the previous SyncFolderHierarchy call 
// in subsequent calls.
ChangeCollection<FolderChange> fcc = service.SyncFolderHierarchy(new FolderId(WellKnownFolderName.Root), PropertySet.IdOnly, cSyncState);
// If the count of changes is zero, there are no changes to synchronize.
if (fcc.Count == 0)
{
    Console.WriteLine("There are no folders to synchronize.");
}
// Otherwise, write all the changes included in the response 
// to the console. 
// For the initial synchronization, all the changes will be of type
// ChangeType.Create.
else
{
    foreach (FolderChange fc in fcc)
    {
        Console.WriteLine("ChangeType: " + fc.ChangeType.ToString());
        Console.WriteLine("FolderId: " + fc.FolderId);
        Console.WriteLine("===========");
    }
}
// Save the sync state for use in future SyncFolderItems requests.
// The sync state is used by the server to determine what changes to report
// to the client.
string fSyncState = fcc.SyncState;

```

Rufen Sie nach dem Sie die Liste der neuen oder geänderten Ordner auf dem Server, [Erstellen oder aktualisieren den Ordner auf dem Client](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_nextsteps)ab.
  
## <a name="get-the-initial-list-of-folders-by-using-ews"></a>Möchten Sie die ursprüngliche Liste der Ordner mithilfe der Exchange-Webdienste
<a name="bk_cesyncewsrequest"> </a>

Das folgende Beispiel zeigt eine XML-Anforderung die anfänglichen Ordnerhierarchie mithilfe des Vorgangs [SyncFolderHierarchy](http://msdn.microsoft.com/library/b31916b1-bc6c-4451-a475-b7c5417f752d%28Office.15%29.aspx) abrufen. Dies ist auch die XML-Anfrage, dass die EWS Managed API, wenn gesendet [die Liste der ursprünglichen Ordner mithilfe der SyncFolderHierarchy-Methode abrufen](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_cesyncinitialewsma). Das Element [Synchronisierungsstatus](http://msdn.microsoft.com/library/e5ebaae3-0f07-481d-ac67-d9687a3c7ac3%28Office.15%29.aspx) des Vorgangs [SyncFolderHierarchy](http://msdn.microsoft.com/library/7f0de089-8876-47ec-a871-df118ceae75d%28Office.15%29.aspx) ist nicht mit inbegriffen, da dies die anfängliche Synchronisierung ist. In diesem Beispiel wird das Element [BaseShape](http://msdn.microsoft.com/library/42c04f3b-abaa-4197-a3d6-d21677ffb1c0%28Office.15%29.aspx) **IdOnly** um Anrufe an die Exchange-Datenbank eine [bewährte Methode Synchronisierung ist](mailbox-synchronization-and-ews-in-exchange.md#bk_bestpractices)reduzieren.
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                    xmlns:m="http://schemas.microsoft.com/exchange/services/2006/messages"
                    xmlns:t="http://schemas.microsoft.com/exchange/services/2006/types"
                    xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Header>
    <t:RequestServerVersion Version="Exchange2013" />
  </soap:Header>
  <soap:Body>
    <m:SyncFolderHierarchy>
      <m:FolderShape>
        <t:BaseShape>IdOnly</t:BaseShape>
      </m:FolderShape>
      <m:SyncFolderId>
        <t:DistinguishedFolderId Id="root" />
      </m:SyncFolderId>
    </m:SyncFolderHierarchy>
  </soap:Body>
</soap:Envelope>
```

Das folgende Beispiel zeigt die XML-Antwort, die vom Server zurückgegeben wird, nachdem die [SyncFolderHierarchy](http://msdn.microsoft.com/library/b31916b1-bc6c-4451-a475-b7c5417f752d%28Office.15%29.aspx) Vorgang Anforderung verarbeitet. Die erste Antwort enthält Elemente für alle Ordner [Erstellen](http://msdn.microsoft.com/library/6b463d0a-70e9-40c5-ade4-c7d9a5f36bc1%28Office.15%29.aspx) , da alle Ordner neu beim eine anfängliche Synchronisierung berücksichtigt werden. Die Werte der einige Attribute und Elemente wurden zur besseren Lesbarkeit gekürzt wurde, und einige **Erstellen** Element Blöcke der Kürze halber entfernt wurden. 
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ServerVersionInfo MajorVersion="15"
                         MinorVersion="0"
                         MajorBuildNumber="785"
                         MinorBuildNumber="6"
                         Version="V2_6"
                         xmlns:h="http://schemas.microsoft.com/exchange/services/2006/types"
                         xmlns="http://schemas.microsoft.com/exchange/services/2006/types"
                         xmlns:xsd="http://www.w3.org/2001/XMLSchema"
                         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"/>
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <m:SyncFolderHierarchyResponse xmlns:m="http://schemas.microsoft.com/exchange/services/2006/messages"
                                   xmlns:t="http://schemas.microsoft.com/exchange/services/2006/types">
      <m:ResponseMessages>
        <m:SyncFolderHierarchyResponseMessage ResponseClass="Success">
          <m:ResponseCode>NoError</m:ResponseCode>
          <m:SyncState>H4sIAA==</m:SyncState>
          <m:IncludesLastFolderInRange>true</m:IncludesLastFolderInRange>
          <m:Changes>
            <t:Create>
              <t:Folder>
                <t:FolderId Id="AAMkADM="
                            ChangeKey="AQAAABYA"/>
              </t:Folder>
            </t:Create>
            <t:Create>
              <t:Folder>
                <t:FolderId Id="AAMkADMzM="
                            ChangeKey="AQAAABY"/>
              </t:Folder>
            </t:Create>
            <t:Create>
              <t:Folder>
                <t:FolderId Id="AAMkAD/AAA="
                            ChangeKey="AQAAABYA"/>
              </t:Folder>
            </t:Create>
            <t:Create>
              <t:Folder>
                <t:FolderId Id="AAMkADBh="
                            ChangeKey="AQAAABYA"/>
              </t:Folder>
            </t:Create>
            ...
          </m:Changes>
        </m:SyncFolderHierarchyResponseMessage>
      </m:ResponseMessages>
    </m:SyncFolderHierarchyResponse>
  </s:Body>
</s:Envelope>
```

Abgerufen Sie nachdem die Liste der neue Ordner auf dem Server, [Erstellen Sie die Ordner auf dem Client](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_nextsteps).
  
## <a name="get-the-changes-since-the-last-sync-by-using-ews"></a>Abrufen von Änderungen seit der letzten Synchronisierung mithilfe der Exchange-Webdienste
<a name="bk_cesyncrespews"> </a>

Das folgende Beispiel zeigt die XML-Anforderung an die Liste der Änderungen auf Ordner im Stammordner abrufen, indem Sie den Vorgang [SyncFolderHierarchy](http://msdn.microsoft.com/library/b31916b1-bc6c-4451-a475-b7c5417f752d%28Office.15%29.aspx) . Dies ist auch, dass die EWS Managed API, wenn gesendet die XML-Anfrage [Abrufen der Liste der Änderungen in den Stammordner](how-to-synchronize-folders-by-using-ews-in-exchange.md#bk_cesyncinitialewsma). In diesem Beispiel wird den [Synchronisierungsstatus](http://msdn.microsoft.com/library/e5ebaae3-0f07-481d-ac67-d9687a3c7ac3%28Office.15%29.aspx) Elementwert auf den Wert in der vorherigen Antwort zurückgegeben. Und zur Veranschaulichung in diesem Beispiel wird das Element [BaseShape](http://msdn.microsoft.com/library/42c04f3b-abaa-4197-a3d6-d21677ffb1c0%28Office.15%29.aspx) **AllProperties** anstelle von **IdOnly** zum Anzeigen der zusätzlichen Eigenschaften zurückgegeben. Festlegen der [BaseShape](http://msdn.microsoft.com/library/42c04f3b-abaa-4197-a3d6-d21677ffb1c0%28Office.15%29.aspx) -Elements auf **IdOnly** ist eine [bewährte Methode Synchronisierung](mailbox-synchronization-and-ews-in-exchange.md#bk_bestpractices). Der Wert der **Synchronisierungsstatus** wurde zur besseren Lesbarkeit gekürzt. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
                    xmlns:m="http://schemas.microsoft.com/exchange/services/2006/messages"
                    xmlns:t="http://schemas.microsoft.com/exchange/services/2006/types"
                    xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Header>
    <t:RequestServerVersion Version="Exchange2013" />
  </soap:Header>
  <soap:Body>
    <m:SyncFolderHierarchy>
      <m:FolderShape>
        <t:BaseShape>AllProperties</t:BaseShape>
      </m:FolderShape>
      <m:SyncFolderId>
        <t:DistinguishedFolderId Id="root" />
      </m:SyncFolderId>
      <m:SyncState>H4sIAA==</m:SyncState>
    </m:SyncFolderHierarchy>
  </soap:Body>
</soap:Envelope>
```

Das folgende Beispiel zeigt die XML-Antwort, die vom Server zurückgegeben wird, nachdem der [Vorgang SyncFolderHierarchy](http://msdn.microsoft.com/library/b31916b1-bc6c-4451-a475-b7c5417f752d%28Office.15%29.aspx) Anforderung vom Client verarbeitet. Diese Antwort gibt an, dass ein Ordner aktualisiert wurde, einen Ordner erstellt wurde, und ein Ordner, seit der vorherigen Synchronisierung gelöscht wurde. Der Wert der [Synchronisierungsstatus](http://msdn.microsoft.com/library/e5ebaae3-0f07-481d-ac67-d9687a3c7ac3%28Office.15%29.aspx) -Element, Attribute **Id** und **ChangeKey** Attribute wurde zur besseren Lesbarkeit gekürzt. 
  
Denken Sie daran, dass die Anforderung der **AllProperties**[BaseShape](http://msdn.microsoft.com/library/42c04f3b-abaa-4197-a3d6-d21677ffb1c0%28Office.15%29.aspx)enthalten. Dies ist nur zu Demonstrationszwecken. Es wird empfohlen, dass Sie das **BaseShape** -Element in der Produktion auf **IdOnly** festgelegt. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
<h:ServerVersionInfo MajorVersion="15" MinorVersion="0" MajorBuildNumber="745" MinorBuildNumber="21" Version="V2_3" 
           xmlns:h="http://schemas.microsoft.com/exchange/services/2006/types" 
           xmlns="http://schemas.microsoft.com/exchange/services/2006/types" 
           xmlns:xsd="http://www.w3.org/2001/XMLSchema" 
           xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" />
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <m:SyncFolderHierarchyResponse xmlns:m="http://schemas.microsoft.com/exchange/services/2006/messages" 
            xmlns:t="http://schemas.microsoft.com/exchange/services/2006/types">
      <m:ResponseMessages>
        <m:SyncFolderHierarchyResponseMessage ResponseClass="Success">
          <m:ResponseCode>NoError</m:ResponseCode>
          <m:SyncState>H4sIAAA</m:SyncState>
          <m:IncludesLastFolderInRange>true</m:IncludesLastFolderInRange>
          <m:Changes>
            <t:Update>
              <t:Folder>
                <t:FolderId Id="AAMkADM=" ChangeKey="AQAAABY" />
                <t:ParentFolderId Id="AQMkADMzADI1==" ChangeKey="AQAAAA==" />
                <t:FolderClass>IPF.Note</t:FolderClass>
                <t:DisplayName>Meeting Notes</t:DisplayName>
                <t:TotalCount>3</t:TotalCount>
                <t:ChildFolderCount>0</t:ChildFolderCount>
                <t:EffectiveRights>
                  <t:CreateAssociated>true</t:CreateAssociated>
                  <t:CreateContents>true</t:CreateContents>
                  <t:CreateHierarchy>true</t:CreateHierarchy>
                  <t:Delete>true</t:Delete>
                  <t:Modify>true</t:Modify>
                  <t:Read>true</t:Read>
                  <t:ViewPrivateItems>true</t:ViewPrivateItems>
                </t:EffectiveRights>
                <t:UnreadCount>0</t:UnreadCount>
              </t:Folder>
            </t:Update>
            <t:Create>
              <t:Folder>
                <t:FolderId Id="AAMkADMzM=" ChangeKey="AQAAABYAA" />
                <t:ParentFolderId Id="AQMkO67A==" ChangeKey="AQAAAA==" />
                <t:FolderClass>IPF.Note</t:FolderClass>
                <t:DisplayName>Schedules</t:DisplayName>
                <t:TotalCount>0</t:TotalCount>
                <t:ChildFolderCount>0</t:ChildFolderCount>
                <t:EffectiveRights>
                  <t:CreateAssociated>true</t:CreateAssociated>
                  <t:CreateContents>true</t:CreateContents>
                  <t:CreateHierarchy>true</t:CreateHierarchy>
                  <t:Delete>true</t:Delete>
                  <t:Modify>true</t:Modify>
                  <t:Read>true</t:Read>
                  <t:ViewPrivateItems>true</t:ViewPrivateItems>
                </t:EffectiveRights>
                <t:UnreadCount>0</t:UnreadCount>
              </t:Folder>
            </t:Create>
            <t:Delete>
              <t:FolderId Id="AAMkAD/AAA=" ChangeKey="AQAAAA==" />
            </t:Delete>
          </m:Changes>
        </m:SyncFolderHierarchyResponseMessage>
      </m:ResponseMessages>
    </m:SyncFolderHierarchyResponse>
  </s:Body>
</s:Envelope>

```

## <a name="update-the-client"></a>Aktualisieren des Clients
<a name="bk_nextsteps"> </a>

Wenn Sie die EWS Managed API, nachdem Sie die Liste der neuen oder geänderten Ordner abrufen, verwenden Sie die [Folder.Load](http://msdn.microsoft.com/en-us/library/microsoft.exchange.webservices.data.folder.load%28v=exchg.80%29.aspx) -Methode zum Abrufen von Eigenschaften für die neue oder geänderte Elemente, die Eigenschaften in die lokale Werte vergleichen und aktualisieren oder erstellen Sie die Ordner auf dem Client verwenden. 
  
Wenn Sie Exchange-Webdienste verwenden, verwenden Sie die [GetFolder-Vorgang](http://msdn.microsoft.com/library/355bcf93-dc71-4493-b177-622afac5fdb9%28Office.15%29.aspx) zum Abrufen von Eigenschaften für die neue oder geänderte Ordner und aktualisieren oder erstellen Sie die Ordner auf dem Client. 
  
## <a name="see-also"></a>Siehe auch

- [Postfachsynchronisierung und EWS in Exchange](mailbox-synchronization-and-ews-in-exchange.md)   
- [Synchronisieren von Elementen mithilfe von EWS in Exchange](how-to-synchronize-items-by-using-ews-in-exchange.md)   
- [Fehlerbehandlung Synchronisierung-bezogene in EWS in Exchange](handling-synchronization-related-errors-in-ews-in-exchange.md)
    
