---
title: Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Office 365."
ms.openlocfilehash: a8a02c10f799b136b299801a3636820e4f64e087
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217136"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="8840a-103">Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test</span><span class="sxs-lookup"><span data-stu-id="8840a-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="8840a-104">**Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8840a-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>
  
<span data-ttu-id="8840a-p101">I siti del team di SharePoint online in Office 365 sono percorsi per la collaborazione utilizzando una raccolta documenti comune, un blocco appunti di OneNote e altri servizi. In molti casi, è necessario un accesso esteso e una collaborazione tra dipartimenti o organizzazioni. Tuttavia, in alcuni casi, si desidera controllare in modo rigoroso l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di persone.</span><span class="sxs-lookup"><span data-stu-id="8840a-p101">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services. In many cases, you want wide access and collaboration across departments or organizations. However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>
  
<span data-ttu-id="8840a-p102">L'accesso ai siti del team di SharePoint Online e gli elementi che gli utenti possono eseguire sono controllati da gruppi e livelli di autorizzazione di SharePoint. Per impostazione predefinita, i siti di SharePoint Online hanno tre livelli di accesso:</span><span class="sxs-lookup"><span data-stu-id="8840a-p102">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels. By default, SharePoint Online sites have three levels of access:</span></span>
  
- <span data-ttu-id="8840a-110">**Membri**, che possono visualizzare, creare e modificare le risorse sul sito.</span><span class="sxs-lookup"><span data-stu-id="8840a-110">**Members**, who can view, create, and modify resources on the site.</span></span>
    
- <span data-ttu-id="8840a-111">**Proprietari**, che hanno il controllo completo del sito, compresa la possibilità di modificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8840a-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
    
- <span data-ttu-id="8840a-112">**Visitatori**, che possono solo visualizzare le risorse sul sito.</span><span class="sxs-lookup"><span data-stu-id="8840a-112">**Visitors**, who only can view resources on the site.</span></span>
    
<span data-ttu-id="8840a-p103">In questo articolo viene illustrata la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreto denominato ProjectX. I requisiti di accesso sono:</span><span class="sxs-lookup"><span data-stu-id="8840a-p103">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX. The access requirements are:</span></span>
  
- <span data-ttu-id="8840a-115">Solo i membri del progetto possono accedere al sito e ai suoi contenuti (documenti, Blocco appunti di OneNote, Pages), con livelli di autorizzazione di SharePoint per la modifica e la visualizzazione controllati mediante l'appartenenza al gruppo.</span><span class="sxs-lookup"><span data-stu-id="8840a-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>
    
- <span data-ttu-id="8840a-116">Solo l'autore del sito e i membri di un gruppo Amministratori per il sito possono eseguire operazioni amministrative sul sito, inclusa la modifica delle autorizzazioni a livello del sito.</span><span class="sxs-lookup"><span data-stu-id="8840a-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>
    
<span data-ttu-id="8840a-117">Sono disponibili tre fasi per la configurazione di un sito del team di SharePoint Online isolato nell'ambiente di sviluppo/test di Office 365:</span><span class="sxs-lookup"><span data-stu-id="8840a-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>
  
1. <span data-ttu-id="8840a-118">Creare l'ambiente di sviluppo/testing di Office 365</span><span class="sxs-lookup"><span data-stu-id="8840a-118">Create the Office 365 dev/test environment.</span></span>
    
2. <span data-ttu-id="8840a-119">Creare gli utenti e i gruppi per ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8840a-119">Create the users and groups for ProjectX.</span></span>
    
3. <span data-ttu-id="8840a-120">Creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo.</span><span class="sxs-lookup"><span data-stu-id="8840a-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>
    
