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
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: È possibile abilitare la funzionalità di ricerca del registro di controllo nel centro sicurezza &amp; e conformità di Office 365. Se si cambia idea, è possibile attivarlo in qualsiasi momento. Quando la ricerca del registro di controllo è disattivata, gli amministratori non possono eseguire ricerche nel log di controllo di Office 365 per l'attività dell'utente e dell'amministratore nell'organizzazione.
ms.openlocfilehash: f0532ae7ba205001d89164ac3f00822d14aa81cd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218006"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="80158-105">Abilitare o disabilitare la ricerca nel log di controllo di Office 365</span><span class="sxs-lookup"><span data-stu-id="80158-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="80158-p102">L'utente (o un altro amministratore) deve attivare la registrazione di controllo prima di iniziare la ricerca nel registro di controllo di Office 365. Quando la ricerca del registro di controllo nel centro &amp; sicurezza e conformità di Office 365 è attivata, l'attività dell'utente e dell'amministratore dell'organizzazione viene registrata nel registro di controllo e conservata per 90 giorni. Tuttavia, è possibile che l'organizzazione non desideri registrare e conservare i dati del log di controllo. In alternativa, è possibile utilizzare un'applicazione di sicurezza di terze parti e la gestione eventi (SIEM) per accedere ai dati di controllo. In questi casi, un amministratore globale può disattivare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="80158-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="80158-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="80158-111">Before you begin</span></span>

- <span data-ttu-id="80158-p103">È necessario essere assegnati al ruolo registri di controllo in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo nell'organizzazione di Office 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80158-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="80158-p104">Gli utenti devono disporre delle autorizzazioni in Exchange Online per abilitare o disabilitare la ricerca del registro di controllo. Se si assegnano gli utenti al ruolo registri di controllo nella pagina **autorizzazioni** nel &amp; Centro sicurezza e conformità, non sarà possibile abilitare o disabilitare la ricerca del registro di controllo. Ciò è dovuto al fatto che il cmdlet sottostante è un cmdlet di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80158-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="80158-p105">Se si disattiva la ricerca del registro di controllo in Office 365, è comunque possibile utilizzare l'API di attività di gestione di Office 365 per accedere ai dati di controllo per l'organizzazione. La disattivazione della ricerca del registro di controllo seguendo i passaggi descritti in questo articolo indica che non verranno restituiti risultati quando si esegue una ricerca &amp; nel log di controllo utilizzando il Centro sicurezza e conformità quando si utilizza il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Tuttavia, se l'utente ha autorizzato qualsiasi applicazione per accedere ai dati di controllo dell'organizzazione tramite l'API di attività di gestione di Office 365, tali applicazioni continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="80158-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="80158-121">Per istruzioni dettagliate sulla ricerca nel registro di controllo di Office 365, vedere [Search the audit log in the office 365 &amp; Security Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="80158-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="80158-122">Attiva ricerca log di controllo</span><span class="sxs-lookup"><span data-stu-id="80158-122">Turn on audit log search</span></span>

<span data-ttu-id="80158-p106">È possibile utilizzare il centro &amp; conformità di sicurezza o PowerShell per abilitare la ricerca del registro di controllo in Office 365. Dopo aver eseguito la ricerca nel registro di controllo, potrebbero essere necessarie diverse ore dopo aver attivato la ricerca del registro di controllo. Per abilitare la ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80158-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="80158-126">Utilizzare il centro &amp; sicurezza e conformità per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="80158-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="80158-127">Nel centro sicurezza &amp; e conformità, andare alla **ricerca nel registro di controllo**analisi \> di \*\*ricerca &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="80158-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="80158-128">Fare clic su **Avvia registrazione attività utente e amministratore**.</span><span class="sxs-lookup"><span data-stu-id="80158-128">Click **Start recording user and admin activities**.</span></span>
    
    ![Fare clic su Inizia registrazione delle attività utente e di amministrazione per attivare il controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="80158-130">Viene visualizzata una finestra di dialogo in cui viene indicato che l'attività dell'utente e dell'amministratore nell'organizzazione verrà registrata nel log di controllo di Office 365 e disponibile per la visualizzazione in un report.</span><span class="sxs-lookup"><span data-stu-id="80158-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="80158-131">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="80158-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="80158-132">Viene visualizzato un messaggio che indica che il registro di controllo viene preparato e che è possibile eseguire una ricerca in un paio di ore dopo il completamento della preparazione.</span><span class="sxs-lookup"><span data-stu-id="80158-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="80158-133">Utilizzo di PowerShell per abilitare la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="80158-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="80158-134">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="80158-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="80158-135">Eseguire il seguente comando di PowerShell per abilitare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="80158-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="80158-136">Viene visualizzato un messaggio in cui viene indicato che potrebbe essere necessario fino a 60 minuti per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="80158-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="80158-137">Disattiva la ricerca nel registro di controllo</span><span class="sxs-lookup"><span data-stu-id="80158-137">Turn off audit log search</span></span>

<span data-ttu-id="80158-p107">Per disattivare la ricerca del registro di controllo, è necessario utilizzare Remote PowerShell connesso all'organizzazione di Exchange Online. Analogamente all'attivazione della ricerca del registro di controllo, è necessario assegnare il ruolo registri di controllo in Exchange Online per disattivare la ricerca del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="80158-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="80158-140">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="80158-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="80158-141">Eseguire il seguente comando di PowerShell per disattivare la ricerca del registro di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="80158-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="80158-p108">Dopo un po' di tempo, verificare che la ricerca del registro di controllo sia disattivata (disattivata). È possibile eseguire questa operazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="80158-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="80158-144">In PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="80158-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="80158-145">Il valore della `False` proprietà _UnifiedAuditLogIngestionEnabled_ indica che la ricerca del registro di controllo è disattivata.</span><span class="sxs-lookup"><span data-stu-id="80158-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="80158-146">Nel centro sicurezza &amp; e conformità, andare alla ricerca nel registro di \> **controllo** \*\*analisi di ricerca &amp; \*\* e quindi fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="80158-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="80158-147">Viene visualizzato un messaggio in cui viene indicato che la ricerca del registro di controllo non è attivata.</span><span class="sxs-lookup"><span data-stu-id="80158-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![Un messaggio viene dispagato se il controllo è disattivato](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
