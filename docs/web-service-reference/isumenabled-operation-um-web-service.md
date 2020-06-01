---
title: IsUMEnabled-Vorgang (um-Webdienst)
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
api_name:
- IsUMEnabled
api_type:
- schema
ms.assetid: fbe6cd95-f7a5-42b9-8a9d-b6159a269d55
description: Der IsUMEnabled-Vorgang bestimmt, ob ein Postfach für Unified Messaging aktiviert ist.
ms.openlocfilehash: b1478f5a113059251fe1b036ac7d77e5a4ab4f50
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44458236"
---
# <a name="isumenabled-operation-um-web-service"></a><span data-ttu-id="0ea9c-103">IsUMEnabled-Vorgang (um-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="0ea9c-103">IsUMEnabled operation (UM web service)</span></span>

<span data-ttu-id="0ea9c-104">Der IsUMEnabled-Vorgang bestimmt, ob ein Postfach für Unified Messaging aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0ea9c-104">The IsUMEnabled operation determines whether a mailbox is enabled for Unified Messaging.</span></span>
  
## <a name="isumenabled-request-example"></a><span data-ttu-id="0ea9c-105">IsUMEnabled-Anforderungs Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ea9c-105">IsUMEnabled request example</span></span>

### <a name="description"></a><span data-ttu-id="0ea9c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ea9c-106">Description</span></span>

<span data-ttu-id="0ea9c-107">Im folgenden Beispiel einer IsUMEnabled-Anforderung wird gezeigt, wie Sie eine Anforderung zum bestimmen, ob ein Postfach für Unified Messaging aktiviert ist, bilden.</span><span class="sxs-lookup"><span data-stu-id="0ea9c-107">The following example of an IsUMEnabled request shows how to form a request to determine whether a mailbox is enabled for Unified Messaging.</span></span>
  
### <a name="code"></a><span data-ttu-id="0ea9c-108">Code</span><span class="sxs-lookup"><span data-stu-id="0ea9c-108">Code</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <IsUMEnabled xmlns="https://schemas.microsoft.com/exchange/services/2006/messages" />
  </soap:Body>
</soap:Envelope>
```

## <a name="successful-isumenabled-response-example"></a><span data-ttu-id="0ea9c-109">Erfolgreiches IsUMEnabled-Antwortbeispiel</span><span class="sxs-lookup"><span data-stu-id="0ea9c-109">Successful IsUMEnabled response example</span></span>

### <a name="description"></a><span data-ttu-id="0ea9c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ea9c-110">Description</span></span>

<span data-ttu-id="0ea9c-111">Das folgende Beispiel zeigt eine erfolgreiche Antwort auf eine IsUMEnabled-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0ea9c-111">The following example shows a successful response to an IsUMEnabled request.</span></span>
  
### <a name="code"></a><span data-ttu-id="0ea9c-112">Code</span><span class="sxs-lookup"><span data-stu-id="0ea9c-112">Code</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <soap:Body>
    <IsUMEnabledResponse xmlns="https://schemas.microsoft.com/exchange/services/2006/messages">
      <IsUMEnabledResponse>true</IsUMEnabledResponse> 
    </IsUMEnabledResponse>
  </soap:Body>
</soap:Envelope>
```

## <a name="see-also"></a><span data-ttu-id="0ea9c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ea9c-113">See also</span></span>



[<span data-ttu-id="0ea9c-114">IsUMEnabled (um-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="0ea9c-114">IsUMEnabled (UM web service)</span></span>](isumenabled-um-web-service.md)
  
[<span data-ttu-id="0ea9c-115">IsUMEnabledResponse (um-Webdienst)</span><span class="sxs-lookup"><span data-stu-id="0ea9c-115">IsUMEnabledResponse (UM web service)</span></span>](isumenabledresponse-um-web-service.md)


[<span data-ttu-id="0ea9c-116">XML-Elemente des Unified Messaging-Webdiensts für Exchange</span><span class="sxs-lookup"><span data-stu-id="0ea9c-116">Unified Messaging web service XML elements for Exchange</span></span>](unified-messaging-web-service-xml-elements-for-exchange.md)

