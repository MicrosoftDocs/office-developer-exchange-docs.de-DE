---
title: PostItem-Objekt
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PostItem
api_type:
- schema
ms.assetid: 7727ed84-9591-4a1c-bb04-12129926499b
description: Das PostItem-Element stellt ein Post-Element im Exchange-Speicher.
ms.openlocfilehash: 3fb6d6cfe334999c93ca0238547dd5aee8150a5f
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19830866"
---
# <a name="postitem"></a>PostItem-Objekt

Das **PostItem** -Element stellt ein Post-Element im Exchange-Speicher. 
  
```xml
<PostItem>
   <MimeContent/>
   <ItemId/>
   <ParentFolderId/>
   <ItemClass/>
   <Subject/>
   <Sensitivity/>
   <Body/>
   <Attachments/>
   <DateTimeReceived/>
   <Size/>
   <Categories/>
   <Importance/>
   <InReplyTo/>
   <IsSubmitted/>
   <IsDraft/>
   <IsFromMe/>
   <IsResend/>
   <IsUnmodified/>
   <InternetMessageHeaders/>
   <DateTimeSent/>
   <DateTimeCreated/>
   <ResponseObjects/>
   <ReminderDueBy/>
   <ReminderIsSet/>
   <ReminderMinutesBeforeStart/>
   <DisplayCc/>
   <DisplayTo/>
   <HasAttachments/>
   <ExtendedProperty/>
   <Culture/>
   <EffectiveRights/>
   <LastModifiedName/>
   <LastModifiedTime/>
   <IsAssociated/>
   <WebClientReadFormQueryString/>
   <WebClientEditFormQueryString/>
   <ConversationId/>
   <UniqueBody/>
   <ConversationIndex/>
   <ConversationTopic/>
   <From/>
   <InternetMessageId/>
   <IsRead/>
   <PostedTime/>
   <References/>
   <Sender/>
</PostItem>
```

 **PostItemType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[' MimeContent '](mimecontent.md) <br/> |Enthält den systemeigene Multipurpose Internet Mail Extensions (MIME) Stream eines Objekts, das im Format base64Binary dargestellt wird.  <br/> |
