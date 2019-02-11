---
title: Gestire le app di OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: App OAuth in Office 365 Cloud App protezione consentono di gestire le app che gli utenti di scaricare da utilizzare con i dati di Office 365
ms.openlocfilehash: ae32e3c6b15f4ad4794a3dd08c3992adaeba655c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603687"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="e33b2-103">Gestire le app di OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e33b2-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="e33b2-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e33b2-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="e33b2-105">Pianificazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e33b2-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="e33b2-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="e33b2-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="e33b2-107">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="e33b2-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e33b2-108">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="e33b2-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e33b2-109">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="e33b2-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e33b2-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="e33b2-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e33b2-111">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="e33b2-111">You are here!</span></span>  <br/> [<span data-ttu-id="e33b2-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e33b2-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="e33b2-p101">Persone amare App e vengono scaricati spesso, soprattutto delle applicazioni che utenti interazione utente verranno risparmiare tempo e rendere più semplice ottenere il proprio lavoro o scuola informazioni. Alcune applicazioni potenzialmente potrebbero comportare rischi di protezione dell'organizzazione, a seconda delle informazioni che accedono e modalità di gestione di tali informazioni. Con [Office 365 Cloud App protezione](office-365-cas-overview.md), in caso di un amministratore globale o di sicurezza, è possibile gestire App OAuth per l'organizzazione. È possibile visualizzare le persone App utilizza con Office 365 dati, quali autorizzazioni tali applicazioni hanno e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="e33b2-117">In questo articolo viene descritto dove è possibile per gestire le app OAuth, come approvare, escludere o un'app di report e come creare una query di app.</span><span class="sxs-lookup"><span data-stu-id="e33b2-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="e33b2-118">Come trovare la pagina di App gestire OAuth</span><span class="sxs-lookup"><span data-stu-id="e33b2-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="e33b2-p102">OAuth App vengono gestite nel portale di Office 365 Cloud App sicurezza. È necessario essere un amministratore globale o sicurezza per eseguire l'attività seguente. Per informazioni su ulteriori, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e33b2-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="e33b2-122">Accedere al portale di protezione di applicazione Cloud ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e33b2-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="e33b2-123">Scegliere **indagare** \> **apps OAuth**.</span><span class="sxs-lookup"><span data-stu-id="e33b2-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="e33b2-124">![Nel portale di accesso client di Office 365, selezionare indagare.](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="e33b2-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="e33b2-125">Verrà visualizzato nella pagina Gestisci OAuth App</span><span class="sxs-lookup"><span data-stu-id="e33b2-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="e33b2-126">Nella tabella seguente vengono descritti i controlli e le opzioni disponibili nella pagina Gestisci OAuth app.</span><span class="sxs-lookup"><span data-stu-id="e33b2-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="e33b2-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e33b2-127">**Item**</span></span>|<span data-ttu-id="e33b2-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e33b2-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e33b2-129">Base icona nella barra delle applicazioni query</span><span class="sxs-lookup"><span data-stu-id="e33b2-129">Basic icon in the app query bar</span></span>  <br/> ![Icona che indica la visualizzazione query di base per l'esecuzione di query](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="e33b2-131">Selezionare questa opzione per passare alla visualizzazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="e33b2-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="e33b2-132">(Se viene visualizzata **base**, si utilizza la visualizzazione avanzata)</span><span class="sxs-lookup"><span data-stu-id="e33b2-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="e33b2-133">Icona avanzata nella barra delle applicazioni query</span><span class="sxs-lookup"><span data-stu-id="e33b2-133">Advanced icon in the app query bar</span></span>  <br/> ![Icona che indica di visualizzazione della query avanzate per l'esecuzione di query](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="e33b2-135">Selezionare questa opzione per passare alla visualizzazione di base.</span><span class="sxs-lookup"><span data-stu-id="e33b2-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="e33b2-136">(Se viene visualizzata **Avanzate**, si utilizza la visualizzazione di base.)</span><span class="sxs-lookup"><span data-stu-id="e33b2-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="e33b2-137">Aprire o chiudere tutti i dettagli delle icone app</span><span class="sxs-lookup"><span data-stu-id="e33b2-137">Open or close all details icon in the app list</span></span>  <br/> ![Fare clic su questa icona per aprire o chiudere tutti i dettagli di tutte le app](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="e33b2-139">Selezionare questa icona per visualizzare più o meno informazioni dettagliate su ogni app.</span><span class="sxs-lookup"><span data-stu-id="e33b2-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="e33b2-140">Esporta l'icona nell'elenco app</span><span class="sxs-lookup"><span data-stu-id="e33b2-140">Export icon in the app list</span></span>  <br/> ![Fare clic su questa icona per esportare un file csv di tutte le app](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="e33b2-142">Selezionare questa icona per esportare un file CSV contenente un elenco delle App, numero di utenti per ogni applicazione, le autorizzazioni associate le app, il livello di autorizzazioni, allo stato delle app, e Usa il livello di community.</span><span class="sxs-lookup"><span data-stu-id="e33b2-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="e33b2-143">Name</span><span class="sxs-lookup"><span data-stu-id="e33b2-143">Name</span></span>  <br/> |<span data-ttu-id="e33b2-p103">Utilizzare per visualizzare il nome di una selezione di App, il nome per visualizzare ulteriori informazioni, ad esempio la descrizione, publisher, sito Web app e ID app.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p103">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="e33b2-146">Autorizzato da</span><span class="sxs-lookup"><span data-stu-id="e33b2-146">Authorized by</span></span>  <br/> |<span data-ttu-id="e33b2-p104">Questa scheda per visualizzare il numero di utenti è autorizzati a un'applicazione di accedere al proprio account di Office 365. Selezionare il numero di visualizzare ulteriori informazioni, ad esempio un elenco di account utente.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p104">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="e33b2-149">Livello di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e33b2-149">Permissions Level</span></span>  <br/> ![Icona che indica il livello di permisiions per un'applicazione](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="e33b2-p105">Questa scheda per visualizzare il tipo di accesso un'app sia ai dati di Office 365. Livelli di autorizzazioni indicano **bassa**, **Media**o **alta**, in **basso** potrebbe indicare che l'app accede solo profili e il nome dell'utente. Selezionare il livello di visualizzare ulteriori informazioni, ad esempio le autorizzazioni concesse per le app, l'utilizzo di community e attività correlati nel [Registro di Governance](suspend-or-restore-an-account-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="e33b2-p105">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="e33b2-154">Ultima autorizzato</span><span class="sxs-lookup"><span data-stu-id="e33b2-154">Last authorized</span></span> <br/> |<span data-ttu-id="e33b2-155">Questa scheda per visualizzare la data e ora che un'app OAuth ultimo è stata autorizzata ad accedere i dati dell'organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="e33b2-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="e33b2-156">Azioni</span><span class="sxs-lookup"><span data-stu-id="e33b2-156">Actions</span></span><br/>![App OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="e33b2-158">Utilizzare questa opzione per visualizzare o per contrassegnare un'applicazione come approvato o Banned, segnalare un'app OAuth a Microsoft oppure lasciare come indeterminato.</span><span class="sxs-lookup"><span data-stu-id="e33b2-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="e33b2-159">Contrassegnare un'applicazione come approvati</span><span class="sxs-lookup"><span data-stu-id="e33b2-159">Mark an app as approved</span></span>

<span data-ttu-id="e33b2-160">Nella pagina **applicazioni di gestire OAuth** , individuare l'app che si desidera approvare e scegliere l'icona **app contrassegna come approvati** .</span><span class="sxs-lookup"><span data-stu-id="e33b2-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![Scegliere l'app contrassegna come icona approvata](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="e33b2-162">L'icona viene verde e l'applicazione viene approvata per tutti gli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e33b2-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e33b2-p106">Quando si contrassegna un'app come approvati, non esiste alcun effetto sull'utente finale. Contrassegno visivamente le app approvate consente di separarli da applicazioni che non sono state implementate ancora.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p106">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="e33b2-165">Escludere un'app</span><span class="sxs-lookup"><span data-stu-id="e33b2-165">Ban an app</span></span>

1. <span data-ttu-id="e33b2-166">Nella pagina **applicazioni di gestire OAuth** , individuare l'app che si desidera escludere e scegliere l'icona **vietata app contrassegna come** .</span><span class="sxs-lookup"><span data-stu-id="e33b2-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="e33b2-167">![Scegliere l'app contrassegna come icona da escludere](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="e33b2-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="e33b2-p107">Nella finestra di messaggio di notifica, mantenere il testo esistente invariata o personalizzare il testo. Scegliere se si desidera informare gli utenti che è stata vietata la propria applicazione.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p107">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![Il modello di posta elettronica per un'applicazione da escludere](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="e33b2-171">Scegliere **divieto app**.</span><span class="sxs-lookup"><span data-stu-id="e33b2-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="e33b2-172">Segnalare un'app OAuth a Microsoft</span><span class="sxs-lookup"><span data-stu-id="e33b2-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="e33b2-173">Se si desidera inviare un'app OAuth a Microsoft per l'analisi, è possibile segnalare che app.</span><span class="sxs-lookup"><span data-stu-id="e33b2-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="e33b2-174">Nella pagina **applicazioni di gestire OAuth** , individuare l'app che si desidera inviare per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e33b2-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="e33b2-175">Fare clic sui puntini di sospensione verticale e quindi fare clic su **Report app....**.</span><span class="sxs-lookup"><span data-stu-id="e33b2-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="e33b2-176">![Segnala un'app OAuth](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="e33b2-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="e33b2-p108">Nella finestra di dialogo **Report l'app** , utilizzare l'elenco a discesa per indicare il problema. Per impostazione predefinita, **questa applicazione è dannosa** viene selezionata. Tuttavia, è possibile scegliere una delle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e33b2-p108">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="e33b2-180">![Segnala un'app OAuth](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="e33b2-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="e33b2-181">(Scelta consigliata) Mantenere l'opzione per contattare l'utente selezionato e verificare l'indirizzo di posta elettronica elencato (o modifica).</span><span class="sxs-lookup"><span data-stu-id="e33b2-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="e33b2-182">Scegliere **Submit**.</span><span class="sxs-lookup"><span data-stu-id="e33b2-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="e33b2-183">Creare una query di app</span><span class="sxs-lookup"><span data-stu-id="e33b2-183">Create an app query</span></span>

<span data-ttu-id="e33b2-184">È consigliabile utilizzare la visualizzazione avanzata, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e33b2-184">We recommend using the Advanced view, which looks like this:</span></span> 

![Visualizzazione avanzata](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="e33b2-p109">Nella barra di query delle applicazioni, se viene visualizzata **Avanzate**, si utilizza la visualizzazione di base. Fare clic su **Avanzate** per passare alla visualizzazione avanzata (o toccare).</span><span class="sxs-lookup"><span data-stu-id="e33b2-p109">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![Visualizzazione di base](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="e33b2-189">Nella barra di query, utilizzare l'elenco **Selezionare un filtro** per scegliere un'opzione.</span><span class="sxs-lookup"><span data-stu-id="e33b2-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="e33b2-190">**App** App con determinati nomi</span><span class="sxs-lookup"><span data-stu-id="e33b2-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="e33b2-191">**Stato delle App** Applicazioni in base al proprio stato (approvato, Banned o elementi indeterminati)</span><span class="sxs-lookup"><span data-stu-id="e33b2-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="e33b2-192">**Utilizzare community** App basato sulla community di utilizzare i livelli (Rare, Uncommon o comune)</span><span class="sxs-lookup"><span data-stu-id="e33b2-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="e33b2-193">**Livello di autorizzazione** App basato su determinati livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e33b2-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="e33b2-194">**Autorizzazioni** App che richiedono autorizzazioni specifiche</span><span class="sxs-lookup"><span data-stu-id="e33b2-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="e33b2-195">**Server di pubblicazione**  App da determinati autori</span><span class="sxs-lookup"><span data-stu-id="e33b2-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="e33b2-196">**Utente** Applicazioni che un determinato utente autorizzato</span><span class="sxs-lookup"><span data-stu-id="e33b2-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="e33b2-197">Selezionare **è uguale a** o **diverso**e quindi specificare un valore per il filtro.</span><span class="sxs-lookup"><span data-stu-id="e33b2-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="e33b2-198">Per aggiungere ulteriori filtri, selezionare il segno di addizione (</span><span class="sxs-lookup"><span data-stu-id="e33b2-198">To add more filters, select the plus sign (</span></span>![Aggiungere un'icona del filtro per eseguire query sulle App](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="e33b2-200">) e quindi ripetere i passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="e33b2-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="e33b2-201">Per rimuovere un filtro, selezionare il x (</span><span class="sxs-lookup"><span data-stu-id="e33b2-201">To remove a filter, select the x (</span></span>![Rimuovere un'icona del filtro per eseguire query sulle App](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="e33b2-203">) accanto al nome di un filtro.</span><span class="sxs-lookup"><span data-stu-id="e33b2-203">) next to a filter name.</span></span>
    
<span data-ttu-id="e33b2-204">Vengono applicati automaticamente i filtri e l'elenco di applicazioni viene aggiornata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e33b2-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e33b2-205">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e33b2-205">Next steps</span></span>

- [<span data-ttu-id="e33b2-206">Leggere ed eseguire l'azione gli avvisi</span><span class="sxs-lookup"><span data-stu-id="e33b2-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="e33b2-207">Esaminare i [registri di traffico Web e le origini dati per la protezione di Office 365 Cloud App](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="e33b2-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="e33b2-208">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="e33b2-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

