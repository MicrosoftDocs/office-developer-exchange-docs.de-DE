---
title: SendNotification
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- SendNotification
api_type:
- schema
ms.assetid: e45c4451-a286-4aec-a691-119ec41c58e0
description: Das SendNotification-Element enthält, die vom Computer gesendet werden, die Microsoft Exchange Server 2007, an die Clientanwendung ausgeführt wird Pushbenachrichtigungen.
ms.openlocfilehash: 2288dbb5cf97b57a64b3c645eb72836342f4c178
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19831345"
---
# <a name="sendnotification"></a>SendNotification

Das **SendNotification** -Element enthält, die vom Computer gesendet werden, die Microsoft Exchange Server 2007, an die Clientanwendung ausgeführt wird Pushbenachrichtigungen. 
  
```xml
<SendNotification>
   <ResponseMessages/>
</SendNotification>
```

 **SendNotificationResponseType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[ResponseMessages](responsemessages.md) <br/> |Enthält die Pushbenachrichtigungen, die vom Client Access-Server gesendet werden.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

Keine.
  
## <a name="remarks"></a>Hinweise

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen EWS-Verzeichnis des Computers, der MicrosoftExchange Server 2007 mit installierter Clientzugriff-Serverrolle ausführt.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|Namespace  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichtenschema  <br/> |
|Überprüfungsdatei  <br/> |Messages.xsd  <br/> |
|Leer kann sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch



- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)


[Ereignisbenachrichtigungen in Exchange-Webdienste](http://msdn.microsoft.com/library/4fd4b351-d35c-4ccc-9ed9-878932ab9d50%28Office.15%29.aspx)
  
[Beispielanwendung für Pushbenachrichtigungen](http://msdn.microsoft.com/library/db1f8523-fa44-483f-bdb6-ab5939b52eee%28Office.15%29.aspx)
