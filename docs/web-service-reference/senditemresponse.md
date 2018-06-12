---
title: SendItemResponse
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- SendItemResponse
api_type:
- schema
ms.assetid: 26ac41c7-57d9-473e-ab7a-bae93e1d2aba
description: Das SendItemResponse-Element definiert eine Antwort auf eine an den SendItem.
ms.openlocfilehash: 41f450e1d4c95f7ba389adcaa2ed7e18ea74d61c
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19831339"
---
# <a name="senditemresponse"></a><span data-ttu-id="3c63d-103">SendItemResponse</span><span class="sxs-lookup"><span data-stu-id="3c63d-103">SendItemResponse</span></span>

<span data-ttu-id="3c63d-104">Das **SendItemResponse** -Element definiert eine Antwort auf eine an den SendItem.</span><span class="sxs-lookup"><span data-stu-id="3c63d-104">The **SendItemResponse** element defines a response to a SendItem request.</span></span> 
  
```xml
<SendItemResponse>
   <ResponseMessages/>
</SendItemResponse>
```

 <span data-ttu-id="3c63d-105">**SendItemResponseType**</span><span class="sxs-lookup"><span data-stu-id="3c63d-105">**SendItemResponseType**</span></span>
## <a name="attributes-and-elements"></a><span data-ttu-id="3c63d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c63d-106">Attributes and elements</span></span>

<span data-ttu-id="3c63d-107">In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.</span><span class="sxs-lookup"><span data-stu-id="3c63d-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3c63d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c63d-108">Attributes</span></span>

<span data-ttu-id="3c63d-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="3c63d-109">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3c63d-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c63d-110">Child elements</span></span>

|<span data-ttu-id="3c63d-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="3c63d-111">**Element**</span></span>|<span data-ttu-id="3c63d-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c63d-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3c63d-113">ResponseMessages</span><span class="sxs-lookup"><span data-stu-id="3c63d-113">ResponseMessages</span></span>](responsemessages.md) <br/> |<span data-ttu-id="3c63d-114">Enthält die Antwortnachrichten für eine Exchange-Webdienste-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="3c63d-114">Contains the response messages for an Exchange Web Services request.</span></span>  <br/> |
   
### <a name="parent-elements"></a><span data-ttu-id="3c63d-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c63d-115">Parent elements</span></span>

<span data-ttu-id="3c63d-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="3c63d-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3c63d-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3c63d-117">Remarks</span></span>

<span data-ttu-id="3c63d-118">Das Schema, das dieses Element beschreibt, befindet sich im virtuellen EWS-Verzeichnis des Computers, der MicrosoftExchange Server 2007 mit installierter Clientzugriff-Serverrolle ausführt.</span><span class="sxs-lookup"><span data-stu-id="3c63d-118">The schema that describes this element is located in the EWS virtual directory of the computer that is running MicrosoftExchange Server 2007 that has the Client Access server role installed.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="3c63d-119">Informationen zum Element</span><span class="sxs-lookup"><span data-stu-id="3c63d-119">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3c63d-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="3c63d-120">Namespace</span></span>  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|<span data-ttu-id="3c63d-121">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="3c63d-121">Schema name</span></span>  <br/> |<span data-ttu-id="3c63d-122">Nachrichtenschema</span><span class="sxs-lookup"><span data-stu-id="3c63d-122">Messages schema</span></span>  <br/> |
|<span data-ttu-id="3c63d-123">Überprüfungsdatei</span><span class="sxs-lookup"><span data-stu-id="3c63d-123">Validation file</span></span>  <br/> |<span data-ttu-id="3c63d-124">Messages.xsd</span><span class="sxs-lookup"><span data-stu-id="3c63d-124">Messages.xsd</span></span>  <br/> |
|<span data-ttu-id="3c63d-125">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="3c63d-125">Can be empty</span></span>  <br/> |<span data-ttu-id="3c63d-126">False</span><span class="sxs-lookup"><span data-stu-id="3c63d-126">False</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3c63d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c63d-127">See also</span></span>



[<span data-ttu-id="3c63d-128">SendItem Operation</span><span class="sxs-lookup"><span data-stu-id="3c63d-128">SendItem operation</span></span>](senditem-operation.md)
  
[<span data-ttu-id="3c63d-129">SendItem</span><span class="sxs-lookup"><span data-stu-id="3c63d-129">SendItem</span></span>](senditem.md)


- [<span data-ttu-id="3c63d-130">EWS-XML-Elemente in Exchange</span><span class="sxs-lookup"><span data-stu-id="3c63d-130">EWS XML elements in Exchange</span></span>](ews-xml-elements-in-exchange.md)
