---
title: Distribuire siti di SharePoint Online per tre livelli di protezione
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/05/2018
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
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Sintesi: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.'
ms.openlocfilehash: 54392194f7ac5ce90337df3f33e23db595b1aa5c
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345828"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="bd975-103">Distribuire siti di SharePoint Online per tre livelli di protezione</span><span class="sxs-lookup"><span data-stu-id="bd975-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

 <span data-ttu-id="bd975-104">**Sintesi**: creare e configurare siti del team di SharePoint Online per diversi livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="bd975-104">**Summary:** Create and configure SharePoint Online team sites for various levels of information protection.</span></span>
  
<span data-ttu-id="bd975-p101">Usare i passaggi descritti in questo articolo per progettare e distribuire siti del team di SharePoint Online di base, sensibili e con riservatezza elevata. Per altre informazioni su questi tre livelli di protezione, vedere [Proteggere siti e file di SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bd975-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="bd975-107">Siti del team di SharePoint Online di base</span><span class="sxs-lookup"><span data-stu-id="bd975-107">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="bd975-p102">La protezione di siti di base include siti del team pubblici e privati. I siti del team pubblici possono essere individuati e usati da qualsiasi persona dell'organizzazione. I siti privati possono essere individuati e usati solo dai membri del gruppo di Office 365 associato al sito del team. Entrambi questi tipi di siti del team consentono ai membri di condividere il sito con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="bd975-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="bd975-112">Pubblico</span><span class="sxs-lookup"><span data-stu-id="bd975-112">Public</span></span>

<span data-ttu-id="bd975-113">Per creare un sito del team di SharePoint Online di base con accesso pubblico e autorizzazioni, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd975-113">To create a baseline SharePoint Online team site with public access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="bd975-p103">Accedere al portale di Office 365 con un account che verrà usato anche per gestire il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="bd975-p103">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bd975-116">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bd975-116">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bd975-117">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="bd975-117">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bd975-118">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="bd975-118">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bd975-119">In **Nome sito** digitare il nome del sito del team pubblico.</span><span class="sxs-lookup"><span data-stu-id="bd975-119">In **Site name**, type a name for the public team site.</span></span> 
    
6. <span data-ttu-id="bd975-120">In **Team site description** (Descrizione sito del team) digitare una descrizione dello scopo del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-120">In **Team site description**, type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="bd975-121">In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd975-121">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bd975-122">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bd975-122">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="bd975-123">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="bd975-123">Here is your resulting configuration.</span></span>
  
![Protezione di livello di base per un sito del team di SharePoint Online pubblico.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="bd975-125">Private</span><span class="sxs-lookup"><span data-stu-id="bd975-125">Private</span></span>

<span data-ttu-id="bd975-126">Per creare un sito del team di SharePoint Online di base con accesso privato e autorizzazioni, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="bd975-126">To create a baseline SharePoint Online team site with private access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="bd975-p104">Accedere al portale di Office 365 con un account che verrà usato anche per gestire il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="bd975-p104">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bd975-129">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bd975-129">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bd975-130">Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="bd975-130">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bd975-131">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="bd975-131">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bd975-132">In **Nome sito** digitare il nome del sito del team privato.</span><span class="sxs-lookup"><span data-stu-id="bd975-132">In **Site name**, type a name for the private team site.</span></span> 
    
6. <span data-ttu-id="bd975-133">In **Team site description** (Descrizione sito del team) digitare una descrizione dello scopo del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-133">In **Team site description,** type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="bd975-134">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd975-134">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bd975-135">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) in **Aggiungi membri** digitare i nomi degli account utente che hanno accesso a questo sito del team privato.</span><span class="sxs-lookup"><span data-stu-id="bd975-135">On the **Who do you want to add?** pane, in **Add members**, type the names of user accounts that have access to this private team site.</span></span>
    
9. <span data-ttu-id="bd975-136">Quando il set iniziale di membri è stato aggiunto al sito, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bd975-136">When you are done adding the initial set of members to the site, click **Finish**</span></span>
    
<span data-ttu-id="bd975-137">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="bd975-137">Here is your resulting configuration.</span></span>
  
![Protezione di livello di base per un sito del team di SharePoint Online privato.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="bd975-139">Siti del team di SharePoint Online sensibili</span><span class="sxs-lookup"><span data-stu-id="bd975-139">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="bd975-140">Un sito del team di SharePoint Online riservato è un sito del team isolato. Ciò significa che le autorizzazioni vengono controllate tramite l'appartenenza ai gruppi di SharePoint anziché tramite l’appartenenza al gruppo di Office 365 associato al sito del team.</span><span class="sxs-lookup"><span data-stu-id="bd975-140">A sensitive SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="bd975-141">Per creare un sito del team isolato, sono disponibili due passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="bd975-141">To create an isolated team site, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="bd975-142">Passaggio 1: Progettare un sito isolato</span><span class="sxs-lookup"><span data-stu-id="bd975-142">Step 1: Design your isolated site</span></span>

<span data-ttu-id="bd975-143">Per progettare un sito del team isolato è necessario stabilire:</span><span class="sxs-lookup"><span data-stu-id="bd975-143">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="bd975-144">I gruppi di SharePoint e i livelli di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd975-144">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="bd975-145">Il set di gruppi di accesso che saranno membri dei gruppi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bd975-145">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="bd975-146">Il set di gruppi di accesso consigliato è uno per i membri del sito, uno per i visualizzatori del sito e uno per gli amministratori del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-146">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="bd975-147">Se verranno usati gruppi nidificati all'interno dei gruppi di accesso.</span><span class="sxs-lookup"><span data-stu-id="bd975-147">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="bd975-148">Ad esempio, la struttura dei gruppi e i livelli di autorizzazione consigliati sono simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd975-148">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="bd975-149">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="bd975-149">**SharePoint group**</span></span>|<span data-ttu-id="bd975-150">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="bd975-150">**Permission level**</span></span>|<span data-ttu-id="bd975-151">**Gruppo di accesso (esempi)**</span><span class="sxs-lookup"><span data-stu-id="bd975-151">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd975-152">Membri di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-152">[site name] Members</span></span>  <br/> |<span data-ttu-id="bd975-153">Modifica</span><span class="sxs-lookup"><span data-stu-id="bd975-153">Edit</span></span>  <br/> |<span data-ttu-id="bd975-154">Membri di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-154">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="bd975-155">Visitatori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-155">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="bd975-156">Lettura</span><span class="sxs-lookup"><span data-stu-id="bd975-156">Read</span></span>  <br/> |<span data-ttu-id="bd975-157">Visualizzatori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-157">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="bd975-158">Proprietari di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-158">[site name] Owners</span></span>  <br/> |<span data-ttu-id="bd975-159">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="bd975-159">Full control</span></span>  <br/> |<span data-ttu-id="bd975-160">Amministratori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-160">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="bd975-p105">Per un sito del team, i gruppi e i livelli di autorizzazione di SharePoint vengono creati per impostazione predefinita. È necessario stabilire i nomi dei gruppi di accesso.</span><span class="sxs-lookup"><span data-stu-id="bd975-p105">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="bd975-163">Per i dettagli del processo di progettazione, vedere [Progettare un sito del team SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bd975-163">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="bd975-164">Passaggio 2: Distribuire un sito isolato</span><span class="sxs-lookup"><span data-stu-id="bd975-164">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="bd975-165">Per distribuire un sito isolato è innanzitutto necessario:</span><span class="sxs-lookup"><span data-stu-id="bd975-165">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="bd975-166">Stabilire gli account utente e i gruppi da aggiungere a ogni gruppo di accesso.</span><span class="sxs-lookup"><span data-stu-id="bd975-166">Determine the user accounts and groups to add to each of your access groups.</span></span>
    
- <span data-ttu-id="bd975-167">Creare i gruppi di accesso e aggiungere i membri di tipo utente e gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd975-167">Create the access groups and add the user and group members.</span></span>
    
<span data-ttu-id="bd975-168">Per istruzioni dettagliate, vedere la **Fase 1** di [Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bd975-168">For the detailed steps, see **Phase 1** of [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="bd975-169">Successivamente, creare il sito del team di SharePoint Online seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="bd975-169">Next, you create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="bd975-p106">Accedere al portale di Office 365 con un account che verrà usato anche per gestire il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="bd975-p106">Sign in to the Office 365 portal with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator). For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="bd975-172">Nell'elenco dei riquadri fare clic su **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bd975-172">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="bd975-173">Nella nuova **scheda SharePoint** del browser fare clic su **+ Crea sito**.</span><span class="sxs-lookup"><span data-stu-id="bd975-173">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="bd975-174">Nella pagina **Crea sito** fare clic su **Sito del team**.</span><span class="sxs-lookup"><span data-stu-id="bd975-174">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="bd975-175">In **Nome sito** digitare il nome del sito del team privato.</span><span class="sxs-lookup"><span data-stu-id="bd975-175">In **Site name**, type a name for the private team site.</span></span>
    
6. <span data-ttu-id="bd975-176">Nella descrizione **Sito del team** digitare una descrizione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bd975-176">In **Team site description**, type an optional description.</span></span>
    
7. <span data-ttu-id="bd975-177">In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bd975-177">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bd975-178">Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bd975-178">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="bd975-179">Dal nuovo sito del team di SharePoint Online configurare quindi le autorizzazioni seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="bd975-179">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>
  
1. <span data-ttu-id="bd975-p107">Determinare il Nome dell'entità utente (UPN) di cui l'amministratore IT o altra persona sarà responsabile per rispondere a e indirizzare le richieste di accesso al sito (un esempio di UPN è belindan@contoso.com). Scrivere l'UPN di seguito: ![](./media/Common-Images/TableLine.png).</span><span class="sxs-lookup"><span data-stu-id="bd975-p107">Determine the User Principal Name (UPN) of the IT administrator or other person who will be responsible for responding to and addressing requests for access to the site (belindan@contoso.com is an example of a UPN). Write that UPN here: ![](./media/Common-Images/TableLine.png).</span></span>
    
2. <span data-ttu-id="bd975-182">Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="bd975-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
3. <span data-ttu-id="bd975-183">Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).</span><span class="sxs-lookup"><span data-stu-id="bd975-183">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
4. <span data-ttu-id="bd975-184">Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="bd975-184">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
5. <span data-ttu-id="bd975-185">Nella finestra di dialogo **Impostazioni richieste di accesso**:</span><span class="sxs-lookup"><span data-stu-id="bd975-185">In the **Access Requests Settings** dialog box:</span></span>
    
  - <span data-ttu-id="bd975-186">Deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**.</span><span class="sxs-lookup"><span data-stu-id="bd975-186">Clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes.</span></span>
    
  - <span data-ttu-id="bd975-187">Digitare il nome dell'entità utente dell'amministratore IT al passaggio 1 in **Invia tutte le richieste di accesso**.</span><span class="sxs-lookup"><span data-stu-id="bd975-187">Type the UPN of your IT administrator from step 1 in **Send all requests for access**.</span></span>
    
  - <span data-ttu-id="bd975-188">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd975-188">Click **OK**.</span></span>
    
6. <span data-ttu-id="bd975-189">Nella scheda **Autorizzazioni** del browser fare clic su **Membri di [nome sito]** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd975-189">On the **Permissions** tab of your browser, click **[site name] Members** in the list.</span></span>
    
7. <span data-ttu-id="bd975-190">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bd975-190">In **People and Groups**, click **New**.</span></span>
    
8. <span data-ttu-id="bd975-191">Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso dei membri del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="bd975-191">In the **Share** dialog box, type the name of your site members access group for this site, select it, and then click **Share**.</span></span>
    
9. <span data-ttu-id="bd975-192">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="bd975-192">Click the back button on your browser.</span></span>
    
10. <span data-ttu-id="bd975-193">Fare clic su **Proprietari di <nome del sito>** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd975-193">Click **[site name] Owners** in the list.</span></span>
    
11. <span data-ttu-id="bd975-194">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bd975-194">In **People and Groups**, click **New**.</span></span>
    
12. <span data-ttu-id="bd975-195">Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso degli amministratori del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="bd975-195">In the **Share** dialog box, type the name of the site administrators access group for this site, select it, and then click **Share**.</span></span>
    
13. <span data-ttu-id="bd975-196">Fare clic sul pulsante Indietro del browser.</span><span class="sxs-lookup"><span data-stu-id="bd975-196">Click the back button on your browser.</span></span>
    
14. <span data-ttu-id="bd975-197">Fare clic su **Visitatori di <nome del sito>** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd975-197">Click **[site name] Visitors** in the list.</span></span>
    
15. <span data-ttu-id="bd975-198">In **Utenti e gruppi** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bd975-198">In **People and Groups**, click **New**.</span></span>
    
16. <span data-ttu-id="bd975-199">Nella finestra di dialogo **Condividi** digitare il nome del gruppo di accesso dei visualizzatori del sito per questo sito, selezionarlo e quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="bd975-199">In the **Share** dialog box, type the name of the site viewers access group for this site, select it, and then click **Share**.</span></span>
    
17. <span data-ttu-id="bd975-200">Chiudere la scheda **Autorizzazioni** del browser.</span><span class="sxs-lookup"><span data-stu-id="bd975-200">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="bd975-201">I risultati di queste impostazioni delle autorizzazioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd975-201">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="bd975-202">Il gruppo di SharePoint **Proprietari di [nome sito]** contiene il gruppo di accesso degli amministratori del sito in cui tutti i membri hanno il livello di autorizzazione **Controllo completo**.</span><span class="sxs-lookup"><span data-stu-id="bd975-202">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="bd975-203">Il gruppo di SharePoint **Membri di [nome sito]** contiene il gruppo di accesso dei membri del sito in cui tutti i membri hanno il livello di autorizzazione **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bd975-203">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="bd975-204">Il gruppo di SharePoint **Visitatori di [nome sito]** contiene il gruppo di accesso dei visualizzatori del sito in cui tutti i membri hanno il livello di autorizzazione **Lettura**.</span><span class="sxs-lookup"><span data-stu-id="bd975-204">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="bd975-205">La possibilità per i membri di invitare altri membri è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bd975-205">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="bd975-206">La possibilità per gli utenti non membri di richiedere l'accesso è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bd975-206">The ability for non-members to request access is enabled.</span></span>
    
<span data-ttu-id="bd975-207">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="bd975-207">Here is your resulting configuration.</span></span>
  
![Protezione di livello riservato per un sito del team di SharePoint Online isolato.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="bd975-209">I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-209">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="bd975-210">Siti del team di SharePoint Online con riservatezza elevata</span><span class="sxs-lookup"><span data-stu-id="bd975-210">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="bd975-211">Un sito del team di SharePoint Online con riservatezza elevata è un sito del team isolato in cui le autorizzazioni sono controllate tramite l'appartenenza ai gruppi di SharePoint anziché l'appartenenza al gruppo di Office 365 associato al sito del team.</span><span class="sxs-lookup"><span data-stu-id="bd975-211">A highly confidential SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="bd975-212">La creazione di un sito del team isolato per le informazioni e la collaborazione con riservatezza elevata richiede due passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="bd975-212">To create an isolated team site for highly confidential information and collaboration, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="bd975-213">Passaggio 1: Progettare un sito isolato</span><span class="sxs-lookup"><span data-stu-id="bd975-213">Step 1: Design your isolated site</span></span>

<span data-ttu-id="bd975-214">Per progettare un sito del team isolato è necessario stabilire:</span><span class="sxs-lookup"><span data-stu-id="bd975-214">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="bd975-215">I gruppi di SharePoint e i livelli di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd975-215">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="bd975-216">Il set di gruppi di accesso che saranno membri dei gruppi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bd975-216">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="bd975-217">Il set di gruppi di accesso consigliato è uno per i membri del sito, uno per i visualizzatori del sito e uno per gli amministratori del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-217">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="bd975-218">Se verranno usati gruppi nidificati all'interno dei gruppi di accesso.</span><span class="sxs-lookup"><span data-stu-id="bd975-218">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="bd975-219">Ad esempio, la struttura dei gruppi e i livelli di autorizzazione consigliati sono simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd975-219">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="bd975-220">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="bd975-220">**SharePoint group**</span></span>|<span data-ttu-id="bd975-221">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="bd975-221">**Permission level**</span></span>|<span data-ttu-id="bd975-222">**Gruppo di accesso (esempi)**</span><span class="sxs-lookup"><span data-stu-id="bd975-222">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd975-223">Membri di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-223">[site name] Members</span></span>  <br/> |<span data-ttu-id="bd975-224">Modifica</span><span class="sxs-lookup"><span data-stu-id="bd975-224">Edit</span></span>  <br/> |<span data-ttu-id="bd975-225">Membri di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-225">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="bd975-226">Visitatori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-226">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="bd975-227">Lettura</span><span class="sxs-lookup"><span data-stu-id="bd975-227">Read</span></span>  <br/> |<span data-ttu-id="bd975-228">Visualizzatori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-228">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="bd975-229">Proprietari di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-229">[site name] Owners</span></span>  <br/> |<span data-ttu-id="bd975-230">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="bd975-230">Full control</span></span>  <br/> |<span data-ttu-id="bd975-231">Amministratori di [nome sito]</span><span class="sxs-lookup"><span data-stu-id="bd975-231">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="bd975-p108">Per un sito del team, i gruppi e i livelli di autorizzazione di SharePoint vengono creati per impostazione predefinita. È necessario stabilire i nomi dei gruppi di accesso.</span><span class="sxs-lookup"><span data-stu-id="bd975-p108">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="bd975-234">Per i dettagli del processo di progettazione, vedere [Progettare un sito del team SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bd975-234">For the details of the design process, see [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="bd975-235">Passaggio 2: Distribuire un sito isolato</span><span class="sxs-lookup"><span data-stu-id="bd975-235">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="bd975-236">Per distribuire un sito isolato è innanzitutto necessario:</span><span class="sxs-lookup"><span data-stu-id="bd975-236">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="bd975-237">Determinare l’utente e i membri del gruppo di ciascun gruppo di accesso</span><span class="sxs-lookup"><span data-stu-id="bd975-237">Determine the user and group members of each of your access groups</span></span>
    
- <span data-ttu-id="bd975-238">Creare gruppi di accesso e aggiungere l’utente e i membri dei gruppi</span><span class="sxs-lookup"><span data-stu-id="bd975-238">Create the access groups and add the user and group members</span></span>
    
- <span data-ttu-id="bd975-239">Creare un sito del team isolato che utilizzi i gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="bd975-239">Create an isolated team site that uses your access groups</span></span>
    
<span data-ttu-id="bd975-240">Per istruzioni dettagliate, vedere [Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bd975-240">For the detailed steps, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="bd975-241">I risultati di queste impostazioni delle autorizzazioni sono:</span><span class="sxs-lookup"><span data-stu-id="bd975-241">The results of the permission settings are:</span></span>
  
- <span data-ttu-id="bd975-242">Il gruppo di SharePoint **Proprietari di [nome sito]** contiene il gruppo di accesso degli amministratori del sito in cui tutti i membri hanno il livello di autorizzazione **Controllo completo**.</span><span class="sxs-lookup"><span data-stu-id="bd975-242">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="bd975-243">Il gruppo di SharePoint **Membri di [nome sito]** contiene il gruppo di accesso dei membri del sito in cui tutti i membri hanno il livello di autorizzazione **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bd975-243">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="bd975-244">Il gruppo di SharePoint **Visitatori di [nome sito]** contiene il gruppo di accesso dei visualizzatori del sito in cui tutti i membri hanno il livello di autorizzazione **Lettura**.</span><span class="sxs-lookup"><span data-stu-id="bd975-244">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="bd975-245">La possibilità per i membri di invitare altri membri è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bd975-245">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="bd975-246">La possibilità per gli utenti non membri di richiedere l'accesso è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bd975-246">The ability for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="bd975-247">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="bd975-247">Here is your resulting configuration.</span></span>
  
![Protezione di livello estremamente riservato per un team di SharePoint Online isolato.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="bd975-249">I membri del sito, attraverso l'appartenenza a uno dei gruppi di accesso, possono ora collaborare in modo sicuro alle risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="bd975-249">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="bd975-250">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bd975-250">Next step</span></span>

[<span data-ttu-id="bd975-251">Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="bd975-251">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)
    
## <a name="see-also"></a><span data-ttu-id="bd975-252">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd975-252">See also</span></span>

[<span data-ttu-id="bd975-253">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd975-253">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="bd975-254">Proteggere i siti di SharePoint Online in un ambiente di sviluppo e di testing</span><span class="sxs-lookup"><span data-stu-id="bd975-254">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="bd975-255">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="bd975-255">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="bd975-256">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="bd975-256">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)



