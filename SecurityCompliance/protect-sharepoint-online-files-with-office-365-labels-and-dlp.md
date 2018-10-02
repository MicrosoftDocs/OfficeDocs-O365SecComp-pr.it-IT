---
title: Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
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
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Sintesi: applicare le etichette di Office 365 e i criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.'
ms.openlocfilehash: f8d835481c0eac00be11f7934c1d74b8a2d08d78
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345968"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a><span data-ttu-id="aa22a-103">Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="aa22a-103">Protect SharePoint Online files with Office 365 labels and DLP</span></span>

 <span data-ttu-id="aa22a-104">**Sintesi:** applicare le etichette di Office 365 e i criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="aa22a-104">**Summary:** Apply Office 365 labels and data loss prevention (DLP) policies for SharePoint Online team sites with various levels of information protection.</span></span>
  
<span data-ttu-id="aa22a-p101">Usare i passaggi descritti in questo articolo per progettare e implementare le etichette di Office 365 e i criteri di protezione della perdita dei dati (DLP) per i siti del team di SharePoint Online di base, riservati ed estremamente riservati. Per ulteriori informazioni su questi tre livelli di protezione, vedere [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="aa22a-p101">Use the steps in this article to design and deploy Office 365 labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="aa22a-107">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="aa22a-107">How this works</span></span>
1. <span data-ttu-id="aa22a-p102">Creare le etichette desiderate e pubblicarle. La pubblicazione può richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p102">Create the desired labels and publish these. It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="aa22a-110">Per i siti di SharePoint desiderati, modificare le impostazioni della raccolta documenti per applicare un'etichetta agli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="aa22a-110">For the desired SharePoint sites, edit the document library settings to apply a label to items in the library.</span></span>
3. <span data-ttu-id="aa22a-111">Creare criteri di prevenzione della perdita dei dati per intervenire in base alle etichette.</span><span class="sxs-lookup"><span data-stu-id="aa22a-111">Create DLP policies to take action based on the labels.</span></span>

<span data-ttu-id="aa22a-p103">Quando gli utenti aggiungono un documento alla raccolta, al documento viene assegnata un'etichetta predefinita. È possibile modificare l'etichetta, se necessario. Quando un utente condivide un documento all'esterno dell'organizzazione, i criteri di prevenzione della perdita dei dati verificano se è assegnata un'etichetta e intervengono in caso di corrispondenza all'etichetta. Quindi cercano la corrispondenza anche ad altri criteri, ad esempio la protezione dei file con i numeri di carta di credito, se questo tipo di criterio è configurato.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p103">When users add a document to the library, the document will receive the assigned label by default. Users can change the label,if needed. When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label. DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="aa22a-116">Etichette di Office 365 per i siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="aa22a-116">Office 365 labels for your SharePoint Online sites</span></span>

<span data-ttu-id="aa22a-117">Esistono tre fasi per creare e poi assegnare le etichette di Office 365 ai siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa22a-117">There are three phases to creating and then assigning Office 365 labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-office-365-label-names"></a><span data-ttu-id="aa22a-118">Fase 1: definire i nomi etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa22a-118">Phase 1: Determine the Office 365 label names</span></span>

<span data-ttu-id="aa22a-p104">In questa fase si definiscono i nomi etichette di Office 365 per i quattro livelli di protezione delle informazioni applicati ai siti del team di SharePoint Online. La tabella seguente elenca i nomi consigliati per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p104">In this phase, you determine the names of your Office 365 labels for the four levels of information protection applied to SharePoint Online team sites. The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="aa22a-121">**Livello di protezione del sito del team di SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="aa22a-121">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="aa22a-122">**Nome etichetta**</span><span class="sxs-lookup"><span data-stu-id="aa22a-122">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa22a-123">Pubblico di base</span><span class="sxs-lookup"><span data-stu-id="aa22a-123">Baseline-Public</span></span>  <br/> |<span data-ttu-id="aa22a-124">Pubblico interno</span><span class="sxs-lookup"><span data-stu-id="aa22a-124">Internal public</span></span>  <br/> |
|<span data-ttu-id="aa22a-125">Privato di base</span><span class="sxs-lookup"><span data-stu-id="aa22a-125">Baseline-Private</span></span>  <br/> |<span data-ttu-id="aa22a-126">Private</span><span class="sxs-lookup"><span data-stu-id="aa22a-126">Private</span></span>  <br/> |
|<span data-ttu-id="aa22a-127">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="aa22a-127">Sensitive</span></span>  <br/> |<span data-ttu-id="aa22a-128">Dati sensibili</span><span class="sxs-lookup"><span data-stu-id="aa22a-128">Sensitive</span></span>  <br/> |
|<span data-ttu-id="aa22a-129">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="aa22a-129">Highly Confidential</span></span>  <br/> |<span data-ttu-id="aa22a-130">Highly Confidential (Riservatezza elevata)</span><span class="sxs-lookup"><span data-stu-id="aa22a-130">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a><span data-ttu-id="aa22a-131">Fase 2: creare le etichette di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa22a-131">Phase 2: Create the Office 365 labels</span></span>

<span data-ttu-id="aa22a-132">In questa fase si creano e poi pubblicano le etichette specificate per i diversi livelli di protezione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="aa22a-132">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
<span data-ttu-id="aa22a-133">Per creare le etichette, è possibile utilizzare l'interfaccia di amministrazione di Office 365 o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa22a-133">To create the labels, you can use the Office 365 Admin center or Microsoft PowerShell.</span></span>
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a><span data-ttu-id="aa22a-134">Creare etichette di Office 365 con l'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa22a-134">Create Office 365 labels with the Office 365 Admin center</span></span>

1. <span data-ttu-id="aa22a-p105">Accedere al portale di Office 365 con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società. Per informazioni, vedere [Dove accedere a Office 365 per le aziende](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="aa22a-p105">Sign in to the Office 365 portal with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="aa22a-137">Dalla scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-137">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="aa22a-138">Dalla nuova scheda **Interfaccia di amministrazione di Office** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-138">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="aa22a-139">Dalla nuova scheda **Home: Sicurezza e conformità** del browser fare clic su Classificazioni > Etichette.</span><span class="sxs-lookup"><span data-stu-id="aa22a-139">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="aa22a-140">Dal riquadro **Home > Etichette** fare clic su **Create a label** (Crea un'etichetta).</span><span class="sxs-lookup"><span data-stu-id="aa22a-140">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="aa22a-141">Nel riquadro \*\*Denomina l'etichetta \*\*, digitare il nome dell’etichetta e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-141">On the **Name your label** pane, type the name of the label, and then click **Next**.</span></span>
    
7. <span data-ttu-id="aa22a-142">Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-142">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="aa22a-143">Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-143">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="aa22a-144">Ripetere i passaggi da 5 a 8 per etichette aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="aa22a-144">Repeat steps 5-8 for your additional labels.</span></span>
    
### <a name="create-office-365-labels-with-powershell"></a><span data-ttu-id="aa22a-145">Creare etichette di Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa22a-145">Create Office 365 labels with PowerShell</span></span>

1. <span data-ttu-id="aa22a-146">[Connettersi al Centro sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) tramite sessione remota di PowerShell e specificare le credenziali di un account con ruolo Amministratore della sicurezza o Amministratore società.</span><span class="sxs-lookup"><span data-stu-id="aa22a-146">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) and specify the credentials of an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="aa22a-147">Compilare l'elenco dei nomi delle etichette ed eseguire questi comandi al prompt dei comandi di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aa22a-147">Fill out the list of label names, and then run these commands at the PowerShell command prompt:</span></span>
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

<span data-ttu-id="aa22a-148">Successivamente, seguire questa procedura per pubblicare le nuove etichette di Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa22a-148">Next, use these steps to publish the new Office 365 labels.</span></span>
  
1. <span data-ttu-id="aa22a-149">Dal riquadro **Home > Etichette** del Centro sicurezza e conformità, fare clic su **Pubblica etichette**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-149">From the **Home > Labels** pane the Security &amp; Compliance Center, click **Publish labels**.</span></span>
    
2. <span data-ttu-id="aa22a-150">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).</span><span class="sxs-lookup"><span data-stu-id="aa22a-150">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="aa22a-151">Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.</span><span class="sxs-lookup"><span data-stu-id="aa22a-151">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
4. <span data-ttu-id="aa22a-152">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-152">Click **Done**.</span></span>
    
5. <span data-ttu-id="aa22a-153">Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-153">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="aa22a-154">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-154">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="aa22a-155">Nel riquadro **Denomina il criterio**, digitare un nome per il set di etichette in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-155">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="aa22a-156">Nel riquadro **Verifica le impostazioni**, fare clic su **Pubblica etichette** e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-156">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="aa22a-157">Fase 3: applicare le etichette di Office 365 ai siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="aa22a-157">Phase 3: Apply the Office 365 labels to your SharePoint Online sites</span></span>

<span data-ttu-id="aa22a-158">Seguire questa procedura per applicare le etichette di Office 365 alle cartelle di documenti dei siti del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa22a-158">Use these steps to apply the Office 365 labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="aa22a-159">Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-159">From the **Microsoft Office Home** tab of your browser, click the **SharePoint** tile.</span></span>
    
2. <span data-ttu-id="aa22a-160">Nella nuova scheda **SharePoint** del browser selezionare un sito per cui è necessario assegnare un'etichetta di Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa22a-160">On the new **SharePoint** tab in your browser, click a site that needs an Office 365 label assigned.</span></span>
    
3. <span data-ttu-id="aa22a-161">Nella nuova scheda del sito di SharePoint del browser fare clic su **Documenti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-161">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="aa22a-162">Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-162">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="aa22a-163">In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).</span><span class="sxs-lookup"><span data-stu-id="aa22a-163">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="aa22a-164">In **Impostazioni - Applica etichetta**, selezionare l’etichetta appropriata, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-164">In **Settings-Apply Label**, select the appropriate label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="aa22a-165">Chiudere la scheda per il sito di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa22a-165">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="aa22a-166">Ripetere i passaggi da 3 a 8 per assegnare le etichette di Office 365 a siti di SharePoint Online aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="aa22a-166">Repeat steps 3-8 to assign Office 365 labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="aa22a-167">Di seguito è riportata la configurazione risultante.</span><span class="sxs-lookup"><span data-stu-id="aa22a-167">Here is your resulting configuration.</span></span>
  