|[ItemId](itemid.md) <br/> |Enthält den eindeutigen Bezeichner und Ändern eines Elements in der Exchange-Speicher. Diese Eigenschaft ist schreibgeschützt.  <br/> |
|[ParentFolderId](parentfolderid.md) <br/> |Stellt den Bezeichner des übergeordneten Ordners, der das Element oder Ordner enthält. Diese Eigenschaft ist schreibgeschützt.  <br/> |
|[ItemClass](itemclass.md) <br/> |Die Nachrichtenklasse eines Elements darstellt.  <br/> |
|[Betreff](subject.md) <br/> |Der Betreff den Exchange-Speicherelemente und Antwortobjekte darstellt. Der Betreff ist auf 255 Zeichen beschränkt.  <br/> |
|[Vertraulichkeit](sensitivity.md) <br/> |Gibt die Vertraulichkeitsstufe eines Elements an.  <br/> |
|[Body](body.md) <br/> |Stellt den tatsächlichen Textkörperinhalt einer Nachricht.  <br/> |
|[Anlagen](attachments-ex15websvcsotherref.md) <br/> |Enthält die Elemente oder Dateien, die ein Element in der Exchange-Informationsspeicher zugeordnet sind.  <br/> |
|[DateTimeReceived](datetimereceived.md) <br/> |Stellt das Datum und die Uhrzeit, die ein Element in einem Postfach empfangen wurde.  <br/> |
|[Size](size.md) <br/> |Die Größe in Bytes eines Elements darstellt. Diese Eigenschaft ist schreibgeschützt.  <br/> |
|[Kategorien](categories-ex15websvcsotherref.md) <br/> |Stellt eine Auflistung von Zeichenfolgen, die die Kategorien zu identifizieren, zu denen ein Element im Postfach gehört.  <br/> |
|[Importance](importance.md) <br/> |Beschreibt die Bedeutung eines Elements an.  <br/> |
|[InReplyTo](inreplyto.md) <br/> |Stellt den Bezeichner des Elements, der dieses Element eine Antwort ist.  <br/> |
|[IsSubmitted](issubmitted.md) <br/> |Gibt an, ob ein Element in den Standardordner Postausgang gesendet wurde.  <br/> |
|[IsDraft](isdraft.md) <br/> |Stellt dar, ob ein Element noch nicht gesendet wurde.  <br/> |
|[IsFromMe](isfromme.md) <br/> |Gibt an, ob ein Benutzer ein Element an sich gesendet.  <br/> |
|[IsResend](isresend.md) <br/> |Gibt an, ob das Element zuvor gesendet wurden.  <br/> |
|[IsUnmodified](isunmodified.md) <br/> |Gibt an, ob das Element geändert wurde.  <br/> |
|[InternetMessageHeaders](internetmessageheaders.md) <br/> |Stellt die Auflistung aller Internet Message Header, die in einem Element in einem Postfach enthalten sind.  <br/> |
|[DateTimeSent](datetimesent.md) <br/> |Stellt das Datum und die Uhrzeit, die ein Element in einem Postfach gesendet wurde.  <br/> |
|["Datetimecreated"](datetimecreated.md) <br/> |Stellt das Datum und die Uhrzeit, die ein bestimmtes Element im Postfach erstellt wurde.  <br/> |
|[ResponseObjects](responseobjects.md) <br/> |Enthält eine Auflistung aller Antwort-Objekte, die ein Element in der Exchange-Informationsspeicher zugeordnet sind.  <br/> |
|[ReminderDueBy](reminderdueby.md) <br/> |Stellt das Datum und die Uhrzeit bei des Ereignisses eintreten. Dies wird durch die [ReminderMinutesBeforeStart](reminderminutesbeforestart.md) -Element verwendet, um zu bestimmen, wann die Erinnerung angezeigt wird.  <br/> |
|[ReminderIsSet](reminderisset.md) <br/> |Gibt an, ob eine Erinnerung für ein Element in der Exchange-Informationsspeicher festgelegt wurde.  <br/> |
|[ReminderMinutesBeforeStart](reminderminutesbeforestart.md) <br/> |Stellt die Anzahl der Minuten, bevor ein Ereignis, wenn eine Erinnerung angezeigt wird.  <br/> |
|[DisplayCc](displaycc.md) <br/> |Stellt die Zeichenfolge, die für den Inhalt des im Feld "Cc" verwendet wird. Dies ist die verkettete Zeichenfolge alle Anzeigenamen der Cc-Empfänger.  <br/> |
|[DisplayTo](displayto.md) <br/> |Stellt die Zeichenfolge, die für den Inhalt des im Feld an verwendet wird. Dies ist die verkettete Zeichenfolge aller in Empfänger Anzeigenamen.  <br/> |
|[HasAttachments](hasattachments.md) <br/> |Stellt eine Eigenschaft, die auf **true** festgelegt ist, wenn ein Element mindestens eine Anlage hat. Diese Eigenschaft ist schreibgeschützt.  <br/> |
|[ExtendedProperty](extendedproperty.md) <br/> |Erweiterte Eigenschaften für Ordner und Elemente identifiziert.  <br/> |
|[Kultur](culture.md) <br/> |Stellt die Kultur für ein bestimmtes Element in einem Postfach an.  <br/> |
|[EffectiveRights](effectiverights.md) <br/> |Der Client Rechte basierend auf den berechtigungseinstellungen für das Element oder Ordner enthält. Dieses Element ist schreibgeschützt.  <br/> |
|[LastModifiedName](lastmodifiedname.md) <br/> |Enthält den Anzeigenamen des Benutzers auf ein Element zu ändern.  <br/> |
|[ZuletztGeändertUm](lastmodifiedtime.md) <br/> |Gibt an, wann ein Element zuletzt geändert wurde.  <br/> |
|[IsAssociated](isassociated.md) <br/> |Gibt an, ob das Element einem Ordner zugeordnet ist.  <br/> |
|[WebClientReadFormQueryString](webclientreadformquerystring.md) <br/> |Stellt eine URL zu verketten an den Microsoft Office Outlook Web App-Endpunkt ein Elements in Outlook Web App zu lesen.  <br/> |
|[WebClientEditFormQueryString](webclienteditformquerystring.md) <br/> |Stellt eine URL an den Endpunkt Outlook Web App so bearbeiten Sie ein Element in Outlook Web App verketten.  <br/> |
|[ConversationId](conversationid.md) <br/> |Enthält die ID eines Elements oder einer Unterhaltung.  <br/> |
|[UniqueBody](uniquebody.md) <br/> |Stellt ein HTML-Fragment oder nur-Text, der den eindeutigen Text an dieser Unterhaltung darstellt.  <br/> |
|[ConversationIndex](conversationindex.md) <br/> |Enthält eine binäre Kennung, die den Thread darstellt, zu dem diese Nachricht gehört.  <br/> |
|[ConversationTopic](conversationtopic.md) <br/> |Den Bezeichner für die Unterhaltung darstellt.  <br/> |
|[Von](from.md) <br/> |Stellt die Adresse an, von der das Post-Element gesendet wurde. Das Element **von** kann nur zum Zeitpunkt der Erstellung festgelegt werden.  <br/> |
|[InternetMessageId](internetmessageid.md) <br/> |Die Internetnachricht-ID eines Elements darstellt.  <br/> |
|[IsRead](isread.md) <br/> |Gibt an, ob eine Nachricht gelesen wurde.  <br/> |
|[PostedTime](postedtime.md) <br/> |Gibt die Zeit, die ein [PostItem-Objekt](postitem.md) veröffentlicht wurde.  <br/> |
|[Referenzen](references.md) <br/> |Stellt den Usenet-Header, der mit den ursprünglichen Nachrichten Antworten zugeordnet wird.  <br/> |
|[Absender](sender.md) <br/> |Bezeichnet den Absender eines Elements.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[SetItemField](setitemfield.md) <br/> |Stellt eine Aktualisierung einer einzelnen Eigenschaft eines Elements in einer UpdateItem-Operation dar.  <br/> |
|[AppendToItemField](appendtoitemfield.md) <br/> |Identifiziert Daten an eine einzelne Eigenschaft eines Elements oder Ordners während eines [Vorgangs UpdateItem](updateitem-operation.md)angefügt.  <br/> |
|[ItemAttachment](itemattachment.md) <br/> |Stellt ein Exchange-Element, das mit einem anderen Exchange-Element zugeordnet ist.  <br/> |
|[Erstellen (ItemSync)](create-itemsync.md) <br/> |Gibt ein einzelnes Element in der lokalen Client-Speicher zu erstellen.  <br/> |
|[Update (ItemSync)](update-itemsync.md) <br/> |Gibt ein einzelnes Element in den Speicher des lokalen Client aktualisieren.  <br/> |
|[ReadFlagChange](readflagchange.md) <br/> |In [SyncFolderItems](syncfolderitems.md) Antworten zurückgegeben, wenn ein Element gelesen wurde. Diese Eigenschaft ist schreibgeschützt. Dieses Element wurde in Exchange 2007 SP1 eingeführt.  <br/> |
|[Elemente](items.md) <br/> |Enthält ein Array von Elementen an.  <br/> |
|[ConflictingMeetings](conflictingmeetings.md) <br/> |Identifiziert alle Elemente, die mit einem bestimmten Zeitpunkt treffen Konflikt.  <br/> |
|[AdjacentMeetings](adjacentmeetings.md) <br/> |Werden alle Kalenderelemente, die an eine Besprechungszeit angrenzen beschrieben.  <br/> |
   
## <a name="text-value"></a>Textwert

Keine.
  
## <a name="remarks"></a>Hinweise

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|Namespace  <br/> |http://schemas.microsoft.com/exchange/services/2006/types  <br/> |
|Name des Schemas  <br/> |Schematypen  <br/> |
|Überprüfungsdatei  <br/> |Types.xsd  <br/> |
|Leer kann sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch



- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)
