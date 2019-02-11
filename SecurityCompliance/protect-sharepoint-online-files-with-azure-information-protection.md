---
title: Proteggere i file di SharePoint Online con Azure Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/08/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Sintesi: Applicare la protezione delle informazioni di Azure per proteggere i file in un sito del team di SharePoint Online di livello estremamente riservato.'
ms.openlocfilehash: 738e64784de20af46050413985fb7932000f864e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "28021645"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a><span data-ttu-id="c45ae-103">Proteggere i file di SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="c45ae-103">Protect SharePoint Online files with Azure Information Protection</span></span>

 <span data-ttu-id="c45ae-104">**Riepilogo:** Applicare la protezione delle informazioni di Azure per proteggere i file in un sito del team di SharePoint Online di livello estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="c45ae-104">**Summary:** Apply Azure Information Protection to protect files in a highly confidential SharePoint Online team site.</span></span>
  
<span data-ttu-id="c45ae-p101">Utilizzare la procedura in questo articolo per configurare Azure Information Protection in modo da fornire la crittografia e le autorizzazioni per i file. Tali file possono essere aggiunti alla raccolta di SharePoint configurata per la protezione estremamente riservata. In alternativa, è possibile aprire un file direttamente dal sito e usare il client Azure Information Protection per aggiungere la crittografia. La protezione tramite crittografia e autorizzazioni si sposta insieme al file, persino quando questo viene scaricato dal sito.</span><span class="sxs-lookup"><span data-stu-id="c45ae-p101">Use the steps in this article to configure Azure Information Protection to provide encryption and permissions for files. These files can be added to a SharePoint library configured for highly confidential protection. Or, you can open a file directly from the site and use the Azure Information Protection client to add encryption. The encryption and permissions protection travels with a file even when it is downloaded from the site.</span></span> 

