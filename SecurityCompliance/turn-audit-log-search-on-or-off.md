---
title: Abilitare o disabilitare la ricerca nel log di controllo di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: È possibile attivare la funzionalità di ricerca del Registro di controllo in Office 365 Security &amp; centro conformità. Se si modifica è presente, è possibile attivare se sono disattivati in qualsiasi momento. Durante la ricerca dei registri di controllo è disattivato, gli amministratori non possono ricerca nel Registro di controllo di Office 365 per l'attività di amministrazione e utente nell'organizzazione.
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530815"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>Abilitare o disabilitare la ricerca nel log di controllo di Office 365

Utente (o un'altra amministrazione) è necessario attivare registrazione di controllo prima di iniziare la ricerca nel Registro di controllo di Office 365. Controllare se le ricerche log in Office 365 Security &amp; centro conformità è attivata, attività di amministrazione e utente dall'organizzazione viene registrato nel Registro di controllo e conservati per 90 giorni. Tuttavia, l'organizzazione non possibile registrare e mantenere i dati dei registri di controllo. O si stia utilizzando un'applicazione di gestione (SIEM) eventi e informazioni di sicurezza di terze parti per accedere ai dati di controllo. In questi casi, un amministratore globale è possibile disattivare la ricerca dei registri di controllo in Office 365.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnato il ruolo registri di controllo di Exchange Online per attivare o disattivare la ricerca dei registri di controllo nella propria organizzazione Office 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli di gestione della conformità e la gestione dell'organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in linea di Exchange. 
    
    > [!IMPORTANT]
    > Gli utenti devono disporre delle autorizzazioni di Exchange Online per attivare o disattivare la ricerca dei registri di controllo. Se si assegna agli utenti il ruolo registri di controllo nella pagina **autorizzazioni** di sicurezza &amp; centro conformità, non saranno in grado di attivare o disattivare la ricerca dei registri di controllo. Ciò avviene perché il cmdlet sottostante è un cmdlet di Exchange Online. 
  
- Se si disattiva la ricerca dei registri di controllo in Office 365, è possibile utilizzare ancora l'API di Office 365 Gestione attività per accedere a dati di controllo per l'organizzazione. Disattivazione ricerca dei registri di controllo seguendo i passaggi descritti in questo articolo significa che, non sarà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando la sicurezza &amp; centro conformità o quando si esegue il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Tuttavia, se si è autorizzato qualsiasi applicazione per accedere ai dati di controllo dell'organizzazione tramite l'API di Office 365 Gestione attività, le applicazioni continueranno a funzionare. 
    
- Per istruzioni dettagliate sul processo di ricerca di Office 365 Registro di controllo, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).
    
## <a name="turn-on-audit-log-search"></a>Attivare la ricerca dei registri di controllo

È possibile utilizzare la sicurezza &amp; centro conformità o PowerShell per attivare la ricerca dei registri di controllo in Office 365. Potrebbe richiedere diverse ore dopo l'attivazione della ricerca dei registri di controllo prima che è possibile restituire risultati quando si esegue una ricerca nel Registro di controllo. È necessario essere assegnato il ruolo registri di controllo di Exchange Online per attivare la ricerca dei registri di controllo.
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a>Utilizzare la protezione &amp; centro conformità per attivare la ricerca dei registri di controllo

1. In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca dei registri di controllo**.
    
2. Fare clic su **Avvia registrazione utente e le attività di amministrazione**.
    
    ![Fare clic su Inizia registrazione delle attività utente e di amministrazione per attivare il controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    Viene visualizzata una finestra di dialogo che informa l'utente e all'attività di amministrazione dell'organizzazione registrato nel Registro di controllo di Office 365 e da disponibili per la visualizzazione in un report. 
    
3. Fare clic su **Attiva**.
    
    Viene visualizzato un messaggio che informa che il Registro di controllo per la preparazione e che è possibile eseguire una ricerca di due ore dopo aver completata la preparazione.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Utilizzare PowerShell per attivare la ricerca dei registri di controllo

1. [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per attivare la ricerca dei registri di controllo in Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Viene visualizzato un messaggio che informa che potrebbero richiedere fino a 60 minuti rendere effettive le modifiche.
  
## <a name="turn-off-audit-log-search"></a>Disattivare la ricerca dei registri di controllo

È necessario utilizzare remote PowerShell connessa all'organizzazione Exchange Online per disattivare la ricerca dei registri di controllo. Analogamente ai attivazione della ricerca dei registri di controllo, è necessario essere assegnato il ruolo registri di controllo di Exchange Online per disattivare la ricerca dei registri di controllo.
  
1. [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Eseguire il seguente comando di PowerShell per disattivare la ricerca dei registri di controllo in Office 365.
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Dopo aver eseguito un po' di tempo, verificare che le ricerche del Registro di controllo sono disattivata (disattivata). Esistono due modi per eseguire questa operazione:
    
    - In PowerShell, utilizzare il comando seguente:

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        Il valore di `False` per _UnifiedAuditLogIngestionEnabled_ proprietà indica che le ricerche del Registro di controllo sono disattivata. 
    
    - In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca dei registri di controllo**e quindi fare clic su **Cerca**.
    
      Viene visualizzato un messaggio indicante che la ricerca del Registro di controllo non è attivata. 
    
      ![Dispayed è un messaggio se il controllo è disattivato](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
