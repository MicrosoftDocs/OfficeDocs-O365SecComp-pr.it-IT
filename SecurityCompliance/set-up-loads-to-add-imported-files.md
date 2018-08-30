---
title: Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: "Rivedere i passaggi per aggiungere i file importati all'ultimo caricamento definita o blocco dei file prima di eseguire formazione pertinenza di Office 365 avanzate eDiscovery.  "
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531323"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="e48f2-103">Configurare i gruppi di file per aggiungere i file importati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e48f2-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="e48f2-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="e48f2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e48f2-p102">In eDiscovery avanzate, un carico è un nuovo batch di file aggiunti a un caso. Per impostazione predefinita, viene definito un carico e tutti i file importati vengono aggiunti a esso. Prima di eseguire formazione pertinenza, file importati devono essere aggiunti al carico.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="e48f2-109">Prendere in considerazione i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="e48f2-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="e48f2-p103">Nuovi file sono noti per essere simile al file precedenti caricati nel database maiuscole oppure il caricamento dei file precedente è incluso un insieme casuale dall'insieme di file. In questo caso, aggiungere i file importati per il caricamento del file corrente.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="e48f2-p104">Nuovi file sono diversi da quelli precedenti (ad esempio, da un'origine diversa) o non si conoscono precedenti che utilizzano simili o diversi carichi precedenti. In questo scenario, aggiungere i file importati a un nuovo caricamento di file. EDiscovery avanzate la riconosce come scenario carichi in sequenza, consente di richiamare un processo di aggiornamento, blocca calcoli Batch e formazione di pertinenza fino al completamento dell'aggiornamento e il carico nuovo è integrato e addestrato.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="e48f2-115">Aggiunta di file importati per il carico corrente</span><span class="sxs-lookup"><span data-stu-id="e48f2-115">Adding imported files to the current load</span></span>

<span data-ttu-id="e48f2-p105">Tutti i file importati devono essere aggiunti a un carico di elaborazione di eDiscovery avanzate. I file importati vengono aggiunte all'ultimo caricamento definito. Se successivamente si importano i file aggiuntivi, devono essere aggiunti anche al carico.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="e48f2-119">Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![Scheda dei caricamenti per la configurazione di pertinenza](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="e48f2-p106">**File di inclusione**: selezionare un'opzione per i file da includere. Per impostazione predefinita, l'aggiunta di file per il carico corrente si basa popolazione "Tutti i file".</span><span class="sxs-lookup"><span data-stu-id="e48f2-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e48f2-p107">Caricare tutti i file riformati disponibili in pertinenza. Se si prevede di caricare solo un sottoinsieme di file disponibili, innanzitutto consultare grazie al supporto, come il caricamento sottoinsiemi può influire negativamente sulle formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="e48f2-125">**Gestione dei carichi**, selezionare un carico.</span><span class="sxs-lookup"><span data-stu-id="e48f2-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="e48f2-p108">Fare clic su **Aggiungi file**. I file vengono aggiunti al carico e viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="e48f2-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-128">Click **OK**.</span></span>
    
<span data-ttu-id="e48f2-129">Ora, è possibile elaborare i file di eDiscovery avanzate pertinenza per i file di formazione.</span><span class="sxs-lookup"><span data-stu-id="e48f2-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="e48f2-130">Un nome di carico all'interno di un caso di modifica</span><span class="sxs-lookup"><span data-stu-id="e48f2-130">Editing a load name within a case</span></span>

<span data-ttu-id="e48f2-131">Se la modifica del nome del carico, è consigliabile utilizzare un nome significativo al caso.</span><span class="sxs-lookup"><span data-stu-id="e48f2-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="e48f2-132">Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="e48f2-p109">Dall'elenco di **gestione di carichi** , selezionare un carico e fare clic sull'icona **Modifica** . Viene visualizzata la finestra di modifica del carico.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="e48f2-135">Immettere le modifiche e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="e48f2-136">Aggiunta di file importato a un nuovo caricamento</span><span class="sxs-lookup"><span data-stu-id="e48f2-136">Adding imported files to a new load</span></span>

