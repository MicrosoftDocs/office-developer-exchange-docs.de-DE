---
title: GetSharingFolderResponse
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- GetSharingFolderResponse
api_type:
- schema
ms.assetid: fee90e84-3ad4-4c4b-831f-bbc95070aebf
description: Das GetSharingFolderResponse-Element definiert eine Antwort auf eine GetSharingFolder-Vorgangsanforderung.
ms.openlocfilehash: 2b5a263b350ae54e87a8fea7cb7cc2d9485b5814
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44460484"
---
# <a name="getsharingfolderresponse"></a>GetSharingFolderResponse

Das **GetSharingFolderResponse** -Element definiert eine Antwort auf eine [GetSharingFolder-Vorgangs](getsharingfolder-operation.md) Anforderung. 
  
```XML
<GetSharingFolderResponse ResponseClass="">
   <MessageText/>
   <ResponseCode/>
   <DescriptiveLinkKey/>
   <MessageXml/>   <SharingFolderId/>
</GetSharingFolderResponse>
```

 **GetSharingFolderResponseMessageType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|**ResponseClass** <br/> | Beschreibt den Status der Antwort.<br/><br/> Die folgenden Werte sind für dieses Attribut gültig:  <br/><br/>-Success  <br/>-Warnung  <br/>-Error  <br/> |
   
#### <a name="responseclass-attribute-values"></a>ResponseClass-Attributwerte

|**Wert**|**Beschreibung**|
|:-----|:-----|
|**Success** <br/> |Beschreibt eine Anforderung, die erfüllt ist.  <br/> |
|**Warning** <br/> | Beschreibt eine Anforderung, die nicht verarbeitet wurde. Wenn ein Fehler aufgetreten ist, während ein Element in der Anforderung verarbeitet wurde, kann eine Warnung zurückgegeben werden, und nachfolgende Elemente konnten nicht verarbeitet werden. <br/><br/>Im folgenden sind Beispiele für Quellen von Warnungen aufgeführt:  <br/><br/>-Der Exchange-Informationsspeicher ist während des Batches offline.  <br/>-Der Active Directory Verzeichnisdienst oder Active Directory-Domänendienste (AD DS) ist offline.  <br/>-Postfächer wurden verschoben.  <br/>-Die Nachrichtendatenbank (MDB) ist offline.  <br/>-Ein Kennwort ist abgelaufen.  <br/>-Ein Kontingent wurde überschritten.  <br/> |
|**Error** <br/> | Beschreibt eine Anforderung, die nicht erfüllt werden kann. <br/><br/>Im folgenden finden Sie Beispiele für Fehlerquellen:  <br/><br/>-Ungültige Attribute oder Elemente  <br/>-Attribute oder Elemente außerhalb des gültigen Bereichs  <br/>-Ein unbekanntes Tag  <br/>-Ein Attribut oder Element, das im Kontext ungültig ist  <br/>-Ein nicht autorisierter Zugriff versucht von einem beliebigen Client  <br/>-Ein serverseitiger Fehler als Reaktion auf einen gültigen clientseitigen Anruf  <br/><br/>  Informationen zum Fehler finden Sie in den Elementen [Response Code](responsecode.md) und [MessageText](messagetext.md) .  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[MessageText](messagetext.md) <br/> |Enthält eine Textbeschreibung des Status der Antwort.  <br/> |
|[ResponseCode](responsecode.md) <br/> |Stellt einen Fehlercode bereit, der den spezifischen Fehler identifiziert, der bei der Anforderung aufgetreten ist.  <br/> |
|[DescriptiveLinkKey](descriptivelinkkey.md) <br/> |Wird derzeit nicht verwendet und für die zukünftige Verwendung reserviert. Dieses Element enthält den Wert 0.  <br/> |
|[Messagexml verwendet](messagexml.md) <br/> |Bietet zusätzliche Fehlerantwortinformationen.  <br/> |
|[SharingFolderId](sharingfolderid.md) <br/> |Stellt den Bezeichner des lokalen Ordners in einer Freigabebeziehung dar.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

Keine.
  
## <a name="remarks"></a>Bemerkungen

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zu Elementen

|||
|:-----|:-----|
|Namespace  <br/> |https://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichtenschema  <br/> |
|Überprüfungsdatei  <br/> |Messages. xsd  <br/> |
|Leer kann sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch

- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)

