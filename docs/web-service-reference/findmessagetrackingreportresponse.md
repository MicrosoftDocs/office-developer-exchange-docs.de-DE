---
title: FindMessageTrackingReportResponse
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FindMessageTrackingReportResponse
api_type:
- schema
ms.assetid: ed4265dc-0e79-4b34-8bf4-88a94875629d
description: Das FindMessageTrackingReportResponse-Element enthält den Status und das Ergebnis einer Anforderung FindMessageTrackingReport Vorgang.
ms.openlocfilehash: fa381f500eac9a46b11aea8c813f1ffc625a3bc3
ms.sourcegitcommit: 34041125dc8c5f993b21cebfc4f8b72f0fd2cb6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "19758472"
---
# <a name="findmessagetrackingreportresponse"></a>FindMessageTrackingReportResponse

Das **FindMessageTrackingReportResponse** -Element enthält, der Status und das Ergebnis einer einzelnen Anforderung [FindMessageTrackingReport Vorgang](findmessagetrackingreport-operation.md) . 
  
```xml
<FindMessageTrackingReportResponse ResponseClass="">
   <MessageText/>
   <ResponseCode/>
   <DescriptiveLinkKey/>
   <MessageXml/>
   <Diagnostics/>
   <MessageTrackingSearchResults/>
   <Errors/>
   <Properties/>
</FindMessageTrackingReportResponse>
```

 **FindMessageTrackingReportResponseMessageType**
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete und übergeordnete Elemente erläutert.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Beschreibung**|
|:-----|:-----|
|**ResponseClass** <br/> | Beschreibt den Status der Antwort.<br/><br/> Die folgenden Werte sind für dieses Attribut gültig:  <br/><br/>-Success  <br/>-Warnung  <br/>-Fehler  <br/> |
   
#### <a name="responseclass-attribute-values"></a>Attributwerte ResponseClass

|**Wert**|**Beschreibung**|
|:-----|:-----|
|**Success** <br/> |Beschreibt eine Anforderung, die erfüllt ist.  <br/> |
|**Warning** <br/> | Beschreibt eine Anforderung, die nicht verarbeitet wurde. Eine Warnung kann zurückgegeben werden, wenn ein Fehler aufgetreten ist, während ein Element in der Anforderung verarbeitet hat, und die nachfolgenden Elemente nicht verarbeitet werden konnte. <br/><br/>Es folgen Beispiele für die Quellen der Warnungen: <br/> <br/>-Der Exchange-Speicher ist während der Batchaktualisierung offline.  <br/>-Active Directory-Domänendienste (AD DS) ist offline.  <br/>-Postfächern verschoben wurden.  <br/>-Die Nachrichtendatenbank (MDB) ist offline.  <br/>-Ein Kennwort ist abgelaufen.  <br/>-Ein Kontingent wurde überschritten.  <br/> |
|**Fehler** <br/> | Beschreibt eine Anforderung, die nicht gewährleistet werden kann. <br/><br/>Es folgen Beispiele für Datenquellen von Fehlern:  <br/><br/>-Ungültige Attribute oder Elemente  <br/>-Attribute oder Elemente, die sich außerhalb des gültigen Bereichs befinden.  <br/>-Eine unbekannte Marke  <br/>-Eines Attributs oder Elements, das nicht im Kontext gültig ist.  <br/>-Einen nicht autorisierten Zugriffsversuch von jedem client  <br/>-Eine serverseitige Fehler als Reaktion auf einen gültigen mithilfe der clientseitigen Anruf  <br/><br/>  Informationen zu dem Fehler kann in den Elementen [ResponseCode](responsecode.md) und [MessageText](messagetext.md) gefunden werden.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Beschreibung**|
|:-----|:-----|
|[MessageText](messagetext.md) <br/> |Enthält einen beschreibenden Text für den Status der Antwort.  <br/> |
|[ResponseCode](responsecode.md) <br/> |Enthält einen Fehlercode, der den jeweiligen Fehler identifiziert, bei dem die Anforderung auftrat.  <br/> |
|[DescriptiveLinkKey](descriptivelinkkey.md) <br/> |Derzeit nicht verwendet wird und für die zukünftige Verwendung reserviert. Dieses Element enthält den Wert 0.  <br/> |
|[MessageXml](messagexml.md) <br/> |Bietet zusätzliche Fehlerantwortinformationen.  <br/> |
|[Diagnose](diagnostics.md) <br/> |Enthält Informationen, die verwendet wird, um verschiedene statistische Berichte für die Tracking-Feature in einem Datencenter zu erstellen.  <br/> |
|[MessageTrackingSearchResults](messagetrackingsearchresults.md) <br/> |Enthält und Array von Nachrichten, die die Suche Anforderungen entsprechen.  <br/> |
|[ExecutedSearchScope](executedsearchscope.md) <br/> |Enthält den Bereich der Suche, die ausgeführt wurde, um die Suchergebnisse erhalten.  <br/> |
|[Fehler](errors-ex15websvcsotherref.md) <br/> |Enthält einen Eigenschaftenbehälter zum Speichern von Fehlern, die über den Webdienst zurückgegeben werden.  <br/> |
|[Eigenschaften (ArrayOfTrackingPropertiesType)](properties-arrayoftrackingpropertiestype.md) <br/> |Enthält eine Liste der Eigenschaften für eine oder mehrere Tracking an.  <br/> |
   
### <a name="parent-elements"></a>Übergeordnete Elemente

Keine.
  
## <a name="text-value"></a>Textwert

Keine.
  
## <a name="remarks"></a>Hinweise

Das Schema, das dieses Element beschreibt, befindet sich im virtuellen IIS-Verzeichnis, das Exchange-Webdienste hostet.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|Namespace  <br/> |http://schemas.microsoft.com/exchange/services/2006/messages  <br/> |
|Name des Schemas  <br/> |Nachrichtenschema  <br/> |
|Überprüfungsdatei  <br/> |Messages.xsd  <br/> |
|Leer kann sein  <br/> |False  <br/> |
   
## <a name="see-also"></a>Siehe auch

- [FindMessageTrackingReport-Vorgang](findmessagetrackingreport-operation.md)
- [EWS-XML-Elemente in Exchange](ews-xml-elements-in-exchange.md)
