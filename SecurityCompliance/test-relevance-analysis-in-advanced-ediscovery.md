---
title: Valutare l’analisi di Rilevanza in Office 365 Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: "Informazioni su come utilizzare la scheda Test dopo il calcolo Batch in Office 365 avanzate eDiscovery per testare, confronto e convalidare della qualità globale dell'elaborazione.  "
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530819"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="927ac-103">Valutare l’analisi di Rilevanza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="927ac-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="927ac-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="927ac-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="927ac-p102">Nella scheda Test di eDiscovery avanzate consente di testare, confronto e convalidare della qualità globale dell'elaborazione. Questi test vengono eseguiti dopo il calcolo Batch. Per contrassegno i file della raccolta, un esperto rende la decisione finale se tutti i file contrassegnati viene effettivamente rilevanti per il case.</span><span class="sxs-lookup"><span data-stu-id="927ac-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="927ac-p103">Negli scenari con uno o più problemi test sono in genere eseguito per ogni problema. I risultati possono essere visualizzati dopo ogni test e i risultati dei test può essere adattati con i file di test di esempio specificato.</span><span class="sxs-lookup"><span data-stu-id="927ac-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="927ac-111">Nella parte restante di test</span><span class="sxs-lookup"><span data-stu-id="927ac-111">Testing the rest</span></span>

