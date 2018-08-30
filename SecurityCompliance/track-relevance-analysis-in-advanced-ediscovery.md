---
title: Tener traccia dell’analisi di Rilevanza in Office 365 Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Informazioni su come visualizzare e interpretare i risultati per i problemi casi di eDiscovery avanzate di Office 365 e lo stato di formazione di pertinenza.  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531455"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ecf02-103">Tener traccia dell’analisi di Rilevanza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ecf02-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ecf02-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ecf02-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ecf02-106">In eDiscovery avanzate, la scheda di tenere traccia di pertinenza Mostra la validità calcolata di formazione pertinenza eseguita nella scheda Tag e indica il passaggio successivo da eseguire nel processo di formazione iterativo pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ecf02-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="ecf02-107">Monitorare lo stato di formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="ecf02-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="ecf02-108">Visualizzare i dettagli seguenti in pertinenza traccia dei problemi di maiuscole, come illustrato nell'esempio seguente di una finestra di dialogo **nome problema** riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ecf02-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="ecf02-p102">**Valutazione**: questo indicatore di stato indica in quale misura la pertinenza formazione eseguite fino a questo punto ha raggiunto la destinazione di valutazione in termini di margine di errore. Viene visualizzato anche di sfruttare i risultati di formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p102">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error. The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="ecf02-p103">**Formazione**: in questo corso caratterizzata indicatore e descrizione comando è visualizzato il formazione pertinenza dei risultati di stabilità e contrassegnati per ogni problema di una scala numerica indicante il numero di campioni di formazione di pertinenza. Esperto consente di monitorare lo stato di avanzamento del processo di training pertinenza iterativo.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p103">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue. The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="ecf02-113">**Calcolo batch**: questo indicatore di stato vengono fornite informazioni relative al completamento del calcolo Batch.</span><span class="sxs-lookup"><span data-stu-id="ecf02-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="ecf02-114">**Passaggio successivo**: viene visualizzato il suggerimento per il passaggio successivo da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ecf02-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="ecf02-p104">Nell'esempio viene visualizzata una valutazione completata correttamente a un problema indicato dall'indicatore di stato completato colore e il segno di spunta. Tagging è in corso, ma il caso viene considerato ancora instabile (come mostrato nella descrizione comando stato stabilità). L'indicazione di passaggio successivo è "Training".</span><span class="sxs-lookup"><span data-stu-id="ecf02-p104">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark. Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip). The next step recommendation is "Training".</span></span> 
    
    ![Fase 1 del corso di formazione sulla traccia di pertinenza](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="ecf02-p105">La visualizzazione espansa Mostra opzioni e le informazioni aggiuntive. Il margine di errore visualizzato corrente è il margine di errore di richiamo nello stato corrente della valutazione, dato i file assessment (già contrassegnati) esistenti.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p105">The expanded view displays additional information and options. The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="ecf02-p106">È possibile ignorare la fase di valutazione, deselezionare la casella di controllo di **valutazione** per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci sarà alcun le statistiche per questo problema. > Deselezionando la casella di controllo **Assessment** può essere eseguita solo prima dell'esecuzione di valutazione. Quando sono presenti più problemi in un caso, valutazione viene ignorato solo se la casella di controllo è deselezionata per ogni problema</span><span class="sxs-lookup"><span data-stu-id="ecf02-p106">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="ecf02-125">Al termine della valutazione non con assessment potrebbe essere il passaggio successivo per il tagging più file nel primo esempio viene impostata dei file.</span><span class="sxs-lookup"><span data-stu-id="ecf02-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="ecf02-p107">In **pertinenza** \> **traccia**, l'indicatore di stato di formazione e descrizione comando specificare il numero stimato di esempi aggiuntivi necessari per raggiungere la stabilità. Questa stima vengono fornite linee guida per la formazione aggiuntiva necessaria.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p107">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability. This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Corso di formazione sulla traccia di pertinenza](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="ecf02-p108">Una volta tagging fine e se è necessario continuare la formazione, fare clic su **formazione**. Un altro insieme di file di esempio è generato da impostare per la formazione aggiuntiva del file caricato. Vengono restituiti la scheda Tag per contrassegnare e formazione più file.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p108">When you're done tagging and if you need to continue training, click **Training**. Another sample set of files is generated from the loaded file set for additional training. You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="ecf02-132">Sta per raggiungere i livelli di formazione stabili</span><span class="sxs-lookup"><span data-stu-id="ecf02-132">Reaching stable training levels</span></span>

<span data-ttu-id="ecf02-133">I file di valutazione hanno raggiunto un livello stabile del corso di formazione, eDiscovery avanzate è pronto per il calcolo Batch.</span><span class="sxs-lookup"><span data-stu-id="ecf02-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecf02-p109">In genere dopo tre stabile esempi di formazione, il passaggio successivo è "Calcolo Batch". Potrebbero esserci eccezioni, ad esempio, quando sono state eseguite modifiche per il tagging del file da esempi precedenti o in cui sono stati aggiunti i file di seeding.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p109">Usually, after three stable training samples, the next step is "Batch calculation". There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="ecf02-136">Esecuzione di calcolo Batch</span><span class="sxs-lookup"><span data-stu-id="ecf02-136">Performing Batch calculation</span></span>

<span data-ttu-id="ecf02-137">Calcolo batch viene eseguito il passaggio successivo al termine formazione correttamente (quando lo stato stabile formazione viene visualizzato dall'indicatore di stato, un segno di spunta e lo stato stabile nella descrizione comando.) Calcolo batch applica le conoscenze acquisite durante la formazione di pertinenza per popolazione intero file, per valutare la pertinenza i file e assegnare punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ecf02-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="ecf02-p110">Quando sono presenti più di un problema, Batch il calcolo viene eseguito per ogni problema. Durante il calcolo Batch, stato di avanzamento viene monitorato durante l'elaborazione di tutti i file.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p110">When there is more than one issue, Batch calculation is done per issue. During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="ecf02-p111">In questo caso, il passaggio successivo consigliato è "None", che non indica che nessuna formazione pertinenza iterativa aggiuntiva necessaria a questo punto. Fase successiva è il **pertinenza \> stabilire** scheda.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p111">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point. The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="ecf02-142">Se si desidera importare nuovi file dopo il calcolo Batch, l'amministratore può aggiungere i file importati a un carico di nuovo.</span><span class="sxs-lookup"><span data-stu-id="ecf02-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecf02-p112">Se si sceglie **Annulla** durante il calcolo Batch, il processo di Salva quali è stato già eseguito. Se si esegue nuovamente calcolo Batch, il processo verrà completato l'ultimo punto eseguita.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p112">If you click **Cancel** during Batch calculation, the process saves what was already executed. If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="ecf02-145">Valutazione della coerenza tagging</span><span class="sxs-lookup"><span data-stu-id="ecf02-145">Assessing tagging consistency</span></span>

<span data-ttu-id="ecf02-p113">Se nel file tagging sono presenti incongruenze, può influire l'analisi. Consente di eDiscovery avanzate tagging processo coerenza quando i risultati non sono ottimali o coerenza è in dubbio. Viene restituito un elenco dei file in modo incoerente contrassegnati possibili e può essere esaminati e nuovamente contrassegnati da tag, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p113">If there are inconsistencies in file tagging, it can affect the analysis. The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt. A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecf02-p114">Dopo aver sette o più Arrotonda formazione assessment seguente, la coerenza di tagging possono essere visualizzati in **pertinenza** \> **traccia** \> **problema** \> **risultati dettagliati** \> **corso di formazione**. Questa verifica viene eseguita per un problema alla volta.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p114">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**. This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="ecf02-151">In **pertinenza \> traccia**, espandere la riga del problema.</span><span class="sxs-lookup"><span data-stu-id="ecf02-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="ecf02-152">A destra del **passaggio successivo**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ecf02-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="ecf02-153">Selezionare **le incoerenze di Tag** all'opzione **passaggio successivo** , dopo aver sette esempi di formazione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecf02-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="ecf02-p115">Selezionare **le incoerenze di Tag**. Viene visualizzata la scheda **Tag** un elenco di incongruenze nuovamente contrassegnare in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p115">Select **Tag inconsistencies**. The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="ecf02-p116">Fare clic su **Calcola** per inviare le modifiche. Il passaggio successivo tagging incoerenze è "Training".</span><span class="sxs-lookup"><span data-stu-id="ecf02-p116">Click **Calculate** to submit the changes. The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="ecf02-158">Visualizzazione e utilizzo dei risultati di pertinenza</span><span class="sxs-lookup"><span data-stu-id="ecf02-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="ecf02-p117">Nella **pertinenza \> traccia** la scheda, espandere la riga del problema e accanto a **risultati dettagliati**, fare clic su **Visualizza**. I riquadri risultati dettagliati sono visualizzate, come illustrato e descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p117">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**. The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Risultati dettagliati della formazione sulla pertinenza](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="ecf02-162">Tagging di riepilogo</span><span class="sxs-lookup"><span data-stu-id="ecf02-162">Tagging summary</span></span>

 <span data-ttu-id="ecf02-163">Nell'esempio riportato di seguito, il **Riepilogo utilizzo dei tag** vengono visualizzati i totali per ognuno di valutazione, formazione e file di aggiornamento contrassegno processi.</span><span class="sxs-lookup"><span data-stu-id="ecf02-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Riepilogo tagging della traccia di pertinenza](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="ecf02-165">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecf02-165">Keywords</span></span>

<span data-ttu-id="ecf02-p118">Una parola chiave è una stringa univoca, word, frase o sequenza di parole in un file identificato da eDiscovery avanzate come indicatore significativo se di un file è pertinente. Le colonne "Include" elencano pesi nei file contrassegnati come relativo e parola chiave e le colonne "Escludere" sono elencate le parole chiave e spessori nei file contrassegnati come non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p118">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant. The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="ecf02-p119">EDiscovery avanzate assegna dei valori di peso parola chiave positiva o negativa. Più è alto il peso, maggiore sarà la probabilità che un file in cui viene visualizzata la parola chiave viene assegnato un punteggio di pertinenza durante il calcolo Batch.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p119">Advanced eDiscovery assigns negative or positive keyword weight values. The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="ecf02-170">L'elenco di eDiscovery avanzata delle parole chiave può essere utilizzato per integrare un elenco creato da un esperto o come un test di integrità indiretti in qualsiasi punto nel file del processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="ecf02-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="ecf02-171">Corso di formazione</span><span class="sxs-lookup"><span data-stu-id="ecf02-171">Training progress</span></span>

<span data-ttu-id="ecf02-172">Nel riquadro di **Corso di formazione** include una formazione stato grafico e qualità indicatore display, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ecf02-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Stato di avanzamento del corso di formazione sulla traccia di pertinenza](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="ecf02-174">**Formazione indicatore di qualità**: la classificazione della coerenza tagging come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ecf02-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="ecf02-p120">**Buona**: file contrassegnati in modo coerente. (Verde chiaro visualizzati)</span><span class="sxs-lookup"><span data-stu-id="ecf02-p120">**Good**: Files are tagged consistently. (Green light displayed)</span></span>
    
- <span data-ttu-id="ecf02-p121">**Medio**: alcuni file possono essere contrassegnati in modo incoerente. (Visualizzato di colore giallo chiaro)</span><span class="sxs-lookup"><span data-stu-id="ecf02-p121">**Medium**: Some files may be tagged inconsistently. (Yellow light displayed)</span></span>
    
- <span data-ttu-id="ecf02-p122">**Avviso**: numero di file potrebbe essere contrassegnati in modo incoerente. (Spia rossa visualizzata)</span><span class="sxs-lookup"><span data-stu-id="ecf02-p122">**Warning**: Many files may be tagged inconsistently. (Red light displayed)</span></span>
    
 <span data-ttu-id="ecf02-p123">**Grafico di corso di formazione**: viene illustrato il grado di stabilità della formazione pertinenza dopo un numero di cicli di formazione di pertinenza rispetto a quando il valore di misura F. Si sposta da sinistra a destra sul grafico, consente di restringere l'intervallo di confidenza e viene utilizzata insieme F-misura, da eDiscovery avanzate pertinenza per determinare la stabilità sono ottimizzate quando la formazione pertinenza dei risultati.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p123">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value. As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecf02-p124">Pertinenza utilizza F2, una metrica F misura in cui richiamo riceve del doppio spessore come precisione doppia. Per i casi con complessità alta (oltre 25%), viene utilizzata la pertinenza F1 (rapporto 1:1). Il rapporto F misura può essere configurato nelle **impostazioni di pertinenza** \> **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p124">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision. For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio). The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="ecf02-186">Risultati del calcolo batch</span><span class="sxs-lookup"><span data-stu-id="ecf02-186">Batch calculation results</span></span>

<span data-ttu-id="ecf02-187">Riquadro **dei risultati di calcolo Batch** include il numero di file che sono stati punteggio di pertinenza, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ecf02-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="ecf02-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="ecf02-188">**Success**</span></span>
    
- <span data-ttu-id="ecf02-189">**Vuoto**: non contiene testo, ad esempio, solo gli spazi/schede</span><span class="sxs-lookup"><span data-stu-id="ecf02-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="ecf02-190">**Operazione non riuscita**: a causa di dimensioni eccessive o non è stato possibile leggere</span><span class="sxs-lookup"><span data-stu-id="ecf02-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="ecf02-191">**Ignored**: a causa di dimensioni eccessive</span><span class="sxs-lookup"><span data-stu-id="ecf02-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="ecf02-192">**Nebulous**: contiene testo privo di significato o nessuna funzionalità pertinente al problema</span><span class="sxs-lookup"><span data-stu-id="ecf02-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="ecf02-193">Vuoto, non superato, Ignored o Nebulous riceverà un punteggio di pertinenza-1.</span><span class="sxs-lookup"><span data-stu-id="ecf02-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="ecf02-194">Statistiche di formazione</span><span class="sxs-lookup"><span data-stu-id="ecf02-194">Training statistics</span></span>

<span data-ttu-id="ecf02-195">Il riquadro delle **statistiche di formazione** consente di visualizzare le statistiche e grafici in base ai risultati di formazione di pertinenza eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="ecf02-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Statistiche del corso di formazione sulla traccia di pertinenza](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="ecf02-197">Consente di visualizzare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecf02-197">This view shows the following:</span></span>
  
- <span data-ttu-id="ecf02-p125">**Rapporto richiamo revisione**: confronto tra i risultati in base alla pertinenza punteggi una revisione registrare lineare. Richiamo stima assegnato il set di dimensioni di set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p125">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review. Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="ecf02-200">**Parametro**: cumulativo calcolate le statistiche relative alla revisione imposta in relazione alla popolazione di file per il case intero.</span><span class="sxs-lookup"><span data-stu-id="ecf02-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="ecf02-201">**Esaminare**: percentuale di file da esaminare basato su questo limite.</span><span class="sxs-lookup"><span data-stu-id="ecf02-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="ecf02-202">**Richiamo**: percentuale del relativo file nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="ecf02-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="ecf02-p126">**Distribuzione per punteggio di pertinenza**: file visualizzati in grigio scuro a sinistra nella sono sotto il limite punteggio. Descrizione comando viene visualizzato il punteggio di pertinenza e la percentuale correlata dei file nel file di revisione impostato in base al numero totale di file.</span><span class="sxs-lookup"><span data-stu-id="ecf02-p126">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ecf02-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecf02-205">See also</span></span>

[<span data-ttu-id="ecf02-206">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ecf02-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ecf02-207">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="ecf02-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ecf02-208">Esecuzione e la revisione di valutazione</span><span class="sxs-lookup"><span data-stu-id="ecf02-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ecf02-209">Esecuzione di formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="ecf02-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ecf02-210">Le decisioni basate sui risultati</span><span class="sxs-lookup"><span data-stu-id="ecf02-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="ecf02-211">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="ecf02-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

