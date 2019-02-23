---
title: La valutazione in Rilevanza di Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Ottenere una panoramica della fase di valutazione e del relativo ruolo per determinare la ricchezza dei problemi durante la formazione di pertinenza in Office 365 Advanced eDiscovery.
ms.openlocfilehash: 1ddaa7ef37f762d7b63bb6c0c51193ff382b8d6b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212976"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="03889-103">La valutazione in Rilevanza di Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="03889-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="03889-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="03889-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="03889-p102">Advanced eDiscovery consente di valutare precocemente, ad esempio, i problemi definiti e i dati importati per un caso. Advanced eDiscovery consente all'esperto di prendere decisioni relative a un approccio adottato e di applicarle al progetto di revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="03889-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="03889-108">Informazioni sulla valutazione</span><span class="sxs-lookup"><span data-stu-id="03889-108">Understanding assessment</span></span>

<span data-ttu-id="03889-p103">In valutazione, l'esperto esamina un insieme casuale di almeno 500 file, che vengono utilizzati per determinare la ricchezza dei problemi e produrre statistiche che riflettono i risultati della formazione. La valutazione ha esito positivo quando sono stati trovati file rilevanti sufficienti per raggiungere un livello statistico che consentirà di rendere più efficace la pertinenza di eDiscovery per fornire statistiche accurate e determinare efficacemente il punto di stabilizzazione nel processo di formazione.</span><span class="sxs-lookup"><span data-stu-id="03889-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="03889-p104">Maggiore è il numero di file rilevanti nel set di valutazione, maggiore è la precisione delle statistiche e l'efficacia dell'algoritmo di stabilità. Il numero di file rilevanti all'interno dei file di valutazione dipende dalla ricchezza del problema. La ricchezza è la percentuale stimata di file rilevanti nel set pertinente a un problema. I problemi con una ricchezza maggiore raggiungeranno un numero maggiore di file rilevanti più rapidamente rispetto ai problemi con una ricchezza più bassa. I problemi con una ricchezza estremamente bassa (ad esempio, il 2% o meno) richiedono un set di valutazioni molto esteso per raggiungere un numero significativo di file rilevanti.</span><span class="sxs-lookup"><span data-stu-id="03889-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="03889-p105">Le statistiche, presentate nelle schede traccia e decidi durante l'allenamento e dopo il calcolo del batch, includono stime di richiamo per diversi insiemi di revisione. In statistica, le stime basate su un set di esempio (in questo caso, i file di valutazione) includono il margine di errore e il livello di confidenza del margine di errore. Ad esempio, il richiamo stimato del 80% potrebbe avere un margine di errore pari o meno al 5% con un livello di confidenza pari al 95%. Questo significa che il richiamo stimato è effettivamente 75%-85% e questa stima ha 95% di confidenza. Maggiore è il set di valutazione, il margine di errore diventa più piccolo e le statistiche sono più accurate.</span><span class="sxs-lookup"><span data-stu-id="03889-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="03889-p106">Dopo che l'esperto ha esaminato un gruppo di valutazione iniziale di 500 file, la pertinenza è in grado di determinare il margine di errore corrente dei valori di richiamo. La pertinenza consentirà anche di impostare un margine di errore predefinito che consiglia di raggiungere per ottimizzare il set di valutazione. Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="03889-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="03889-124">Se il set di valutazione ha già restituito un margine di errore pari o meno al 10%, la pertinenza consiglierà di passare alla formazione (non è necessaria alcuna revisione di valutazione supplementare).</span><span class="sxs-lookup"><span data-stu-id="03889-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="03889-125">Se il set di valutazione ha restituito un margine di errore più o meno 13%, la pertinenza potrebbe consigliare la revisione di un altro gruppo di file di valutazione per raggiungere un margine inferiore.</span><span class="sxs-lookup"><span data-stu-id="03889-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="03889-126">Se la ricchezza è estremamente bassa, la pertinenza potrebbe consigliare l'interruzione della valutazione anche se il margine di errore è di grandi dimensioni (per rendere impraticabile la statistica), in quanto il set di valutazione necessario per raggiungere un margine di errore utile è troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="03889-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="03889-p107">Ogni problema ha la propria ricchezza, il margine di errore corrente e, di conseguenza, il numero stimato di file di valutazione aggiuntivi. Il set di valutazione successivo viene creato in base al numero massimo di file (fino a 1.000 in un solo set).</span><span class="sxs-lookup"><span data-stu-id="03889-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="03889-p108">È possibile accettare le indicazioni relative alla pertinenza o regolare il margine di errore corrente in base alle proprie esigenze. Il margine di errore corrente predefinito è determinato per il richiamo pari o superiori a 75%.</span><span class="sxs-lookup"><span data-stu-id="03889-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03889-p109">La fase di valutazione può essere ignorata, nella \*\* \> \*\* scheda Tracking pertinenza della visualizzazione espansa per un problema, deselezionando la casella di controllo **valutazione** per problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non saranno disponibili statistiche per questo problema. > deSelezionando la casella di controllo **valutazione** può essere eseguita solo prima di eseguire la valutazione. Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="03889-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="03889-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03889-135">See also</span></span>

[<span data-ttu-id="03889-136">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="03889-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="03889-137">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="03889-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="03889-138">Formazione di tagging e pertinenza</span><span class="sxs-lookup"><span data-stu-id="03889-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="03889-139">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="03889-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="03889-140">Decidere in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="03889-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="03889-141">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="03889-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

