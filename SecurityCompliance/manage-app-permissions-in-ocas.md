---
title: Gestire le autorizzazioni dell'app con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Autorizzazioni delle App in Office 365 Cloud App protezione consentono di gestire le app che gli utenti di scaricare da utilizzare con i dati di Office 365
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531191"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a><span data-ttu-id="f583f-103">Gestire le autorizzazioni dell'app con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f583f-103">Manage app permissions using Office 365 Cloud App Security</span></span>

<span data-ttu-id="f583f-104">Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f583f-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="f583f-105">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="f583f-105">****Evaluation** \>**</span></span>|<span data-ttu-id="f583f-106">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="f583f-106">****Planning** \>**</span></span>|<span data-ttu-id="f583f-107">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="f583f-107">****Deployment** \>**</span></span>|<span data-ttu-id="f583f-108">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="f583f-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="f583f-109">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="f583f-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="f583f-110">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="f583f-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="f583f-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="f583f-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="f583f-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="f583f-112">You are here!</span></span>  <br/> [<span data-ttu-id="f583f-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f583f-113">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="f583f-p101">Persone amare App e vengono scaricati spesso, soprattutto delle applicazioni che utenti interazione utente verranno risparmiare tempo e rendere più semplice ottenere il proprio lavoro o scuola informazioni. Alcune applicazioni potenzialmente potrebbero comportare rischi di protezione dell'organizzazione, a seconda delle informazioni che accedono e modalità di gestione di tali informazioni. Con [Office 365 Cloud App protezione](office-365-cas-overview.md), in caso di un amministratore globale o di sicurezza, è possibile gestire le autorizzazioni dell'app per l'organizzazione. È possibile visualizzare le persone App utilizza con Office 365 dati, quali autorizzazioni tali applicazioni hanno e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f583f-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="f583f-118">In questo articolo viene descritto dove è possibile per gestire le autorizzazioni dell'app, sull'approvazione o escludere un'app e come creare una query di app.</span><span class="sxs-lookup"><span data-stu-id="f583f-118">This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-app-permissions-page"></a><span data-ttu-id="f583f-119">Come trovare la pagina autorizzazioni di gestione app</span><span class="sxs-lookup"><span data-stu-id="f583f-119">How to find the Manage app permissions page</span></span>
<span data-ttu-id="f583f-120"><a name="findappperms"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-120"></span></span>

> [!NOTE]
> <span data-ttu-id="f583f-p102">Le autorizzazioni dell'App vengono gestite nel portale di Office 365 Cloud App sicurezza. È necessario essere un amministratore globale o sicurezza per eseguire l'attività seguente. Per informazioni su ulteriori, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f583f-p102">App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="f583f-p103">Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.)</span><span class="sxs-lookup"><span data-stu-id="f583f-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="f583f-126">Accedere agli **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="f583f-126">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="f583f-127">Fare clic su (o toccare) **accedere a Office 365 Cloud App sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f583f-127">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span>
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > <span data-ttu-id="f583f-p104">Se Office 365 Cloud App è attivata la protezione non ancora, è possibile farlo in questa pagina. Vedere [prepararsi per la protezione di Office 365 Cloud App](get-ready-for-office-365-cas.md).</span><span class="sxs-lookup"><span data-stu-id="f583f-p104">If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="f583f-131">Scegliere **indagare** \> **le autorizzazioni dell'App**.</span><span class="sxs-lookup"><span data-stu-id="f583f-131">Choose **Investigate** \> **App permissions**.</span></span>
    
    ![Nel portale di accesso client di Office 365, selezionare indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a><span data-ttu-id="f583f-133">Verrà visualizzato nella pagina Gestisci app permissions</span><span class="sxs-lookup"><span data-stu-id="f583f-133">What you'll see on the Manage app permissions page</span></span>
<span data-ttu-id="f583f-134"><a name="whatsonpage"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-134"></span></span>

<span data-ttu-id="f583f-135">Nella tabella seguente vengono descritti i controlli e le opzioni disponibili nella pagina Gestisci app permissions.</span><span class="sxs-lookup"><span data-stu-id="f583f-135">The following table describes the controls and options available on the Manage app permissions page.</span></span>
  
|<span data-ttu-id="f583f-136">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="f583f-136">**Item**</span></span>|<span data-ttu-id="f583f-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f583f-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f583f-138">Base icona nella barra delle applicazioni query</span><span class="sxs-lookup"><span data-stu-id="f583f-138">Basic icon in the app query bar</span></span>  <br/> ![Icona che indica la visualizzazione query di base per eseguire query sulle autorizzazioni di app](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="f583f-140">Selezionare questa opzione per passare alla visualizzazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="f583f-140">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="f583f-141">(Se viene visualizzata **base**, si utilizza la visualizzazione avanzata)</span><span class="sxs-lookup"><span data-stu-id="f583f-141">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="f583f-142">Icona avanzata nella barra delle applicazioni query</span><span class="sxs-lookup"><span data-stu-id="f583f-142">Advanced icon in the app query bar</span></span>  <br/> ![Icona che indica avanzate visualizzazione della query per eseguire query sulle autorizzazioni di app](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="f583f-144">Selezionare questa opzione per passare alla visualizzazione di base.</span><span class="sxs-lookup"><span data-stu-id="f583f-144">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="f583f-145">(Se viene visualizzata **Avanzate**, si utilizza la visualizzazione di base.)</span><span class="sxs-lookup"><span data-stu-id="f583f-145">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="f583f-146">Aprire o chiudere tutti i dettagli delle icone app</span><span class="sxs-lookup"><span data-stu-id="f583f-146">Open or close all details icon in the app list</span></span>  <br/> ![Fare clic su questa icona per aprire o chiudere tutti i dettagli di tutte le app](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="f583f-148">Selezionare questa icona per visualizzare più o meno informazioni dettagliate su ogni app.</span><span class="sxs-lookup"><span data-stu-id="f583f-148">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="f583f-149">Esporta l'icona nell'elenco app</span><span class="sxs-lookup"><span data-stu-id="f583f-149">Export icon in the app list</span></span>  <br/> ![Fare clic su questa icona per esportare un file csv di tutte le app](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="f583f-151">Selezionare questa icona per esportare un file CSV contenente un elenco delle App, numero di utenti per ogni applicazione, le autorizzazioni associate le app, il livello di autorizzazioni, allo stato delle app, e Usa il livello di community.</span><span class="sxs-lookup"><span data-stu-id="f583f-151">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="f583f-152">Name</span><span class="sxs-lookup"><span data-stu-id="f583f-152">Name</span></span>  <br/> |<span data-ttu-id="f583f-p105">Utilizzare per visualizzare il nome di una selezione di App, il nome per visualizzare ulteriori informazioni, ad esempio la descrizione, publisher, sito Web app e ID app.</span><span class="sxs-lookup"><span data-stu-id="f583f-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="f583f-155">Autorizzato da</span><span class="sxs-lookup"><span data-stu-id="f583f-155">Authorized by</span></span>  <br/> |<span data-ttu-id="f583f-p106">Questa scheda per visualizzare il numero di utenti è autorizzati a un'applicazione di accedere al proprio account di Office 365. Selezionare il numero di visualizzare ulteriori informazioni, ad esempio un elenco di account utente.</span><span class="sxs-lookup"><span data-stu-id="f583f-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="f583f-158">Livello di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f583f-158">Permissions Level</span></span>  <br/> ![Icona che indica il livello di permisiions per un'applicazione](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="f583f-p107">Questa scheda per visualizzare il tipo di accesso un'app sia ai dati di Office 365. Livelli di autorizzazioni indicano **bassa**, **Media**o **alta**, in **basso** potrebbe indicare che l'app accede solo profili e il nome dell'utente. Selezionare il livello di visualizzare ulteriori informazioni, ad esempio le autorizzazioni concesse per le app, l'utilizzo di community e attività correlati nel [Registro di Governance](suspend-or-restore-an-account-in-ocas.md).</span><span class="sxs-lookup"><span data-stu-id="f583f-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="f583f-163">Stato di App ( **Banned**, **approvato**o **Elementi indeterminati**)</span><span class="sxs-lookup"><span data-stu-id="f583f-163">App state ( **Banned**, **Approved**, or **Undetermined**)</span></span>  <br/> <span data-ttu-id="f583f-164">![Icone di autorizzazioni App dopo viene consentiti, bloccati o nessuna azione è stato escluso da un amministratore](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span><span class="sxs-lookup"><span data-stu-id="f583f-164">![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span></span>|<span data-ttu-id="f583f-165">Utilizzare questa opzione per contrassegnare un'applicazione come approvato o Banned oppure lasciare come indeterminato.</span><span class="sxs-lookup"><span data-stu-id="f583f-165">Use this to mark an app as Approved or Banned, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="f583f-166">Contrassegnare un'applicazione come approvati</span><span class="sxs-lookup"><span data-stu-id="f583f-166">Mark an app as approved</span></span>
<span data-ttu-id="f583f-167"><a name="approveapp"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-167"></span></span>

<span data-ttu-id="f583f-168">Nella pagina **Gestisci autorizzazioni app** individuare l'app che si desidera approvare e scegliere l'icona **app contrassegna come approvati** .</span><span class="sxs-lookup"><span data-stu-id="f583f-168">On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![Scegliere l'app contrassegna come icona approvata](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
<span data-ttu-id="f583f-170">L'icona viene verde e l'applicazione viene approvata per tutti gli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f583f-170">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f583f-p108">Quando si contrassegna un'app come approvati, non esiste alcun effetto sull'utente finale. Contrassegno visivamente le app approvate consente di separarli da applicazioni che non sono state implementate ancora.</span><span class="sxs-lookup"><span data-stu-id="f583f-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="f583f-173">Escludere un'app</span><span class="sxs-lookup"><span data-stu-id="f583f-173">Ban an app</span></span>
<span data-ttu-id="f583f-174"><a name="banapp"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-174"></span></span>

1. <span data-ttu-id="f583f-175">Nella pagina **Gestisci autorizzazioni app** individuare app che si desidera escludere e scegliere l'icona **app contrassegna come vietate** .</span><span class="sxs-lookup"><span data-stu-id="f583f-175">On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span> 
    
    ![Scegliere l'app contrassegna come icona da escludere](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. <span data-ttu-id="f583f-177">Scegliere se si desidera informare gli utenti che è stata vietata la propria applicazione.</span><span class="sxs-lookup"><span data-stu-id="f583f-177">Choose whether to let users know that their app has been banned.</span></span>
    
    <span data-ttu-id="f583f-178">(Scelta consigliata) Per informare gli utenti, selezionare **gli utenti di notifica che ha concesso l'accesso a questa applicazione da escludere**e aggiungere o modificare un messaggio di notifica personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f583f-178">(Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.</span></span>
    
    <span data-ttu-id="f583f-179">Per non consentire agli utenti di conoscere, deselezionare la **notifica agli utenti che ha concesso l'accesso a questa applicazione da escludere**.</span><span class="sxs-lookup"><span data-stu-id="f583f-179">To not let users know, clear **Notify users who granted access to this banned app**.</span></span>
    
    ![Il modello di posta elettronica per un'applicazione da escludere](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. <span data-ttu-id="f583f-181">Scegliere **divieto app**.</span><span class="sxs-lookup"><span data-stu-id="f583f-181">Choose **Ban app**.</span></span>
    
## <a name="create-an-app-query"></a><span data-ttu-id="f583f-182">Creare una query di app</span><span class="sxs-lookup"><span data-stu-id="f583f-182">Create an app query</span></span>
<span data-ttu-id="f583f-183"><a name="createapp"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-183"></span></span>

1. <span data-ttu-id="f583f-p109">Nella barra di query delle applicazioni, se viene visualizzata **Avanzate**, fare clic su (o toccare) per passare alla visualizzazione avanzata. (Se viene visualizzata Basic, si utilizza la visualizzazione avanzata, mantenere la visualizzazione invariata).</span><span class="sxs-lookup"><span data-stu-id="f583f-p109">In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)</span></span>
    
2. <span data-ttu-id="f583f-p110">Utilizzare l'elenco **Selezionare un filtro** per scegliere un'opzione. Nella tabella seguente sono riepilogate le opzioni di filtro disponibili.</span><span class="sxs-lookup"><span data-stu-id="f583f-p110">Use the **Select a filter** list to choose an option. The following table summarizes your available filter options.</span></span> 
    
|<span data-ttu-id="f583f-188">**Utilizzare il filtro**</span><span class="sxs-lookup"><span data-stu-id="f583f-188">**Use this filter**</span></span>|<span data-ttu-id="f583f-189">**Per visualizzare**</span><span class="sxs-lookup"><span data-stu-id="f583f-189">**To display**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f583f-190">**App**</span><span class="sxs-lookup"><span data-stu-id="f583f-190">**App**</span></span> <br/> |<span data-ttu-id="f583f-191">App con determinati nomi</span><span class="sxs-lookup"><span data-stu-id="f583f-191">Apps with certain names</span></span>  <br/> |
|<span data-ttu-id="f583f-192">**Stato delle App**</span><span class="sxs-lookup"><span data-stu-id="f583f-192">**App state**</span></span> <br/> |<span data-ttu-id="f583f-193">Applicazioni in base al proprio stato (approvato, Banned o elementi indeterminati)</span><span class="sxs-lookup"><span data-stu-id="f583f-193">Apps based on their state (Approved, Banned, or Undetermined)</span></span>  <br/> |
|<span data-ttu-id="f583f-194">**Utilizzo di community**</span><span class="sxs-lookup"><span data-stu-id="f583f-194">**Community use**</span></span> <br/> |<span data-ttu-id="f583f-195">App basato sulla community di utilizzare i livelli (Rare, Uncommon o comune)</span><span class="sxs-lookup"><span data-stu-id="f583f-195">Apps based on community use levels (Rare, Uncommon, or Common)</span></span>  <br/> |
|<span data-ttu-id="f583f-196">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="f583f-196">**Permission level**</span></span> <br/> |<span data-ttu-id="f583f-197">App basato su determinati livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f583f-197">Apps based on certain permission levels</span></span>  <br/> |
|<span data-ttu-id="f583f-198">**Autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="f583f-198">**Permissions**</span></span> <br/> |<span data-ttu-id="f583f-199">App che richiedono autorizzazioni specifiche</span><span class="sxs-lookup"><span data-stu-id="f583f-199">Apps that require certain permissions</span></span>  <br/> |
|<span data-ttu-id="f583f-200">**Server Editore**</span><span class="sxs-lookup"><span data-stu-id="f583f-200">**Publisher**</span></span> <br/> |<span data-ttu-id="f583f-201">App da determinati autori</span><span class="sxs-lookup"><span data-stu-id="f583f-201">Apps from certain publishers</span></span>  <br/> |
|<span data-ttu-id="f583f-202">**Utente**</span><span class="sxs-lookup"><span data-stu-id="f583f-202">**User**</span></span> <br/> |<span data-ttu-id="f583f-203">Applicazioni che un determinato utente autorizzato</span><span class="sxs-lookup"><span data-stu-id="f583f-203">Apps that a certain user authorized</span></span>  <br/> |
   
3. <span data-ttu-id="f583f-204">Selezionare **è uguale a** o **diverso**e quindi specificare un valore per il filtro.</span><span class="sxs-lookup"><span data-stu-id="f583f-204">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
4. <span data-ttu-id="f583f-205">Per aggiungere ulteriori filtri, selezionare il segno di addizione (</span><span class="sxs-lookup"><span data-stu-id="f583f-205">To add more filters, select the plus sign (</span></span>![Aggiungere un'icona del filtro per eseguire query sulle App](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="f583f-207">) e quindi ripetere i passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="f583f-207">), and then repeat steps 2 and 3.</span></span>
    
5. <span data-ttu-id="f583f-208">Per rimuovere un filtro, selezionare il x (</span><span class="sxs-lookup"><span data-stu-id="f583f-208">To remove a filter, select the x (</span></span>![Rimuovere un'icona del filtro per eseguire query sulle App](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="f583f-210">) accanto al nome di un filtro.</span><span class="sxs-lookup"><span data-stu-id="f583f-210">) next to a filter name.</span></span>
    
<span data-ttu-id="f583f-211">Vengono applicati automaticamente i filtri e l'elenco di applicazioni viene aggiornata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f583f-211">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="f583f-212">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f583f-212">Next steps</span></span>
<span data-ttu-id="f583f-213"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="f583f-213"></span></span>

- [<span data-ttu-id="f583f-214">Leggere ed eseguire l'azione gli avvisi</span><span class="sxs-lookup"><span data-stu-id="f583f-214">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="f583f-215">Esaminare i [registri di traffico Web e le origini dati per la protezione di Office 365 Cloud App](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="f583f-215">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="f583f-216">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="f583f-216">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

