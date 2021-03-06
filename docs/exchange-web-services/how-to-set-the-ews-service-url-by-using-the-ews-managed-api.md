---
title: Festlegen der EWS-Dienst-URL mithilfe der verwalteten EWS-API
manager: sethgros
ms.date: 09/17/2015
ms.audience: Developer
ms.assetid: cddf6525-1c04-484b-a911-56c2f0f1f7b6
description: Informationen zum Festlegen der EWS-Dienst-URL in Ihrer EWS Managed API-Anwendung.
localization_priority: Priority
ms.openlocfilehash: 5ba79b48d4eb4fec62110448c5924de16b67ce10
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44456733"
---
# <a name="set-the-ews-service-url-by-using-the-ews-managed-api"></a>Festlegen der EWS-Dienst-URL mithilfe der verwalteten EWS-API

Informationen zum Festlegen der EWS-Dienst-URL in Ihrer EWS Managed API-Anwendung.
  
Die Dienst-URL ist die Adresse, über die Exchange mit Exchange-Webdienste (EWS) kommuniziert. Wenn die verwaltete EWS-API-Anwendung über diese Adresse und entsprechenden Zugriff zum [Kommunizieren mit EWS](how-to-communicate-with-ews-by-using-the-ews-managed-api.md) verfügt, kann sie Aufrufe an die [ExchangeService-Klasse](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.exchangeservice%28v=exchg.80%29.aspx) durchführen. Die Dienst-URL für einen lokalen Exchange-Server kann wie folgt aussehen. 
  
```HTML
https://computer.domain.contoso.com/EWS/Exchange.asmx
```

Sie können die EWS-URL in der Anwendung auf verschiedene Weise festlegen. Empfohlen wird die Verwendung des [AutoErmittlungsdiensts](https://msdn.microsoft.com/library/39726b67-2eb2-451b-9307-cfd0b518b55c%28Office.15%29.aspx) zum Abrufen der URL, da sich die URL bei einer großen Gesamtstruktur von Servern ändern kann, wenn das Postfach auf einen anderen Server migriert wird. Da der Aufruf der AutoErmittlung jedoch einige Zeit in Anspruch nehmen und die Anwendung verlangsamen kann, sollten Sie, falls Sie mehrere Aufrufe innerhalb eines kurzen Zeitraums durchführen müssen, den von der AutoErmittlung abgerufenen URL-Wert zwischenspeichern und die EWS-Dienst-URL mit diesem zwischengespeicherten Wert manuell festlegen. Dies verbessert die Leistung der Anwendung; stellen Sie lediglich sicher, dass Sie den zwischengespeicherten Wert regelmäßig mithilfe der AutoErmittlung aktualisieren, falls sich der Wert auf dem Server ändert. 
  
## <a name="set-the-ews-service-url-by-using-the-autodiscover-service"></a>Festlegen der EWS-Dienst-URL mithilfe des AutoErmittlungsdiensts
<a name="bk_SetURLusingAutoDiscover"> </a>

Die [AutodiscoverUrl](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.exchangeservice.autodiscoverurl%28v=exchg.80%29.aspx)-Methode verwendet die E-Mail-Adresse zum Festlegen des [ExchangeService](https://msdn.microsoft.com/library/microsoft.exchange.webservices.data.exchangeservice%28v=exchg.80%29.aspx)-Endpunkts und ermöglicht es der Anwendung, alle in den **ExchangeService** -Proxyklassen enthaltenen Methoden zu verwenden. Im folgenden Beispiel wird die Verwendung der **AutodiscoverURL** -Methode veranschaulicht. 
  
```cs
// Create the binding.
ExchangeService service = new ExchangeService();
// Set the credentials for the on-premises server.
service.Credentials = new WebCredentials("user1@contoso.com", "password");
// Set the URL.
service.AutodiscoverUrl("User1@contoso.com");

```

## <a name="set-the-exchange-service-url-manually"></a>Manuelles Festlegen der Exchange-Dienst-URL
<a name="bk_SetURLmanually"> </a>

Im folgenden Beispiel wird gezeigt, wie Sie die EWS-Dienst-URL unter Verwendung eines zwischengespeicherten Werts festlegen. Vorher müssen Sie mithilfe des AutoErmittlungsdiensts die EWS-URL abrufen.
  
```cs
// Create the binding.
ExchangeService service = new ExchangeService();
// Set the credentials for the on-premises server.
service.Credentials = new WebCredentials("user1@contoso.com", "password");
// Set the URL.
service.Url = new Uri("https://computername.domain.contoso.com/EWS/Exchange.asmx");

```

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit verwalteten EWS-API-Clientanwendungen](get-started-with-ews-managed-api-client-applications.md)   
- [Einrichten der Umgebung der Exchange-Anwendungsentwicklung](setting-up-your-exchange-application-development-environment.md)   
- [Steuern des Zugriffs auf EWS in Exchange](how-to-control-access-to-ews-in-exchange.md) 
- [Kommunizieren mit EWS unter Verwendung der verwalteten EWS-API](how-to-communicate-with-ews-by-using-the-ews-managed-api.md)  
- [Verwenden der AutoErmittlung für die Suche nach Verbindungspunkten](how-to-use-autodiscover-to-find-connection-points.md)
    

