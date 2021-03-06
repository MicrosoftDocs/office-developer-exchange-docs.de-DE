---
title: Exchange Online- und Exchange-Entwicklung
manager: sethgros
ms.date: 03/9/2015
ms.audience: Developer
ms.assetid: f33d1093-75ba-4ff2-8d15-b0bf73a401bf
description: Hier finden Sie eine ausführliche Entwicklerdokumentation für Exchange Server, einschließlich Exchange Online im Rahmen von Office 365 und Exchange Server lokalen Versionen.
localization_priority: Priority
ms.openlocfilehash: 12a29ca07801561e7a746603d795468d9cb7491f
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44528496"
---
# <a name="exchange-online-and-exchange-development"></a>Exchange Online- und Exchange-Entwicklung

Hier finden Sie eine ausführliche Entwicklerdokumentation für Exchange Server, einschließlich Exchange Online im Rahmen von Office 365 und Exchange Server lokalen Versionen.

Mithilfe der Vorgehensweise, erste Schritte, neuen Features und API-Referenzdokumentation können Sie Tools für den Zugriff auf und die Verwaltung von Postfachdaten von Diensten, Websites, Desktopcomputern und mobilen Geräten entwickeln sowie benutzerdefinierte Lösungen für e-Mail, Kalender, Kontakte und andere Elemente erstellen, die in Exchange Online oder auf einem Exchange 2010, 2013, 2016 und 2019-Server gespeichert sind.

Sie können Graph-API, Rest-API, Exchange-Webdienste, AutoErmittlung, Outlook-Add-Ins oder andere APIs verwenden, um Ihre Anwendungen zu entwickeln. Diese Seite hilft Ihnen bei der Auswahl der richtigen Exchange-Technologie.

## <a name="exchange-developer-content"></a>Inhalte für Exchange-Entwickler

Verwenden Sie die folgende Tabelle, um die Technologie und die zugehörigen API-Inhalte zu identifizieren, mit denen Sie Ihre Entwicklungsziele erreichen können.

> [!IMPORTANT]
> Microsoft Graph ist die empfohlene API für den Zugriff auf Exchange Online-Daten. Neue Anwendungen, die zum Zugreifen auf Exchange Online-Daten entwickelt werden, sollten Microsoft Graph verwenden.

