---
title: Utilizzo del modulo di pertinenza per analizzare i dati di eDiscovery avanzate (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 5e30a7f6919f50d2d73606fae3b53f21ef33e223
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607885"
---
# <a name="using-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a><span data-ttu-id="14b0e-102">Utilizzo del modulo di pertinenza per analizzare i dati di eDiscovery avanzate (Preview)</span><span class="sxs-lookup"><span data-stu-id="14b0e-102">Using the Relevance module to analyze data in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="14b0e-p101">In eDiscovery avanzate (anteprima), la funzionalità di pertinenza include i pertinenza e verifica dei file correlati a un caso. Il flusso di lavoro di pertinenza è illustrato e descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="14b0e-p101">In Advanced eDiscovery (Preview), the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="14b0e-106">**Cicli di valutazione e monitoraggio**:</span><span class="sxs-lookup"><span data-stu-id="14b0e-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="14b0e-107">**Valutazione**: Abilita assessment anticipati in base a un campione casuale di file e viene utilizzata questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittiva.</span><span class="sxs-lookup"><span data-stu-id="14b0e-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="14b0e-108">**Tenere traccia degli**: calcolare e visualizzare i risultati della valutazione durante il monitoraggio statistiche validità del processo di.</span><span class="sxs-lookup"><span data-stu-id="14b0e-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="14b0e-109">**Cicli di verifica e corsi di formazione**</span><span class="sxs-lookup"><span data-stu-id="14b0e-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="14b0e-110">**Tag**: criteri di pertinenza specifici per ogni problema sulla base iterativo verifica dell'esperto e tagging dei singoli file acquisita dalla eDiscovery avanzate (Preview).</span><span class="sxs-lookup"><span data-stu-id="14b0e-110">**Tag**: Advanced eDiscovery (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="14b0e-111">**Tenere traccia degli**: calcolare e visualizzare i risultati della formazione pertinenza durante il monitoraggio statistiche validità del processo.</span><span class="sxs-lookup"><span data-stu-id="14b0e-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="14b0e-112">**Calcolo batch**: I criteri di pertinenza accumulati e acquisiti viene applicato all'intero insieme di file e per ogni file viene generato un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="14b0e-113">**Stabilire**: I risultati dell'analisi applicata al caso intera viene visualizzata dopo il calcolo Batch e dati utilizzati per prendere decisioni revisione documento vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="14b0e-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="14b0e-114">**Test**: risultati devono essere provati per verificare la validità e l'efficacia dell'elaborazione eDiscovery avanzate (Preview).</span><span class="sxs-lookup"><span data-stu-id="14b0e-114">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery (Preview) processing.</span></span>

- <span data-ttu-id="14b0e-115">**Ricerca**: una volta completato il flusso di lavoro di pertinenza, è possibile utilizzare l'output, ad esempio percentile lettura di un documento per il problema quando si esegue una query all'interno del set di lavoro.</span><span class="sxs-lookup"><span data-stu-id="14b0e-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="14b0e-116">Linee guida per la revisione e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="14b0e-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="14b0e-117">Di seguito è fornita una panoramica delle linee guida per la revisione e formazione di pertinenza:</span><span class="sxs-lookup"><span data-stu-id="14b0e-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="14b0e-p102">**Errori ed incoerenze**: se errori tagging vengono apportati durante la formazione, tornare alla precedente esempi di file per correggerli. Se sono presenti troppi errori da correggere o non esiste un nuovo punto di vista del case o problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e riavviata la formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p102">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="14b0e-120">**Formazione e utilizzo dei tag**:</span><span class="sxs-lookup"><span data-stu-id="14b0e-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="14b0e-p103">File devono essere contrassegnati in base al contenuto solo. È consigliabile non metadati, ad esempio depositaria, date o percorso del file.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p103">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="14b0e-123">Non prende in considerazione data indicazioni intervallo nel testo tagging file.</span><span class="sxs-lookup"><span data-stu-id="14b0e-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="14b0e-124">Non prende in considerazione incorporate immagini grafiche tagging file.</span><span class="sxs-lookup"><span data-stu-id="14b0e-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="14b0e-p104">Ignora testo applicato a seconda della pertinenza verrà rimosso al contenuto del file visualizzato nella visualizzazione di testo di pertinenza. Se sono stati definiti i valori per il testo Ignora dopo la pertinenza già formazione introduttiva, il nuovo testo ignorato verrà applicato al file di esempio creati dal punto in cui è stata definita. La caratteristica di ignorare il testo deve essere utilizzata attenzione, poiché il suo utilizzo può consentire una riduzione delle prestazioni di analisi dei file</span><span class="sxs-lookup"><span data-stu-id="14b0e-p104">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="14b0e-p105">Utilizzare l'opzione **Ignora tagging** solo quando necessario. EDiscovery avanzate (Preview) istruire non basato su file ignorati. Nella valutazione, se è difficile stabilire se un file è rilevante, è preferibile tag come Relevant (R) o non rilevanti (NR) ogni volta che è possibile invece selezionando **Ignora**. Quando eDiscovery avanzate (Preview) valuta formazione, può quindi essere visualizzato adeguatezza questi tipi di file sono stati elaborati.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p105">Use the **Skip tagging** option only when necessary. Advanced eDiscovery (Preview) does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="14b0e-132">Anche i file con dimensioni molto piccole quantità di testo estratto essere contrassegnati di formazione come R/NR anziché come "Ignora", se possibile.</span><span class="sxs-lookup"><span data-stu-id="14b0e-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="14b0e-133">Assegnazione dei tag che possono influire sugli classificatore, purché il file può essere letta e può essere contrassegnato come R/NR.</span><span class="sxs-lookup"><span data-stu-id="14b0e-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="14b0e-134">Il numero di sequenza file presente nell'elenco di file di esempio visualizzato nella scheda **Tag** consente all'utente restituire l'ordine di visualizzazione originale dei file.</span><span class="sxs-lookup"><span data-stu-id="14b0e-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="14b0e-p106">È possibile tornare a un campione e modificare il contrassegno della valutazione e formazione imposta i file. Le modifiche verranno applicate quando si crea il codice di esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p106">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="14b0e-137">Analizzate Excel i file in formato PDF devono essere considerato come file di Excel nativi quando i file di tagging.</span><span class="sxs-lookup"><span data-stu-id="14b0e-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="14b0e-p107">In caso di dubbi sulle tagging pertinenza di un file, rivolgersi a un esperto. Tagging non corretto durante la formazione pertinenza possono causare perdite di tempo durante il processo e può inoltre avere un impatto negativo sulla qualità dei risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p107">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="14b0e-140">Parole chiave che sono state definite nella parola chiave elenchi verranno visualizzati in colori per consentire all'utente di identificare i file rilevanti durante l'assegnazione dei tag.</span><span class="sxs-lookup"><span data-stu-id="14b0e-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="14b0e-p108">**Calcolo batch**: i file che sono stati contrassegnati come R/NR da un esperto ricevono un punteggio pari a 0 o 100. Ciò vale per prendere prima calcolo Batch per il tagging. Se l'esperto trasferito il problema su inattivo dopo il calcolo Batch e continuato tagging questo problema, i punteggi appena contrassegnati non saranno 100/0, ma piuttosto il punteggio originale.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p108">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="14b0e-144">**Problemi e campionamento delle modalità**: problemi sono in genere disattivate al termine lavoro su esse formazione di pertinenza è stabile e calcolo Batch è stato eseguito, quando vengono annullati i problemi o in un altro utente è impegnato nei problemi.</span><span class="sxs-lookup"><span data-stu-id="14b0e-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="14b0e-145">Procedure di formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="14b0e-145">Steps in Relevance training</span></span>

<span data-ttu-id="14b0e-p109">Nella **pertinenza \> traccia** scheda Avanzate eDiscovery vengono forniti suggerimenti su come procedere per l'elaborazione, con i seguenti passaggi successivi. Le implicazioni sono descritti di seguito per ognuna delle procedure seguenti è consigliabile nel processo di formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p109">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="14b0e-148">Contrassegno /continue. tagging: verifica File e pertinenza tagging eseguita da un esperto per ogni file, quindi inviare all'interno di un campione.</span><span class="sxs-lookup"><span data-stu-id="14b0e-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="14b0e-149">Implicazioni: Un esempio esistente deve essere contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="14b0e-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="14b0e-150">Valutazione /continue. assessment: consente la convalida anticipata del problema maiuscole pertinenza e una visualizzazione preliminare di pertinenza della popolazione file importati per il case corrente.</span><span class="sxs-lookup"><span data-stu-id="14b0e-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="14b0e-151">Implicazioni: Assessment ulteriori è necessario o consigliato.</span><span class="sxs-lookup"><span data-stu-id="14b0e-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="14b0e-152">Formazione /continue. formazione: processo durante i Advanced eDiscovery apprendimento da esperto che è il file di tagging esempi e acquisisce la possibilità di identificare i criteri di rilevanza pertinenti per ogni problema nel contesto di ogni caso.</span><span class="sxs-lookup"><span data-stu-id="14b0e-152">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="14b0e-153">Implicazioni: Il problema è necessario ulteriore formazione; Nell'esempio successivo deve essere creato e contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="14b0e-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="14b0e-p110">Blocco calcolo: processo di pertinenza in quali avanzate eDiscovery accetta le conoscenze acquisite durante la fase di formazione e viene applicato alla popolazione intero file. Tutti i file nel gruppo di file pertinenti vengono valutati per pertinenza e assegnati un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p110">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="14b0e-156">Implicazioni: Il problema è diventato stabile e calcolo Batch può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="14b0e-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="14b0e-157">Aggiornamento: Pertinenza indica quando un esperto vengono esaminati tag e un esempio di file selezionati da un carico aggiuntivo file durante uno scenario di distribuzione viene caricato.</span><span class="sxs-lookup"><span data-stu-id="14b0e-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="14b0e-158">Implicazioni: È stato aggiunto un nuovo caricamento e aggiornamento è necessario per continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="14b0e-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="14b0e-159">Contrassegnare le incoerenze: processo consente di identificare, tramite un algoritmo di eDiscovery avanzate incoerenze nel file di tagging del processo che può influire negativamente sull'analisi.</span><span class="sxs-lookup"><span data-stu-id="14b0e-159">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="14b0e-160">Implicazioni: Nell'esempio successivo includerà i file che sono stati applicati i tag negli esempi precedenti e il contrassegno deve essere ripetute.</span><span class="sxs-lookup"><span data-stu-id="14b0e-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="14b0e-161">Aggiornare classificatore: consente di applicare tagging o le modifiche di seeding.</span><span class="sxs-lookup"><span data-stu-id="14b0e-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="14b0e-162">Implicazioni: Tagging e il seeding modifiche possono essere applicate senza dover eseguire manualmente un ulteriore esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="14b0e-163">In attesa: completamento del processo formazione la pertinenza.</span><span class="sxs-lookup"><span data-stu-id="14b0e-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="14b0e-164">Implicazioni: Nessun formazione di pertinenza è necessaria a questo punto.</span><span class="sxs-lookup"><span data-stu-id="14b0e-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="14b0e-165">Sebbene eDiscovery avanzate viene descritto il processo con altri passaggi consigliati nelle diverse fasi, consente inoltre per esplorare le pagine e schede e per effettuare le scelte a situazioni indirizzo che possono essere pertinenti al caso singolo problema, o processo di revisione documento.</span><span class="sxs-lookup"><span data-stu-id="14b0e-165">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="14b0e-p111">È possibile accettare o ignorare opportune eDiscovery avanzate scelte di elaborazione. Se si desidera eseguire un passaggio oltre il passaggio successivo consigliato, fare clic sul **passaggio successivo** elencate nella visualizzazione problema espansa nella finestra di dialogo, fare clic sul pulsante **Modifica** accanto al passaggio successivo e selezionare un'altra opzione passaggio successiva.</span><span class="sxs-lookup"><span data-stu-id="14b0e-p111">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="14b0e-168">Alcune opzioni continuino a restituire disabilitati dopo lo sblocco come non supportati per l'utilizzo a questo punto del processo.</span><span class="sxs-lookup"><span data-stu-id="14b0e-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="14b0e-169">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="14b0e-169">More information</span></span>

[<span data-ttu-id="14b0e-170">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="14b0e-170">Understanding Assessment in Relevance</span></span>](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="14b0e-171">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="14b0e-171">Tagging and Assessment</span></span>](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="14b0e-172">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="14b0e-172">Tagging and Relevance training</span></span>](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="14b0e-173">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="14b0e-173">Tracking Relevance analysis</span></span>](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="14b0e-174">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="14b0e-174">Deciding based on the results</span></span>](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="14b0e-175">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="14b0e-175">Testing Relevance analysis</span></span>](../test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="14b0e-176">Eseguire una query all'interno di working set</span><span class="sxs-lookup"><span data-stu-id="14b0e-176">Query within working set</span></span>](working-set-search.md)
