---
title: Abrufen von Terminen und Besprechungen mithilfe von EWS in Exchange
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.assetid: 1bae582a-8cb3-4e77-be2a-7e107fad26fe
description: Hier erhalten Sie Informationen zum Abrufen von Terminen und Besprechungen mithilfe der verwalteten EWS-API oder von EWS in Exchange.
localization_priority: Priority
ms.openlocfilehash: d951bfeccdf50ae1397ecdd4887ed05548b25001
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44528090"
---
# <a name="get-appointments-and-meetings-by-using-ews-in-exchange"></a>Abrufen von Terminen und Besprechungen mithilfe von EWS in Exchange

Hier erhalten Sie Informationen zum Abrufen von Terminen und Besprechungen mithilfe der verwalteten EWS-API oder von EWS in Exchange.
  
Mit der [CalendarFolder.FindAppointments](https://msdn.microsoft.com/library/dd636179%28v=exchg.80%29.aspx) verwalteten EWS-API-Methode oder dem [FindItem](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx)-EWS-Vorgang können Sie Termine und Besprechungen aus dem Kalenderordner abrufen. 
  
## <a name="get-appointments-by-using-the-ews-managed-api"></a>Abrufen von Terminen mithilfe der verwalteten EWS-API
<a name="bk_retrieveappsEWSMA"> </a>

Im folgenden Codebeispiel wird veranschaulicht, wie Sie die verwaltete EWS-API zum Abrufen von Terminen eines Benutzers in einem bestimmten Zeitraum verwenden.
  
```cs
       // Initialize values for the start and end times, and the number of appointments to retrieve.
            DateTime startDate = DateTime.Now;
            DateTime endDate = startDate.AddDays(30);
            const int NUM_APPTS = 5;
            // Initialize the calendar folder object with only the folder ID. 
            CalendarFolder calendar = CalendarFolder.Bind(service, WellKnownFolderName.Calendar, new PropertySet());
            // Set the start and end time and number of appointments to retrieve.
            CalendarView cView = new CalendarView(startDate, endDate, NUM_APPTS);
            // Limit the properties returned to the appointment's subject, start time, and end time.
            cView.PropertySet = new PropertySet(AppointmentSchema.Subject, AppointmentSchema.Start, AppointmentSchema.End);
            // Retrieve a collection of appointments by using the calendar view.
            FindItemsResults<Appointment> appointments = calendar.FindAppointments(cView);
            Console.WriteLine("\nThe first " + NUM_APPTS + " appointments on your calendar from " + startDate.Date.ToShortDateString() + 
                              " to " + endDate.Date.ToShortDateString() + " are: \n");
            
            foreach (Appointment a in appointments)
            {
                Console.Write("Subject: " + a.Subject.ToString() + " ");
                Console.Write("Start: " + a.Start.ToString() + " ");
                Console.Write("End: " + a.End.ToString());
                Console.WriteLine();
            }

```

<br/>

Das Codebeispiel gibt die folgende Ausgabe zurück:
  
```text
The first five appointments on your calendar from 8/21/2013 to 9/20/2013 are: 
  
Subject: Contoso devs team meeting Start: 8/21/2013 12:30:00 PM End: 8/21/2013 1:00:00 PM
  
Subject: Daily status meeting Start: 8/21/2013 1:00:00 PM End: 8/21/2013 2:00:00 PM
  
Subject: Lunch with sales team Start: 8/21/2013 2:30:00 PM End: 8/21/2013 3:30:00 PM
  
Subject: Tennis at the club Start: 8/22/2013 11:00:00 AM End: 8/22/2013 12:00:00 PM
  
Subject: Online training webcast: 8/22/2013 2:00:00 PM End: 8/22/2013 3:00:00 PM
```

## <a name="get-appointments-by-using-ews"></a>Abrufen von Terminen mithilfe von EWS
<a name="bk_xml"> </a>

Das folgende XML zeigt eine [GetFolder](https://msdn.microsoft.com/library/355bcf93-dc71-4493-b177-622afac5fdb9%28Office.15%29.aspx)-Vorgangsanforderung zum Zurückgeben einer Ordner-ID für den [FindItem](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx)-Vorgang. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
       xmlns:m="https://schemas.microsoft.com/exchange/services/2006/messages" 
       xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types" 
       xmlns:soap="https://schemas.xmlsoap.org/soap/envelope/">
  <soap:Header>
    <t:RequestServerVersion Version="Exchange2007_SP1" />
  </soap:Header>
  <soap:Body>
    <m:GetFolder>
      <m:FolderShape>
        <t:BaseShape>IdOnly</t:BaseShape>
      </m:FolderShape>
      <m:FolderIds>
        <t:DistinguishedFolderId Id="calendar" />
      </m:FolderIds>
    </m:GetFolder>
  </soap:Body>
</soap:Envelope>
```

<br/>

Das folgende XML zeigt die **GetFolder**-Antwort. Beachten Sie, dass die **FolderID** - und **ChangeKey** -Attribute aus Lesbarkeitsgründen gekürzt wurden. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="https://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ServerVersionInfo MajorVersion="15" MinorVersion="0" MajorBuildNumber="731" MinorBuildNumber="10" Version="V2_3" 
 xmlns:h="https://schemas.microsoft.com/exchange/services/2006/types" 
 xmlns="https://schemas.microsoft.com/exchange/services/2006/types" 
 xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" />
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <m:GetFolderResponse xmlns:m="https://schemas.microsoft.com/exchange/services/2006/messages" 
 xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types">
      <m:ResponseMessages>
        <m:GetFolderResponseMessage ResponseClass="Success">
          <m:ResponseCode>NoError</m:ResponseCode>
          <m:Folders>
            <t:CalendarFolder>
              <t:FolderId Id="AAMk" ChangeKey="AgAA" />
            </t:CalendarFolder>
          </m:Folders>
        </m:GetFolderResponseMessage>
      </m:ResponseMessages>
    </m:GetFolderResponse>
  </s:Body>
</s:Envelope>
```

<br/>

Das folgende XML zeigt die **FindItem**-Anforderung zum Zurückgeben der angeforderten Termine. Beachten Sie, dass die **FolderID** - und **ChangeKey** -Attribute aus Lesbarkeitsgründen gekürzt wurden. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
       xmlns:m="https://schemas.microsoft.com/exchange/services/2006/messages" 
       xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types" 
       xmlns:soap="https://schemas.xmlsoap.org/soap/envelope/">
  <soap:Header>
    <t:RequestServerVersion Version="Exchange2007_SP1" />
  </soap:Header>
  <soap:Body>
    <m:FindItem Traversal="Shallow">
      <m:ItemShape>
        <t:BaseShape>IdOnly</t:BaseShape>
        <t:AdditionalProperties>
          <t:FieldURI FieldURI="item:Subject" />
          <t:FieldURI FieldURI="calendar:Start" />
          <t:FieldURI FieldURI="calendar:End" />
        </t:AdditionalProperties>
      </m:ItemShape>
      <m:CalendarView MaxEntriesReturned="5" StartDate="2013-08-21T17:30:24.127Z" EndDate="2013-09-20T17:30:24.127Z" />
      <m:ParentFolderIds>
        <t:FolderId Id="AAMk" ChangeKey="AgAA" />
      </m:ParentFolderIds>
    </m:FindItem>
  </soap:Body>
</soap:Envelope>
```

<br/>

Das folgende XML zeigt die **FindItem**-Antwort. Beachten Sie, dass die **ItemID** - und **ChangeKey** -Attribute aus Lesbarkeitsgründen gekürzt wurden. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="https://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <h:ServerVersionInfo MajorVersion="15" MinorVersion="0" MajorBuildNumber="731" MinorBuildNumber="10" Version="V2_3" 
 xmlns:h="https://schemas.microsoft.com/exchange/services/2006/types" 
 xmlns="https://schemas.microsoft.com/exchange/services/2006/types" 
 xmlns:xsd="http://www.w3.org/2001/XMLSchema" 
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" />
  </s:Header>
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <m:FindItemResponse xmlns:m="https://schemas.microsoft.com/exchange/services/2006/messages" 
xmlns:t="https://schemas.microsoft.com/exchange/services/2006/types">
      <m:ResponseMessages>
        <m:FindItemResponseMessage ResponseClass="Success">
          <m:ResponseCode>NoError</m:ResponseCode>
          <m:RootFolder TotalItemsInView="33" IncludesLastItemInRange="false">
            <t:Items>
              <t:CalendarItem>
                <t:ItemId Id="AAMk" ChangeKey="DwAA" />
                <t:Subject>Contoso devs team meeting</t:Subject>
                <t:Start>2013-08-21T19:30:00Z</t:Start>
                <t:End>2013-08-21T20:00:00Z</t:End>
              </t:CalendarItem>
              <t:CalendarItem>
                <t:ItemId Id="AAMk" ChangeKey="DwAA" />
                <t:Subject>Daily status meeting</t:Subject>
                <t:Start>2013-08-21T20:00:00Z</t:Start>
                <t:End>2013-08-21T21:00:00Z</t:End>
              </t:CalendarItem>
              <t:CalendarItem>
                <t:ItemId Id="AAMk" ChangeKey="DwAA" />
                <t:Subject>Lunch with sales team</t:Subject>
                <t:Start>2013-08-21T21:30:00Z</t:Start>
                <t:End>2013-08-21T22:30:00Z</t:End>
              </t:CalendarItem>
              <t:CalendarItem>
                <t:ItemId Id="AAMk" ChangeKey="DwAA" />
                <t:Subject>Tennis at the club</t:Subject>
                <t:Start>2013-08-22T18:00:00Z</t:Start>
                <t:End>2013-08-22T19:00:00Z</t:End>
              </t:CalendarItem>
              <t:CalendarItem>
                <t:ItemId Id="AAMkA" ChangeKey="DwAA" />
                <t:Subject>Online training webcast</t:Subject>
                <t:Start>2013-08-22T21:00:00Z</t:Start>
                <t:End>2013-08-22T22:00:00Z</t:End>
              </t:CalendarItem>
            </t:Items>
          </m:RootFolder>
        </m:FindItemResponseMessage>
      </m:ResponseMessages>
    </m:FindItemResponse>
  </s:Body>
</s:Envelope>
```

## <a name="recurring-meetings-and-the-calendar-view"></a>Besprechungsserien und die Kalenderansicht
<a name="bk_recurring"> </a>

Der Kalenderordner unterscheidet sich in gewisser Weise von anderen Ordnern in einem Postfach, da Serienelemente in Besprechungsserien und Ausnahmen von diesen Besprechungsserien keine Elemente im Postfach darstellen, sondern intern als Anlagen in einer übergeordneten Besprechungsserie gespeichert werden. Das heißt: Obwohl sie eine EWS-Anforderung erstellen können, die Werte in einem bestimmten Bereich zwischen **Start** und **Ende** mithilfe der überladenen **FindItems** -Methoden der verwalteten EWS-API wie [ExchangeService.FindItems](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.exchangeservice.finditems%28v=exchg.80%29.aspx) oder des [FindItem](https://msdn.microsoft.com/library/ebad6aae-16e7-44de-ae63-a95b24539729%28Office.15%29.aspx)-Vorgangs von EWS abruft, wird EWS nicht in der Anlagentabelle jedes Kalenderelements nach Ausnahmen und Serienelementen suchen. 
  
Stattdessen möchten Sie eine  *Datenansicht*  auf zwei SQL-Tabellen mithilfe eines [CalendarView](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.calendarview%28v=exchg.80%29.aspx)-Objekts anwenden. Aus Leistungsgründen wird empfohlen, die [PropertySet](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.propertyset%28v=exchg.80%29.aspx)-Eigenschaft zum Einschränken der Antwortgröße durch Angeben der zurückzugebenden Anzahl von Terminen oder Besprechungen sowie von bestimmten Eigenschaften zu verwenden. 
  
## <a name="see-also"></a>Siehe auch
<a name="bk_additional"> </a>

- [Kalender und EWS in Exchange](calendars-and-ews-in-exchange.md)   
- [Erstellen von Terminen und Besprechungen mithilfe von EWS in Exchange 2013](how-to-create-appointments-and-meetings-by-using-ews-in-exchange-2013.md)  
- [Aktualisieren von Terminen und Besprechungen mithilfe von EWS in Exchange](how-to-update-appointments-and-meetings-by-using-ews-in-exchange.md)  
- [Löschen von Terminen und Absagen von Besprechungen mithilfe von EWS in Exchange](how-to-delete-appointments-and-cancel-meetings-by-using-ews-in-exchange.md) 
- [Entwickeln von Webdienstclients für Exchange](develop-web-service-clients-for-exchange.md)
    