|Wenn Sie Folgendes erstellen…|Beginnen Sie hier.|
|:-----|:-----|
|Eine REST-basierte App zum Zugreifen auf Exchange Online als Teil von Office 365|[Microsoft Graph-REST-APIs für E-Mail, Kalender und Kontakte](exchange-web-services/office-365-rest-apis-for-mail-calendars-and-contacts.md) |
|Eine kontextabhängige App zum Anzeigen von Informationen in Outlook, Outlook Web App oder OWA für mobile Geräte. |[Outlook-Add-Ins und EWS in Exchange](exchange-web-services/mail-apps-for-outlook-and-ews-in-exchange.md) |
|Einen Postfachclient, der nicht auf dem .NET Framework oder auf Java basiert. |[Erkunden von verwalteter EWS-API, EWS und Webdiensten in Exchange](exchange-web-services/explore-the-ews-managed-api-ews-and-web-services-in-exchange.md) |
|Einen Postfachclient, der den .NET Framework zum Zugriff auf EWS verwendet. |[Erste Schritte mit verwalteten EWS-API-Clientanwendungen](exchange-web-services/get-started-with-ews-managed-api-client-applications.md) |
|Einen Postfachclient, der Java zum Zugriff auf EWS verwendet. |[EWS-Java-API auf GitHub](https://github.com/OfficeDev/ews-java-api) |
|Eine Anwendung, die die Outlook-Benutzeroberfläche anpasst, oder die Geschäftslogik von Outlook verwendet.  |[VBA-Referenz für Outlook](https://msdn.microsoft.com/VBA/VBA-Outlook) |
|Eine Anwendung, die auf Exchange Online oder Exchange 2013 ausgerichtet ist, und von einer früheren Exchange-Version migriert werden muss.  |[Migration zu Exchange-Technologien](migrating-to-exchange-online-and-exchange-2013-technologies.md) |
|Ein benutzerdefiniertes Verwaltungstool, das Windows PowerShell aus verwaltetem Code verwendet.   |[Exchange-Verwaltungsshell](management/exchange-management-shell.md) |
|Eine Lösung zum Sichern oder Wiederherstellen von Exchange-Daten.  |[Sicherung und Wiederherstellung für Exchange](backup-restore/backup-and-restore-for-exchange-2013.md) |
|Eine Erweiterung, um den Zugriff auf Meldungen in der Transportpipeline zu unterstützen.   |[Transport-Agents in Exchange](transport-agents/transport-agents-in-exchange-2013.md)  |
|Ein Postfachclient für ein Mobilgerät.   |[Exchange ActiveSync](https://technet.microsoft.com/library/aa998357.aspx) |

## <a name="exchange-interactions-with-custom-applications"></a>Exchange-Interaktionen mit benutzerdefinierten Anwendungen

Einige dieser Technologien ermöglichen Ihren Anwendungen, mit in Exchange gespeicherten Daten zu arbeiten, und andere werden verwendet, um den Exchange-Server zu verwalten und zu steuern. In vielen Fällen können Sie mehr als eine Programmiertechnik oder -sprache verwenden, um eine Aufgabe auszuführen, wodurch Sie die Technologien und Sprachen verwenden können, mit denen Sie sich auskennen.Sie können zum Beispiel Eigenschaften auf Elementen im Exchange-Speicher festlegen, indem Sie Mail REST API, EWS oder Verwaltete EWS-API verwenden.

Exchange interagiert mit benutzerdefinierten Anwendungen je nach Anwendungsarchitektur und Funktion auf verschiedene Arten. Exchange leitet Nachrichten nicht nur weiter, sondern pflegt auch Posteingänge, führt formularbasierte Anwendungen aus, usw.

|Exchange-Interaktion|Beschreibung|
|:-----|:-----|
|**Nachrichtentransport**|Exchange fungiert als standardmäßiger E-Mail-Server für Anwendungen, die Nachrichten senden.<br/>Exchange enthält verschiedene APIs, die Nachrichten weiterleiten, einschließlich REST, EWS und Verwaltete EWS-API.<br/>Darüber hinaus können Anwendungen zum Antworten Transport-Agents verwenden, wenn Nachrichten von Exchange verarbeitet und übermittelt werden. |
|**Postfachspeicher** |Exchange bietet eine hierarchische Struktur von Ordnern, Elementen und Eigenschaften für Anwendungen, die auf in Postfächern gespeicherte Daten zugreifen.<br/>Sie können auf diese gespeicherten Informationen zugreifen, indem Sie eine Kombination aus Datenbank und Komponentenobjektstilen verwenden.<br/>Sie können Abfragen auf den Daten durchführen, und Exchange verwaltet den Zugriff auf die gespeicherten Daten auf Grundlage der Benutzer- und Speicherberechtigungen.<br/>Anwendungen, die Postfachdaten verarbeiten, verwenden in der Regel REST, EWS oder die verwaltete EWS-API.|
|**Verwalteter Unternehmensserver** |Exchange fungiert als verwalteter Server für Anwendungen, die Exchange-Server und -Speicher verwalten.<br/>Anwendungen können aktuelle Aktivitäten sowie den Zustand von Exchange-Servern in der Organisation konfigurieren, steuern und überwachen.<br/>Exchange-Verwaltungsanwendungen verwenden die Exchange-Verwaltungsshell zum Verwalten von Exchange-Servern. |

## <a name="see-also"></a>Siehe auch

- 
  [Server-API-Referenz für Exchange](https://msdn.microsoft.com/library/dn186243(v=exchg.150).aspx)
- [Weitere Informationen zu Exchange in Office-Blogs](https://www.microsoft.com/microsoft-365/blog/)
- [101 Codebeispiele für Exchange 2013](https://code.msdn.microsoft.com/office/Exchange-2013-101-Code-3c38582c)
- [Abrufen der verwalteten EWS-API (GitHub)](https://github.com/OfficeDev/ews-managed-api/blob/master/README.md)
- [Unterstützung für Exchange Server](https://support.microsoft.com/getsupport?oaspworkflow=start_1.0.0.0&wf=0&wfname=productselection&gprid=730&x=13&y=7&st=1&wfxredirect=1&sd=gn&ccsid=635890984021344661&forceorigin=esmc)