<span data-ttu-id="e48f2-137">Dopo aver avviato formazione pertinenza o la conduzione di calcolo di blocco, è possibile importare ed elaborare un insieme di file aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e48f2-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="e48f2-p110">Durante l'aggiornamento, possono creare, tag e analizzare l'insieme di aggiornamento. EDiscovery avanzate confronta la valutazione dei file relativo e Non relativo il carico di nuovo a quelli di carichi precedenti. In base ai risultati, viene chiesto di prendere decisioni di aggiornamento, se necessario e avanzata eDiscovery vengono forniti suggerimenti sulla base delle informazioni di pertinenza maturate.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="e48f2-141">Ripristino dello stato carichi e funzionalità di aggiornamento varia nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e48f2-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="e48f2-142">Quando si importa un nuovo caricamento file dopo il calcolo Batch, eDiscovery avanzate determina in quale misura i file rientrano in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="e48f2-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="e48f2-143">Analogamente (omogenei): non è richiesto un arrotondamento personalizzata del corso di formazione pertinenza e la conoscenza di attribuzione dal carico precedente può essere applicata "così com'è" per il carico di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e48f2-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="e48f2-144">DISTINCT (eterogenee): è necessario un arrotondamento personalizzata del corso di formazione pertinenza e la conoscenza di attribuzione dal carico precedente non è possibile applicare.</span><span class="sxs-lookup"><span data-stu-id="e48f2-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="e48f2-145">Queste condizioni, fare riferimento a livello di similarità dei file tra i carichi di e non all'interno del caricamento.</span><span class="sxs-lookup"><span data-stu-id="e48f2-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="e48f2-p111">Quando si importa un nuovo caricamento di file durante la formazione di pertinenza (prima del calcolo Batch), aggiornamento consente di continuare formazione pertinenza sul set di file united. EDiscovery avanzate non vengono valutati se il carico nuovo è simile a o diverso dal carico precedente. Raccoglie informazioni sulla nuova carico semplicemente e consente la pertinenza di formazione continuare nella nuova e precedente imposta dei file.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="e48f2-149">Quando sono presenti più problemi di formazione di pertinenza e problemi dopo il calcolo Batch, il processo di aggiornamento viene eseguito una volta per tutti i problemi e i risultati vengono calcolati e visualizzati per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="e48f2-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e48f2-p112">La dimensione del campione aggiornamento può variare. Dipende dalle dimensioni dei nuovo carico rispetto al caricamento della precedente e al numero di campioni completati prima di aggiungere il nuovo carico. Nell'esempio di aggiornamento in genere è un insieme di file 200 a 2.000 il carico di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e48f2-p113">Aggiornamento degli smette di altre attività e richiede singolo file tagging e revisione. Di conseguenza, è possibile ridurre il sovraccarico quando si aggiungono nuovi file in grandi batch.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="e48f2-155">Aggiunta di un nuovo caricamento di file tramite aggiornamento e in sequenza carica</span><span class="sxs-lookup"><span data-stu-id="e48f2-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="e48f2-156">Nella **pertinenza \> il programma di installazione di pertinenza** selezionare **carichi**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="e48f2-p114">**Gestione dei carichi**fare clic sul **+** icona per aggiungere un carico. Viene visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="e48f2-p115">Fare clic su **Sì** per continuare. Viene visualizzata la finestra di dialogo **Aggiungi nuovo carico** .</span><span class="sxs-lookup"><span data-stu-id="e48f2-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e48f2-161">È possibile aggiungere un nuovo caricamento solo se le azioni eseguite al carico precedente.</span><span class="sxs-lookup"><span data-stu-id="e48f2-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="e48f2-p116">Nella finestra di dialogo **Aggiungi nuovo carico** digitare l'informazione da **caricare il nome** e **Descrizione** e quindi fare clic su **OK**. EDiscovery avanzate consente di aggiungere un nuovo caricamento.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="e48f2-p117">Per importare il nuovo file di carico, fare clic su **Aggiungi file**. Tutti i nuovi file vengono aggiunti a questo carico. Dopo aver eDiscovery avanzate consente di importare i file, riconosce lo scenario di carichi in sequenza e indica aggiornamento come il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="e48f2-167">Fare clic su **aggiornamento** nella parte inferiore della finestra di dialogo per l'esecuzione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="e48f2-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="e48f2-168">Un singolo insieme di aggiornamento, in genere che contiene il file di 200 a 2.000 dal carico nuovo, viene creato per tutti i problemi consentire file simultanee tagging.</span><span class="sxs-lookup"><span data-stu-id="e48f2-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="e48f2-169">Vengono fornite informazioni dettagliate su se carichi sono simili o distinti, che eDiscovery avanzate unite o dividere automaticamente i carichi e informazioni per quanto riguarda l'elaborazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e48f2-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="e48f2-p118">È possibile quindi contrassegnare i file ed eseguire un'operazione di calcolo. Il contrassegno consente di abilitare pertinenza determinare se i carichi sono simili o distinti e per continuare con il nuovo set di file.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="e48f2-172">Una volta viene esaminato il set di aggiornamento, visualizzare **pertinenza \> traccia** per i risultati di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e48f2-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="e48f2-173">Se durante la formazione di pertinenza è stato aggiunto il nuovo caricamento del file, ovvero, il problema non è stato ancora inviato calcolo Batch, **formazione continua** è il passaggio successivo, indipendentemente dal fatto i risultati di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e48f2-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="e48f2-p119">I carichi di nuovi e precedenti vengono elaborati come un caricamento e formazione di pertinenza continua sul set di united. È stata completata con questa procedura e possono continuare formazione pertinenza.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="e48f2-176">Se il carico nuovo è stato aggiunto dopo il calcolo Batch, procedere con la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e48f2-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="e48f2-177">Per i caricamenti di nuovi aggiunti dopo il calcolo Batch, eDiscovery avanzate determina se il carico nuovo è simile a o diverso dal precedente viene caricato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e48f2-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="e48f2-p120">Se sono stati trovati carichi simile: non è necessaria alcun formazione aggiuntiva di pertinenza. Viene illustrato il dashboard deve eseguire il passaggio successivo consigliato * * Batch calcolo * * per calcolare i punteggi pertinenza per il carico di nuovo. Carichi sono stati trovati per essere simile, in modo che l'analisi classificatore precedente può essere eseguito sui nuovi file.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run ** Batch calculation ** again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="e48f2-p121">Se sono stati trovati carichi distinto: formazione di maggiore rilevanza è necessaria e il passaggio successivo consiste decisione di aggiornamento. Selezionare una decisione di aggiornamento nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e48f2-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="e48f2-p122">Se si seleziona **unire carichi**, eDiscovery avanzate consente di unire i carichi precedenti e nuovi per il set di formazione. Anche se il primo caricamento è stato sottoposto a calcolo Batch, è necessario ulteriore formazione. Continuare formazione insieme carichi nuovi e precedenti. Calcolo batch verrà quindi eseguito nuovamente e devono essere ignorati i punteggi calcolo Batch precedenti. Selezionare questa opzione quando può ricalcolato punteggio di pertinenza del carichi esistenti, ad esempio, quando non è stata avviata esame dei caricamenti di file esistente.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="e48f2-p123">Se si seleziona **diviso carica**, procedere formazione pertinenza solo il carico di nuovo. In questo caso, i punteggi di calcolo Batch precedenti verrà modificata. Scegliere questa opzione quando esistente punteggio di pertinenza del carichi esistenti non possa essere ricalcolato, ad esempio, se è già iniziato esame dei carichi di esistenti. Punteggio di pertinenza viene gestiti separatamente da questo punto in poi e non può essere unite.</span><span class="sxs-lookup"><span data-stu-id="e48f2-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="e48f2-192">Fare clic su **Continua formazione**.</span><span class="sxs-lookup"><span data-stu-id="e48f2-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e48f2-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e48f2-193">See also</span></span>

[<span data-ttu-id="e48f2-194">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e48f2-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e48f2-195">Definizione dei problemi e assegnazione di utenti</span><span class="sxs-lookup"><span data-stu-id="e48f2-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="e48f2-196">Definizione evidenziate le parole chiave e avanzate opzioni</span><span class="sxs-lookup"><span data-stu-id="e48f2-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

