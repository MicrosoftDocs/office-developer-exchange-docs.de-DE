---
title: Status (um-Webdienst – SetOofStatus)
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
api_name:
- Status
api_type:
- schema
ms.assetid: 893bcff1-ccdc-493f-b366-ce8a68c813bd
description: Das Status-Element definiert den Wert, der in einer SetOofStatus-Vorgangsanforderung (um-Webdienst) verwendet werden soll.
ms.openlocfilehash: 865152baf28c22578664e16db2dcd5f82a04af98
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44459980"
---
# <a name="status-um-web-service---setoofstatus"></a>Status (um-Webdienst – SetOofStatus)

Das **Status** -Element definiert den Wert, der in einer [SetOofStatus-Vorgangsanforderung (um-Webdienst)](setoofstatus-operation-um-web-service.md) verwendet werden soll. 
  
[SetOofStatus (um-Webdienst)](setoofstatus-um-web-service.md)
  
[Status (um-Webdienst – SetOofStatus)](status-um-web-servicesetoofstatus.md)
  
```xml
<SetOofStatus>
  <status/>
</SetOofStatus>
```

 **Boolescher Wert**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine.
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[SetOofStatus (um-Webdienst)](setoofstatus-um-web-service.md) <br/> |Definiert eine Anforderung zum Festlegen des Status von Unified Messaging Abwesenheit (Out of Office, OOF) für den Benutzer, der die Anforderung stellt.  <br/> |
   
## <a name="text-value"></a>Textwert

Ein boolescher Wert ist erforderlich. Im Folgenden sind die möglichen Werte aufgeführt:
  
- Wahr
    
- Falsch
    
## <a name="element-information"></a>Informationen zu Elementen

|||
|:-----|:-----|
|Namespace  <br/> |https://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichten  <br/> |
|Überprüfungsdatei  <br/> |Messages. xsd  <br/> |
|Leer kann sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch



[SetOofStatus-Vorgang (um-Webdienst)](setoofstatus-operation-um-web-service.md)

