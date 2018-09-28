---
title: Distribuire un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Sintesi: istruzioni dettagliate per distribuire un nuovo sito del team di SharePoint Online isolato.'
ms.openlocfilehash: d233ec46b1e7257a92451c781afd6c61312f44b8
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345978"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="5c00d-103">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5c00d-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="5c00d-104">**Sintesi:** istruzioni dettagliate per distribuire un nuovo sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="5c00d-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="5c00d-p101">In questo articolo viene fornita una guida dettagliata alla distribuzione per creare e configurare un sito del team di SharePoint Online isolato in Microsoft Office 365. Questa procedura presuppone l'utilizzo di tre gruppi di SharePoint predefiniti e dei livelli di autorizzazione corrispondenti, con un singolo gruppo di Azure Active Directory (AD) per ogni livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="5c00d-107">Fase 1: Creare e compilare i gruppi di accesso del sito del team</span><span class="sxs-lookup"><span data-stu-id="5c00d-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="5c00d-108">In questa fase, vengono creati tre gruppi di accesso basati su Azure AD per i tre gruppi di SharePoint predefiniti e vengono popolati con gli account utente appropriati.</span><span class="sxs-lookup"><span data-stu-id="5c00d-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c00d-p102">La procedura seguente presuppone che tutti gli account utente necessari già esistano e siano dotati delle licenze appropriate. In caso contrario, aggiungerli e assegnare le licenze prima di procedere con il passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="5c00d-111">Passaggio 1: elencare gli amministratori di SharePoint Online per il sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="5c00d-112">Determinare il set di account utente corrispondenti agli amministratori di SharePoint Online per il sito del team isolato.</span><span class="sxs-lookup"><span data-stu-id="5c00d-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="5c00d-113">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare Windows PowerShell, fare un elenco dei loro nomi dell'entità utente (UPN), ad esempio, UPN: belindan@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5c00d-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="5c00d-114">Passaggio 2: elencare i membri del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="5c00d-115">Determinare il set di account utente corrispondenti ai membri del sito del team isolato, quelli che collaboreranno sulle risorse archiviate nel sito.</span><span class="sxs-lookup"><span data-stu-id="5c00d-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="5c00d-p103">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p103">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="5c00d-118">Passaggio 3: elencare i visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="5c00d-119">Determinare il set di account utente corrispondenti ai visualizzatori del sito del tam isolato, quelli che possono visualizzare le risorse archiviate nel sito ma non modificarle o collaborare direttamente sui contenuti.</span><span class="sxs-lookup"><span data-stu-id="5c00d-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="5c00d-p104">Se si gestiscono account utente e gruppi con Office 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p104">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs. If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="5c00d-122">I visualizzatori del sito potrebbero includere la direzione esecutiva, i consulenti legali o gli stakeholder interdipartimentali.</span><span class="sxs-lookup"><span data-stu-id="5c00d-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="5c00d-123">Passaggio 4: creare i tre gruppi di accesso per il sito di Azure AD</span><span class="sxs-lookup"><span data-stu-id="5c00d-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="5c00d-124">È necessario creare i gruppi di accesso seguenti in Azure AD:</span><span class="sxs-lookup"><span data-stu-id="5c00d-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="5c00d-125">Amministratori del sito (che contiene l'elenco creato al passaggio 1)</span><span class="sxs-lookup"><span data-stu-id="5c00d-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="5c00d-126">Membri del sito (che contiene l'elenco creato al passaggio 2)</span><span class="sxs-lookup"><span data-stu-id="5c00d-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="5c00d-127">Visualizzatori del sito (che contiene l'elenco creato al passaggio 3)</span><span class="sxs-lookup"><span data-stu-id="5c00d-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="5c00d-128">Nel browser, accedere al portale di Azure in [https://portal.azure.com](https://portal.azure.com) e accedere con le credenziali di un account assegnato con ruolo di amministratore Gestione utente o amministratore aziendale.</span><span class="sxs-lookup"><span data-stu-id="5c00d-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="5c00d-129">Nel portale di Azure fare clic su **Azure Active Directory > Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="5c00d-130">Nel pannello **Gruppi - Tutti i gruppi** fare clic su **+ Nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="5c00d-131">Nel pannello **Gruppo**:</span><span class="sxs-lookup"><span data-stu-id="5c00d-131">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="5c00d-132">Selezionare **Office 365** in **Tipo di gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-132">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="5c00d-133">Digitare il nome del gruppo nella **casella Nome**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="5c00d-134">Digitare una descrizione del gruppo nella **descrizione del gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="5c00d-135">Selezionare **Assegnato** in **Tipo di appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="5c00d-136">Fare clic su **Crea** e quindi chiudere il pannello **Gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="5c00d-137">Ripetere i passaggi da 3 a 5 per i gruppi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5c00d-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5c00d-p105">È necessario utilizzare il portale di Azure per creare i gruppi che dispongono di funzionalità di Office attivata. Se un sito di SharePoint Online isolato in seguito è configurato come sito altamente riservati con un'etichetta di protezione informazioni Azure (AIP) per crittografare i file e assegnare autorizzazioni a gruppi specifici, i gruppi autorizzati devono essere stati creati con caratteristiche di Office abilitato. È possibile modificare l'impostazione di funzionalità di Office di un gruppo di Azure Active Directory dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p105">You need to use the Azure portal to create the groups so that they have Office features enabled. If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection (AIP) label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled. You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="5c00d-141">Di seguito è la configurazione risultante con i gruppi di accesso di tre siti.</span><span class="sxs-lookup"><span data-stu-id="5c00d-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![I tre gruppi di accesso per la distribuzione di un sito di SharePoint Online isolato.](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="5c00d-p106">Passaggio 5. Aggiungere gli account utente ai gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="5c00d-p106">Step 5. Add the user accounts to the access groups</span></span>

<span data-ttu-id="5c00d-145">In questo passaggio, eseguire la procedura riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="5c00d-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="5c00d-146">Aggiungere l'elenco di utenti creato nel passaggio 1 al gruppo di accesso degli amministratori del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="5c00d-147">Aggiungere l'elenco di utenti creato nel passaggio 2 al gruppo di accesso dei membri del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="5c00d-148">Aggiungere l'elenco di utenti creato nel passaggio 3 al gruppo di accesso dei visualizzatori del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="5c00d-149">Se si gestiscono account utente e gruppi con Windows Server AD, aggiungere gli utenti ai gruppi di accesso appropriati utilizzando le normali procedure di gestione di gruppi e utenti di Windows Server AD e attendere la sincronizzazione con l'abbonamento a Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c00d-149">If you are managing user accounts and groups through Windows Server AD, add users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="5c00d-p107">Se si gestiscono account utente e gruppi con Office 365, è possibile utilizzare l'interfaccia di amministrazione di Office o PowerShell. Se si dispone di nomi di gruppo duplicati per uno dei gruppi di accesso, è necessario utilizzare l'interfaccia di amministrazione di Office.</span><span class="sxs-lookup"><span data-stu-id="5c00d-p107">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell. If you have duplicate group names for any of the access groups, you should use the Office Admin center.</span></span>
  
<span data-ttu-id="5c00d-152">Per l'interfaccia di amministrazione di Office, accedere con un account utente che è stato assegnato il ruolo di amministratore degli Account utente o amministratore aziendale e utilizzare gruppi aggiungere gli account utente appropriati e ai gruppi di accesso appropriato.</span><span class="sxs-lookup"><span data-stu-id="5c00d-152">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="5c00d-153">Per PowerShell, consultare [Connettersi con il modulo Azure Active Directory V2 PowerShell](https://go.microsoft.com/fwlink/?linkid=842218).</span><span class="sxs-lookup"><span data-stu-id="5c00d-153">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>
  
<span data-ttu-id="5c00d-154">Successivamente, utilizzare il seguente blocco di comando per aggiungere un singolo account utente a un gruppo di accesso:</span><span class="sxs-lookup"><span data-stu-id="5c00d-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="5c00d-155">Per un file di testo che contiene tutti i comandi di PowerShell e un foglio di lavoro di configurazione di Excel che genera comandi di PowerShell in base ai nomi degli account utente e di gruppo, scaricare [Kit di distribuzione del sito di SharePoint Online Team isolato](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span><span class="sxs-lookup"><span data-stu-id="5c00d-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="5c00d-156">Se gli UPN degli account utente per uno dei gruppi di accesso è archiviato in un file di testo, è possibile utilizzare il seguente blocco di comandi PowerShell per aggiungerli tutti contemporaneamente:</span><span class="sxs-lookup"><span data-stu-id="5c00d-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="5c00d-157">Per PowerShell, utilizzare il seguente blocco di comando per aggiungere un singolo gruppo a un gruppo di accesso:</span><span class="sxs-lookup"><span data-stu-id="5c00d-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="5c00d-158">Dovrebbero essere visualizzati i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="5c00d-158">The results should be the following:</span></span>
  
- <span data-ttu-id="5c00d-159">Gruppo di Azure Active Directory gli amministratori del sito contiene gli account utente amministratore del sito o i gruppi</span><span class="sxs-lookup"><span data-stu-id="5c00d-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="5c00d-160">Il gruppo di Azure Active Directory di membri del sito contiene gli account utente membro del sito o i gruppi</span><span class="sxs-lookup"><span data-stu-id="5c00d-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="5c00d-161">Gruppo visualizzatori Azure Active Directory siti contiene gli account utente o gruppi che possono visualizzare solo il contenuto del sito</span><span class="sxs-lookup"><span data-stu-id="5c00d-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="5c00d-162">Convalidare l'elenco dei membri di ogni gruppo di accesso con l'interfaccia di amministrazione di Office o con il seguente blocco di comandi PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5c00d-162">Validate the list of group members for each access group with the Office Admin center or with the following PowerShell command block:</span></span>
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="5c00d-163">Di seguito è la configurazione risultante con i gruppi di accesso di tre siti popolato con account utente o gruppo.</span><span class="sxs-lookup"><span data-stu-id="5c00d-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![I tre gruppi di accesso popolati con account utente.](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="5c00d-165">Fase 2: creare e configurare il sito del team isolato</span><span class="sxs-lookup"><span data-stu-id="5c00d-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="5c00d-166">In questa fase, viene creato il sito di SharePoint Online isolato e vengono configurate le autorizzazioni per i livelli di autorizzazione di SharePoint Online predefiniti affinché vengano utilizzati i nuovi gruppi di accesso basati su Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c00d-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="5c00d-167">Creare innanzitutto il sito del team di SharePoint Online seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="5c00d-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="5c00d-p108">Accedere al portale di Office 365 con un account che verrà usato anche per gestire il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="5c00d-p108">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="5c00d-170">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="5c00d-171">Nella nuova **scheda SharePoint** del browser fare clic su **+ Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="5c00d-172">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="5c00d-173">In **nome sito**digitare un nome per il sito del team.</span><span class="sxs-lookup"><span data-stu-id="5c00d-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="5c00d-174">Nella **descrizione del sito del Team,** digitare una descrizione facoltativa dello scopo del sito.</span><span class="sxs-lookup"><span data-stu-id="5c00d-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="5c00d-175">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="5c00d-176">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="5c00d-177">Successivamente, dal nuovo sito del team di SharePoint Online configurare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5c00d-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="5c00d-178">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="5c00d-179">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="5c00d-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="5c00d-180">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="5c00d-181">Nella finestra di dialogo **Impostazioni di richieste di accesso** , deselezionare **Consenti membro per condividere il sito e i singoli file e cartelle** e **Consenti richieste di accesso** (in modo che tutti i tre caselle di controllo è deselezionate), quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="5c00d-182">Nella scheda **autorizzazioni** del browser fare clic su \*\* \<nome del sito > membri\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c00d-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="5c00d-183">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="5c00d-184">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei membri del sito di accesso, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="5c00d-185">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="5c00d-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="5c00d-186">Fare clic su \*\* \<nome del sito > proprietari\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c00d-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="5c00d-187">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="5c00d-188">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di accesso degli amministratori del sito, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="5c00d-189">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="5c00d-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="5c00d-190">Fare clic su \*\* \<nome del sito > visitatori\*\* nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c00d-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="5c00d-191">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="5c00d-192">Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei visualizzatori del sito di accesso, selezionarlo e fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="5c00d-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="5c00d-193">Chiudere la scheda **Autorizzazioni** del browser.</span><span class="sxs-lookup"><span data-stu-id="5c00d-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="5c00d-194">I risultati di queste impostazioni delle autorizzazioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c00d-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="5c00d-195">Il \*\* \<nome del sito > proprietari\*\* gruppo di SharePoint contiene il gruppo di accesso gli amministratori del sito, in cui tutti i membri dispongono del livello di autorizzazione **controllo completo** .</span><span class="sxs-lookup"><span data-stu-id="5c00d-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="5c00d-196">Il \*\* \<nome del sito > membri\*\* gruppo di SharePoint contiene il gruppo di accesso membri del sito, in cui tutti i membri dispongono del livello di autorizzazione **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="5c00d-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="5c00d-197">Il \*\* \<nome del sito > visitatori\*\* gruppo di SharePoint contiene il gruppo di accesso i visualizzatori del sito, in cui tutti i membri dispongono del livello di autorizzazione **lettura** .</span><span class="sxs-lookup"><span data-stu-id="5c00d-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="5c00d-198">I membri non hanno la possibilità di invitare altri membri o di richiedere l'accesso per utenti non membri.
</span><span class="sxs-lookup"><span data-stu-id="5c00d-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="5c00d-199">Di seguito è la configurazione risultante con i tre gruppi di SharePoint per il sito configurato per l'utilizzo di tre gruppi di accesso, popolati con gli account utente o gruppi di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c00d-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![La configurazione finale del sito di SharePoint Online isolato con gruppi di accesso e account utente.](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="5c00d-201">I membri del sito, tramite l'appartenenza a uno dei gruppi di accesso, possono ora collaborare utilizzando le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="5c00d-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="5c00d-202">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="5c00d-202">Next step</span></span>

<span data-ttu-id="5c00d-203">Se è necessario modificare l'appartenenza al gruppo di accesso del sito o creare una cartella di documenti con autorizzazioni personalizzate, vedere [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="5c00d-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c00d-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c00d-204">See Also</span></span>

[<span data-ttu-id="5c00d-205">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="5c00d-205">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="5c00d-206">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5c00d-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="5c00d-207">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="5c00d-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



