---
title: Attivare il componente aggiuntivo Segnala messaggio
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Informazioni su come abilitare il componente aggiuntivo di report per Outlook e Outlook sul web, per i singoli utenti o l'intera organizzazione.
ms.openlocfilehash: f35899d3f0be9ee07cb6dae5c5fec40395948340
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706370"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="66616-103">Attivare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="66616-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="66616-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="66616-104">Overview</span></span>

<span data-ttu-id="66616-p101">Il componente aggiuntivo di report per Outlook e Outlook sul Web consente agli utenti di comunicare facilmente e-mail classificazioni non corrette, se attendibili o volontario, con Microsoft e consociate per l'analisi. Questi invii utilizzate da Microsoft per migliorare l'efficienza delle tecnologie di protezione della posta elettronica. Inoltre, se l'organizzazione utilizza [Protezione rischio avanzate di Office 365](office-365-atp.md) o [Business Intelligence di Office 365 rischio](office-365-ti.md), il componente aggiuntivo di report fornisce il team di protezione dell'organizzazione con informazioni utili, che è possibile utilizzare per esaminare e aggiornare criteri di protezione.</span><span class="sxs-lookup"><span data-stu-id="66616-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="66616-p102">Ad esempio, si supponga che le persone riportano una quantità elevata di messaggi di phishing. Nel [Dashboard di sicurezza](security-dashboard.md) e altri report le superfici di informazioni. Team di protezione dell'organizzazione possono utilizzare queste informazioni come indicazione che criteri anti-phishing potrebbero non essere aggiornate. In alternativa, se gli utenti sono report una quantità elevata di messaggi contrassegnati come posta indesiderata come posta non indesiderata tramite il componente aggiuntivo di report, team di protezione dell'organizzazione potrebbe essere necessario modificare [i criteri di protezione da posta indesiderati](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="66616-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="66616-112">Il componente aggiuntivo di report può essere utilizzato con la sottoscrizione a Office 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="66616-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="66616-113">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="66616-113">Outlook on the Web</span></span>
 - <span data-ttu-id="66616-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="66616-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="66616-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66616-115">Outlook 2016</span></span>
 - <span data-ttu-id="66616-116">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="66616-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="66616-117">Outlook inclusi in Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="66616-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="66616-118">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo di report per se stessi](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="66616-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="66616-p103">Se si è un amministratore globale di Office 365 o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization). Il componente aggiuntivo nel messaggio di Report è ora disponibile nella [Distribuzione centralizzata](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="66616-p103">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="66616-121">Ottenere il messaggio di rapporto componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="66616-121">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="66616-122">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), cercare il [componente aggiuntivo di report](https://appsource.microsoft.com/product/office/wa104381180).</span><span class="sxs-lookup"><span data-stu-id="66616-122">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="66616-123">Scegliere **ottenere subito**.</span><span class="sxs-lookup"><span data-stu-id="66616-123">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="66616-124">![Report messaggio - Scarica ora](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="66616-124">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="66616-p104">Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="66616-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="66616-127">Accedere alla posta elettronica di Office 365 utilizzando il proprio lavoro o scuola account (per l'utilizzo business) o l'account Microsoft (per utilizzo personale).</span><span class="sxs-lookup"><span data-stu-id="66616-127">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="66616-128">Dopo che il componente aggiuntivo è installato e attivato, si noterà icone riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="66616-128">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="66616-129">In Outlook l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66616-129">In Outlook the icon looks like this:</span></span> <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="66616-131">In Outlook Web App l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66616-131">In Outlook Web App the icon looks like this:</span></span><br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="66616-133">In una fase successiva, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="66616-133">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="66616-134">Ottenere e abilitare il componente aggiuntivo di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="66616-134">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66616-p105">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività. Inoltre, Exchange deve essere configurato per l'utilizzo dell'autenticazione OAuth per ulteriori informazioni, vedere [requisiti di Exchange (Centralized distribuzione dei componenti aggiuntivi)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span><span class="sxs-lookup"><span data-stu-id="66616-p105">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="66616-137">Passare alla [pagina di componenti aggiuntivi e servizi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nella nuova interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66616-137">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="66616-138">![Pagina servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="66616-138">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="66616-139">Scegliere **+ distribuzione componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="66616-139">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="66616-140">![Scegliere distribuzione di componenti aggiuntivi](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="66616-140">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="66616-141">Nella schermata nuovo componente aggiuntivo, esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66616-141">In the New Add-In screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="66616-142">![Nuovi componenti dettagli](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="66616-142">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="66616-143">Selezionare **desidera aggiungere un componente aggiuntivo da Office Store**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66616-143">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="66616-144">![Desidera aggiungere un nuovo componente aggiuntivo](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="66616-144">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="66616-145">Messaggio di Report e nell'elenco dei risultati, accanto al Report messaggio componente aggiuntivo di ricerca, scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="66616-145">Search for Report Message, and in the list of results, next to the Report Message Add-In, choose Add.</span></span><br/>![Ricerca di report e quindi fare clic su Aggiungi](media/NewAddInScreen3.png)<br/>
    
6. <span data-ttu-id="66616-147">Nella schermata del messaggio di Report, esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66616-147">On the Report Message screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="66616-148">![Rapporto dettagli del messaggio](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="66616-148">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="66616-149">Specificare le impostazioni predefinite di utente per Outlook e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66616-149">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="66616-150">![Segnalare le impostazioni predefinite di messaggio per Outlook](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="66616-150">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="66616-151">Specificare che ottiene il componente aggiuntivo di report e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66616-151">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="66616-152">![Componente aggiuntivo che ottiene il messaggio di Report](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="66616-152">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="66616-153">Si consiglia di [impostazione di una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span><span class="sxs-lookup"><span data-stu-id="66616-153">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="66616-p106">In base al quale è selezionata utilizzando la procedura guidata, gli utenti dell'organizzazione avranno il [componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibili. Gli utenti dell'organizzazione verranno visualizzato le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="66616-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="66616-156">In Outlook l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66616-156">In Outlook the icon looks like this:</span></span> <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="66616-158">In Outlook Web App l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="66616-158">In Outlook Web App the icon looks like this:</span></span><br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="66616-160">Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="66616-160">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66616-161">È necessario essere un amministratore di Exchange Online per eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="66616-161">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="66616-p107">È possibile impostare backup di una regola per ottenere una copia dei messaggi di posta elettronica segnalato dagli utenti nell'organizzazione. A tale scopo dopo avere scaricato e abilitato il componente aggiuntivo di report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66616-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="66616-164">Nell'interfaccia di amministrazione di Exchange, scegliere **flusso di posta** \> **regole**.</span><span class="sxs-lookup"><span data-stu-id="66616-164">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="66616-165">Scegliere **+** \> **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="66616-165">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="66616-166">Nella casella **nome** digitare un nome, ad esempio invii.</span><span class="sxs-lookup"><span data-stu-id="66616-166">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="66616-167">Nell'elenco **Applica questa regola se** , selezionare **l'indirizzo del destinatario include...**.</span><span class="sxs-lookup"><span data-stu-id="66616-167">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="66616-168">Nella schermata **specificare parole o frasi** , aggiungere `junk@office365.microsoft.com` e `phish@office365.microsoft.com`e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="66616-168">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="66616-169">![Specificare gli indirizzi di posta elettronica indesiderata e per attività di phishing per la regola](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="66616-169">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="66616-170">Nell'elenco **eseguire le operazioni seguenti...** scegliere **Ccn del messaggio per...**.</span><span class="sxs-lookup"><span data-stu-id="66616-170">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="66616-171">Aggiungere un amministratore globale, amministratore della sicurezza e/o lettore di sicurezza che deve ricevere una copia di ogni messaggio di posta elettronica che gli utenti di segnalare a Microsoft e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="66616-171">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="66616-172">![Aggiungere un amministratore globale o di protezione per la ricezione di una copia di ogni messaggio segnalata](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="66616-172">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="66616-173">Selezionare **Controlla questa regola con livello di gravità**e scegliere **medio**.</span><span class="sxs-lookup"><span data-stu-id="66616-173">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="66616-174">Nella casella **scegliere una modalità per la regola**, selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="66616-174">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="66616-175">![Impostare una regola per ottenere una copia di ogni messaggio segnalata](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="66616-175">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="66616-176">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="66616-176">Choose **Save**.</span></span> 
    
<span data-ttu-id="66616-p108">Con questa regola, ogni volta che qualcuno all'interno dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo di report, l'amministratore globale, amministratore della sicurezza e/o lettore di sicurezza riceverà una copia del messaggio. Queste informazioni possono consentono di configurare o modificare criteri, ad esempio i criteri di [Office 365 degli strumenti di analisi provvisoria collegamenti](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="66616-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="66616-179">Verificare o modificare le impostazioni per il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="66616-179">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="66616-180">È possibile esaminare e modificare le impostazioni predefinite per il rapporto messaggio componente aggiuntivo nella [pagina servizi e componenti aggiuntivi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span><span class="sxs-lookup"><span data-stu-id="66616-180">You can review and edit the default settings for the Report Message Add-In in the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="66616-181">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="66616-181">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="66616-182">Passare alla [pagina di componenti aggiuntivi e servizi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nella nuova interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66616-182">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="66616-183">![Pagina servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="66616-183">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="66616-184">Individuare e selezionare il componente aggiuntivo nel messaggio di Report.</span><span class="sxs-lookup"><span data-stu-id="66616-184">Find and select the Report Message Add-In.</span></span><br/>![Individuare e selezionare il componente aggiuntivo di report](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="66616-186">Nella schermata del messaggio di Report, esaminare e modificare le impostazioni nel modo appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66616-186">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![Impostazioni per il componente aggiuntivo di report](media/EditReportMessageAddIn.png)<br/> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="66616-188">Informazioni su come utilizzare il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="66616-188">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="66616-189">Vedere [utilizzo del componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="66616-189">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66616-190">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="66616-190">Related topics</span></span>

[<span data-ttu-id="66616-191">Usare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="66616-191">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="66616-192">Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="66616-192">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="66616-193">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="66616-193">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="66616-194">Utilizzare Esplora in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="66616-194">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

