---
title: Rolle
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b115c990-3a2d-4536-9af3-ac1fd06d00dc
description: Das Persona-Element gibt einen Satz von Persona Daten von einer Anforderung GetPersona zurückgegeben.
ms.openlocfilehash: 15af72eb0e25e424aa7293ce0cbc2dd31e76abda
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19830736"
---
# <a name="persona"></a>Rolle

Das **Persona** -Element gibt einen Satz von Persona Daten von einer Anforderung **GetPersona** zurückgegeben. 
  
```XML
<Persona>
   <PersonaId/>
   <PersonaType/>
   <PersonaObjectStatus/>
   <CreationTime/>
   <Bodies/>
   <DisplayNameFirstLastSortKey/>
   <DisplayNameLastFirstSortKey/>
   <CompanyNameSortKey/>
   <HomeCitySortKey/>
   <WorkCitySortKey/>
   <DisplayNameFirstLastHeader/>
   <DisplayNameLastFirstHeader/>
   <FileAsHeader/>
   <DisplayName/>
   <DisplayNameFirstLast/>
   <DisplayNameLastFirst/>
   <FileAs/>
   <FileAsId/>
   <DisplayNamePrefix/>
   <GivenName/>
   <MiddleName/>
   <Surname/>
   <Generation/>
   <Nickname/>
   <YomiCompanyName/>
   <YomiFirstName/>
   <YomiLastName/>
   <Title/>
   <Department/>
   <CompanyName/>
   <Location/>
   <EmailAddress/>
   <EmailAddresses/>
   <PhoneNumber/>
   <ImAddress/>
   <HomeCity/>
   <WorkCity/>
   <RelevanceScore/>
   <FolderIds/>
   <Attributions/>
   <DisplayNames/>
   <FileAses/>
   <FileAsIds/>
   <DisplayNamePrefixes/>
   <GivenNames/>
   <MiddleNames/>
   <Surnames/>
   <Generations/>
   <Nicknames/>
   <Initials/>
   <YomiCompanyNames/>
   <YomiFirstNames/>
   <YomiLastNames/>
   <BusinessPhoneNumbers/>
   <BusinessPhoneNumbers2/>
   <HomePhones/>
   <HomePhones2/>
   <MobilePhones/>
   <MobilePhones2/>
   <AssistantPhoneNumbers/>
   <CallbackPhones/>
   <CarPhones/>
   <HomeFaxes/>
   <OrganizationMainPhones/>
   <OtherFaxes/>
   <OtherTelephones/>
   <OtherPhones2/>
   <Pagers/>
   <RadioPhones/>
   <TelexNumbers/>
   <TTYTDDPhoneNumbers/>
   <WorkFaxes/>
   <Emails1/>
   <Emails2/>
   <Emails3/>
   <BusinessHomePages/>
   <PersonalHomePages/>
   <OfficeLocations/>
   <ImAddresses/>
   <ImAddresses2/>
   <ImAddresses3/>
   <BusinessAddresses/>
   <HomeAddresses/>
   <OtherAddresses/>
   <Titles/>
   <Departments/>
   <CompanyNames/>
   <Managers/>
   <AssistantNames/>
   <Professions/>
   <SpouseNames/>
   <Children/>
   <Schools/>
   <Hobbies/>
   <WeddingAnniversaries/>
   <Birthdays/>
   <Locations/>
   <ExtendedProperties/>
</Persona>

```

 **PersonaType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

Keine.
  
### <a name="child-elements"></a>Untergeordnete Elemente

