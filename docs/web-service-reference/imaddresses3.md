---
title: ImAddresses3
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cab51a28-dfad-4c70-aafe-e239321b784e
description: Das ImAddresses3-Element gibt ein Array von sofortnachrichtenadressen und die Bezeichner ihrer Quell Zuweisungen für die zugeordnete Rolle an.
ms.openlocfilehash: 2f02a57b1a113abe39a2852f8f8dbbd2b5b803ce
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44460750"
---
# <a name="imaddresses3"></a>ImAddresses3

Das **ImAddresses3** -Element gibt ein Array von sofortnachrichtenadressen und die Bezeichner ihrer Quell Zuweisungen für die zugeordnete Rolle an. 
  
```XML
<ImAddresses3>
    <StringAttributedValue/>
</ImAddresses3>
```

 **ArrayOfStringAttributedValuesType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[StringAttributedValue](stringattributedvalue.md) <br/> |Gibt eine Instanz in einem Array von Attributen an, die mit einem Persona-Element verknüpft sind.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[Persona](persona.md) <br/> |Gibt eine Gruppe von Persona-Daten an, die von einer **getpersona** -Anforderung zurückgegeben werden.  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Dieses Element wurde in Exchange Server 2013 eingeführt.
  
Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zu Elementen

|||
|:-----|:-----|
|Namespace  <br/> |https://schemas.microsoft.com/exchange/services/2006/types  <br/> |
|Name des Schemas  <br/> |Typschema  <br/> |
|Überprüfungsdatei  <br/> |Types. xsd  <br/> |
|Kann leer sein  <br/> ||
   
## <a name="see-also"></a>Siehe auch



- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)

