---
title: SetHoldOnMailboxesResponseMessage
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61de0f3-24e0-434a-946a-c53d393b7d04
description: Das SetHoldOnMailboxesResponseMessage-Element gibt die Antwortnachricht für eine Anforderung SetHoldOnMailboxes.
ms.openlocfilehash: b7cb890a71d27340e328e39c1c463fefa080b8cb
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19831420"
---
# <a name="setholdonmailboxesresponsemessage"></a><span data-ttu-id="2b852-103">SetHoldOnMailboxesResponseMessage</span><span class="sxs-lookup"><span data-stu-id="2b852-103">SetHoldOnMailboxesResponseMessage</span></span>

<span data-ttu-id="2b852-104">Das **SetHoldOnMailboxesResponseMessage** -Element gibt die Antwortnachricht für eine Anforderung **SetHoldOnMailboxes** .</span><span class="sxs-lookup"><span data-stu-id="2b852-104">The **SetHoldOnMailboxesResponseMessage** element specifies the response message for a **SetHoldOnMailboxes** request.</span></span> 
  
```XML
<SetHoldOnMailboxesResponseMessage>
   <MessageText/>
   <ResponseCode/>
   <DescriptiveLinkKey/>
   <MessageXml/>
   <MailboxHoldResult/>
</SetHoldOnMailboxesResponseMessage>
```

 <span data-ttu-id="2b852-105">**SetHoldOnMailboxesResponseMessageType**</span><span class="sxs-lookup"><span data-stu-id="2b852-105">**SetHoldOnMailboxesResponseMessageType**</span></span>
## <a name="attributes-and-elements"></a><span data-ttu-id="2b852-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2b852-106">Attributes and elements</span></span>

<span data-ttu-id="2b852-107">In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.</span><span class="sxs-lookup"><span data-stu-id="2b852-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2b852-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b852-108">Attributes</span></span>

<span data-ttu-id="2b852-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="2b852-109">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2b852-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b852-110">Child elements</span></span>

<span data-ttu-id="2b852-111">[MessageText](messagetext.md) | [ResponseCode](responsecode.md) | [DescriptiveLinkKey](descriptivelinkkey.md) | [MessageXml](messagexml.md) | [MailboxHoldResult](mailboxholdresult.md)</span><span class="sxs-lookup"><span data-stu-id="2b852-111">[MessageText](messagetext.md) | [ResponseCode](responsecode.md) | [DescriptiveLinkKey](descriptivelinkkey.md) | [MessageXml](messagexml.md) | [MailboxHoldResult](mailboxholdresult.md)</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="2b852-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b852-112">Parent elements</span></span>

[<span data-ttu-id="2b852-113">ResponseMessages</span><span class="sxs-lookup"><span data-stu-id="2b852-113">ResponseMessages</span></span>](responsemessages.md)
  
## <a name="remarks"></a><span data-ttu-id="2b852-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b852-114">Remarks</span></span>

<span data-ttu-id="2b852-115">Dieses Element wurde in Exchange Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2b852-115">This element was introduced in Exchange Server 2013.</span></span>
  
<span data-ttu-id="2b852-116">Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.</span><span class="sxs-lookup"><span data-stu-id="2b852-116">The schema that describes this element is located in the IIS virtual directory that hosts Exchange Web Services.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2b852-117">Informationen zum Element</span><span class="sxs-lookup"><span data-stu-id="2b852-117">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b852-118">Namespace</span><span class="sxs-lookup"><span data-stu-id="2b852-118">Namespace</span></span>  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|<span data-ttu-id="2b852-119">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="2b852-119">Schema name</span></span>  <br/> |<span data-ttu-id="2b852-120">Nachrichtenschema</span><span class="sxs-lookup"><span data-stu-id="2b852-120">Messages schema</span></span>  <br/> |
|<span data-ttu-id="2b852-121">Überprüfungsdatei</span><span class="sxs-lookup"><span data-stu-id="2b852-121">Validation file</span></span>  <br/> |<span data-ttu-id="2b852-122">Messages.xsd</span><span class="sxs-lookup"><span data-stu-id="2b852-122">Messages.xsd</span></span>  <br/> |
|<span data-ttu-id="2b852-123">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="2b852-123">Can be empty</span></span>  <br/> ||
   