[PersonaId](personaid.md) | [PersonaType](personatype.md) | [PersonaObjectStatus](personaobjectstatus.md) | [CreationTime](creationtime.md) | [Bodies](bodies.md) | [DisplayNameFirstLastSortKey](displaynamefirstlastsortkey.md) | [DisplayNameLastFirstSortKey ](displaynamelastfirstsortkey.md)  |  [CompanyNameSortKey](companynamesortkey.md) | [HomeCitySortKey](homecitysortkey.md) | [WorkCitySortKey](workcitysortkey.md) | [DisplayNameFirstLastHeader](displaynamefirstlastheader.md) | [DisplayNameLastFirstHeader](displaynamelastfirstheader.md)  |  [FileAsHeader](fileasheader.md) | [DisplayName (String)](displayname-string.md) | [DisplayNameFirstLast](displaynamefirstlast.md) | [DisplayNameLastFirst](displaynamelastfirst.md) | [FileAs](fileas.md) | [FileAsId](fileasid.md)  |  [DisplayNamePrefix](displaynameprefix.md)  |  [Vorname](givenname.md) | [MiddleName](middlename.md) | [Surname](surname.md) | [Generation](generation.md) | [Spitzname](nickname.md) | [YomiCompanyName](yomicompanyname.md) | [YomiFirstName ](yomifirstname.md)  |  [YomiLastName](yomilastname.md) | [Titel](title.md) | [Abteilung](department.md) | [CompanyName](companyname.md) | [Speicherort](location.md) | [EmailAddress (EmailAddressType)](emailaddress-emailaddresstype.md)  |  [EmailAddresses (ArrayOfEmailAddressesType)](emailaddresses-arrayofemailaddressestype.md)  |  [PhoneNumber](phonenumber.md) | [ImAddress (String)](imaddress-string.md) | [HomeCity](homecity.md) | [WorkCity](workcity.md) | [RelevanceScore](relevancescore.md) | [FolderIds (ArrayOfFolderIdType)](folderids-arrayoffolderidtype.md)  |  [Marken (ArrayOfPersonaAttributionsType)](attributions-arrayofpersonaattributionstype.md) | [DisplayNames](displaynames.md) | [FileAses](fileases.md) | [FileAsIds](fileasids.md) | [DisplayNamePrefixes](displaynameprefixes.md) | [GivenNames ](givennames.md)  |  [MiddleNames](middlenames.md) | [Nachnamen](surnames.md) | [Generationen](generations.md) | [Spitznamen](nicknames.md) | [Initialen (ArrayOfStringAttributedValuesType)](initials-arrayofstringattributedvaluestype.md)  |  [ YomiCompanyNames](yomicompanynames.md) | [YomiFirstNames](yomifirstnames.md) | [YomiLastNames](yomilastnames.md) | [BusinessPhoneNumbers](businessphonenumbers.md) | [BusinessPhoneNumbers2](businessphonenumbers2.md) | [HomePhones ](homephones.md)  |  [HomePhones2](homephones2.md) | [MobilePhones](mobilephones.md) | [MobilePhones2](mobilephones2.md) | [AssistantPhoneNumbers](assistantphonenumbers.md) | [CallbackPhones](callbackphones.md)  |  [CarPhones](carphones.md)  |  [HomeFaxes](homefaxes.md) | [OrganizationMainPhones](organizationmainphones.md) | [OtherFaxes](otherfaxes.md) | [OtherTelephones](othertelephones.md) | [OtherPhones2](otherphones2.md) | [Pager ](pagers.md)  |  [RadioPhones](radiophones.md) | [TelexNumbers](telexnumbers.md) | [TTYTDDPhoneNumbers](ttytddphonenumbers.md) | [WorkFaxes](workfaxes.md) | [Emails1](emails1.md) | [Emails2 ](emails2.md)  |  [Emails3](emails3.md) | [BusinessHomePages](businesshomepages.md) | [PersonalHomePages](personalhomepages.md) | [OfficeLocations](officelocations.md) | [ImAddresses ( ArrayOfStringAttributedValuesType)](imaddresses-arrayofstringattributedvaluestype.md) | [ImAddresses2](imaddresses2.md) | [ImAddresses3](imaddresses3.md) | [BusinessAddresses](businessaddresses.md) | [HomeAddresses](homeaddresses.md)  |  [ OtherAddresses](otheraddresses.md) | [Titel](titles.md) | [Abteilungen](departments.md) | [CompanyNames](companynames.md) | [Manager](managers.md) | [AssistantNames](assistantnames.md)  |  [ Berufen](professions.md) | [SpouseNames](spousenames.md) | [untergeordnete Elemente (ArrayOfStringArrayAttributedValuesType)](children-arrayofstringarrayattributedvaluestype.md) | [Schulen](schools.md) | [Hobbys](hobbies.md)  |  [ WeddingAnniversaries](weddinganniversaries.md) | [Geburtstage](birthdays.md) | [Speicherorte](locations.md) | [ExtendedProperties (ArrayOfExtendedPropertyAttributedValueType)](extendedproperties-arrayofextendedpropertyattributedvaluetype.md)
  
### <a name="parent-elements"></a>Übergeordnete Elemente

[AddNewImContactToGroupResponse](addnewimcontacttogroupresponse.md) | [AddNewTelUriContactToGroupResponse](addnewteluricontacttogroupresponse.md) | [GetPersonaResponseMessage](getpersonaresponsemessage.md) | [Personen](people.md) | [Rollen](personas-ex15websvcsotherref.md)
  
## <a name="remarks"></a>Hinweise

Dieses Element wurde in Exchange Server 2013 eingeführt.
  
Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|Namespace  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichtenschema  <br/> |
|Überprüfungsdatei  <br/> |Messages.xsd  <br/> |
|Kann leer sein  <br/> |false  <br/> |
   
