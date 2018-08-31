---
title: Aggiunta di tag e valutazione in Office 365 Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 'Rivedere i passaggi per eseguire la formazione Assessment, inclusi i file di tagging ed esaminare i risultati della valutazione di Office 365 avanzate eDiscovery. '
ms.openlocfilehash: 0f67dd4780a29536888231f556c18fe887f230ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530669"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d14c3-103">Aggiunta di tag e valutazione in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d14c3-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d14c3-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="d14c3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d14c3-106">In questa sezione viene descritta la procedura per il modulo di valutazione della pertinenza eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="d14c3-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="d14c3-107">Esecuzione di analisi e formazione di valutazione</span><span class="sxs-lookup"><span data-stu-id="d14c3-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="d14c3-108">Nella **pertinenza \> traccia** fare clic su **Assessment** per avviare assessment maiuscole.</span><span class="sxs-lookup"><span data-stu-id="d14c3-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="d14c3-109">Ad esempio ai fini di questa procedura, viene creato un set di valutazione di esempio di 500 file e viene visualizzata la scheda **Tag** , che contiene il pannello di Tagging, il contenuto del file visualizzato e altre opzioni tagging.</span><span class="sxs-lookup"><span data-stu-id="d14c3-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![Scheda Tag pertinenza per la valutazione](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="d14c3-111">Ogni file di esempio di leggere, determinare la pertinenza del file per ogni problema di maiuscole e contrassegnare il file utilizzando il Relevance (R) non pertinenti (NR) ed evitare i pulsanti nel riquadro **Pannello Tagging** .</span><span class="sxs-lookup"><span data-stu-id="d14c3-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="d14c3-p102">Valutazione richiede 500 file contrassegnati. Se i file sono "ignorati", si riceverà più file al tag.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p102">Assessment requires 500 tagged files. If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="d14c3-114">Dopo aver tagging tutti i file nel modello, fare clic su **Calcola**.</span><span class="sxs-lookup"><span data-stu-id="d14c3-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="d14c3-p103">Il margine di errore corrente di valutazione e complessità vengono calcolate e visualizzate nella scheda **Tenere traccia di pertinenza** , con informazioni dettagliate espanse per ogni problema, come illustrato di seguito. Ulteriori informazioni su questa finestra di dialogo sono descritti nella sezione successiva "Risultati valutazioni revisioni".</span><span class="sxs-lookup"><span data-stu-id="d14c3-p103">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below. More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![Traccia di pertinenza: valutazione](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="d14c3-p104">Per impostazione predefinita, è consigliabile che procedere al passaggio successivo predefinito al termine, l'indicatore di stato di valutazione per il problema per indicare che è stato rivisto il codice di esempio di valutazione e relativi file sufficienti sono stati contrassegnati. > In caso contrario, se si desidera visualizzare i risultati della scheda di **tenere traccia** e controllo margine di errore e il passaggio successivo, fare clic su **Modifica** accanto al **Passaggio successivo**, selezionare **continua valutazione**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p104">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged. > Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="d14c3-p105">Fare clic su **Modifica** a destra della casella di controllo **Assessment** per visualizzare e specificare i parametri di valutazione per ogni problema. Verrà visualizzata una finestra di dialogo **livello di valutazione** per ogni problema, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d14c3-p105">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue. An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![Problema relativo al livello di valutazione per il caso](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="d14c3-123">I parametri seguenti per il rilascio vengono calcolati e visualizzati nella finestra di dialogo **livello di valutazione** :</span><span class="sxs-lookup"><span data-stu-id="d14c3-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="d14c3-p106">**Margine di errore di destinazione per il richiamo stima**: in base a questo valore, viene calcolato il numero stimato di file aggiuntivi necessari per la revisione. Il margine utilizzato per il richiamo è maggiore di con un livello di probabilità 95% e 75%.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p106">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated. The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="d14c3-126">**I file di valutazione aggiuntive necessarie**: indica il numero di file ulteriori è necessario se non sono stati soddisfatti i requisiti del margine di errore corrente.</span><span class="sxs-lookup"><span data-stu-id="d14c3-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="d14c3-127">Per regolare il margine di errore corrente e verificare l'effetto dei margini di errore diverso (per ogni problema):</span><span class="sxs-lookup"><span data-stu-id="d14c3-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="d14c3-128">Nell'elenco **Selezionare problema** , selezionare un problema.</span><span class="sxs-lookup"><span data-stu-id="d14c3-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="d14c3-129">Nel **margine di errore di destinazione per il richiamo stima**, immettere un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="d14c3-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="d14c3-130">Fare clic su **Aggiorna i valori** per visualizzare l'impatto delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="d14c3-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="d14c3-131">Fare clic su **Avanzate** nella finestra di dialogo **livello di valutazione** per vedere i seguenti parametri aggiuntivi e i dettagli:</span><span class="sxs-lookup"><span data-stu-id="d14c3-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![Visualizzazione avanzata dei problemi relativi al livello di valutazione per il caso](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="d14c3-133">**Complessità stimata**: stimato complessità in base ai risultati della valutazione corrente</span><span class="sxs-lookup"><span data-stu-id="d14c3-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="d14c3-p107">**Per il richiamo assunto**: per impostazione predefinita, il margine di errore di destinazione si applica per richiamare il 75%. Se si desidera modificare questo parametro e controllare il margine di errore in un intervallo di valori richiamo diverso, fare clic su **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="d14c3-p107">**For assumed recall**: By default, the target error margin applies to recall above 75%. Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="d14c3-p108">**Livello di probabilità**: per impostazione predefinita, il margine di errore consigliato per la probabilità è 95%. Se si desidera modificare questo parametro, fare clic su **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="d14c3-p108">**Confidence level**: By default, the recommended error margin for confidence is 95%. Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="d14c3-138">**Margine di errore previsto complessità**: dati i valori aggiornati, si tratta il margine di errore della completezza previsto dopo vengono esaminati tutti i file di valutazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d14c3-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="d14c3-139">**I file di valutazione aggiuntive necessarie**: in base ai valori aggiornati, il numero di valutazione aggiuntive file che devono essere esaminato per raggiungere la destinazione.</span><span class="sxs-lookup"><span data-stu-id="d14c3-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="d14c3-140">**Valutazione totale file necessari**: dati i valori aggiornati, in totale file assessment necessari per la revisione.</span><span class="sxs-lookup"><span data-stu-id="d14c3-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="d14c3-141">**Numero previsto di file rilevanti nella valutazione**: in base ai valori aggiornati, il numero previsto di file rilevanti nell'intera valutazione dopo che tutti i file di valutazione aggiuntive vengono esaminati.</span><span class="sxs-lookup"><span data-stu-id="d14c3-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="d14c3-p109">Fare clic su **Ricalcola valori**, se sono stati modificati parametri. Al termine, se non esiste un problema, fare clic su **OK** per salvare le modifiche (o **successiva** quando sono presenti più problemi per leggere o modificare, quindi **completare la**).</span><span class="sxs-lookup"><span data-stu-id="d14c3-p109">Click **Recalculate values**, if parameters are changed. When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="d14c3-144">Quando sono presenti più problemi, dopo che tutti i problemi sono stati esaminati o modificati, un **livello di valutazione: riepilogo** finestra di dialogo visualizzata come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d14c3-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Riepilogo del livello di valutazione](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="d14c3-146">Dopo il completamento della valutazione, passare alla fase successiva di formazione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="d14c3-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="d14c3-147">Esaminare i risultati della valutazione</span><span class="sxs-lookup"><span data-stu-id="d14c3-147">Reviewing assessment results</span></span>

<span data-ttu-id="d14c3-148">Dopo che è contrassegnato come un esempio di valutazione, i risultati della valutazione vengono calcolati e visualizzati nella scheda tenere traccia di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="d14c3-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="d14c3-149">I risultati seguenti vengono visualizzati nella visualizzazione della traccia espansa:</span><span class="sxs-lookup"><span data-stu-id="d14c3-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="d14c3-150">Margine di errore corrente di valutazione per le stime richiamo</span><span class="sxs-lookup"><span data-stu-id="d14c3-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="d14c3-151">Complessità stimato</span><span class="sxs-lookup"><span data-stu-id="d14c3-151">Estimated richness</span></span>
    
- <span data-ttu-id="d14c3-152">File di valutazione aggiuntive necessari (per revisione)</span><span class="sxs-lookup"><span data-stu-id="d14c3-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="d14c3-p110">Il margine di errore Assessment corrente è il margine di errore consigliato da eDiscovery avanzate. Il numero visualizzato per i file di valutazione aggiuntive"necessari" corrisponde a tale suggerimento.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p110">The Assessment current error margin is the error margin recommended by Advanced eDiscovery. The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="d14c3-p111">L'indicatore di stato Assessment Mostra il livello di completamento della valutazione, in base al margine di errore corrente. Durante la valutazione è in corso, l'utente verrà contrassegnare un ulteriore esempio di valutazione.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p111">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin. When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="d14c3-157">Quando l'indicatore di stato assessment viene indicato anche come completata, significa che è stata completata la revisione di esempio valutazione e relativi file sufficienti sono stati contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="d14c3-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="d14c3-158">Visualizzazione della traccia espansa viene illustrato il passaggio successivo consigliato, le statistiche di valutazione e l'accesso a risultati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="d14c3-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="d14c3-p112">Quando è molto ridotta complessità, il numero di file di valutazione aggiuntive necessarie per raggiungere un numero minimo di file rilevanti per generare statistiche utili è molto alto. EDiscovery avanzate consiglierà quindi passare alla formazione. L'indicatore di stato assessment è ombreggiato e statistiche non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p112">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high. Advanced eDiscovery will then recommend moving on to training. The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="d14c3-p113">In assenza di forma statistica base stabilizzazione, ci sarà risultati con un livello inferiore del livello di affidabilità e accuratezza. Tuttavia, questi risultati possono essere utilizzati per individuare i file necessari quando non è necessario conoscere la percentuale di trovare i file necessari. Analogamente, questo stato utilizzabile per formare problemi con complessità bassa, dove punteggio di pertinenza in grado di accelerare l'accesso ai file rilevanti per un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p113">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level. However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found. Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="d14c3-p114">Nella **pertinenza \> traccia** scheda visualizzazione problema espansa, sono disponibili le seguenti opzioni di visualizzazione: > passaggio successivo consigliato, ad esempio **passaggio successivo: Tagging** può essere ignorata (per ogni problema) fare clic sul pulsante **Modifica** per il relativo destra e quindi selezionare un altro passaggio nel **passaggio successivo**. Se l'indicatore di stato assessment non è stata completata, valutazione sarà l'opzione consigliata successivo, tag più file di valutazione e aumentare l'accuratezza statistiche. > È possibile modificare il margine di errore e valutarne l'impatto, fare clic su **Modifica**e nella finestra di **dialogo livello Assessment**modifica il **margine di errore di destinazione per il richiamo stima**e facendo clic su **valori di aggiornamento**. Inoltre, questa finestra di dialogo è possibile visualizzare le opzioni avanzate, facendo clic su **Avanzate**. > È possibile visualizzare le statistiche a livello di valutazione aggiuntive e l'impatto facendo clic su **Visualizza**. Nella finestra di dialogo risultati dettagli visualizzata le statistiche sono disponibili per ogni problema, quando sono presenti file assessment contrassegnati almeno 500 e i file di almeno 18 contrassegnati come relativo per il problema.</span><span class="sxs-lookup"><span data-stu-id="d14c3-p114">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**. When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy. > You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**. Also, in this dialog, you can view advanced options, by clicking **Advanced**. > You can view additional assessment level statistics and their impact by clicking **View**. In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d14c3-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14c3-171">See also</span></span>

[<span data-ttu-id="d14c3-172">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d14c3-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d14c3-173">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="d14c3-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d14c3-174">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="d14c3-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d14c3-175">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="d14c3-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d14c3-176">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="d14c3-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d14c3-177">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="d14c3-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

