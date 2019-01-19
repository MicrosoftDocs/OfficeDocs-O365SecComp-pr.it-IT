---
title: Attivare il componente aggiuntivo Segnala messaggio
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Informazioni su come abilitare il componente aggiuntivo di report per Outlook e Outlook sul web, per i singoli utenti o l'intera organizzazione.
ms.openlocfilehash: 013145813e8feb3e7389f6248ee26195c1df3d08
ms.sourcegitcommit: 1169a5759b9c2336fbc89d4651daf29e556f62fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "28727870"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f5ab1-103">Attivare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="f5ab1-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="f5ab1-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f5ab1-104">Overview</span></span>

<span data-ttu-id="f5ab1-p101">Il componente aggiuntivo di report per Outlook e Outlook sul web consente agli utenti di comunicare facilmente e-mail classificazioni non corrette, se attendibili o volontario, con Microsoft e consociate per l'analisi. Questi invii utilizzate da Microsoft per migliorare l'efficienza delle tecnologie di protezione della posta elettronica. Inoltre, se l'organizzazione utilizza [Protezione rischio avanzate di Office 365](office-365-atp.md) o [Business Intelligence di Office 365 rischio](office-365-ti.md), il componente aggiuntivo di report fornisce il team di protezione dell'organizzazione con informazioni utili, che è possibile utilizzare per esaminare e aggiornare criteri di protezione.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="f5ab1-p102">Ad esempio, si supponga che le persone riportano una quantità elevata di messaggi di phishing. Nel [Dashboard di sicurezza](security-dashboard.md) e altri report le superfici di informazioni. Team di protezione dell'organizzazione possono utilizzare queste informazioni come indicazione che criteri anti-phishing potrebbero non essere aggiornate. In alternativa, se gli utenti sono report una quantità elevata di messaggi contrassegnati come posta indesiderata come posta non indesiderata tramite il componente aggiuntivo di report, team di protezione dell'organizzazione potrebbe essere necessario modificare [i criteri di protezione da posta indesiderati](configure-the-anti-spam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="f5ab1-112">Il componente aggiuntivo di report può essere utilizzato con la sottoscrizione a Office 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="f5ab1-113">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="f5ab1-113">Outlook on the web</span></span>
 - <span data-ttu-id="f5ab1-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="f5ab1-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="f5ab1-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5ab1-115">Outlook 2016</span></span>
 - <span data-ttu-id="f5ab1-116">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="f5ab1-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="f5ab1-117">Outlook inclusi in Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f5ab1-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="f5ab1-p103">Il componente aggiuntivo di report per Outlook e Outlook sul web è non esattamente la stessa funzione del [Filtro posta indesiderata di Outlook](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), sebbene entrambe può essere utilizzati per contrassegnare posta indesiderata, non indesiderata o un tentativo di phishing. Il componente aggiuntivo di report per Outlook e Outlook sul web invia una notifica Microsoft informazioni sulla posta elettronica classificazioni non corrette, mentre il filtro posta indesiderata di Outlook viene utilizzato per organizzare i messaggi di posta elettronica nella cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="f5ab1-120">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo di report per se stessi](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="f5ab1-p104">Se si è un amministratore globale di Office 365 o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization). Il componente aggiuntivo nel messaggio di Report è ora disponibile nella [Distribuzione centralizzata](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f5ab1-123">Ottenere il messaggio di rapporto componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="f5ab1-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f5ab1-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), cercare il [componente aggiuntivo di report](https://appsource.microsoft.com/product/office/wa104381180).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="f5ab1-125">Scegliere **ottenere subito**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="f5ab1-126">![Report messaggio - Scarica ora](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="f5ab1-p105">Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="f5ab1-129">Accedere a Office 365 utilizzando il proprio lavoro o scuola account (per l'utilizzo business) o l'account Microsoft (per utilizzo personale).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="f5ab1-130">Dopo che il componente aggiuntivo è installato e attivato, si noterà icone riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="f5ab1-131">In Outlook, l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-131">In Outlook, the icon looks like this:</span></span> <br/> ![Report sull'icona messaggio componente aggiuntivo per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="f5ab1-133">In Outlook Web App o Outlook sul web, l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-133">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Outlook su componente aggiuntivo di report icona](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="f5ab1-135">In una fase successiva, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f5ab1-136">Ottenere e abilitare il componente aggiuntivo di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f5ab1-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5ab1-p106">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività. Inoltre, Exchange deve essere configurato per l'utilizzo dell'autenticazione OAuth per ulteriori informazioni, vedere [requisiti di Exchange (Centralized distribuzione dei componenti aggiuntivi)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="f5ab1-139">Passare alla [pagina di componenti aggiuntivi & servizi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="f5ab1-140">![Pagina servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="f5ab1-141">Scegliere **+ distribuzione componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="f5ab1-142">![Scegliere distribuzione di componenti aggiuntivi](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="f5ab1-143">Nella schermata **Nuovo componente aggiuntivo** , esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="f5ab1-144">![Nuovi componenti dettagli](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="f5ab1-145">Selezionare **desidera aggiungere un componente aggiuntivo da Office Store**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="f5ab1-146">![Desidera aggiungere un nuovo componente aggiuntivo](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="f5ab1-147">La ricerca per **Il messaggio di Report**e nell'elenco dei risultati, accanto al **Componente aggiuntivo di Report messaggio**, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="f5ab1-148">![Ricerca di report e quindi fare clic su Aggiungi](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="f5ab1-149">Nella schermata del **Messaggio di Report** , esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="f5ab1-150">![Rapporto dettagli del messaggio](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="f5ab1-151">Specificare le impostazioni predefinite di utente per Outlook e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="f5ab1-152">![Segnalare le impostazioni predefinite di messaggio per Outlook](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="f5ab1-153">Specificare che ottiene il componente aggiuntivo di report e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="f5ab1-154">![Componente aggiuntivo che ottiene il messaggio di Report](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="f5ab1-155">Si consiglia di [impostazione di una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="f5ab1-p107">A seconda dell'opzione selezionata quando si configura il componente aggiuntivo (passaggi 7-8 sopra), gli utenti dell'organizzazione avranno il [componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibili. Gli utenti dell'organizzazione verranno visualizzato le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="f5ab1-158">In Outlook, l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-158">In Outlook, the icon looks like this:</span></span> <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="f5ab1-160">In Outlook Web App o Outlook sul web, l'icona simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f5ab1-160">In Outlook Web App (or Outlook on the web), the icon looks like this:</span></span><br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="f5ab1-162">Quando si avvisare gli utenti del componente aggiuntivo di report, includere un collegamento a [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="f5ab1-163">Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="f5ab1-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5ab1-164">È necessario essere un amministratore di Exchange Online per eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="f5ab1-p108">È possibile impostare backup di una regola per ottenere una copia dei messaggi di posta elettronica segnalato dagli utenti nell'organizzazione. A tale scopo dopo avere scaricato e abilitato il componente aggiuntivo di report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="f5ab1-167">Nell'interfaccia di amministrazione di Exchange, scegliere **flusso di posta** \> **regole**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-167">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="f5ab1-168">Scegliere **+** \> **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="f5ab1-169">Nella casella **nome** digitare un nome, ad esempio invii.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="f5ab1-170">Nell'elenco **Applica questa regola se** , selezionare **l'indirizzo del destinatario include...**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="f5ab1-171">Nella schermata **specificare parole o frasi** , aggiungere `junk@office365.microsoft.com` e `phish@office365.microsoft.com`e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="f5ab1-172">![Specificare gli indirizzi di posta elettronica indesiderata e per attività di phishing per la regola](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="f5ab1-173">Nell'elenco **eseguire le operazioni seguenti...** scegliere **Ccn del messaggio per...**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="f5ab1-174">Aggiungere un amministratore globale, amministratore della sicurezza e/o lettore di sicurezza che deve ricevere una copia di ogni messaggio di posta elettronica che gli utenti di segnalare a Microsoft e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="f5ab1-175">![Aggiungere un amministratore globale o di protezione per la ricezione di una copia di ogni messaggio segnalata](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="f5ab1-176">Selezionare **Controlla questa regola con livello di gravità**e scegliere **medio**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="f5ab1-177">Nella casella **scegliere una modalità per la regola**, selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="f5ab1-178">![Impostare una regola per ottenere una copia di ogni messaggio segnalata](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="f5ab1-179">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="f5ab1-p109">Con questa regola, ogni volta che qualcuno all'interno dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo di report, l'amministratore globale, amministratore della sicurezza e/o lettore di sicurezza riceverà una copia del messaggio. Queste informazioni consentono di configurare o modificare i criteri, ad esempio i criteri di [Office 365 degli strumenti di analisi provvisoria collegamenti](atp-safe-links.md) o le impostazioni di [protezione da posta indesiderata](anti-spam-protection.md) .</span><span class="sxs-lookup"><span data-stu-id="f5ab1-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f5ab1-182">Informazioni su come utilizzare il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="f5ab1-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f5ab1-183">Vedere [utilizzo del componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f5ab1-184">Verificare o modificare le impostazioni per il componente aggiuntivo di report</span><span class="sxs-lookup"><span data-stu-id="f5ab1-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="f5ab1-185">È possibile esaminare e modificare le impostazioni predefinite per il componente aggiuntivo di report nella [pagina Add-Ins & servizi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span><span class="sxs-lookup"><span data-stu-id="f5ab1-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f5ab1-186">È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="f5ab1-187">Passare alla [pagina di componenti aggiuntivi & servizi](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="f5ab1-188">![Pagina servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="f5ab1-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="f5ab1-189">Individuare e selezionare il componente aggiuntivo di report.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-189">Find and select the Report Message add-in.</span></span><br/>![Individuare e selezionare il componente aggiuntivo di report](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="f5ab1-191">Nella schermata del messaggio di Report, esaminare e modificare le impostazioni nel modo appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5ab1-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![Impostazioni per il componente aggiuntivo di report](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="f5ab1-193">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f5ab1-193">Related topics</span></span>

[<span data-ttu-id="f5ab1-194">Usare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="f5ab1-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="f5ab1-195">Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="f5ab1-195">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f5ab1-196">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="f5ab1-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="f5ab1-197">Utilizzare Esplora in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="f5ab1-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

