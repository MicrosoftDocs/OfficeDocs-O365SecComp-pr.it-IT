---
title: Attivare il componente aggiuntivo Segnala messaggio
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare il componente aggiuntivo per i messaggi di report per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: c184b7ac1baef297d65e6e93e4e7a085920d87b0
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341427"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="72144-103">Attivare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="72144-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="72144-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="72144-104">Overview</span></span>

<span data-ttu-id="72144-p101">Il componente aggiuntivo del messaggio di report per Outlook e Outlook sul Web consente agli utenti di segnalare facilmente messaggi di posta indesiderata, siano essi sicuri o dannosi, a Microsoft e ai suoi affiliati per l'analisi. Microsoft utilizza questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica. Inoltre, se l'organizzazione utilizza [office 365 Advanced Threat Protection](office-365-atp.md) o [Office 365 Threat Intelligence](office-365-ti.md), il componente aggiuntivo segnala messaggio fornisce al team di sicurezza dell'organizzazione informazioni utili che è possibile utilizzare per esaminare e aggiornare criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="72144-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="72144-p102">Si supponga, ad esempio, che le persone riferiscono un gran quantità di messaggi come phishing. Queste informazioni si riferiscono al [dashboard di sicurezza](security-dashboard.md) e ad altri report. Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri di protezione anti-phishing. In alternativa, se la gente segnala un gran quantità di messaggi che sono stati contrassegnati come posta indesiderata come non inDesiderata utilizzando il componente aggiuntivo segnala messaggio, il team di sicurezza dell'organizzazione potrebbe dover adeguare i criteri di protezione da [posta](configure-the-anti-spam-policies.md)indesiderata.</span><span class="sxs-lookup"><span data-stu-id="72144-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="72144-112">Il componente aggiuntivo segnala messaggio è compatibile con l'abbonamento a Office 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="72144-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="72144-113">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="72144-113">Outlook on the web</span></span>
 - <span data-ttu-id="72144-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="72144-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="72144-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72144-115">Outlook 2016</span></span>
 - <span data-ttu-id="72144-116">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="72144-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="72144-117">Outlook incluso con Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="72144-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="72144-p103">Il componente aggiuntivo del messaggio di report per Outlook e Outlook sul Web non è esattamente lo stesso del filtro della [posta](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)indesideraTa di Outlook, sebbene entrambi possano essere utilizzati per contrassegnare la posta elettronica come indesiderata, non indesiderata o tentativo di phishing. Il componente aggiuntivo segnala messaggio per Outlook e Outlook sul Web comunica a Microsoft la posta elettronica non classificata, mentre il filtro posta inDesiderata di Outlook viene utilizzato per organizzare i messaggi di posta elettronica nella cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="72144-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="72144-120">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo per i messaggi di report](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="72144-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="72144-p104">Se si è un amministratore globale di Office 365 o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo per i messaggi di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization). Il componente aggiuntivo segnala messaggio è ora disponibile tramite la [distribuzione centralizzata](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="72144-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="72144-123">Ottenere il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="72144-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="72144-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), cercare il [componente aggiuntivo](https://appsource.microsoft.com/product/office/wa104381180)per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="72144-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="72144-125">Scegliere **Get it now**.</span><span class="sxs-lookup"><span data-stu-id="72144-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="72144-126">![Segnala messaggio-ottienilo subito](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="72144-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="72144-p105">Esaminare le condizioni di utilizzo e i criteri di privacy. Scegliere **continue**.</span><span class="sxs-lookup"><span data-stu-id="72144-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="72144-129">Accedere a Office 365 utilizzando l'account aziendale o dell'Istituto di istruzione (per uso commerciale) o il proprio account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="72144-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="72144-130">Dopo aver installato e abilitato il componente aggiuntivo, vengono visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="72144-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="72144-131">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="72144-131">In Outlook, the icon looks like this:</span></span> <br/> ![Icona del componente aggiuntivo per i messaggi di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="72144-133">In Outlook sul Web (in precedenza noto come Outlook Web App), l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="72144-133">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![Icona del componente aggiuntivo messaggio di Outlook sul Web report](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="72144-135">Come passaggio successivo, informazioni su come [utilizzare il componente aggiuntivo per i messaggi di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="72144-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="72144-136">Ottenere e attivare il componente aggiuntivo per i messaggi di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="72144-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72144-p106">Per eseguire questa attività, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online. Inoltre, Exchange deve essere configurato per l'utilizzo dell'autenticazione OAuth per ulteriori informazioni, vedere [requisiti di Exchange (distribuzione centralizzata dei componenti aggiuntivi)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span><span class="sxs-lookup"><span data-stu-id="72144-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="72144-139">Passare alla pagina dei componenti aggiuntivi di [Servizi &](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72144-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="72144-140">![Pagina Servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="72144-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="72144-141">Scegliere **+ Distribuisci componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="72144-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="72144-142">![Scegliere Distribuisci componente aggiuntivo](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="72144-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="72144-143">Nella schermata **nuovo componente aggiuntivo** , esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="72144-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="72144-144">![Nuovi dettagli del componente aggiuntivo](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="72144-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="72144-145">Selezionare **desidero aggiungere un componente aggiuntivo da Office Store**e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="72144-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="72144-146">![Si desidera aggiungere un nuovo componente aggiuntivo](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="72144-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="72144-147">Cercare il **messaggio di report**e, nell'elenco dei risultati, accanto al **componente aggiuntivo segnala messaggio**, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="72144-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="72144-148">![Cercare il messaggio di rapporto e quindi scegliere Aggiungi](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="72144-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="72144-149">Nella schermata del **messaggio di report** , esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="72144-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="72144-150">![Dettagli del messaggio di report](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="72144-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="72144-151">Specificare le impostazioni predefinite per l'utente di Outlook e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="72144-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="72144-152">![Impostazioni predefinite dei messaggi di report per Outlook](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="72144-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="72144-153">Specificare chi riceve il componente aggiuntivo per i messaggi di report e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="72144-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="72144-154">![Chi ottiene il componente aggiuntivo per i messaggi di report](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="72144-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="72144-155">È consigliabile [impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span><span class="sxs-lookup"><span data-stu-id="72144-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="72144-p107">A seconda di cosa è stato selezionato quando si configura il componente aggiuntivo (passaggi 7-8 sopra), gli utenti dell'organizzazione disporranno del [componente aggiuntivo](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) per i messaggi di report disponibile. Gli utenti dell'organizzazione vedranno le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="72144-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="72144-158">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="72144-158">In Outlook, the icon looks like this:</span></span> <br/> ![Icona del componente aggiuntivo per i messaggi di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="72144-160">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="72144-160">In Outlook on the web, the icon looks like this:</span></span><br/>![Icona del componente aggiuntivo messaggio di Outlook sul Web report](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="72144-162">Quando si informa gli utenti sul componente aggiuntivo per i messaggi di report, includere un collegamento per [l'utilizzo del componente aggiuntivo per i messaggi di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="72144-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="72144-163">Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti</span><span class="sxs-lookup"><span data-stu-id="72144-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72144-164">Per eseguire questa attività, è necessario essere un amministratore di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="72144-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="72144-p108">È possibile configurare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti dell'organizzazione. Questa operazione viene eseguita dopo aver scaricato e abilitato il componente aggiuntivo per i messaggi di report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72144-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="72144-167">Nell'interfaccia di amministrazione di Exchange, scegliere **regole**del **flusso** \> di posta.</span><span class="sxs-lookup"><span data-stu-id="72144-167">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="72144-168">Scegliere **+** \> **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="72144-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="72144-169">Nella casella **nome** Digitare un nome, ad esempio invii.</span><span class="sxs-lookup"><span data-stu-id="72144-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="72144-170">Nell'elenco **applica la regola se** , scegliere **l'indirizzo del destinatario include...**.</span><span class="sxs-lookup"><span data-stu-id="72144-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="72144-171">Nella schermata **specificare parole o frasi** , aggiungere `junk@office365.microsoft.com` e `phish@office365.microsoft.com`quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="72144-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="72144-172">![Specificare gli indirizzi di posta indesiderata e phishing per la regola](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="72144-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="72144-173">Nell'elenco **fare quanto segue...** , scegliere **BCC il messaggio a...**.</span><span class="sxs-lookup"><span data-stu-id="72144-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="72144-174">Aggiungere un amministratore globale, un amministratore della sicurezza e/o un lettore di sicurezza che dovrebbe ricevere una copia di ogni messaggio di posta elettronica che gli utenti riferiscono a Microsoft e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="72144-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="72144-175">![Aggiungere un amministratore globale o di sicurezza per ricevere una copia di ogni messaggio segnalato](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="72144-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="72144-176">Selezionare **Controlla questa regola con livello di gravità**e scegliere **media**.</span><span class="sxs-lookup"><span data-stu-id="72144-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="72144-177">In **Scegli una modalità per questa regola**, scegliere **applica**.</span><span class="sxs-lookup"><span data-stu-id="72144-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="72144-178">![Impostare una regola per ottenere una copia di ogni messaggio segnalato](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="72144-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="72144-179">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="72144-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="72144-p109">Con questa regola sul posto, ogni volta che un utente dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo segnala messaggio, l'amministratore globale, l'amministratore della sicurezza e/o il lettore di sicurezza riceverà una copia del messaggio. Queste informazioni consentono di impostare o modificare i criteri, ad esempio i criteri di [collegamenti sicuri ATP di Office 365](atp-safe-links.md) o le impostazioni di protezione da [posta](anti-spam-protection.md) indesiderata.</span><span class="sxs-lookup"><span data-stu-id="72144-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="72144-182">Informazioni su come utilizzare il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="72144-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="72144-183">Per ulteriori informazioni, vedere [use the report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="72144-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="72144-184">Esaminare o modificare le impostazioni per il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="72144-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="72144-185">È possibile esaminare e modificare le impostazioni predefinite per il componente aggiuntivo dei messaggi di report nella [pagina dei componenti](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)aggiuntivi di &.</span><span class="sxs-lookup"><span data-stu-id="72144-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="72144-186">Per eseguire questa attività, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="72144-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="72144-187">Passare alla pagina dei componenti aggiuntivi di [Servizi &](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72144-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="72144-188">![Pagina Servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="72144-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="72144-189">Individuare e selezionare il componente aggiuntivo per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="72144-189">Find and select the Report Message add-in.</span></span><br/>![Individuare e selezionare il componente aggiuntivo per i messaggi di report](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="72144-191">Nella schermata del messaggio di report, esaminare e modificare le impostazioni appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72144-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![Impostazioni per il componente aggiuntivo per i messaggi di report](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="72144-193">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="72144-193">Related topics</span></span>

[<span data-ttu-id="72144-194">Usare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="72144-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="72144-195">Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="72144-195">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="72144-196">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="72144-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="72144-197">Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="72144-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  

