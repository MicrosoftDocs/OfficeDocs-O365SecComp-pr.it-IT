---
title: Attivare il componente aggiuntivo Segnala messaggio
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Informazioni su come abilitare il componente aggiuntivo di report per Outlook e Outlook sul web, per i singoli utenti o l'intera organizzazione.
ms.openlocfilehash: 8c9853c78a42d6eecd0989475ef8f0a44345f812
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857264"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="ed165-103">Attivare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="ed165-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="ed165-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ed165-104">Overview</span></span>

<span data-ttu-id="ed165-p101">Il componente aggiuntivo di report per Outlook e Outlook sul Web consente agli utenti di comunicare facilmente e-mail classificazioni non corrette, se attendibili o volontario, con Microsoft e consociate per l'analisi. Questi invii utilizzate da Microsoft per migliorare l'efficienza delle tecnologie di protezione della posta elettronica. Inoltre, se l'organizzazione utilizza [Protezione rischio avanzate di Office 365](office-365-atp.md) o [Business Intelligence di Office 365 rischio](office-365-ti.md), il componente aggiuntivo di report fornisce il team di protezione dell'organizzazione con informazioni utili, che è possibile utilizzare per esaminare e aggiornare criteri di protezione.</span><span class="sxs-lookup"><span data-stu-id="ed165-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="ed165-p102">Ad esempio, si supponga che le persone riportano una quantità elevata di messaggi di phishing. Nel [Dashboard di sicurezza](security-dashboard.md) e altri report le superfici di informazioni. Team di protezione dell'organizzazione possono utilizzare queste informazioni come indicazione che criteri anti-phishing potrebbero non essere aggiornate. In alternativa, se gli utenti sono report una quantità elevata di messaggi contrassegnati come posta indesiderata come posta non indesiderata tramite il componente aggiuntivo di report, team di protezione dell'organizzazione potrebbe essere necessario modificare [i criteri di protezione da posta indesiderati](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ed165-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="ed165-112">Il componente aggiuntivo di report può essere utilizzato con la sottoscrizione a Office 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed165-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="ed165-113">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="ed165-113">Outlook on the Web</span></span>
 - <span data-ttu-id="ed165-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="ed165-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="ed165-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed165-115">Outlook 2016</span></span>
 - <span data-ttu-id="ed165-116">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="ed165-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="ed165-117">Outlook inclusi in Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="ed165-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="ed165-118">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo di report per se stessi](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="ed165-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="ed165-119">Se si è un amministratore di Exchange Online, è possibile [abilitare il componente aggiuntivo di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ed165-119">If you're an Exchange Online administrator, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="ed165-120">Ottenere il messaggio di rapporto componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="ed165-120">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="ed165-121">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), cercare il [componente aggiuntivo di report](https://appsource.microsoft.com/product/office/wa104381180).</span><span class="sxs-lookup"><span data-stu-id="ed165-121">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="ed165-122">Scegliere **ottenere subito**.</span><span class="sxs-lookup"><span data-stu-id="ed165-122">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="ed165-123">![Report messaggio - Scarica ora](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="ed165-123">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="ed165-p103">Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="ed165-p103">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="ed165-126">Accedere alla posta elettronica di Office 365 utilizzando il proprio lavoro o scuola account (per l'utilizzo business) o l'account Microsoft (per utilizzo personale).</span><span class="sxs-lookup"><span data-stu-id="ed165-126">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    