> [!TIP]
> <span data-ttu-id="8840a-121">Fare clic [qui](http://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8840a-121">Click [here](http://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="8840a-122">Fase 1: creare l'ambiente di sviluppo/test di Office 365 aziendale leggero o simulato</span><span class="sxs-lookup"><span data-stu-id="8840a-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="8840a-123">Se si desidera creare un sito del team di SharePoint Online isolato in modo semplice con i requisiti minimi, seguire le istruzioni riportate nelle fasi 2 e 3 dell' [ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="8840a-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="8840a-124">Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione aziendale simulata, seguire le istruzioni in [dirsync per l'ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="8840a-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8840a-p104">La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo/test aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Windows Server AD. Qui viene fornito come un'opzione in modo da poter testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="8840a-p104">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="8840a-127">Fase 2: creare account utente e gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="8840a-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="8840a-128">Utilizzare le istruzioni riportate in [Connect to office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) to Connect to your Office 365 Trail Subscription with your Global Administrator account from:</span><span class="sxs-lookup"><span data-stu-id="8840a-128">Use the instructions in [Connect to Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>
  
- <span data-ttu-id="8840a-129">Dal computer (per l'ambiente di sviluppo/test di Office 365 leggero).</span><span class="sxs-lookup"><span data-stu-id="8840a-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>
    
- <span data-ttu-id="8840a-130">Dalla macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Office 365 aziendale simulato).</span><span class="sxs-lookup"><span data-stu-id="8840a-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>
    
<span data-ttu-id="8840a-131">Per creare i nuovi gruppi di accesso per il sito del team di SharePoint Online di ProjectX, eseguire i comandi seguenti dal prompt del modulo di Windows Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8840a-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> <span data-ttu-id="8840a-132">Fare clic [qui](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) per un file di testo contenente tutti i comandi di PowerShell riportati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8840a-132">Click [here](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) for a text file that contains all of the PowerShell commands in this article.</span></span>
  
<span data-ttu-id="8840a-133">Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri e quindi eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8840a-133">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8840a-134">Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Lead Designer e conservarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8840a-134">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>
  
<span data-ttu-id="8840a-135">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8840a-135">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8840a-136">Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Lead Researcher e conservarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8840a-136">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>
  
<span data-ttu-id="8840a-137">Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8840a-137">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8840a-138">Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Development VP e conservarla in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="8840a-138">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>
  
<span data-ttu-id="8840a-139">Successivamente, per aggiungere i nuovi account ai nuovi gruppi di accesso, eseguire i comandi di PowerShell dal modulo di Windows Azure Active Directory per il prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8840a-139">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="8840a-140">Risultati:</span><span class="sxs-lookup"><span data-stu-id="8840a-140">Results:</span></span>
  
- <span data-ttu-id="8840a-141">Il gruppo di accesso ProjectX-Members contiene gli account utente lead designer e Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="8840a-141">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>
    
- <span data-ttu-id="8840a-142">Il gruppo di accesso ProjectX-Admins contiene l'account di amministratore globale per la sottoscrizione di valutazione</span><span class="sxs-lookup"><span data-stu-id="8840a-142">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>
    
- <span data-ttu-id="8840a-143">Il gruppo di accesso ProjectX-Viewer contiene l'account utente Development VP</span><span class="sxs-lookup"><span data-stu-id="8840a-143">The ProjectX-Viewers access group contains the Development VP user account</span></span>
    
<span data-ttu-id="8840a-144">Nella figura 1 vengono visualizzati i gruppi di accesso e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="8840a-144">Figure 1 shows the access groups and their membership.</span></span>
  
<span data-ttu-id="8840a-145">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="8840a-145">**Figure 1**</span></span>

![Gruppi di Office 365 e appartenenza a un sito di gruppi di SharePoint Online isolato](media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="8840a-147">Fase 3: creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo</span><span class="sxs-lookup"><span data-stu-id="8840a-147">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="8840a-148">Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8840a-148">To create a SharePoint Online team site for ProjectX, do the following:</span></span>
  
1. <span data-ttu-id="8840a-149">Utilizzando un browser sul computer locale (configurazione lightweight) o su CLIENT1 (configurazione Enterprise simulata), accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="8840a-149">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using your global administrator account.</span></span>
    
2. <span data-ttu-id="8840a-150">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8840a-150">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="8840a-151">Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="8840a-151">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="8840a-p105">In **nome sito del team**digitare **ProjectX**. In **impostazioni di privacy**, selezionare **membri solo privati possono accedere a questo sito**.</span><span class="sxs-lookup"><span data-stu-id="8840a-p105">In **Team site name**, type **ProjectX**. In **Privacy settings**, select **Private - only members can access this site**.</span></span>
    
5. <span data-ttu-id="8840a-154">In **Descrizione sito del team**, digitare **Sito di SharePoint per ProjectX**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8840a-154">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="8840a-155">Per **chi si desidera aggiungere**? riquadro, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="8840a-155">On the **Who do you want to add**? pane, click **Finish**.</span></span>
    
7. <span data-ttu-id="8840a-156">Nella nuova scheda **ProjectX-Home** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="8840a-156">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
8. <span data-ttu-id="8840a-157">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="8840a-157">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
9. <span data-ttu-id="8840a-158">Nella nuova scheda **Autorizzazioni: ProjectX** visualizzata nel browser, fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="8840a-158">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>
    
10. <span data-ttu-id="8840a-159">Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti richieste di accesso** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8840a-159">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
11. <span data-ttu-id="8840a-160">Fare clic su **Membri ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8840a-160">Click **ProjectX Members** in the list.</span></span>
    
12. <span data-ttu-id="8840a-161">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8840a-161">On the **People and Groups** page, click **New**.</span></span>
    
13. <span data-ttu-id="8840a-162">Nella finestra di dialogo **Condividi**, digitare **ProjectX-Members**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="8840a-162">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="8840a-163">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="8840a-163">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="8840a-164">Fare clic su **Proprietari ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8840a-164">Click **ProjectX Owners** in the list.</span></span>
    
16. <span data-ttu-id="8840a-165">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8840a-165">On the **People and Groups** page, click **New**.</span></span>
    
17. <span data-ttu-id="8840a-166">Nella finestra di dialogo **Condividi**, digitare **ProjectX-Admins**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="8840a-166">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="8840a-167">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="8840a-167">Click the back button on your browser.</span></span>
    
19. <span data-ttu-id="8840a-168">Fare clic su **Visitatori ProjectX** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8840a-168">Click **ProjectX Visitors** in the list.</span></span>
    
20. <span data-ttu-id="8840a-169">Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8840a-169">On the **People and Groups** page, click **New**.</span></span>
    
21. <span data-ttu-id="8840a-170">Nella finestra di dialogo **Condividi**, digitare **ProjectX-Viewers**, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="8840a-170">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>
    
22. <span data-ttu-id="8840a-171">Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **ProjectX-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.
</span><span class="sxs-lookup"><span data-stu-id="8840a-171">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="8840a-172">Ecco i risultati della configurazione delle autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="8840a-172">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="8840a-173">Il gruppo di SharePoint membri di ProjectX contiene solo il gruppo di accesso ProjectX-Members (che contiene solo gli account utente lead designer e Lead Researcher) e il gruppo ProjectX (che contiene solo l'account utente di amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="8840a-173">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="8840a-174">Il gruppo di SharePoint proprietari di ProjectX contiene solo il gruppo di accesso ProjectX-Admins (che contiene solo l'account utente dell'amministratore globale).</span><span class="sxs-lookup"><span data-stu-id="8840a-174">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="8840a-175">Il gruppo di SharePoint visitatori di ProjectX contiene solo il gruppo di accesso ProjectX-Viewer (che contiene solo l'account utente Development VP).</span><span class="sxs-lookup"><span data-stu-id="8840a-175">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>
    
- <span data-ttu-id="8840a-176">I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo ProjectX-Admins).</span><span class="sxs-lookup"><span data-stu-id="8840a-176">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>
    
- <span data-ttu-id="8840a-177">Altri account utente non possono accedere al sito e alle relative risorse o richiedere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="8840a-177">Other user accounts cannot access the site or its resources or request access to the site.</span></span>
    
<span data-ttu-id="8840a-178">Nella figura 2 vengono mostrati i gruppi di SharePoint e la relativa appartenenza.</span><span class="sxs-lookup"><span data-stu-id="8840a-178">Figure 2 shows the SharePoint groups and their membership.</span></span>
  
<span data-ttu-id="8840a-179">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="8840a-179">**Figure 2**</span></span>

![Gruppi di SharePoint Online e appartenenza a un sito di gruppi di SharePoint Online isolato](media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
<span data-ttu-id="8840a-181">Ora dimostreremo l'accesso utilizzando l'account utente lead designer:</span><span class="sxs-lookup"><span data-stu-id="8840a-181">Now let's demonstrate access using the Lead Designer user account:</span></span>
  
1. <span data-ttu-id="8840a-182">Chiudere la scheda **ProjectX-Home** visualizzata nel browser, quindi fare clic sulla scheda **Microsoft Office Home** nel browser.</span><span class="sxs-lookup"><span data-stu-id="8840a-182">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>
    
2. <span data-ttu-id="8840a-183">Fare clic sul nome dell'amministratore globale e quindi fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="8840a-183">Click the name of your global administrator, and then click **Sign out**.</span></span>
    
3. <span data-ttu-id="8840a-184">Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account del progettista principale e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8840a-184">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the Lead Designer account name and its password.</span></span>
    
4. <span data-ttu-id="8840a-185">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8840a-185">In the list of tiles, click **SharePoint**.</span></span>
    
5. <span data-ttu-id="8840a-p106">Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** . Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8840a-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>
    
6. <span data-ttu-id="8840a-p107">Fare clic sull'icona delle impostazioni. Si noti che non sono presenti opzioni per **Autorizzazioni sito**. È corretto perché solo i membri del gruppo ProjectX-Admins possono modificare le autorizzazioni sul sito</span><span class="sxs-lookup"><span data-stu-id="8840a-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>
    
7. <span data-ttu-id="8840a-191">Aprire il Blocco note o un editor di testo di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="8840a-191">Open Notepad or a text editor of your choice.</span></span>
    
8. <span data-ttu-id="8840a-192">Copiare l'URL del sito del team di ProjectX e incollarlo su una nuova riga nel blocco note o nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8840a-192">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>
    
9. <span data-ttu-id="8840a-193">Nella nuova scheda **ProjectX-Home** visualizzata nel browser, fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="8840a-193">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>
    
10. <span data-ttu-id="8840a-194">Copiare l'URL della cartella dei documenti di ProjectX e incollarlo su una nuova riga nel Blocco note o nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8840a-194">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>
    
11. <span data-ttu-id="8840a-195">Nella nuova scheda **ProjectX-Documents** visualizzata nel browser, fare clic su **Nuovo > Documento Word**.</span><span class="sxs-lookup"><span data-stu-id="8840a-195">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>
    
12. <span data-ttu-id="8840a-p108">Digitare del testo nella pagina **Word Online**, attendere che lo stato riporti **Salvato**, fare clic sul pulsante Indietro nel browser, quindi aggiornare la pagina. Viene visualizzato un nuovo file **Document.docx** nella cartella **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="8840a-p108">Type some text in the **Word Online** page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page. You should see a new **Document.docx** in the **Documents** folder.</span></span>
    
13. <span data-ttu-id="8840a-198">Fare clic sui puntini di sospensione del documento **Document.docx**, quindi fare clic su **Ottieni un collegamento**.</span><span class="sxs-lookup"><span data-stu-id="8840a-198">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>
    
14. <span data-ttu-id="8840a-199">Copiare l'URL nella finestra di dialogo **Condividi ' Document. docx '** e incollarlo su una nuova riga nel blocco note o nell'editor di testo, quindi chiudere la finestra di dialogo **Condividi documento. docx** .</span><span class="sxs-lookup"><span data-stu-id="8840a-199">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>
    
15. <span data-ttu-id="8840a-200">Chiudere le schede **ProjectX-Documents** e **SharePoint** nel browser, quindi fare clic sulla scheda **Microsoft Office Home**.</span><span class="sxs-lookup"><span data-stu-id="8840a-200">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>
    
16. <span data-ttu-id="8840a-201">Fare clic sul nome **Lead Designer**, quindi su **Disconnetti**.
</span><span class="sxs-lookup"><span data-stu-id="8840a-201">Click the **Lead Designer** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="8840a-202">Ora dimostreremo l'accesso utilizzando l'account utente Development VP:</span><span class="sxs-lookup"><span data-stu-id="8840a-202">Now let's demonstrate access using the Development VP user account:</span></span>
  
1. <span data-ttu-id="8840a-203">Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account Development VP e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8840a-203">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the Development VP account name and its password.</span></span>
    
2. <span data-ttu-id="8840a-204">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8840a-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="8840a-p109">Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** . Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8840a-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>
    
4. <span data-ttu-id="8840a-207">Fare clic su **Documenti**, quindi sul file **Document.docx**.</span><span class="sxs-lookup"><span data-stu-id="8840a-207">Click **Documents**, and then click the **Document.docx** file.</span></span>
    
5. <span data-ttu-id="8840a-p110">Nella scheda **Document.docx** nel browser, provare a modificare il testo. Viene visualizzato il messaggio **Documento di sola lettura.** Infatti, l'account utente Development VP può solo visualizzare le autorizzazioni per il sito.</span><span class="sxs-lookup"><span data-stu-id="8840a-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>
    
6. <span data-ttu-id="8840a-211">Chiudere le schede **Document.docx**, **ProjectX-Documents** e **SharePoint** nel browser.</span><span class="sxs-lookup"><span data-stu-id="8840a-211">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>
    
7. <span data-ttu-id="8840a-212">Fare clic sulla scheda **Microsoft Office Home**, selezionare il nome **Development VP** e quindi fare clic su **Disconnetti**.
</span><span class="sxs-lookup"><span data-stu-id="8840a-212">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="8840a-213">Ora dimostreremo l'accesso con un account utente che non dispone di autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="8840a-213">Now let's demonstrate access with a user account that has no permissions:</span></span>
  
1. <span data-ttu-id="8840a-214">Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account utente 3 e la relativa password.</span><span class="sxs-lookup"><span data-stu-id="8840a-214">Sign in to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) using the User 3 account name and its password.</span></span>
    
2. <span data-ttu-id="8840a-215">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="8840a-215">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="8840a-p111">	Nella nuova scheda *\*SharePoint** nel browser, digitare *\*ProjectX** nella casella di ricerca e quindi attivare la ricerca. Viene visualizzato il messaggio *\*Nessun elemento corrispondente alla ricerca.**</span><span class="sxs-lookup"><span data-stu-id="8840a-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>
    
4. <span data-ttu-id="8840a-p112">Dall'istanza aperta del Blocco note o dell'editor di testo, copiare l'URL per il sito di ProjectX nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.</span><span class="sxs-lookup"><span data-stu-id="8840a-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
5. <span data-ttu-id="8840a-p113">Dal Blocco note o dall'editor di testo, copiare l'URL per la cartella dei documenti di ProjectX nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.</span><span class="sxs-lookup"><span data-stu-id="8840a-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
6. <span data-ttu-id="8840a-p114">Dal Blocco note o dall'editor di testo, copiare l'URL per il file Documents.docx nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.</span><span class="sxs-lookup"><span data-stu-id="8840a-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>
    
7. <span data-ttu-id="8840a-224">Chiudere la scheda **SharePoint** nel browser, fare clic sulla scheda **Microsoft Office Home**, fare clic sul nome **User 3** e quindi su **Disconnetti**.
</span><span class="sxs-lookup"><span data-stu-id="8840a-224">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>
    
<span data-ttu-id="8840a-225">Il sito di SharePoint Online isolato è ora pronto per la sperimentazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="8840a-225">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="8840a-226">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8840a-226">Next Step</span></span>

<span data-ttu-id="8840a-227">Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="8840a-227">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8840a-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8840a-228">See Also</span></span>

[<span data-ttu-id="8840a-229">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="8840a-229">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="8840a-230">Test Lab Guide (TLG) di adozione cloud</span><span class="sxs-lookup"><span data-stu-id="8840a-230">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="8840a-231">Ambiente di sviluppo/test della configurazione di base</span><span class="sxs-lookup"><span data-stu-id="8840a-231">Base Configuration dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)
  
[<span data-ttu-id="8840a-232">Ambiente di sviluppo/test di Office 365</span><span class="sxs-lookup"><span data-stu-id="8840a-232">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[<span data-ttu-id="8840a-233">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="8840a-233">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




