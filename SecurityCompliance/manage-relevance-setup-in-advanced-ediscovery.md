---
title: Gestire la configurazione di Rilevanza in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: 'Elementi consigliati per configurare il training per la rilevanza in Office 365 Advanced eDiscovery per classificare i file in base alla rilevanza e generare risultati analitici.  '
ms.openlocfilehash: b2f1f848d14bdf77444c2026cbc675042c792542
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530391"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f1d88-103">Gestire la configurazione di Rilevanza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f1d88-103">Manage Relevance setup in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f1d88-p101">Advanced eDiscovery richiede Office 365 E3 con il componente aggiuntivo Advanced Compliance o la sottoscrizione di E5 dell'organizzazione. Se non si dispone di questo piano e si desidera provare Advanced eDiscovery, è possibile [iscriversi a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f1d88-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="f1d88-p102">La tecnologia di rilevanza di Advanced eDiscovery applica software elaborato da specialisti per classificare i file in base alla rilevanza e può essere utilizzata per prime valutazioni dei casi (ECA, Early Case Assessment), eliminazione selettiva e revisione di campioni di file.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="f1d88-p103">Advanced eDiscovery include componenti per il training di rilevanza e tag di file rilevanti per un caso, memorizza esempi di file rilevanti e non per classificare ogni file e generare risultati analitici che possono essere usati durante e dopo il processo di verifica dei file.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="f1d88-110">Linee guida per configurare il training di rilevanza</span><span class="sxs-lookup"><span data-stu-id="f1d88-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="f1d88-p104">In Advance eDiscovery, nella finestra di dialogo **Casi**, selezionare un caso e fare clic su **Passa al caso**. Fare clic su **Rilevanza** \> **Configurazione della rilevanza**. Seguire le linee guida consigliate per configurare la rilevanza.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="f1d88-114">**Aggiunta di tag**: l'efficacia del training di rilevanza dipende dall'abilità dello specialista di contrassegnare i campioni di file con precisione e coerenza.</span><span class="sxs-lookup"><span data-stu-id="f1d88-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="f1d88-115">**Problemi di casi**:</span><span class="sxs-lookup"><span data-stu-id="f1d88-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="f1d88-p105">Per ogni problema, utilizzare lo stesso specialista per l'intero processo di training di rilevanza. Aggiungere contemporaneamente tag da più specialisti non è consentito.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="f1d88-118">Determinare se ogni gruppo di file è pertinente solo per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="f1d88-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="f1d88-p106">Se un problema è definito in modo troppo generico, Advanced eDiscovery potrebbe produrre troppi file che in realtà non sono rilevanti. Se un problema è definito in modo troppo ristretto, il processo di training di rilevanza potrebbe richiedere più tempo.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="f1d88-121">Durante ciascun ciclo di training di rilevanza, Advanced eDiscovery si concentra su un singolo problema attivo e i risultati dei campioni intermedi vengono visualizzati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f1d88-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="f1d88-p107">In uno scenario con più problemi, la modalità campione consente di selezionare i problemi da includere nell'elaborazione. I problemi "inattivi" non vengono gestiti fino a quando la loro modalità di campionamento non viene modificata. Un problema può essere "inattivo" o "attivato" per un solo specialista.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="f1d88-p108">Advanced eDiscovery può essere usato per generare file di privilegi candidati. Configurare un problema separato in base al privilegio. Se possibile, prima eseguire il training ed eliminare in base alla rilevanza, quindi eseguire il training in base al privilegio solo sul set eliminato (ricaricare il set eliminato come caso separato).</span><span class="sxs-lookup"><span data-stu-id="f1d88-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="f1d88-p109">Il calcolo del batch può essere eseguito solo quando non sono presenti campioni aperti (quando si fa clic su Calcolo batch, verrà visualizzato un elenco di utenti con campioni aperti). Per "chiudere" i campioni di altri utenti (questo dovrebbe essere eseguito solo se questi utenti non contrassegnano questi esempi), un amministratore può utilizzare l'utilità "Modifica rilevanza" con l'opzione "Tutti i campioni di utenti".</span><span class="sxs-lookup"><span data-stu-id="f1d88-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="f1d88-p110">**Metadati**: Advanced eDiscovery si concentra sul contenuto. Non considera i metadati nell'ambito dei criteri di rilevanza.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="f1d88-132">**Rilevanza**: se la rilevanza di un problema ha un valore inferiore al 3% dopo la valutazione, si consiglia di effettuare il seeding del training di rilevanza con file rilevanti e non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="f1d88-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="f1d88-p111">**Dimensione del file**: i file di grandi dimensioni (oltre 5.242.880 caratteri di testo estratto) vengono ignorati nella rilevanza. I file non partecipano al training di rilevanza e non vengono classificati per rilevanza dopo il calcolo del batch. I file oltre i 5 MB possono essere inclusi nel set di valutazione.</span><span class="sxs-lookup"><span data-stu-id="f1d88-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="f1d88-136">Configurazione di problemi dei casi</span><span class="sxs-lookup"><span data-stu-id="f1d88-136">Setting up case issues</span></span>

<span data-ttu-id="f1d88-137">I parametri descritti in questa sezione sono disponibili nella tecnologia di rilevanza di Advanced eDiscovery \*\*\*\* \> **Configurazione della rilevanza**.</span><span class="sxs-lookup"><span data-stu-id="f1d88-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="f1d88-138">I problemi devono essere assegnati a un utente che dovrà occuparsi del training dei file.</span><span class="sxs-lookup"><span data-stu-id="f1d88-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="f1d88-139">I file importati devono quindi essere aggiunti al carico di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f1d88-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="f1d88-140">Definire e organizzare con attenzione i problemi, poiché i risultati del training di rilevanza possono esserne influenzati.</span><span class="sxs-lookup"><span data-stu-id="f1d88-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="f1d88-141">Dopo aver impostato i parametri, il revisore/lo specialista può avviare il training r dei file nella scheda **Rilevanza**.</span><span class="sxs-lookup"><span data-stu-id="f1d88-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1d88-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d88-142">See also</span></span>

[<span data-ttu-id="f1d88-143">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f1d88-143">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f1d88-144">Definire i problemi e assegnare gli utenti</span><span class="sxs-lookup"><span data-stu-id="f1d88-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="f1d88-145">Configurare carichi per aggiungere file importati</span><span class="sxs-lookup"><span data-stu-id="f1d88-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="f1d88-146">Definire parole chiave evidenziate e opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="f1d88-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

