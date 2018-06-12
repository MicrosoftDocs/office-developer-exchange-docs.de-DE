---
title: IsVoicemail
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IsVoicemail
api_type:
- schema
ms.assetid: 96d81d6e-4b75-43ad-b151-2dd4fd57db94
description: Das IsVoicemail -Element gibt an, ob eingehende Nachrichten Voicemailnachrichten in Reihenfolge für die Bedingung oder Ausnahme angewendet werden müssen.
ms.openlocfilehash: 513498301aa65eaf0cac5769c940eeedf5c9e629
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19830136"
---
# <a name="isvoicemail"></a><span data-ttu-id="c90fe-103">IsVoicemail</span><span class="sxs-lookup"><span data-stu-id="c90fe-103">IsVoicemail</span></span>

<span data-ttu-id="c90fe-104">Das **IsVoicemail** -Element gibt an, ob eingehende Nachrichten Voicemailnachrichten in Reihenfolge für die Bedingung oder Ausnahme angewendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c90fe-104">The **IsVoicemail** element indicates whether incoming messages must be voice mail messages in order for the condition or exception to apply.</span></span> 
  
```XML
<IsVoicemail>true | false</IsVoicemail>
```

 <span data-ttu-id="c90fe-105">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="c90fe-105">**Boolean**</span></span>
## <a name="attributes-and-elements"></a><span data-ttu-id="c90fe-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c90fe-106">Attributes and elements</span></span>

<span data-ttu-id="c90fe-107">In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.</span><span class="sxs-lookup"><span data-stu-id="c90fe-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c90fe-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="c90fe-108">Attributes</span></span>

<span data-ttu-id="c90fe-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="c90fe-109">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c90fe-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c90fe-110">Child elements</span></span>

<span data-ttu-id="c90fe-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="c90fe-111">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="c90fe-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c90fe-112">Parent elements</span></span>

|<span data-ttu-id="c90fe-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="c90fe-113">**Element**</span></span>|<span data-ttu-id="c90fe-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c90fe-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c90fe-115">Bedingungen</span><span class="sxs-lookup"><span data-stu-id="c90fe-115">Conditions</span></span>](conditions.md) <br/> |<span data-ttu-id="c90fe-116">Stellt die Bedingungen dar, bei deren Erfüllung die Regelaktionen für eine Regel ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c90fe-116">Represents the conditions that, when fulfilled, will trigger the rule actions for a rule.</span></span>  <br/> |
|[<span data-ttu-id="c90fe-117">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="c90fe-117">Exceptions</span></span>](exceptions.md) <br/> |<span data-ttu-id="c90fe-118">Stellt die Ausnahmen, die alle verfügbaren Regel Ausnahmebedingungen für eine Posteingangsregel darstellen.</span><span class="sxs-lookup"><span data-stu-id="c90fe-118">Represents the exceptions that represent all the available rule exception conditions for an Inbox rule.</span></span>  <br/> |
   
## <a name="text-value"></a><span data-ttu-id="c90fe-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="c90fe-119">Text value</span></span>

<span data-ttu-id="c90fe-p101">Der Textwert **true** gibt an, dass die Nachricht eine Voicemailnachricht in Reihenfolge für die Bedingung oder Ausnahme angewendet werden muss. Der Wert **false** gibt an, dass die Nachricht keine Voicemailnachricht in Reihenfolge für die Bedingung oder Ausnahme angewendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c90fe-p101">A text value of **true** indicates that the message must be a voice mail message in order for the condition or exception to apply. A value of **false** indicates that the message must not be a voice mail message in order for the condition or exception to apply.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c90fe-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c90fe-122">Remarks</span></span>

<span data-ttu-id="c90fe-123">Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.</span><span class="sxs-lookup"><span data-stu-id="c90fe-123">The schema that describes this element is located in the IIS virtual directory that hosts Exchange Web Services.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c90fe-124">Informationen zum Element</span><span class="sxs-lookup"><span data-stu-id="c90fe-124">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c90fe-125">Namespace</span><span class="sxs-lookup"><span data-stu-id="c90fe-125">Namespace</span></span>  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|<span data-ttu-id="c90fe-126">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="c90fe-126">Schema Name</span></span>  <br/> |<span data-ttu-id="c90fe-127">Nachrichtenschema</span><span class="sxs-lookup"><span data-stu-id="c90fe-127">Messages schema</span></span>  <br/> |
|<span data-ttu-id="c90fe-128">Überprüfungsdatei</span><span class="sxs-lookup"><span data-stu-id="c90fe-128">Validation File</span></span>  <br/> |<span data-ttu-id="c90fe-129">Messages.xsd</span><span class="sxs-lookup"><span data-stu-id="c90fe-129">Messages.xsd</span></span>  <br/> |
|<span data-ttu-id="c90fe-130">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="c90fe-130">Can be Empty</span></span>  <br/> |<span data-ttu-id="c90fe-131">True</span><span class="sxs-lookup"><span data-stu-id="c90fe-131">True</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c90fe-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c90fe-132">See also</span></span>



- [<span data-ttu-id="c90fe-133">EWS-XML-Elemente in Exchange</span><span class="sxs-lookup"><span data-stu-id="c90fe-133">EWS XML elements in Exchange</span></span>](ews-xml-elements-in-exchange.md)
