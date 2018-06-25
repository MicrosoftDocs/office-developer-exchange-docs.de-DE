---
title: AlternatePublicFolderItemId
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- AlternatePublicFolderItemId
api_type:
- schema
ms.assetid: a67df9b9-8fdb-42de-b9c5-8377b71fa3d9
description: Das Element AlternatePublicFolderItemId beschreibt einen Bezeichner für Öffentliche Ordner in einer anderen Bezeichner Format umwandeln. Dieses Element wurde in Microsoft Exchange Server 2007 Service Pack 1 (SP1) eingeführt.
ms.openlocfilehash: 2240f3ff80c2c5b705611c3cf9286faa62d204cc
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "19757260"
---
# <a name="alternatepublicfolderitemid"></a>AlternatePublicFolderItemId

Das Element **AlternatePublicFolderItemId** beschreibt einen Bezeichner für Öffentliche Ordner in einer anderen Bezeichner Format umwandeln. Dieses Element wurde in Microsoft Exchange Server 2007 Service Pack 1 (SP1) eingeführt. 
  
- [ConvertId](convertid.md)
  
- [SourceIds](sourceids.md)
  
- [AlternatePublicFolderItemId](alternatepublicfolderitemid.md)
  
```xml
<AlternatePublicFolderItemId FolderId="" Format="" ItemId=""/>
```

 **AlternatePublicFolderItemIdType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|FolderId  <br/> |Identifiziert den öffentlichen Ordner, der das öffentliche Ordner-Element enthält. Dieses Attribut ist erforderlich.  <br/> |
|Format  <br/> |Gibt das Format, das der Öffentliche Ordner Elementbezeichner konvertieren beschreibt. Dieses Attribut ist erforderlich.  <br/> |
|ItemId  <br/> |Bezeichner zu konvertierenden Elements für Öffentliche Ordner. Dieses Attribut ist erforderlich.  <br/> |
   
#### <a name="format-attribute-values"></a>Format-Attributwerte

|**Wert**|**Beschreibung**|
|:-----|:-----|
|EwsLegacyId  <br/> |Beschreibt Bezeichner, die in der ursprünglich freigegebenen Version von Exchange 2007 von Exchange-Webdienste erstellt werden.  <br/> |
|EwsId  <br/> |Beschreibt Bezeichner, die von der Exchange-Webdienste beginnend mit Exchange 2007 SP1 erstellt werden.  <br/> |
|EntryId  <br/> |MAPI-IDs, wie in der PR_ENTRYID-Eigenschaft beschreibt.  <br/> |
|HexEntryId  <br/> |Beschreibt eine hexadezimal-codierte Darstellung der PR_ENTRYID-Eigenschaft. Dies ist das Format der Verfügbarkeit Kalender-Ereignis-IDs.  <br/> |
|StoreId  <br/> |Beschreibt die Exchange-Speicher-IDs.  <br/> |
|OwaId  <br/> |Beschreibt einen Outlook Web Access-Bezeichner.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

Keine.
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[SourceIds](sourceids.md) <br/> |Enthält die Bezeichner der Quelle zu konvertieren. Dieses Element wurde in Exchange 2007 SP1 eingeführt.  <br/> |
   
## <a name="remarks"></a>Hinweise

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen EWS-Verzeichnis des Computers, der Microsoft Exchange Server 2007 mit installierter Clientzugriff-Serverrolle ausführt.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|Namespace  <br/> |http://schemas.microsoft.com/exchange/services/2006/types  <br/> |
|Name des Schemas  <br/> |Schematypen  <br/> |
|Überprüfungsdatei  <br/> |Types.xsd  <br/> |
|Leer kann sein  <br/> |True  <br/> |
   
## <a name="see-also"></a>Siehe auch

- [ConvertId-Vorgang](convertid-operation.md)
- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)
- [Konvertieren von Bezeichnern](http://msdn.microsoft.com/library/a5391746-b6ef-4f48-8fc8-8255258651aa%28Office.15%29.aspx)
