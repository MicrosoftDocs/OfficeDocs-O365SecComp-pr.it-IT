---
title: Abilitare o disabilitare la ricerca nel log di controllo di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: È possibile abilitare la funzionalità di ricerca del registro di controllo nel centro sicurezza & Compliance. Se si cambia idea, è possibile attivarlo in qualsiasi momento. Quando la ricerca del registro di controllo è disattivata, gli amministratori non possono eseguire ricerche nel log di controllo di Office 365 per l'attività dell'utente e dell'amministratore nell'organizzazione.
ms.openlocfilehash: a77114ac9b5de18d4718a543983f7a1f94ebc41f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000929"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca nel log di controllo di Office 365

L'utente (o un altro amministratore) deve attivare la registrazione di controllo prima di iniziare la ricerca nel registro di controllo di Office 365. Quando la ricerca del registro di controllo nel centro sicurezza & Compliance è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni. Tuttavia, è possibile che l'organizzazione non desideri registrare e conservare i dati del log di controllo. In alternativa, è possibile utilizzare un'applicazione di sicurezza di terze parti e la gestione eventi (SIEM) per accedere ai dati di controllo. In questi casi, un amministratore globale può disattivare la ricerca del registro di controllo in Office 365.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione di Office 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
    > [!IMPORTANT]
    > Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo. Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel centro conformità di sicurezza &, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo. Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online. 
  
- Se si disattiva la ricerca del registro di controllo in Office 365, è comunque possibile utilizzare l'API di attività di gestione di Office 365 per accedere ai dati di controllo per l'organizzazione. La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca nel log di controllo utilizzando il Centro sicurezza & Compliance o quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Tuttavia, se l'utente ha autorizzato qualsiasi applicazione per accedere ai dati di controllo dell'organizzazione tramite l'API di attività di gestione di Office 365, tali applicazioni continueranno a funzionare. 
    
- Per istruzioni dettagliate sulla ricerca nel registro di controllo di Office 365, vedere [Search the audit log in the Security _AMP_ Compliance Center](search-the-audit-log-in-security-and-compliance.md).
    
## <a name="turn-on-audit-log-search"></a>Attiva ricerca log di controllo

È possibile utilizzare il Centro sicurezza & Compliance o PowerShell per abilitare la ricerca del registro di controllo in Office 365. Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo. Per abilitare la ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Utilizzare il Centro sicurezza & Compliance per abilitare la ricerca nel registro di controllo

1. Nel centro sicurezza & Compliance, andare alla **** \> **ricerca del registro di controllo**della ricerca.
    
2. Fare clic su **Avvia registrazione attività utente e amministratore**.
    
    ![Fare clic su Avvia registrazione attività utente e amministratore per attivare il controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Viene visualizzata una finestra di dialogo in cui viene indicato che l'attività dell'utente e dell'amministratore nell'organizzazione verrà registrata nel log di controllo di Office 365 e disponibile per la visualizzazione in un report. 
    
3. Fare clic su **Attiva**.
    
    Viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio di ore dopo il completamento della preparazione.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo

1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.
  
## <a name="turn-off-audit-log-search"></a>Disattiva la ricerca nel registro di controllo

Per disattivare la ricerca del registro di controllo, è necessario utilizzare Remote PowerShell connesso all'organizzazione di Exchange Online. Analogamente all'attivazione della ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online per disattivare la ricerca del registro di controllo.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo in Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata). Questa operazione può essere eseguita in due modi:
    
    - In PowerShell, eseguire il comando riportato di seguito:

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        Il valore della `False` proprietà _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata. 
    
    - Nel centro sicurezza & Compliance, andare alla ricerca nel **Registro di controllo**di **ricerca** \> e quindi fare clic su **Cerca**.
    
      Viene visualizzato un messaggio in cui viene indicato che la ricerca del registro di controllo non è attivata. 
    
      ![Se il controllo è disattivato, viene visualizzato un messaggio.](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
