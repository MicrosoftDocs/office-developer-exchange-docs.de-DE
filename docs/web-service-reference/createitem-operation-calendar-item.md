---
title: CreateItem-Vorgang (Kalenderelement)
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CreateItem
api_type:
- schema
ms.assetid: aa4a7c94-f668-4bd2-8079-c855f6ab17e1
description: Der CreateItem-Vorgang erstellt Kalenderelemente in der Exchange-Informationsspeicher.
ms.openlocfilehash: 535edf9fe567bc3063a5b853f01d604ea4c7eb95
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44457501"
---
# <a name="createitem-operation-calendar-item"></a>CreateItem-Vorgang (Kalenderelement)

Der CreateItem-Vorgang erstellt Kalenderelemente in der Exchange-Informationsspeicher.
  
## <a name="remarks"></a>Bemerkungen

Mit dem CreateItem-Vorgang werden Termine, Besprechungen und Besprechungsanfragen erstellt. Wenn ein Kalenderelement ohne Teilnehmer erstellt wird, wird es als Termin betrachtet. Wenn Teilnehmer angegeben werden, handelt es sich beim Kalenderelement um eine Besprechung. Wenn eine Besprechung mithilfe des CreateItem-Vorgangs erstellt wird, werden Besprechungsanfragen automatisch an die identifizierten Teilnehmer gesendet, wenn das SendMeetingInvitations-Attribut so festgelegt ist, dass die Besprechungsanfragen gesendet werden.
  
## <a name="createitem-calendar-item-request-example"></a>CreateItem (Calendar Item)-Anforderungs Beispiel

### <a name="description"></a>Beschreibung

Im folgenden Beispiel einer CreateItem-Anforderung wird gezeigt, wie Sie eine Besprechung mit zwei erforderlichen Teilnehmern erstellen. Durch diese Anforderung werden die Besprechungsanfragen an die beiden Teilnehmer gesendet.
  
### <a name="code"></a>Code

```XML
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
               xmlns:xsd="http://www.w3.org/2001/XMLSchema"
               xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/"
               xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types">
  <soap:Body>
    <CreateItem xmlns="https://schemas.microsoft.com/exchange/services/2006/messages"
                xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types" 
                SendMeetingInvitations="SendToAllAndSaveCopy" >
      <SavedItemFolderId>
        <t:DistinguishedFolderId Id="calendar"/>
      </SavedItemFolderId>
      <Items>
        <t:CalendarItem xmlns="https://schemas.microsoft.com/exchange/services/2006/types">
          <Subject>Planning Meeting</Subject>
          <Body BodyType="Text">Plan the agenda for next week's meeting.</Body>
          <ReminderIsSet>true</ReminderIsSet>
          <ReminderMinutesBeforeStart>60</ReminderMinutesBeforeStart>
          <Start>2006-11-02T14:00:00</Start>
          <End>2006-11-02T15:00:00</End>
          <IsAllDayEvent>false</IsAllDayEvent>
          <LegacyFreeBusyStatus>Busy</LegacyFreeBusyStatus>
          <Location>Conference Room 721</Location>
          <RequiredAttendees>
            <Attendee>
              <Mailbox>
                <EmailAddress>User1@example.com</EmailAddress>
              </Mailbox>
            </Attendee>
            <Attendee>
              <Mailbox>
                <EmailAddress>User2@example.com</EmailAddress>
              </Mailbox>
            </Attendee>
          </RequiredAttendees>
        </t:CalendarItem>
      </Items>
    </CreateItem>
  </soap:Body>
</soap:Envelope>
```

### <a name="comments"></a>Comments

Ein Beispiel dafür, wie Sie auf eine Besprechungsanfrage Antworten, finden Sie im Thema [CreateItem-Vorgang (Besprechungsanfrage)](createitem-operation-meeting-request.md) . 
  
### <a name="request-elements"></a>Anfordern von Elementen

In der Anforderung werden folgende Elemente verwendet:
  
- [CreateItem](createitem.md)
    
- [SavedItemFolderId](saveditemfolderid.md)
    
- [DistinguishedFolderId](distinguishedfolderid.md)
    
- [Elemente (NonEmptyArrayOfAllItemsType)](items-nonemptyarrayofallitemstype.md)
    
- [CalendarItem](calendaritem.md)
    
- [Betreff](subject.md)
    
- [Body](body.md)
    
- [ReminderIsSet](reminderisset.md)
    
- [ReminderMinutesBeforeStart](reminderminutesbeforestart.md)
    
- [Start](start.md)
    
- [End](end-ex15websvcsotherref.md)
    
- [IsAllDayEvent](isalldayevent.md)
    
- [LegacyFreeBusyStatus](legacyfreebusystatus.md)
    
- [Standort](location.md)
    
- [RequiredAttendees](requiredattendees.md)
    
- [Teilnehmer](attendee.md)
    
- [Postfach](mailbox.md)
    
- [EmailAddress (NonEmptyStringType)](emailaddress-nonemptystringtype.md)
    
## <a name="successful-createitem-calendar-item-response"></a>Erfolgreiche CreateItem-Antwort (Kalenderelement)

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt eine erfolgreiche Antwort auf die CreateItem-Anforderung.
  
### <a name="code"></a>Code

```XML
<?xml version="1.0" encoding="utf-8" ?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" 
               xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
               xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <soap:Header>
    <t:ServerVersionInfo MajorVersion="8" MinorVersion="0" MajorBuildNumber="685" MinorBuildNumber="8" 
                         xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types" />
  </soap:Header>
  <soap:Body>
    <CreateItemResponse xmlns:m="https://schemas.microsoft.com/exchange/services/2006/messages" 
                        xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types" 
                        xmlns="https://schemas.microsoft.com/exchange/services/2006/messages">
      <m:ResponseMessages>
        <m:CreateItemResponseMessage ResponseClass="Success">
          <m:ResponseCode>NoError</m:ResponseCode>
          <m:Items>
            <t:CalendarItem>
              <t:ItemId Id="AAAlAFV" ChangeKey="DwAAABYA" />
            </t:CalendarItem>
          </m:Items>
        </m:CreateItemResponseMessage>
      </m:ResponseMessages>
    </CreateItemResponse>
  </soap:Body>
</soap:Envelope>
```

### <a name="comments"></a>Comments

Die [ItemID](itemid.md) **-Element-ID** und das **ChangeKey** -Attribut wurden verkürzt, um die Lesbarkeit zu erhalten. 
  
### <a name="successful-response-elements"></a>Erfolgreiche Antwortelemente

In der Antwort werden folgende Elemente verwendet:
  
- [ServerVersionInfo](serverversioninfo.md)
    
- [CreateItemResponse](createitemresponse.md)
    
- [ResponseMessages](responsemessages.md)
    
- [CreateItemResponseMessage](createitemresponsemessage.md)
    
- [ResponseCode](responsecode.md)
    
- [Elemente](items.md)
    
- [CalendarItem](calendaritem.md)
    
- [ItemId](itemid.md)
    
## <a name="see-also"></a>Siehe auch



[CreateItem-Vorgang](createitem-operation.md)