![Etichette di Office 365 per i quattro tipi di siti del team di SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="aa22a-169">Criteri di prevenzione della perdita dei dati per siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="aa22a-169">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="aa22a-170">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che notifica agli utenti la condivisione di un documento in un sito sensibile del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-170">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>
  
1. <span data-ttu-id="aa22a-171">Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-171">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="aa22a-172">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-172">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="aa22a-173">Nel riquadro **Prevenzione perdita dati** fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-173">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="aa22a-174">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-174">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="aa22a-175">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-175">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="aa22a-176">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-176">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="aa22a-177">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-177">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="aa22a-178">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-178">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="aa22a-179">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-179">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="aa22a-180">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-180">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="aa22a-181">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-181">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="aa22a-182">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-182">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="aa22a-183">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="aa22a-183">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="aa22a-184">Nel riquadro **Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica** fare clic su **Personalizza il testo del suggerimento per i criteri**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-184">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="aa22a-185">Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda se è stata implementato Azure Information Protection per proteggere i file estremamente riservati:</span><span class="sxs-lookup"><span data-stu-id="aa22a-185">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="aa22a-p106">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="aa22a-p107">I file estremamente riservati sono protetti con crittografia. Solo gli utenti esterni che hanno ricevuto le autorizzazioni per questi file dal reparto IT possono leggerli.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="aa22a-191">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-191">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="aa22a-192">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-192">Click **OK**.</span></span>
    
17. <span data-ttu-id="aa22a-193">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, deselezionare la casella di testo per **bloccare la condivisione e limitare l'accesso al contenuto condiviso**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-193">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>
    
18. <span data-ttu-id="aa22a-194">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-194">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="aa22a-195">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-195">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="aa22a-196">Di seguito è riportata la configurazione risultante per i siti sensibili del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa22a-196">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato utilizzando l'etichetta Riservato Office 365.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="aa22a-198">Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che blocchi gli utenti in fase di condivisione di un documento in un sito con riservatezza elevata del team di SharePoint Online all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-198">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="aa22a-199">Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Sicurezza e conformità**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-199">From the **Microsoft Office Home** tab in your browser, click the **Security &amp; Compliance** tile.</span></span>
    
2. <span data-ttu-id="aa22a-200">Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-200">On the new **Security &amp; Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>
    
3. <span data-ttu-id="aa22a-201">Nel riquadro **Prevenzione perdita dati** fare clic su **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-201">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>
    
4. <span data-ttu-id="aa22a-202">Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-202">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="aa22a-203">Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello estremamente riservato in **Nome**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-203">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="aa22a-204">Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-204">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="aa22a-205">Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-205">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="aa22a-206">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-206">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="aa22a-207">Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-207">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>
    
10. <span data-ttu-id="aa22a-208">Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-208">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="aa22a-209">Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-209">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="aa22a-210">Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-210">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="aa22a-211">Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="aa22a-211">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="aa22a-212">Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).</span><span class="sxs-lookup"><span data-stu-id="aa22a-212">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="aa22a-213">Nella casella di testo digitare o incollare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="aa22a-213">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="aa22a-p108">Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="aa22a-217">In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa22a-217">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="aa22a-218">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-218">Click **OK**.</span></span>
    
17. <span data-ttu-id="aa22a-219">Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, selezionare l’opzione per **richiedere motivazioni aziendali per eseguire l'override**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-219">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="aa22a-220">Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-220">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="aa22a-221">Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="aa22a-221">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="aa22a-222">Di seguito è riportata la configurazione risultante per i siti con riservatezza elevata del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aa22a-222">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato utilizzando l'etichetta Estremamente riservato Office 365.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="aa22a-224">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="aa22a-224">Next step</span></span>

[<span data-ttu-id="aa22a-225">Proteggere i file di SharePoint Online con Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="aa22a-225">Protect SharePoint Online files with Azure Information Protection</span></span>](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a><span data-ttu-id="aa22a-226">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa22a-226">See Also</span></span>

[<span data-ttu-id="aa22a-227">Protezione di file e siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="aa22a-227">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="aa22a-228">Proteggere i siti di SharePoint Online in un ambiente di sviluppo e di testing</span><span class="sxs-lookup"><span data-stu-id="aa22a-228">Secure SharePoint Online sites in a dev/test environment</span></span>](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[<span data-ttu-id="aa22a-229">Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili</span><span class="sxs-lookup"><span data-stu-id="aa22a-229">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="aa22a-230">Adozione del cloud e soluzioni ibride</span><span class="sxs-lookup"><span data-stu-id="aa22a-230">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)

