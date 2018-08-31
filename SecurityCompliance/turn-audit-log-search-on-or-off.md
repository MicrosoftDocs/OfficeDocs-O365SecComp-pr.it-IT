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
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="25245-105">Abilitare o disabilitare la ricerca nel log di controllo di Office 365</span><span class="sxs-lookup"><span data-stu-id="25245-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="25245-p102">Utente (o un'altra amministrazione) è necessario attivare registrazione di controllo prima di iniziare la ricerca nel Registro di controllo di Office 365. Controllare se le ricerche log in Office 365 Security &amp; centro conformità è attivata, attività di amministrazione e utente dall'organizzazione viene registrato nel Registro di controllo e conservati per 90 giorni. Tuttavia, l'organizzazione non possibile registrare e mantenere i dati dei registri di controllo. O si stia utilizzando un'applicazione di gestione (SIEM) eventi e informazioni di sicurezza di terze parti per accedere ai dati di controllo. In questi casi, un amministratore globale è possibile disattivare la ricerca dei registri di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="25245-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="25245-111">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="25245-111">Before you begin</span></span>

- <span data-ttu-id="25245-p103">È necessario essere assegnato il ruolo registri di controllo di Exchange Online per attivare o disattivare la ricerca dei registri di controllo nella propria organizzazione Office 365. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli di gestione della conformità e la gestione dell'organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 sono membri del gruppo di ruoli Gestione organizzazione in linea di Exchange.</span><span class="sxs-lookup"><span data-stu-id="25245-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="25245-p104">Gli utenti devono disporre delle autorizzazioni di Exchange Online per attivare o disattivare la ricerca dei registri di controllo. Se si assegna agli utenti il ruolo registri di controllo nella pagina **autorizzazioni** di sicurezza &amp; centro conformità, non saranno in grado di attivare o disattivare la ricerca dei registri di controllo. Ciò avviene perché il cmdlet sottostante è un cmdlet di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="25245-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="25245-p105">Se si disattiva la ricerca dei registri di controllo in Office 365, è possibile utilizzare ancora l'API di Office 365 Gestione attività per accedere a dati di controllo per l'organizzazione. Disattivazione ricerca dei registri di controllo seguendo i passaggi descritti in questo articolo significa che, non sarà restituito alcun risultato quando si esegue una ricerca nel log di controllo utilizzando la sicurezza &amp; centro conformità o quando si esegue il cmdlet **Search-UnifiedAuditLog** in Exchange Online PowerShell. Tuttavia, se si è autorizzato qualsiasi applicazione per accedere ai dati di controllo dell'organizzazione tramite l'API di Office 365 Gestione attività, le applicazioni continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="25245-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="25245-121">Per istruzioni dettagliate sul processo di ricerca di Office 365 Registro di controllo, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="25245-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="25245-122">Attivare la ricerca dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="25245-122">Turn on audit log search</span></span>

<span data-ttu-id="25245-p106">È possibile utilizzare la sicurezza &amp; centro conformità o PowerShell per attivare la ricerca dei registri di controllo in Office 365. Potrebbe richiedere diverse ore dopo l'attivazione della ricerca dei registri di controllo prima che è possibile restituire risultati quando si esegue una ricerca nel Registro di controllo. È necessario essere assegnato il ruolo registri di controllo di Exchange Online per attivare la ricerca dei registri di controllo.</span><span class="sxs-lookup"><span data-stu-id="25245-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="25245-126">Utilizzare la protezione &amp; centro conformità per attivare la ricerca dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="25245-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="25245-127">In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca dei registri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="25245-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="25245-128">Fare clic su **Avvia registrazione utente e le attività di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="25245-128">Click **Start recording user and admin activities**.</span></span>
    
    ![Fare clic su Inizia registrazione delle attività utente e di amministrazione per attivare il controllo](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="25245-130">Viene visualizzata una finestra di dialogo che informa l'utente e all'attività di amministrazione dell'organizzazione registrato nel Registro di controllo di Office 365 e da disponibili per la visualizzazione in un report.</span><span class="sxs-lookup"><span data-stu-id="25245-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="25245-131">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="25245-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="25245-132">Viene visualizzato un messaggio che informa che il Registro di controllo per la preparazione e che è possibile eseguire una ricerca di due ore dopo aver completata la preparazione.</span><span class="sxs-lookup"><span data-stu-id="25245-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="25245-133">Utilizzare PowerShell per attivare la ricerca dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="25245-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="25245-134">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="25245-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="25245-135">Eseguire il seguente comando di PowerShell per attivare la ricerca dei registri di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="25245-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="25245-136">Viene visualizzato un messaggio che informa che potrebbero richiedere fino a 60 minuti rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="25245-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="25245-137">Disattivare la ricerca dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="25245-137">Turn off audit log search</span></span>

<span data-ttu-id="25245-p107">È necessario utilizzare remote PowerShell connessa all'organizzazione Exchange Online per disattivare la ricerca dei registri di controllo. Analogamente ai attivazione della ricerca dei registri di controllo, è necessario essere assegnato il ruolo registri di controllo di Exchange Online per disattivare la ricerca dei registri di controllo.</span><span class="sxs-lookup"><span data-stu-id="25245-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="25245-140">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="25245-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="25245-141">Eseguire il seguente comando di PowerShell per disattivare la ricerca dei registri di controllo in Office 365.</span><span class="sxs-lookup"><span data-stu-id="25245-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="25245-p108">Dopo aver eseguito un po' di tempo, verificare che le ricerche del Registro di controllo sono disattivata (disattivata). Esistono due modi per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="25245-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="25245-144">In PowerShell, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="25245-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="25245-145">Il valore di `False` per _UnifiedAuditLogIngestionEnabled_ proprietà indica che le ricerche del Registro di controllo sono disattivata.</span><span class="sxs-lookup"><span data-stu-id="25245-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="25245-146">In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca dei registri di controllo**e quindi fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="25245-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="25245-147">Viene visualizzato un messaggio indicante che la ricerca del Registro di controllo non è attivata.</span><span class="sxs-lookup"><span data-stu-id="25245-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![Dispayed è un messaggio se il controllo è disattivato](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