<span data-ttu-id="c45ae-p102">La procedura fa parte di una soluzione più ampia per configurare la protezione estremamente riservata per i siti di SharePoint e i file al loro interno. Per ulteriori informazioni, vedere [Siti e file di Secure SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p102">These steps are part of a larger solution for configuring highly confidential protection for SharePoint sites and the files within these sites. For more information, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span> 

<span data-ttu-id="c45ae-111">L'utilizzo di Azure Information Protection per i file di SharePoint Online non è consigliato per tutti i clienti, ma è disponibile come opzione per i clienti che hanno l'esigenza di questo livello di protezione per un sottoinsieme dei file.</span><span class="sxs-lookup"><span data-stu-id="c45ae-111">Using Azure Information Protection for files in SharePoint Online is not recommended for all customers, but is an option for customers who need this level of protection for a subset of files.</span></span>

<span data-ttu-id="c45ae-112">Alcune note importanti su questa soluzione:</span><span class="sxs-lookup"><span data-stu-id="c45ae-112">Some important notes about this solution:</span></span>
- <span data-ttu-id="c45ae-p103">Quando la crittografia di Azure Information Protection viene applicata ai file di Office 365, il servizio non può elaborare il contenuto di tali file. Creazione condivisa, eDiscovery, ricerca, Delve e altre funzionalità di collaborazione non funzionano. I criteri di prevenzione della perdita dei dati (DLP) possono funzionare solo con i metadati (comprese le etichette di Office 365), ma non con i contenuti di tali file (ad esempio i numeri di carta di credito all'interno dei file).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p103">When Azure Information Protection encryption is applied to files stored in Office 365, the service cannot process the contents of these files. Co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Data Loss Prevention (DLP) policies can only work with the metadata (including Office 365 labels) but not the contents of these files (such as credit card numbers within files).</span></span>
- <span data-ttu-id="c45ae-p104">Questa soluzione richiede all'utente di selezionare un'etichetta che applica la protezione di Azure Information Protection. Se si richiede la crittografia automatica e la capacità per SharePoint di indicizzare e ispezionare i file, è consigliabile utilizzare Information Rights Management (IRM) in SharePoint Online. Quando si configura una raccolta di SharePoint per IRM, i file vengono crittografati automaticamente nel momento in cui vengono scaricati per la modifica.  IRM di SharePoint include limitazioni che potrebbero influenzare le decisioni. Per ulteriori informazioni, vedere [Configurazione di IRM nell'interfaccia di amministrazione di SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p104">This solution requires a user to select a label that applies the protection from Azure Information Protection. If you require automatic encryption and the ability for SharePoint to index and inspect the files, consider using Information Rights Management (IRM) in SharePoint Online. When you configure a SharePoint library for IRM, files are automatically encrypted when they are downloaded for editing.  SharePoint IRM includes limitations that might influence your decision. For more information, see [Set up Information Rights Management (IRM) in SharePoint admin center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).</span></span>

## <a name="admin-setup"></a><span data-ttu-id="c45ae-121">Configurazione degli amministratori</span><span class="sxs-lookup"><span data-stu-id="c45ae-121">Admin setup</span></span>
<span data-ttu-id="c45ae-122">Innanzitutto, attenersi alle istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) per la sottoscrizione di Office 365 in uso.</span><span class="sxs-lookup"><span data-stu-id="c45ae-122">First, use the instructions in [Activate Azure RMS with the Office 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) for your Office 365 subscription.</span></span>
  
<span data-ttu-id="c45ae-123">Configurare quindi Azure Information Protection con un nuovo criterio con ambito e un'etichetta secondaria per la protezione e le autorizzazioni del sito del team di SharePoint Online di livello estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="c45ae-123">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions of your highly confidential SharePoint Online team site.</span></span>
  
1. <span data-ttu-id="c45ae-p105">Accedere al portale di Office 365 con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società. Per informazioni, vedere [Dove accedere a Office 365 per le aziende](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="c45ae-126">In un'altra scheda del browser, accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)).</span><span class="sxs-lookup"><span data-stu-id="c45ae-126">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="c45ae-127">Se è la prima volta che viene configurato Azure Information Protection, consultare queste [istruzioni](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span><span class="sxs-lookup"><span data-stu-id="c45ae-127">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>

4. <span data-ttu-id="c45ae-128">Nel riquadro dell'elenco, fare clic su **Ulteriori servizi**, digitare **Informazioni**, quindi fare clic su **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-128">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="c45ae-129">Fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-129">Click **Labels**.</span></span>
    
6. <span data-ttu-id="c45ae-130">Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-130">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="c45ae-131">Digitare un nome per l'etichetta secondaria in **Nome** e una descrizione dell'etichetta secondaria in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-131">Type a name for the sub-label in **Name** and a description of the sub-label in **Description**.</span></span>
    
8. <span data-ttu-id="c45ae-132">In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-132">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="c45ae-133">Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-133">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="c45ae-134">Nel pannello **Protezione** fare clic su **Aggiungi autorizzazioni** in **Impostazioni di protezione**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-134">On the **Protection** blade, under **Protection settings**, click **Add permissions**.</span></span>
    
11. <span data-ttu-id="c45ae-135">Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **Sfoglia la directory**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-135">On the **Add permissions** blade, under **Specify users and groups**, click **Browse directory**.</span></span>
    
12. <span data-ttu-id="c45ae-136">Nel riquadro **Utenti e gruppi di AAD**, selezionare i membri del gruppo di accesso per il sito del team di SharePoint Online di livello estremamente riservato, quindi scegliere **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-136">On the **AAD Users and Groups** pane, select the site members access group for your highly sensitive SharePoint Online team site, and then click **Select**.</span></span>
    
13. <span data-ttu-id="c45ae-137">In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, \*\* Salva\*\*, **Rispondi** e **Rispondi a tutti**</span><span class="sxs-lookup"><span data-stu-id="c45ae-137">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="c45ae-138">Fare due volte clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-138">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="c45ae-139">Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-139">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="c45ae-140">Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-140">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="c45ae-141">Digitare un nome per il nuovo criterio in **Nome criterio** e una descrizione in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-141">Type a name for the new policy in **Policy name** and a description in **Description**.</span></span>
    
18. <span data-ttu-id="c45ae-142">Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare i membri del gruppo di accesso per il sito del team di SharePoint Online di livello estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="c45ae-142">Click **Select which users or groups get this policy > User/Groups**, and then select the site members access group for your highly sensitive SharePoint Online team site.</span></span>
    
19. <span data-ttu-id="c45ae-143">Fare clic su **Seleziona > OK**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-143">Click **Select > OK**.</span></span>

20. <span data-ttu-id="c45ae-p106">Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic sul nome dell'etichetta secondaria, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-p106">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click the name of your new sub-label, and then click **OK**.</span></span>   

21. <span data-ttu-id="c45ae-146">Fare clic su **Salva**, quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c45ae-146">Click **Save**, and then click **OK**.</span></span>
 
## <a name="client-setup"></a><span data-ttu-id="c45ae-147">Configurazione client</span><span class="sxs-lookup"><span data-stu-id="c45ae-147">Client setup</span></span>
<span data-ttu-id="c45ae-148">A questo punto si è pronti per iniziare a creare documenti e a proteggerli con Azure Information Protection e con la nuova etichetta.</span><span class="sxs-lookup"><span data-stu-id="c45ae-148">You are now ready to begin creating documents and protecting them with Azure Information Protection and your new label.</span></span>
  
<span data-ttu-id="c45ae-p107">È necessario [installare il client Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) nel computer che esegue Windows o nel dispositivo. È possibile creare uno script e automatizzare l'installazione oppure gli utenti possono installare il client manualmente. Vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="c45ae-p107">You must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on your device or Windows-based computer. You can script and automate the installation, or users can install the client manually. See the following resources:</span></span>
  
- [<span data-ttu-id="c45ae-152">Lato client di Protezione delle informazioni di Azure</span><span class="sxs-lookup"><span data-stu-id="c45ae-152">The client side of Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [<span data-ttu-id="c45ae-153">Installazione del client di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="c45ae-153">Installing the Azure Information Protection client</span></span>](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [<span data-ttu-id="c45ae-154">Pagina di download per l'installazione manuale</span><span class="sxs-lookup"><span data-stu-id="c45ae-154">Download page for manual installation</span></span>](https://www.microsoft.com/download/details.aspx?id=53018)
    
<span data-ttu-id="c45ae-p108">Dopo aver eseguito l'installazione, gli utenti eseguono il programma, quindi accedono da un'applicazione Office (ad esempio Microsoft Word) con l'account Office 365. Una nuova barra di **Information Protection** consente agli utenti di selezionare la nuova etichetta. Assicurarsi che gli utenti conoscano il sito del team di SharePoint Online e l'etichetta da usare per proteggere i file di livello estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="c45ae-p108">Once installed, your users run and then sign-in from an Office application (such as Microsoft Word) with their Office 365 account. A new **Information Protection** bar allows users to select the new label. Make sure that your users know the SharePoint Online team site and which label to use, to protect their highly confidential files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c45ae-158">Se si dispone di più siti del team di SharePoint Online di livello estremamente riservato, è necessario creare più criteri con ambiti di Azure Information Protection con etichette secondarie con le impostazioni precedenti, con le autorizzazioni per ogni etichetta impostata per il gruppo di accesso dei membri di un sito del team di SharePoint Online specifico.</span><span class="sxs-lookup"><span data-stu-id="c45ae-158">If you have multiple highly sensitive SharePoint Online team sites, you should create multiple Azure Information Protection scoped policies with sub-labels with the above settings, with the permissions for each sub-label set to the site members access group of a specific SharePoint Online team site.</span></span> 
  
## <a name="adding-permissions-for-external-users"></a><span data-ttu-id="c45ae-159">Aggiunta delle autorizzazioni per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="c45ae-159">Adding permissions for external users</span></span>
<span data-ttu-id="c45ae-p109">Esistono due modi per concedere agli utenti esterni l'accesso ai file protetti con Azure Information Protection. In entrambi i casi gli utenti esterni devono avere un account Azure AD. Se gli utenti esterni non sono membri di un'organizzazione che usa Azure AD, possono ottenere un account Azure AD come utente singolo da questa pagina di iscrizione: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p109">There are two ways you can grant external users access to files protected with Azure Information Protection. In both cases, external users must have an Azure AD account. If external users aren't members of an organization that uses Azure AD, they can obtain an Azure AD account as an individual by using this signup page: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).</span></span>

 - <span data-ttu-id="c45ae-p110">Per aggiungere utenti esterni a un gruppo di Azure AD utilizzato per configurare la protezione per un'etichetta, è necessario innanzitutto aggiungere l'account come utente B2B nella directory. La memorizzazione nella cache dell'[appartenenza al gruppo da parte di Azure Rights Management può richiedere alcune ore](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="c45ae-p110">Add external users to an Azure AD group that is used to configure protection for a label. You'll need to first add the account as a B2B user in your directory. It can take a couple of hours for [group memership caching by Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).</span></span>  
 - <span data-ttu-id="c45ae-p111">Per aggiungere utenti esterni direttamente alla protezione delle etichette, è possibile aggiungere tutti gli utenti di un'organizzazione (ad esempio Fabrikam.com), un gruppo di Azure AD (ad esempio, un gruppo dell’amministrazione all'interno di un'organizzazione) o un singolo utente. Ad esempio, è possibile aggiungere un team di regolatori esterno alla protezione per un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="c45ae-p111">Add external users directly to the label protection. You can add all users from an organization (e.g. Fabrikam.com), an Azure AD group (such as a finance group within an organization), or user. For example, you can add an external team of regulators to the protection for a label.</span></span>

## <a name="see-also"></a><span data-ttu-id="c45ae-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c45ae-169">See Also</span></span>

[<span data-ttu-id="c45ae-170">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c45ae-170">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="c45ae-171">Proteggere i siti di SharePoint Online in un ambiente di sviluppo e di testing</span><span class="sxs-lookup"><span data-stu-id="c45ae-171">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="c45ae-172">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="c45ae-172">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="c45ae-173">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="c45ae-173">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




