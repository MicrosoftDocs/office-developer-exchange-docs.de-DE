---
title: Zugriff auf Öffentliche Ordner mit EWS in Exchange
manager: sethgros
ms.date: 7/17/2015
ms.audience: Developer
ms.assetid: d9372057-1deb-45de-8f98-b9149604429a
description: Erfahren Sie, wie Sie EWS und die EWS Managed API zum Zugriff auf öffentliche Ordner und Weiterleiten von Anforderungen für öffentliche Ordner in Exchange verwenden können.
localization_priority: Priority
ms.openlocfilehash: e921a77b250e11e974b0c47b1d28a8e020837d44
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44460211"
---
# <a name="public-folder-access-with-ews-in-exchange"></a>Zugriff auf Öffentliche Ordner mit EWS in Exchange

Erfahren Sie, wie Sie EWS und die EWS Managed API zum Zugriff auf öffentliche Ordner und Weiterleiten von Anforderungen für öffentliche Ordner in Exchange verwenden können.
  
Öffentliche Ordner dienen als freigegebene Repositories für Elemente, auf die Benutzer in Ihrer Organisation zugreifen können. Mit Office 365, Exchange Online und lokalen Versionen von Exchange ab Exchange 2013 wird eine neue Architektur für öffentliche Ordner eingeführt. Öffentliche Ordner in Exchange verwenden ein spezielles Postfachdesign (anstelle einer Öffentliche Ordner-Datenbank), um die Hierarchie und Inhalte von öffentlichen Ordnern zu speichern. Die Berechtigungen für öffentliche Ordner werden über die rollenbasierte Zugriffssteuerung (RBAC) verwaltet.
  
Clientzugriffstechnologien, wie Exchange-Webdienste (EWS) und die EWS Managed API ermöglichen den programmgesteuerten Zugriff auf die Öffentliche Ordner-Hierarchie und die Elemente in einer Öffentliche Ordner-Datenbank. Dieser Artikel enthält Informationen darüber, wie Sie mit EWS und der EWS Managed API auf öffentliche Ordner und Daten in öffentlichen Ordnern zugreifen können. 
  
## <a name="ews-operations-and-ews-managed-api-methods-for-public-folder-access"></a>EWS-Vorgänge und EWS Managed API-Methoden für den Zugriff auf öffentliche Ordner
<a name="bk_functionality"> </a>

Die meisten der wichtigen EWS-Vorgänge unterstützen den Zugriff auf öffentliche Ordner. Sie können die in der folgenden Tabelle aufgeführten Ordner- und Datei-Vorgänge sowie EWS Managed API-Methoden zum Arbeiten mit öffentlichen Ordnern verwenden.
  