<span data-ttu-id="ed165-127">Dopo che il componente aggiuntivo è installato e attivato, si noterà icone riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="ed165-127">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="ed165-128">In Outlook l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ed165-128">In Outlook the icon looks like this:</span></span> <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="ed165-130">In Outlook Web App l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ed165-130">In Outlook Web App the icon looks like this:</span></span><br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="ed165-132">In una fase successiva, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="ed165-132">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="ed165-133">Ottenere e abilitare il componente aggiuntivo di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ed165-133">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed165-134">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="ed165-134">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="ed165-135">Accedere a [https://portal.office.com](https://portal.office.com) e accedere utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="ed165-135">Go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="ed165-136">Scegliere **amministrazione** passare al centro di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ed165-136">Choose **Admin** to go to the Admin center.</span></span> 
    
3. <span data-ttu-id="ed165-137">Scegliere **Admin Center** \> **Exchange** per accedere all'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ed165-137">Choose **Admin centers** \> **Exchange** to go to the Exchange admin center (EAC).</span></span> 
    
4. <span data-ttu-id="ed165-138">Scegliere **organizzazione** \> **componenti aggiuntivi**.</span><span class="sxs-lookup"><span data-stu-id="ed165-138">Choose **organization** \> **add-ins**.</span></span> 
    
5. <span data-ttu-id="ed165-139">Scegliere **+**  >  **aggiungere da Office Store**.</span><span class="sxs-lookup"><span data-stu-id="ed165-139">Choose **+** > **Add from the Office Store**.</span></span><br/><span data-ttu-id="ed165-140">![Scegliere Aggiungi da Office Store](media/EAC-Org-AddFromOfficeStore.png)</span><span class="sxs-lookup"><span data-stu-id="ed165-140">![Choose Add from the Office Store](media/EAC-Org-AddFromOfficeStore.png)</span></span><br/><span data-ttu-id="ed165-141">Office Store verrà aperta nel web browser.</span><span class="sxs-lookup"><span data-stu-id="ed165-141">This opens the Office Store in your web browser.</span></span>
    
6. <span data-ttu-id="ed165-142">Cercare di report.</span><span class="sxs-lookup"><span data-stu-id="ed165-142">Search for Report Message.</span></span><br/>![Cercare di report](media/ReportMessageSearchOfficeStore.png)<br/>
    
7. <span data-ttu-id="ed165-144">Nell'elenco delle **App** , selezionare **Di report**e quindi fare clic su **Ottenere IT adesso**.</span><span class="sxs-lookup"><span data-stu-id="ed165-144">In the **Apps** list, select **Report Message**, and then choose **GET IT NOW**.</span></span><br/><span data-ttu-id="ed165-145">![Scegliere GET IT ora](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="ed165-145">![Choose GET IT NOW](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
8. <span data-ttu-id="ed165-p104">Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="ed165-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
    ![Fare clic su Continua per accettare i termini e l'informativa sulla privacy](media/ReportMessageTermsAndConditions.png)
  
9. <span data-ttu-id="ed165-p105">Verrà visualizzata una procedura guidata che consentono di configurare le informazioni della revisione di componente aggiuntivo di report e scegliere **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="ed165-p105">A wizard opens to help you configure the Report Message add-in. Review the information, and choose **Next** to continue.</span></span><br/><span data-ttu-id="ed165-151">![Messaggio componente aggiuntivo Creazione guidata report per Office 365](media/ReportMessageAdminInstallUI.png)</span><span class="sxs-lookup"><span data-stu-id="ed165-151">![Report Message add-in wizard for Office 365](media/ReportMessageAdminInstallUI.png)</span></span><br/> 

10. <span data-ttu-id="ed165-152">Consente di specificare l'impostazione predefinita che si desidera che gli utenti per il componente aggiuntivo di report.</span><span class="sxs-lookup"><span data-stu-id="ed165-152">Specify the default setting you want users to have for the Report Message add-in.</span></span><br/>![Specificare le impostazioni predefinite per il componente aggiuntivo di report](media/ReportMessageUserOptionsAdminsSet.png)<br/>
    
11. <span data-ttu-id="ed165-154">Consente di specificare che ottiene il messaggio di Report di componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ed165-154">Specify who gets the Report Message add-in.</span></span> <br/>![Specifica che ottiene il messaggio di Report di componenti aggiuntivi](media/ReportMessageChooseWhoGetsItAdminSettings.png)<br/>

12. <span data-ttu-id="ed165-156">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="ed165-156">Choose **Save**.</span></span> <br/>
> [!TIP]
> <span data-ttu-id="ed165-157">Si consiglia di [impostazione di una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span><span class="sxs-lookup"><span data-stu-id="ed165-157">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="ed165-p106">In base al quale è selezionata utilizzando la procedura guidata, gli utenti dell'organizzazione avranno il [componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibili. Gli utenti dell'organizzazione verranno visualizzato le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed165-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="ed165-160">In Outlook l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ed165-160">In Outlook the icon looks like this:</span></span> <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="ed165-162">In Outlook Web App l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ed165-162">In Outlook Web App the icon looks like this:</span></span><br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="ed165-164">Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="ed165-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed165-165">È necessario essere un amministratore di Exchange Online per eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="ed165-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="ed165-p107">È possibile impostare backup di una regola per ottenere una copia dei messaggi di posta elettronica segnalato dagli utenti nell'organizzazione. A tale scopo dopo avere scaricato e abilitato il componente aggiuntivo di report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ed165-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="ed165-168">Amministrazione di Exchange, scegliere **flusso di posta** \> **regole**.</span><span class="sxs-lookup"><span data-stu-id="ed165-168">In the EAC, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="ed165-169">Scegliere **+** \> **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="ed165-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="ed165-170">Nella casella **nome** digitare un nome, ad esempio invii.</span><span class="sxs-lookup"><span data-stu-id="ed165-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="ed165-171">Nell'elenco **Applica questa regola se** , selezionare **l'indirizzo del destinatario include...**.</span><span class="sxs-lookup"><span data-stu-id="ed165-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="ed165-172">Nella schermata **specificare parole o frasi** , aggiungere junk@office365.microsoft.com e phish@office365.microsoft.com e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed165-172">In the **specify words or phrases** screen, add junk@office365.microsoft.com and phish@office365.microsoft.com, and then choose **OK**.</span></span> 
    
    ![Specificare gli indirizzi di posta elettronica indesiderata e per attività di phishing per la regola](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. <span data-ttu-id="ed165-174">Nell'elenco **eseguire le operazioni seguenti...** scegliere **Ccn del messaggio per...**.</span><span class="sxs-lookup"><span data-stu-id="ed165-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="ed165-175">Aggiungere un amministratore globale, amministratore della sicurezza e/o lettore di sicurezza che deve ricevere una copia di ogni messaggio di posta elettronica che gli utenti di segnalare a Microsoft e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed165-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span> 
    
    ![Aggiungere un amministratore globale o di protezione per la ricezione di una copia di ogni messaggio segnalata](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. <span data-ttu-id="ed165-177">Selezionare **Controlla questa regola con livello di gravità**e scegliere **medio**.</span><span class="sxs-lookup"><span data-stu-id="ed165-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="ed165-178">Nella casella **scegliere una modalità per la regola**, selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="ed165-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span> 
    
    ![Impostare una regola per ottenere una copia di ogni messaggio segnalata](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. <span data-ttu-id="ed165-180">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="ed165-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="ed165-p108">Con questa regola, ogni volta che qualcuno all'interno dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo di report, l'amministratore globale, amministratore della sicurezza e/o lettore di sicurezza riceverà una copia del messaggio. Queste informazioni possono consentono di configurare o modificare criteri, ad esempio i criteri di [Office 365 degli strumenti di analisi provvisoria collegamenti](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="ed165-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-the-default-settings-for-the-report-message-add-in"></a><span data-ttu-id="ed165-183">Visualizzare o modificare le impostazioni predefinite per il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="ed165-183">Review or edit the default settings for the Report Message add-in</span></span>

<span data-ttu-id="ed165-184">È possibile esaminare e modificare le impostazioni predefinite per il componente aggiuntivo di report tramite l'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ed165-184">You can review and edit the default settings for the Report Message add-in using the Admin Center.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ed165-185">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="ed165-185">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="ed165-p109">Se è stato appena installato il componente aggiuntivo di report per l'organizzazione, già sarà nella pagina servizi e componenti aggiuntivi. In caso contrario, Vai [qui](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) e accedere utilizzando l'account di lavoro o della scuola per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed165-p109">If you've just installed the Report Message add-in for your organization, you'll already be on the Services & add-ins page. Otherwise, go [here](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="ed165-188">Cercare **Di report**e quindi selezionare.</span><span class="sxs-lookup"><span data-stu-id="ed165-188">Search for **Report Message**, and then select it.</span></span><br/><span data-ttu-id="ed165-189">![Servizi e componenti aggiuntivi per Office 365](media/ReportMessage-o365servicesaddins.png)</span><span class="sxs-lookup"><span data-stu-id="ed165-189">![Services and add-ins for Office 365](media/ReportMessage-o365servicesaddins.png)</span></span><br/> 
    
3. <span data-ttu-id="ed165-190">Verrà visualizzato un riquadro che visualizza le impostazioni che sono state selezionate per il componente aggiuntivo di report durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ed165-190">A pane opens that displays the settings that were selected for the Report Message add-in during deployment.</span></span><br/>![Impostazioni per il componente aggiuntivo di report](media/ReportMessage-reviewaddinsettings.png)<br/> 

4. <span data-ttu-id="ed165-192">Esaminare e, se necessario, modificare le impostazioni per il componente aggiuntivo di report e quindi salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ed165-192">Review and if needed, edit settings for the Report Message add-in, and then save your changes.</span></span>
    
## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="ed165-193">Informazioni su come utilizzare il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="ed165-193">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="ed165-194">Vedere [utilizzo del componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="ed165-194">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed165-195">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ed165-195">Related topics</span></span>

[<span data-ttu-id="ed165-196">Usare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="ed165-196">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="ed165-197">Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="ed165-197">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="ed165-198">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="ed165-198">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="ed165-199">Utilizzare Esplora in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="ed165-199">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