<span data-ttu-id="927ac-p104">Il test "Testare il resto" viene utilizzato per convalidare le decisioni eliminazione selettiva, ad esempio, per esaminare solo file sopra un punteggio limito di pertinenza specifico in base ai risultati finali eDiscovery avanzate. Esperto illustra un esempio di file in un punteggio limito selezionato calcolare il numero di file pertinenti all'interno di tale set.</span><span class="sxs-lookup"><span data-stu-id="927ac-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="927ac-p105">Questo test vengono fornite le statistiche e un confronto tra il set di revisione e il Test della popolazione Rest. I risultati del set di revisione sono quelli calcolati per pertinenza durante la formazione. I risultati includono calcoli, in base alle impostazioni e i parametri di input, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="927ac-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="927ac-117">Testare le statistiche di esempio il numero di file in un file pertinente di esempio e identificati.</span><span class="sxs-lookup"><span data-stu-id="927ac-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="927ac-p106">Confronto tra tabulare dei parametri popolazione del set di revisione e gli altri componenti, ad esempio, il numero di file, numero stimato di file rilevanti, complessità stimato e il costo medio di ricerca di un altro file pertinente. Costi parametro impostazioni possono essere configurate dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="927ac-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="927ac-120">Apri il **pertinenza \> Test** scheda.</span><span class="sxs-lookup"><span data-stu-id="927ac-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="927ac-p107">Nella scheda **Test** , fare clic su **Nuovo test**. Verrà visualizzata la finestra di dialogo **Crea di test** , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="927ac-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Risultati del test sull'inattività di pertinenza](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="927ac-124">In **nome Test**e **Descrizione**digitare il nome e descrizione.</span><span class="sxs-lookup"><span data-stu-id="927ac-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="927ac-125">Nell'elenco **tipo di Test** , selezionare **Test il resto**</span><span class="sxs-lookup"><span data-stu-id="927ac-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="927ac-126">Nella **problema / categoria** , selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="927ac-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="927ac-127">Nell'elenco **caricare** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="927ac-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="927ac-128">In **% lettura**, accettare il valore predefinito oppure selezionare un valore per il limite punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="927ac-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="927ac-p108">**Impostare dimensioni**, oppure accettare il valore predefinito. Si noti che le icone di ripristino è possibile ripristinare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="927ac-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="927ac-p109">Fare clic su **Start tagging**. Viene generato un campione.</span><span class="sxs-lookup"><span data-stu-id="927ac-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="927ac-133">Rivedere e contrassegnare ciascuno dei file nel **pertinenza \> Tag** delle schede e al termine, fare clic su **calcolo**.</span><span class="sxs-lookup"><span data-stu-id="927ac-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="927ac-p110">Nella scheda Test è possibile scegliere di **visualizzare i risultati** per visualizzare i risultati del test. Nella figura seguente è illustrato un esempio.</span><span class="sxs-lookup"><span data-stu-id="927ac-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![Risultati del test sull'inattività](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="927ac-137">Nella figura precedente, la sezione **esempi di parametri** della tabella contiene informazioni dettagliate sul numero di file di esempio contrassegnato da un esperto e il numero di file rilevanti trovato nel modello di tale.</span><span class="sxs-lookup"><span data-stu-id="927ac-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="927ac-p111">La sezione **parametri popolazione** della tabella contiene i risultati del test, inclusi la compilazione di set di verifica dei file con un punteggio sotto il limite selezionato e popolazione "Il resto" dei file con un punteggio sopra il limite selezionato. Per ogni popolazione, vengono visualizzati i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="927ac-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="927ac-140">Include i file con % lettura - limite già indicati</span><span class="sxs-lookup"><span data-stu-id="927ac-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="927ac-141">Il numero totale di file</span><span class="sxs-lookup"><span data-stu-id="927ac-141">The total number of files</span></span> 
    
- <span data-ttu-id="927ac-142">Il numero stimato di file rilevanti</span><span class="sxs-lookup"><span data-stu-id="927ac-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="927ac-143">Complessità stimato</span><span class="sxs-lookup"><span data-stu-id="927ac-143">The estimated richness</span></span> 
    
- <span data-ttu-id="927ac-144">Il costo medio revisione della ricerca di un altro file rilevante</span><span class="sxs-lookup"><span data-stu-id="927ac-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="927ac-145">La parte del test</span><span class="sxs-lookup"><span data-stu-id="927ac-145">Testing the slice</span></span>

<span data-ttu-id="927ac-146">"Testare la sezione" test consente di eseguire test simili a "Testare il resto" test, ma a un segmento del file impostata secondo quanto specificato % lettura di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="927ac-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="927ac-147">Apri il **pertinenza \> Test** scheda.</span><span class="sxs-lookup"><span data-stu-id="927ac-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="927ac-p112">Nella scheda **Test** , fare clic su **Nuovo test**. Viene visualizzata la finestra di dialogo **Crea di test** .</span><span class="sxs-lookup"><span data-stu-id="927ac-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="927ac-150">In **nome Test** e **Descrizione**digitare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="927ac-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="927ac-151">Nell'elenco **tipo di Test** , selezionare **la parte del Test**.</span><span class="sxs-lookup"><span data-stu-id="927ac-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="927ac-152">Nell'elenco **problema** , selezionare il nome del problema.</span><span class="sxs-lookup"><span data-stu-id="927ac-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="927ac-153">Nell'elenco **caricare** selezionare il carico.</span><span class="sxs-lookup"><span data-stu-id="927ac-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="927ac-154">Nella finestra **% lettura tra**, accettare i valori predefiniti intervallo massimo e minimo o selezionare i valori per i punteggi pertinenza limiti.</span><span class="sxs-lookup"><span data-stu-id="927ac-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="927ac-155">**Impostare dimensioni**, selezionare un valore o accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="927ac-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="927ac-156">Il valore predefinito è possibile ripristinare le icone di ripristino.</span><span class="sxs-lookup"><span data-stu-id="927ac-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="927ac-p113">Fare clic su **Start tagging**. Viene generato un campione.</span><span class="sxs-lookup"><span data-stu-id="927ac-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="927ac-159">Rivedere e contrassegnare ciascuno dei file nel **pertinenza \> Tag** delle schede e al termine, fare clic su **calcolo**.</span><span class="sxs-lookup"><span data-stu-id="927ac-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="927ac-160">Nella scheda Test è possibile scegliere di **visualizzare i risultati** per visualizzare i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="927ac-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="927ac-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="927ac-161">See also</span></span>

[<span data-ttu-id="927ac-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="927ac-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="927ac-163">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="927ac-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="927ac-164">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="927ac-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="927ac-165">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="927ac-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="927ac-166">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="927ac-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="927ac-167">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="927ac-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