Weitere Informationen über EWS Managed API-Methoden finden Sie unter [EWS Managed API-Namespaces](https://msdn.microsoft.com/library/jj220535%28v=exchg.80%29.aspx).
  
|**EWS-Vorgang**|**EWS Managed API-Methode**|
|:-----|:-----|
|[CreateFolder-Vorgang](https://msdn.microsoft.com/library/6f6c334c-b190-4e55-8f0a-38f2a018d1b3%28Office.15%29.aspx) <br/> |**Folder.Save()** <br/> |
|[UpdateFolder-Vorgang](https://msdn.microsoft.com/library/3494c996-b834-4813-b1ca-d99642d8b4e7%28Office.15%29.aspx) <br/> |**Folder.Update()** <br/> |
|[DeleteFolder-Vorgang](https://msdn.microsoft.com/library/b0f92682-4895-4bcf-a4a1-e4c2e8403979%28Office.15%29.aspx) <br/> |**Folder.Delete()** <br/> |
|[MoveFolder-Vorgang](https://msdn.microsoft.com/library/c7233966-6c87-4a14-8156-b1610760176d%28Office.15%29.aspx)<sup>1</sup> <br/> |**Folder.Move()** <br/> |
|[CopyFolder-Vorgang](https://msdn.microsoft.com/library/c7ea0d68-9793-4144-b378-d99536776db9%28Office.15%29.aspx)<sup>2</sup> <br/> |**Folder.Copy()** <br/> |
|[GetFolder-Vorgang](https://msdn.microsoft.com/library/355bcf93-dc71-4493-b177-622afac5fdb9%28Office.15%29.aspx) <br/> |**Folder.Bind()** <br/> |
|[EmptyFolder-Vorgang](https://msdn.microsoft.com/library/98161486-e2f2-480f-8d5d-708ba81b208a%28Office.15%29.aspx)<sup>3</sup> <br/> |**Folder.Empty-Methode** <br/> |
|[FindFolder-Vorgang](https://msdn.microsoft.com/library/7a9855aa-06cc-45ba-ad2a-645c15b7d031%28Office.15%29.aspx) <br/> |**ExchangeService.FindFolders()** <br/> **Folder.FindFolders()** <br/> |
|[CreateItem-Vorgang](https://msdn.microsoft.com/library/78a52120-f1d0-4ed7-8748-436e554f75b6%28Office.15%29.aspx) <br/> |**Item.Save()** <br/> |
|[MoveItem-Vorgang](https://msdn.microsoft.com/library/dcf40fa7-7796-4a5c-bf5b-7a509a18d208%28Office.15%29.aspx) <br/> |**Item.Move()** <br/> |
|[CopyItem-Vorgang](https://msdn.microsoft.com/library/bcc68f9e-d511-4c29-bba6-ed535524624a%28Office.15%29.aspx) <br/> |**Item.Copy()** <br/> |
|[UpdateItem-Vorgang](https://msdn.microsoft.com/library/5d027523-e0bc-4da2-b60b-0cb9fc1fdfe4%28Office.15%29.aspx) <br/> |**Item.Update()** <br/> |
|[DeleteItem-Operation](https://msdn.microsoft.com/library/3e26c416-fa12-476e-bfd2-5c1f4bb7b348%28Office.15%29.aspx) <br/> |**Item.Delete()** <br/> |
|[FindItem-Vorgang](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx)<sup>4</sup> <br/> |**ExchangeService.FindItems()** <br/> **Folder.FindItems()** <br/> |
|[GetItem-Vorgang](https://msdn.microsoft.com/library/e3590b8b-c2a7-4dad-a014-6360197b68e4%28Office.15%29.aspx) <br/> |**Item.Bind()** <br/> |
|[ConvertId-Vorgang](https://msdn.microsoft.com/library/47d96cf6-9e2f-4fc0-9682-7258d3fbf918%28Office.15%29.aspx)<sup>5</sup> <br/> |**ExchangeService.ConvertId()** <br/> **ExchangeService.ConvertIds()** <br/> |
   
<sup>1</sup>Das Verschieben von Ordnern zwischen öffentlichen und privaten Ordnern wird ab Exchange 2013 nicht mehr unterstützt. 
  
<sup>2</sup>Dieser Vorgang gilt nur für öffentliche Ordner in Exchange Server 2007 und Exchange Server 2010. 
  
<sup>3</sup>Dieser Vorgang gilt nur für öffentliche Ordner in Exchange 2010. 
  
<sup>4</sup>Die indizierte Volltextsuche innerhalb eines einzelnen öffentlichen Ordners mithilfe der Suchoption QueryString wird erst ab Exchange 2013 unterstützt. 
  
<sup>5</sup>Der Vorgang ConvertId konvertiert IDs von öffentlichen Ordnern nicht ordnungsgemäß von einer EWS-ID in eine Speicher-ID. Zur [Problemumgehung](https://msdn.microsoft.com/library/47d96cf6-9e2f-4fc0-9682-7258d3fbf918%28Office.15%29.aspx#bk_usingConvertId) können Sie die zurückgegebene Kennung manuell anpassen.
  
Die folgenden Vorgänge werden für öffentliche Ordner ab Exchange 2013 nicht oder nur teilweise unterstützt:
  
- **CopyFolder** (nicht unterstützt). Sie können die Funktionalität des **CopyFolder**-Vorgangs mit **CreateFolder** in Verbindung mit dem **CopyItems**-Vorgang abbilden. 
    
- **EmptyFolder** (nicht unterstützt). Sie können die Funktionalität des **EmptyFolder**-Vorgangs mit **FindItem** in Verbindung mit dem **DeleteItem**-Vorgang abbilden. 
    
- **MoveFolder** (teilweise unterstützt). Sie können Ordner nicht zwischen privaten und öffentlichen Ordner verschieben. Sie können Ordner zwischen privaten und öffentlichen Ordnern in Exchange 2007 und Exchange 2010 verschieben. Sie können Ordner zwischen öffentlichen Ordner in allen Versionen von Exchange verschieben. 
    
Folgende Funktionen für öffentliche Ordner werden mit EWS und der EWS Managed API nicht unterstützt:
  
- Verwendung von **SyncFolderHierarchy**. Verwenden Sie die Vorgänge **FindFolder**, **GetFolder** und **SyncFolderItems** zum Synchronisieren von Elementen und Ordnern in einem Postfach für öffentliche Ordner. 
    
- Tiefensuche in einer Öffentliche Ordner-Hierarchie. Verwenden Sie rekursive **FindFolder**-Vorgangsaufrufe zum Durchlaufen einer Öffentliche Ordner-Hierarchie. 
    
- Erstellen einer Öffentliche Ordner-Hierarchie mit dem **CreateFolderPath**-Vorgang. Verwenden Sie bei einem Postfach für öffentliche Ordner als Ziel den **CreateFolder**-Vorgang für jede Ordnerebene in einer bestimmten Ordnerhierarchie. 
    
- Speichern von Kopien gesendeter E-Mails mit dem **CreateItem**-Vorgang. Verwenden Sie stattdessen den **MoveItem**-Vorgang zum Verschieben einer Nachricht in einen öffentlichen Ordner. 
    
## <a name="scenarios-for-using-ews-and-the-ews-managed-api-to-work-with-public-folders"></a>Anwendungszenarien für EWS und die EWS Managed API mit öffentlichen Ordnern
<a name="bk_scenarios"> </a>

Öffentliche Ordner ermöglichen viele wichtige Szenarien für Benutzer von Exchange-Postfächern. Sie können Ihre Benutzer mit EWS und der EWS Managed API unterstützen, indem Sie benutzerdefinierte Lösungen für den Zugriff auf und die Verwendung von öffentlichen Ordnern und deren Inhalten implementieren. 
  
### <a name="programmatically-access-email-messages-that-have-been-sent-to-distribution-lists"></a>Programmgesteuertes Zugreifen auf E-Mail-Nachrichten, die an Verteilerlisten gesendet wurden

Benutzer von Exchange-Postfächern können öffentliche Ordner zum Speichern von E-Mail-Nachrichten an Verteilerlisten nutzen. So kann der Verteilerlistenverlauf bequem hinterlegt werden. Der Zugriff auf gespeicherte E-Mails an Verteilerlisten ist in EWS mit dem [FindItem-Vorgang](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx) oder in der EWS Managed API mit den Methoden **ExchangeService.FindItems()** und **Folder.FindItems()** möglich. 
  
### <a name="share-important-email-messages-and-other-mailbox-items"></a>Freigeben von wichtigen E-Mail-Nachrichten und anderen Postfachelementen

Benutzer von Postfächern können öffentliche Ordner als freigegebenes Repository für Postfachelemente verwenden. Verschiedene Benutzer innerhalb einer Organisation können wichtige E-Mail-Nachrichten oder Kontakte mit öffentlichen Ordnern teilen. Über EWS kann auf diese freigegebenen Postfachelemente zugegriffen werden. Sie können E-Mail-Nachrichten, Kontakte und andere Postfachelemente in EWS mit dem [MoveItem Operation](https://msdn.microsoft.com/library/dcf40fa7-7796-4a5c-bf5b-7a509a18d208%28Office.15%29.aspx) und in der EWS Managed API mit der **Item.Move()** -Methode in einen öffentlichen Ordner verschieben oder daraus entfernen. 
  
### <a name="public-discussions-with-post-items"></a>Öffentliche Diskussionen mit Bereitstellungselementen

Öffentliche Ordner sind ein praktischer Container für Bereitstellungselemente. Mit Bereitstellungselementen können Gesprächsverläufe ohne das Versenden von E-Mail-Nachrichten zwischen den Benutzern geführt werden. Benutzer können mit öffentlichen Ordnern und Bereitstellungselementen Gesprächsverläufe zwischen verschiedenen Postfachbenutzern innerhalb einer Organisation hosten und verwalten. Dadurch können Postfachbenutzer auf dem freigegebenen Gesprächsverlauf mit Bereitstellungselementen zugreifen, selbst wenn sie nicht Teilnehmer der Konversation sind. Sie können in EWS mit dem [CreateItem Operation](https://msdn.microsoft.com/library/78a52120-f1d0-4ed7-8748-436e554f75b6%28Office.15%29.aspx) und in der EWS Managed API mit der **Item.Save()** -Methode Bereitstellungselemente erstellen und auf im öffentlichen Ordner gespeicherte Elemente antworten. 
  
## <a name="routing-public-folder-requests"></a>Weiterleiten von Anforderungen für Öffentliche Ordner
<a name="bk_routing"> </a>

Der Inhalte öffentlicher Ordner kann auf mehreren Postfachservern gespeichert werden. Die Öffentliche Ordner-Hierarchie kann in einem Postfach gespeichert werden, während der Inhalt des öffentlichen Ordners in einem anderen Postfach abgelegt ist. Dabei muss es sich außerdem nicht um den Postfachserver des Benutzers handeln, der die Informationen anfordert. In einem solchen Fall ist es besonders wichtig, zum Erhalt zutreffender Informationen zu öffentlichen Ordnern die optionalen Kopfzeilen X-AnchorMailbox und X-PublicFolderMailbox zur Ordneranforderung hinzuzufügen.
  
Die Werte für X-AnchorMailbox und X-PublicFolderMailbox unterscheiden sich möglicherweise bei einer Anforderung an die Ordnerhierarchie bzw. an den Ordnerinhalt. In der folgenden Tabelle wird aufgeschlüsselt, welches Verfahren für die jeweilige EWS Managed API-Methode bzw. den jeweiligen EWS-Vorgang zu verwenden ist.
  
**EWS Managed API-Methoden und EWS-Vorgänge zum Weiterleiten von Anforderungen für öffentliche Ordner**

|**Beim Aufrufen dieser Methoden**|**Beim Aufrufen dieser Vorgänge**|**Verwenden Sie dieses Verfahren**|
|:-----|:-----|:-----|
|[Folder.FindFolders](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.findfolders%28v=exchg.80%29.aspx) <br/> [Folder.Delete](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.delete%28v=exchg.80%29.aspx) <br/> [Folder.Update](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.update%28v=exchg.80%29.aspx) <br/> [Folder.Move](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.move%28v=exchg.80%29.aspx) <br/> |[CreateFolder](https://msdn.microsoft.com/library/6f6c334c-b190-4e55-8f0a-38f2a018d1b3%28Office.15%29.aspx) <br/> [FindFolder](https://msdn.microsoft.com/library/7a9855aa-06cc-45ba-ad2a-645c15b7d031%28Office.15%29.aspx) <br/> [DeleteFolder](https://msdn.microsoft.com/library/b0f92682-4895-4bcf-a4a1-e4c2e8403979%28Office.15%29.aspx) <br/> [UpdateFolder](https://msdn.microsoft.com/library/3494c996-b834-4813-b1ca-d99642d8b4e7%28Office.15%29.aspx) <br/> [MoveFolder](https://msdn.microsoft.com/library/c7233966-6c87-4a14-8156-b1610760176d%28Office.15%29.aspx) <br/> |Weiterleiten von Anforderungen für Öffentliche Ordner-Hierarchien  <br/> |
|[Item.Bind](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.item.bind%28v=exchg.80%29.aspx) <br/> [Item.Update](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.item.update%28v=exchg.80%29.aspx) <br/> [Item.Copy](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.item.copy%28v=exchg.80%29.aspx) <br/> [Item.Move](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.item.move%28v=exchg.80%29.aspx) <br/> [Item.Delete](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.item.delete%28v=exchg.80%29.aspx) <br/> [Folder.Bind](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.bind%28v=exchg.80%29.aspx) <br/> [Folder.FindItems](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.folder.finditems%28v=exchg.80%29.aspx) <br/> |[CreateItem](https://msdn.microsoft.com/library/78a52120-f1d0-4ed7-8748-436e554f75b6%28Office.15%29.aspx) <br/> [GetItem](https://msdn.microsoft.com/library/e3590b8b-c2a7-4dad-a014-6360197b68e4%28Office.15%29.aspx) <br/> [UpdateItem](https://msdn.microsoft.com/library/5d027523-e0bc-4da2-b60b-0cb9fc1fdfe4%28Office.15%29.aspx) <br/> [CopyItem](https://msdn.microsoft.com/library/bcc68f9e-d511-4c29-bba6-ed535524624a%28Office.15%29.aspx) <br/> [MoveItem](https://msdn.microsoft.com/library/dcf40fa7-7796-4a5c-bf5b-7a509a18d208%28Office.15%29.aspx) <br/> [DeleteItem](../web-service-reference/deleteitem-operation.md) <br/> [GetFolder](https://msdn.microsoft.com/library/355bcf93-dc71-4493-b177-622afac5fdb9%28Office.15%29.aspx) <br/> [FindItem](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx) <br/> |Weiterleiten von Anforderungen für Inhalte öffentlicher Ordner  <br/> |
   
## <a name="version-differences"></a>Versionsunterschiede
<a name="VersionDifferences"> </a>

In Exchange 2007 und Exchange 2010 funktioniert der **ConvertId**-Vorgang bei der Konvertierung von IDs öffentlicher Ordner von EWS-IDs in Speicher-IDs ordnungsgemäß. 
  
## <a name="see-also"></a>Siehe auch


- [Entwickeln von Webdienstclients für Exchange](develop-web-service-clients-for-exchange.md)
    
- [Verwenden von Webdiensten in Exchange](start-using-web-services-in-exchange.md)
    
- [Begrenzungen für öffentliche Ordner](https://technet.microsoft.com/library/dn594582%28v=exchg.150%29.aspx)
    
- [Häufig gestellte Fragen: Öffentliche Ordner](https://technet.microsoft.com/library/jj552408.aspx)
    
- [Verfahren für Öffentliche Ordner](https://technet.microsoft.com/library/jj657481.aspx)
    

