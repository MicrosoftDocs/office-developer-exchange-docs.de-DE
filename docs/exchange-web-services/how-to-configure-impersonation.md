---
title: Konfigurieren eines Identitätswechsels
manager: sethgros
ms.date: 11/16/2014
ms.audience: Developer
ms.assetid: efcef39f-e26d-4eed-95ac-36a5bf8c089f
description: Erfahren Sie, wie Sie einem Dienstkonto mithilfe der Exchange-Verwaltungsshell die Identitätswechselrolle gewähren können.
localization_priority: Priority
ms.openlocfilehash: f8fe95536213e347840af082d765a9cc2fbce819
ms.sourcegitcommit: 88ec988f2bb67c1866d06b361615f3674a24e795
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44455898"
---
# <a name="configure-impersonation"></a>Konfigurieren eines Identitätswechsels

Erfahren Sie, wie Sie einem Dienstkonto mithilfe der Exchange-Verwaltungsshell die Identitätswechselrolle gewähren können. 
  
Durch den Identitätswechsel kann ein Aufrufer wie eine Dienstanwendung ein Benutzerkonto imitieren. Der Aufrufer kann Vorgänge mithilfe der Berechtigungen durchführen, die dem imitierten Konto zugewiesen sind, statt die dem Aufruferkonto zugewiesenen Berechtigungen zu verwenden.
  
