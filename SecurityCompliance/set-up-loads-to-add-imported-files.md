---
title: Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: "Esaminare i passaggi per aggiungere i file importati all'ultimo carico definito, o batch, di file prima di eseguire la formazione di pertinenza in Office 365 Advanced eDiscovery.  "
ms.openlocfilehash: 8c5101628b468719f8aa4f81a4c73cbbb226105f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215986"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8ce40-103">Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8ce40-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8ce40-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="8ce40-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8ce40-p102">In Advanced eDiscovery, un carico è un nuovo batch di file aggiunto a un caso. Per impostazione predefinita, viene definito un carico e vengono aggiunti tutti i file importati. Prima di eseguire la formazione di pertinenza, i file importati devono essere aggiunti al carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="8ce40-109">Si conSideri gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ce40-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="8ce40-p103">I nuovi file sono noti per essere simili ai file precedenti caricati nel database del caso oppure il carico precedente di file era un set casuale della raccolta file. In questa istanza, aggiungere i file importati al caricamento del file corrente.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="8ce40-p104">I nuovi file sono diversi da quelli precedenti (ad esempio, da un'origine diversa) oppure non sono presenti informazioni precedenti che sono simili o diversi ai carichi precedenti. In questo scenario, aggiungere i file importati a un nuovo caricamento del file. Advanced eDiscovery riconosce questo come uno scenario dei carichi di rotolamento, richiama un processo di aggiornamento, blocca la formazione di pertinenza e i calcoli in batch fino al completamento del recupero e il nuovo carico è integrato e addestrato.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="8ce40-115">Aggiunta di file importati al carico corrente</span><span class="sxs-lookup"><span data-stu-id="8ce40-115">Adding imported files to the current load</span></span>

<span data-ttu-id="8ce40-p105">Tutti i file importati devono essere aggiunti a un carico da elaborare in Advanced eDiscovery. I file imPortati vengono aggiunti all'ultimo carico definito. Se si importano ulteriori file in un secondo momento, è necessario aggiungerli anche al carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="8ce40-119">Nella scheda configurazione pertinenza pertinenza selezionare **carica**. \*\* \> \*\*</span><span class="sxs-lookup"><span data-stu-id="8ce40-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![Scheda dei caricamenti per la configurazione di pertinenza](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="8ce40-p106">**Includi file**: selezionare un'opzione per i file da includere. Per impostazione predefinita, l'aggiunta di file al carico corrente si basa sulla popolazione "tutti i file".</span><span class="sxs-lookup"><span data-stu-id="8ce40-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8ce40-p107">Caricare tutti i file abbattuti disponibili in pertinenza. Se si prevede di caricare solo un sottoinsieme dei file disponibili, consultare prima di tutto il supporto, in quanto i sottoinsiemi di caricamento possono influire negativamente sulla formazione per pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="8ce40-125">In **gestione carichi**selezionare un carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="8ce40-p108">Fare clic su **Aggiungi file**. I file vengono aggiunti al carico e viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="8ce40-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ce40-128">Click **OK**.</span></span>
    
<span data-ttu-id="8ce40-129">I file possono ora essere elaborati in una pertinenza eDiscovery avanzata per la formazione dei file.</span><span class="sxs-lookup"><span data-stu-id="8ce40-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="8ce40-130">Modifica di un nome di carico all'interno di un caso</span><span class="sxs-lookup"><span data-stu-id="8ce40-130">Editing a load name within a case</span></span>

<span data-ttu-id="8ce40-131">Se si modifica il nome del carico, è consigliabile utilizzare un nome significativo per il caso.</span><span class="sxs-lookup"><span data-stu-id="8ce40-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="8ce40-132">Nella scheda configurazione pertinenza pertinenza selezionare **carica**. \*\* \> \*\*</span><span class="sxs-lookup"><span data-stu-id="8ce40-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="8ce40-p109">Nell'elenco **gestione carichi** selezionare un carico e fare clic sull'icona **modifica** . Viene visualizzata la finestra modifica caricamento.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="8ce40-135">Immettere le modifiche e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ce40-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="8ce40-136">Aggiunta di file importati a un nuovo carico</span><span class="sxs-lookup"><span data-stu-id="8ce40-136">Adding imported files to a new load</span></span>

<span data-ttu-id="8ce40-137">Dopo aver avviato la formazione di pertinenza o aver eseguito il calcolo in batch, è possibile che si desideri importare ed elaborare un ulteriore set di file.</span><span class="sxs-lookup"><span data-stu-id="8ce40-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="8ce40-p110">Durante il recupero, è possibile creare, contrassegnare e analizzare il set di catch-up. Advanced eDiscovery confronta la valutazione dei file rilevanti e non rilevanti nel nuovo carico con quelli presenti nei carichi precedenti. In base ai risultati, viene richiesto di prendere decisioni di catch-up, se necessario, e Advanced eDiscovery fornisce consigli in base alle informazioni sulla pertinenza accumulate.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="8ce40-141">I carichi di rotolamento e la funzionalità di catch-up variano come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ce40-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="8ce40-142">Quando si importa un nuovo caricamento di file dopo il calcolo del batch, Advanced eDiscovery determina in che misura i file rientrano in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ce40-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="8ce40-143">Analogo (omogeneo): non è necessario un nuovo ciclo personalizzato di formazione per la pertinenza e le conoscenze accumulate dal carico precedente possono essere applicate "così com'è" al nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="8ce40-144">Distinct (eterogeneo): è necessario un nuovo ciclo personalizzato di formazione per la pertinenza e non è possibile applicare le informazioni accumulate dal carico precedente.</span><span class="sxs-lookup"><span data-stu-id="8ce40-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="8ce40-145">Tali termini si riferiscono al livello di somiglianza dei file tra i carichi e non all'interno dei carichi.</span><span class="sxs-lookup"><span data-stu-id="8ce40-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="8ce40-p111">Quando si importa un nuovo carico di file durante la formazione di pertinenza (prima del calcolo del batch), il recupero consente di continuare la formazione sulla pertinenza del set di file Uniti. Advanced eDiscovery non calcola se il nuovo carico è simile o distinto rispetto al carico precedente. Raccoglie semplicemente informazioni sul nuovo carico e consente la formazione della pertinenza per continuare con i nuovi e precedenti insiemi di file.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="8ce40-149">Quando sono presenti più problemi relativi alla formazione sulla pertinenza e ai problemi dopo il calcolo del batch, il processo di recupero viene eseguito una volta per tutti i problemi e i risultati vengono calcolati e visualizzati per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="8ce40-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8ce40-p112">Le dimensioni dell'esempio di catch-up possono variare. Dipende dalle dimensioni del nuovo carico rispetto ai carichi precedenti e dal numero di esempi completati prima di aggiungere il nuovo carico. L'esempio di catch-up è in genere un set di 200 a 2.000 file dal nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8ce40-p113">Catch-up interrompe tutte le altre attività e richiede il tagging e la revisione dei singoli file. Pertanto, è possibile ridurre il sovraccarico quando si aggiungono nuovi file in batch di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="8ce40-155">Aggiunta di un nuovo caricamento dei file con i carichi di catch-up e Rolling</span><span class="sxs-lookup"><span data-stu-id="8ce40-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="8ce40-156">Nella scheda configurazione pertinenza pertinenza selezionare **carica**. \*\* \> \*\*</span><span class="sxs-lookup"><span data-stu-id="8ce40-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="8ce40-p114">In **gestione carichi**fare clic sull' **+** icona per aggiungere un carico. Viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="8ce40-p115">Fare clic su **Sì** per continuare. Viene visualizzata la finestra di dialogo **Aggiungi nuovo caricamento** .</span><span class="sxs-lookup"><span data-stu-id="8ce40-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8ce40-161">È possibile aggiungere un nuovo carico solo se le azioni sono state eseguite al carico precedente.</span><span class="sxs-lookup"><span data-stu-id="8ce40-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="8ce40-p116">Nella finestra di dialogo **Aggiungi nuovo carico** , digitare informazioni in nome e **Descrizione** del **caricamento** e quindi fare clic su **OK**. Advanced eDiscovery aggiunge un nuovo carico.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="8ce40-p117">Per importare il nuovo file di caricamento, fare clic su **Aggiungi file**. Tutti i nuovi file vengono aggiunti a questo carico. Dopo che Advanced eDiscovery importa i file, riconosce lo scenario dei carichi di rotolamento e indica il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="8ce40-167">Fare clic su **catch-up** nella parte inferiore della finestra di dialogo per eseguire lo scenario.</span><span class="sxs-lookup"><span data-stu-id="8ce40-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="8ce40-168">Viene creato un singolo set di catch-up, che in genere contiene 200 a 2.000 file dal nuovo carico, per tutti i problemi per consentire il tagging dei file simultanei.</span><span class="sxs-lookup"><span data-stu-id="8ce40-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="8ce40-169">Vengono forniti informazioni dettagliate sul fatto che i carichi siano simili o distinti, se Advanced eDiscovery ha unito o diviso i carichi automaticamente e le informazioni relative all'elaborazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="8ce40-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="8ce40-p118">È quindi possibile contrassegnare i file ed eseguire un'operazione di calcolo. Il tagging attiva la pertinenza per determinare se i carichi sono simili o distinti e consente di continuare a lavorare sul nuovo set di file.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="8ce40-172">Dopo la revisione del set di catch-up, \*\* \> \*\* visualizzare la verifica della pertinenza per i risultati di catch-up.</span><span class="sxs-lookup"><span data-stu-id="8ce40-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="8ce40-173">Se il nuovo caricamento file è stato aggiunto durante la formazione di pertinenza (ovvero, il problema non è stato ancora superato tramite calcolo batch), **continuare l'allenamento** è il passaggio successivo, indipendentemente dai risultati di catch-up.</span><span class="sxs-lookup"><span data-stu-id="8ce40-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="8ce40-p119">I carichi nuovi e precedenti vengono elaborati con un carico e una formazione di pertinenza continua sul set Unito. Dopo aver completato questa procedura, è possibile continuare la formazione sulla pertinenza.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="8ce40-176">Se il nuovo carico è stato aggiunto dopo il calcolo batch, procedere con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8ce40-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="8ce40-177">Per i nuovi carichi aggiunti dopo il calcolo in batch, Advanced eDiscovery determina se il nuovo carico è simile o diverso dai carichi precedenti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ce40-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="8ce40-p120">Se i carichi sono stati trovati come simili: non è necessaria alcuna formazione supplementare sulla pertinenza. Il dashboard indica che il passaggio successivo consigliato consiste nell'eseguire \* \* il calcolo batch \* \* di nuovo per calcolare i punteggi di pertinenza per il nuovo carico. I carichi sono stati trovati come simili, quindi è possibile eseguire l'analisi di classificazione precedente nei nuovi file.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="8ce40-p121">Se i carichi sono stati individuati come distinti: è necessaria una formazione più pertinente e il passaggio successivo è la decisione di catch-up. Selezionare una decisione di catch-up come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ce40-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="8ce40-p122">Se si seleziona **Unisci carichi**, Advanced eDiscovery unisce i carichi precedenti e nuovi per il set di training. Anche se il primo carico ha superato il calcolo in batch, è necessario un numero maggiore di formazione. Continuare a formare carichi nuovi e precedenti insieme. Il calcolo batch verrà quindi eseguito di nuovo e i punteggi del calcolo batch precedenti devono essere ignorati. Scegliere questa selezione quando i punteggi di riLevanza per i carichi esistenti possono essere ricalcolati, ad esempio quando la revisione dei carichi di file esistenti non è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="8ce40-p123">Se si seleziona **Suddividi carichi**, continuare la formazione sulla pertinenza solo sul nuovo carico. In questo caso, i punteggi del calcolo batch precedenti rimarranno così come sono. Scegliere questa opzione se non è possibile ricalcolare i punteggi di pertinenza esistenti per i carichi esistenti, ad esempio se è già stata avviata la revisione dei carichi esistenti. I punteggi relativi alla pertinenza sono gestiti separatamente da questo punto e non possono essere Uniti.</span><span class="sxs-lookup"><span data-stu-id="8ce40-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="8ce40-192">Fare clic su **continua formazione**.</span><span class="sxs-lookup"><span data-stu-id="8ce40-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8ce40-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce40-193">See also</span></span>

[<span data-ttu-id="8ce40-194">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8ce40-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8ce40-195">Definire i problemi e assegnare gli utenti</span><span class="sxs-lookup"><span data-stu-id="8ce40-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="8ce40-196">Definire parole chiave evidenziate e opzioni avanzate</span><span class="sxs-lookup"><span data-stu-id="8ce40-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

