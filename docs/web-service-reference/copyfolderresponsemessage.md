---
title: CopyFolderResponseMessage
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CopyFolderResponseMessage
api_type:
- schema
ms.assetid: c82092a9-50ff-4ae1-b819-ebabbf89262b
description: Das CopyFolderResponseMessage-Element enthält den Status und das Ergebnis einer einzelnen CopyFolder-Vorgangsanforderung.
ms.openlocfilehash: 796ec57116e4b4943ca370e45cf0abefe7782c08
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44458509"
---
# <a name="copyfolderresponsemessage"></a>CopyFolderResponseMessage

Das **CopyFolderResponseMessage** -Element enthält den Status und das Ergebnis einer einzelnen [CopyFolder-Vorgangs](copyfolder-operation.md) Anforderung. 
  
- [CopyFolderResponse](copyfolderresponse.md) 
- [ResponseMessages](responsemessages.md)  
- [CopyFolderResponseMessage](copyfolderresponsemessage.md)
  
```xml
<CopyFolderResponseMessage ResponseClass="">
   <MessageText/>
   <ResponseCode/>
   <DescriptiveLinkKey/>
   <MessageXml/>
   <Folders/>
</CopyFolderResponseMessage>
```

 **FolderInfoResponseMessageType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|**ResponseClass** <br/> | Beschreibt den Status einer [CopyFolder-Vorgangs](copyfolder-operation.md) Antwort.<br/><br/>Die folgenden Werte sind für dieses Attribut gültig:<br/><br/>-Success  <br/>-Warnung  <br/>-Error  <br/> |
   
#### <a name="responseclass-attribute-values"></a>ResponseClass-Attributwerte

|**Wert**|**Beschreibung**|
|:-----|:-----|
|**Success** <br/> |Beschreibt eine Anforderung, die erfüllt ist.  <br/> |
|**Warning** <br/> | Beschreibt eine Anforderung, die nicht verarbeitet wurde. Wenn ein Fehler aufgetreten ist, während ein Element in der Anforderung verarbeitet wurde, kann eine Warnung zurückgegeben werden, und nachfolgende Elemente konnten nicht verarbeitet werden.<br/><br/>Im folgenden sind Beispiele für Quellen von Warnungen aufgeführt:<br/><br/>– Der Exchange-Informationsspeicher wird während des Batches offline geschaltet.  <br/>-Active Directory-Domänendienste (AD DS) wird offline geschaltet.  <br/>-Postfächer werden verschoben.  <br/>-Die Nachrichtendatenbank (MDB) wird offline geschaltet.  <br/>-Ein Kennwort ist abgelaufen.  <br/>-Ein Kontingent wird überschritten.  <br/> |
|**Error** <br/> | Beschreibt eine Anforderung, die nicht erfüllt werden kann.<br/><br/>Im folgenden finden Sie Beispiele für Fehlerquellen:  <br/><br/>-Ungültige Attribute oder Elemente  <br/>-Attribute oder Elemente außerhalb des Bereichs  <br/>-Unbekanntes Tag  <br/>-Attribut oder Element im Kontext ungültig  <br/>-Nicht autorisierter Zugriff durch einen Client versucht  <br/>-Server seitiger Fehler als Reaktion auf einen gültigen clientseitigen Anruf<br/><br/>Informationen zum Fehler finden Sie in den Elementen [Response Code](responsecode.md) und [MessageText](messagetext.md) .  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[MessageText](messagetext.md) <br/> |Enthält eine Textbeschreibung des Status der Antwort.  <br/> |
|[ResponseCode](responsecode.md) <br/> |Stellt einen Fehlercode bereit, der den spezifischen Fehler identifiziert, der bei der Anforderung aufgetreten ist.  <br/> |
|[DescriptiveLinkKey](descriptivelinkkey.md) <br/> |Wird derzeit nicht verwendet und ist für die zukünftige Verwendung reserviert. Sie enthält den Wert 0.  <br/> |
|[Messagexml verwendet](messagexml.md) <br/> |Bietet zusätzliche Fehlerantwortinformationen.  <br/> |
|[Ordner](folders-ex15websvcsotherref.md) <br/> |Enthält ein Array kopierter Ordner.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[ResponseMessages](responsemessages.md) <br/> |Enthält die Antwortnachrichten für eine Exchange Webdienste-Anforderung.  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen EWS-Verzeichnis des Computers, auf dem Microsoft Exchange Server 2010 ausgeführt wird, auf dem die Client Zugriffs-Server Rolle installiert ist.
  
## <a name="element-information"></a>Informationen zu Elementen

|||
|:-----|:-----|
|Namespace  <br/> |https://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichtenschema  <br/> |
|Überprüfungsdatei  <br/> |Messages. xsd  <br/> |
|Kann leer sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch

- [CopyFolder-Vorgang](copyfolder-operation.md)
- [EWS-Referenz für Exchange](ews-reference-for-exchange.md) 
- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)

