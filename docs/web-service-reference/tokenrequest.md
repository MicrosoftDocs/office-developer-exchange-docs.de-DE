---
title: TokenRequest
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 54f45f8e-c02b-4ead-b15a-38b30872c362
description: Das TokenRequest-Element gibt eine einzelne Token-Anforderung an.
ms.openlocfilehash: 5d16a82a382cb7fc9996db84f775fe6230f512c3
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44468922"
---
# <a name="tokenrequest"></a>TokenRequest

Das **TokenRequest** -Element gibt eine einzelne Token-Anforderung an. 
  
```XML
<TokenRequest>
   <Id/>
   <TokenType/>
</TokenRequest>
```

 **ClientAccessTokenRequestType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

[ID (Zeichenfolge)](id-string.md)  |  [TokenType (ClientAccessTokenType)](tokentype-clientaccesstokentype.md)
  
### <a name="parent-elements"></a>Übergeordnete Elemente

[TokenRequests](tokenrequests.md)
  
## <a name="remarks"></a>Bemerkungen

Dieses Element wurde in Exchange Server 2013 eingeführt.
  
Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zu Elementen

|||
|:-----|:-----|
|Namespace  <br/> |https://schemas.microsoft.com/exchange/services/2006/types  <br/> |
|Name des Schemas  <br/> |Schematypen  <br/> |
|Überprüfungsdatei  <br/> |Types.xsd  <br/> |
|Kann leer sein  <br/> |False  <br/> |
   