Exchange Online, Exchange Online als Teil von Office 365 und Versionen von Exchange ab Exchange 2013 verwenden die rollenbasierte Zugriffssteuerung (RBAC), um Konten Berechtigungen zu gewähren. Ihr Exchange-Serveradministrator muss den Dienstkonten die **ApplicationImpersonation**-Rolle mithilfe des [New-ManagementRoleAssignment](https://msdn.microsoft.com/library/34d4f2e3-f2c5-49e1-a6a9-1366da65a78c.aspx)-Cmdlets gewähren, die andere Benutzer imitieren. 
  
## <a name="configuring-the-applicationimpersonation-role"></a>Konfigurieren der ApplicationImpersonation-Rolle

Verwenden Sie oder Ihr Exchange-Serveradministrator beim Zuweisen der **ApplicationImpersonation**-Rolle folgende Parameter des **New-ManagementRoleAssignment**-Cmdlets: 
  
-  _Name_ &ndash; Der Anzeigename der Rollenzuweisung. Jedes Mal, wenn eine Rolle zugewiesen wird, wird ein Eintrag in der Liste der RBAC-Rollen vorgenommen. Verwenden Sie das Cmdlet [Get-ManagementRoleAssignment](https://msdn.microsoft.com/library/a3a6ee46-061b-444a-8639-43a416309445.aspx), um Rollenzuweisungen zu überprüfen. 
    
-  _Role_ &ndash; Die zuzuweisende RBAC-Rolle. Beim Einrichten des Identitätswechsels weisen Sie die **ApplicationImpersonation**-Rolle zu. 
    
-  _User_ &ndash; Das Dienstkonto. 
    
-  _CustomRecipientScope_ &ndash; Der Benutzerumfang, den das Benutzerkonto imitieren kann. Das Dienstkonto darf den Identitätswechsel nur für andere Benutzer innerhalb des angegebenen Bereichs zulassen. Wenn kein Umfang angegeben ist, wird dem Dienstkonto die **ApplicationImpersonation**-Rolle für alle Benutzer in einem Unternehmen gewährt. Sie können benutzerdefinierte Verwaltungsbereiche mithilfe des [New-ManagementScope](https://msdn.microsoft.com/library/1ea1f474-69d6-48c0-9beb-bfa4442c5dab.aspx)-Cmdlets angeben. 
    
Bevor Sie den Identitätswechsel konfigurieren, benötigen Sie Folgendes:
  
- Administratoranmeldeinformationen für den Exchange-Server
    
- Domänenadministrator-Anmeldeinformationen oder andere Anmeldeinformationen mit der Berechtigung zum Erstellen und Zuweisen von Rollen und Bereichen
    
- Exchange-Verwaltungstools. Sie werden auf dem Computer installiert, über den Sie die Befehle ausführen.
    
### <a name="to-configure-impersonation-for-all-users-in-an-organization"></a>So konfigurieren Sie den Identitätswechsel für alle Benutzer in einem Unternehmen

1. Öffnen Sie die Exchange-Verwaltungsshell. Wählen Sie im Startmenü **Alle Programme** > **Microsoft Exchange Server 2013**. 
    
2. Führen Sie das **New-ManagementRoleAssignment**-Cmdlet aus, um die Identitätswechselberechtigung für den angegebenen Benutzer hinzuzufügen. Im folgenden Beispiel wird veranschaulicht, wie man den Identitätswechsel konfigurieren muss, damit ein Dienstkonto alle anderen Benutzer in einem Unternehmen imitieren kann. 
    
   ```powershell
   New-ManagementRoleAssignment -name:impersonationAssignmentName -Role:ApplicationImpersonation -User:serviceAccount 
   ```

### <a name="to-configure-impersonation-for-specific-users-or-groups-of-users"></a>So konfigurieren Sie den Identitätswechsel für bestimmte Benutzer oder Benutzergruppen

1. Öffnen Sie die Exchange-Verwaltungsshell. Wählen Sie im Startmenü **Alle Programme** > **Microsoft Exchange Server 2013**. 
    
2. Führen Sie das **New-ManagementScope**-Cmdlet aus, um einen Bereich zu erstellen, dem die Identitätswechselrolle zugewiesen werden kann. Wenn ein vorhandener Bereich verfügbar ist, können Sie diesen Schritt überspringen. Im folgenden Beispiel wird veranschaulicht, wie ein Verwaltungsbereich für eine bestimmte Gruppe erstellt werden kann. 
    
   ```powershell
    New-ManagementScope -Name:scopeName -RecipientRestrictionFilter:recipientFilter
   ```

   Der _RecipientRestrictionFilter_-Parameter des **New-ManagementScope**-Cmdlets definiert die Elemente des Bereichs. Sie können die Eigenschaften des **Identity**-Objekt verwenden, um den Filter zu erstellen. Das folgende Beispiel ist ein Filter, der das Ergebnis auf einen einzelnen Benutzer mit dem Benutzernamen „John" begrenzt. 
    
   ```powershell
   Name -eq "john"
   ```

3. Führen Sie das **New-ManagementRoleAssignment**-Cmdlet aus, um die Berechtigung zum Imitieren der Elemente des angegebenen Bereichs hinzuzufügen. Im folgenden Beispiel wird veranschaulicht, wie ein Dienstkonto zum Imitieren aller Benutzer in einem Bereich konfiguriert werden muss. 
    
   ```powershell
    New-ManagementRoleAssignment -Name:impersonationAssignmentName -Role:ApplicationImpersonation -User:serviceAccount -CustomRecipientWriteScope:scopeName
    
   ```


Nachdem der Administrator die Identitätswechsel-Berechtigungen gewährt hat, können Sie das Dienstkonto verwenden, um Aufrufe zu anderen Benutzerkonten auszuführen. Sie können die Rollenzuweisungen mithilfe des [Get-ManagementRoleAssignment](https://msdn.microsoft.com/library/a3a6ee46-061b-444a-8639-43a416309445.aspx)-Cmdlets verifizieren. 
  
## <a name="see-also"></a>Siehe auch

- [Identitätswechsel und EWS in Exchange](impersonation-and-ews-in-exchange.md)
- [ApplicationImpersonation-Rolle](https://technet.microsoft.com/library/dd776119%28v=exchg.150%29.aspx)   
- [New-ManagementRoleAssignment](https://msdn.microsoft.com/library/34d4f2e3-f2c5-49e1-a6a9-1366da65a78c.aspx)    
- [Get-ManagementRoleAssignment](https://msdn.microsoft.com/library/a3a6ee46-061b-444a-8639-43a416309445.aspx)
    

