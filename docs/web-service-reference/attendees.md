---
title: Teilnehmer
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 837bb372-39eb-48ae-9c09-0d2552511f93
description: Das Teilnehmer-Element gibt die Empfänger einer Einladung zu einer Besprechung.
ms.openlocfilehash: 22d88bb092b416c553144496e133680b53f5d30e
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19757403"
---
# <a name="attendees"></a><span data-ttu-id="684d6-103">Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="684d6-103">Attendees</span></span>

<span data-ttu-id="684d6-104">Das **Teilnehmer** -Element gibt die Empfänger einer Einladung zu einer Besprechung.</span><span class="sxs-lookup"><span data-stu-id="684d6-104">The **Attendees** element specifies the recipients of an invitation to a meeting.</span></span> 
  
```XML
<Attendees>
    <EmailUser></EmailUser>
</Attendees>
```

 <span data-ttu-id="684d6-105">**ArrayOfEmailUsersType**</span><span class="sxs-lookup"><span data-stu-id="684d6-105">**ArrayOfEmailUsersType**</span></span>
## <a name="attributes-and-elements"></a><span data-ttu-id="684d6-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="684d6-106">Attributes and elements</span></span>

<span data-ttu-id="684d6-107">In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.</span><span class="sxs-lookup"><span data-stu-id="684d6-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="684d6-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="684d6-108">Attributes</span></span>

<span data-ttu-id="684d6-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="684d6-109">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="684d6-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="684d6-110">Child elements</span></span>

|<span data-ttu-id="684d6-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="684d6-111">**Element**</span></span>|<span data-ttu-id="684d6-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="684d6-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="684d6-113">EmailUser</span><span class="sxs-lookup"><span data-stu-id="684d6-113">EmailUser</span></span>](emailuser.md) <br/> |<span data-ttu-id="684d6-114">Gibt eine e-Mail-Empfänger oder Active Directory-Kontakt.</span><span class="sxs-lookup"><span data-stu-id="684d6-114">Specifies an email recipient or Active Directory contact.</span></span>  <br/> |
   
### <a name="parent-elements"></a><span data-ttu-id="684d6-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="684d6-115">Parent elements</span></span>

|<span data-ttu-id="684d6-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="684d6-116">**Element**</span></span>|<span data-ttu-id="684d6-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="684d6-117">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="684d6-118">MeetingSuggestion</span><span class="sxs-lookup"><span data-stu-id="684d6-118">MeetingSuggestion</span></span>](meetingsuggestion.md) <br/> |<span data-ttu-id="684d6-119">Gibt eine vorgeschlagene Besprechung an.</span><span class="sxs-lookup"><span data-stu-id="684d6-119">Specifies a proposed meeting.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="684d6-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="684d6-120">Remarks</span></span>

<span data-ttu-id="684d6-121">Dieses Element wurde in Exchange Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="684d6-121">This element was introduced in Exchange Server 2013.</span></span>
  
<span data-ttu-id="684d6-122">Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.</span><span class="sxs-lookup"><span data-stu-id="684d6-122">The schema that describes this element is located in the IIS virtual directory that hosts Exchange Web Services.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="684d6-123">Informationen zum Element</span><span class="sxs-lookup"><span data-stu-id="684d6-123">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="684d6-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="684d6-124">Namespace</span></span>  <br/> |http://schemas.microsoft.com/exchange/services/2006/types  <br/> |
|<span data-ttu-id="684d6-125">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="684d6-125">Schema Name</span></span>  <br/> |<span data-ttu-id="684d6-126">Typschema</span><span class="sxs-lookup"><span data-stu-id="684d6-126">Type schema</span></span>  <br/> |
|<span data-ttu-id="684d6-127">Überprüfungsdatei</span><span class="sxs-lookup"><span data-stu-id="684d6-127">Validation File</span></span>  <br/> |<span data-ttu-id="684d6-128">Types.xsd</span><span class="sxs-lookup"><span data-stu-id="684d6-128">types.xsd</span></span>  <br/> |
|<span data-ttu-id="684d6-129">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="684d6-129">Can Be Empty</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="684d6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="684d6-130">See also</span></span>

- [<span data-ttu-id="684d6-131">EWS-XML-Elemente in Exchange</span><span class="sxs-lookup"><span data-stu-id="684d6-131">EWS XML elements in Exchange</span></span>](ews-xml-elements-in-exchange.md)
