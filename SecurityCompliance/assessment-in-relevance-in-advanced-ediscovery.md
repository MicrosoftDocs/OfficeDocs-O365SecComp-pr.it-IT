---
title: Informazioni sulla valutazione in Rilevanza di Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 'Panoramica della fase di valutazione e il ruolo per determinare la complessità dei problemi durante la formazione di pertinenza di Office 365 avanzate eDiscovery.  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530810"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2946f-103">Informazioni sulla valutazione in Rilevanza di Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2946f-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2946f-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2946f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2946f-p102">EDiscovery avanzate consente anticipata valutazione, ad esempio, per i problemi definiti e i dati importati per un caso. EDiscovery avanzate consente esperto per prendere decisioni relative a un approccio adottato e applicarle al progetto di revisione del documento.</span><span class="sxs-lookup"><span data-stu-id="2946f-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="2946f-108">Valutazione di informazioni</span><span class="sxs-lookup"><span data-stu-id="2946f-108">Understanding assessment</span></span>

<span data-ttu-id="2946f-p103">Nella valutazione, esperto viene esaminato un insieme casuale di almeno 500 file, che vengono utilizzati per determinare la complessità dei problemi e per generare statistiche che riflettono i risultati di formazione. Quando vengono rilevati file sufficienti pertinenti per raggiungere un livello statistico utili avanzate eDiscovery pertinenza per fornire statistiche accurate e determinare in modo efficace il punto stabilizzazione nel processo di formazione, valutazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2946f-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="2946f-p104">Maggiore che del numero dei pertinenti file nel set di valutazione, più precise le statistiche e l'efficacia dell'algoritmo stabilità. Il numero di file pertinenti all'interno dei file di valutazione dipende dalla quantità del problema. Complessità è % stimate del file rilevanti nel set di interesse per un problema. Problemi con maggiore complessità verranno raggiunta più velocemente rispetto a problemi di un numero elevato di file rilevanti con complessità inferiore. Problemi di complessità estremamente basso (ad esempio, % 2 o meno) richiederà una valutazione molto grande set di raggiungere un numero significativo di file rilevanti.</span><span class="sxs-lookup"><span data-stu-id="2946f-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="2946f-p105">Le statistiche, sono disponibili nelle schede tenere traccia e stabilire durante la formazione e dopo il calcolo Batch, includono stime della richiamo per la revisione diversi set. In statistiche, stime basate su un campione impostato (in questo caso, i file di valutazione) includono il margine di errore e il livello di probabilità di tale margine di errore. Richiamo stimato di 80%, ad esempio, potrebbe essere un margine di errore più o meno il 5% del con un livello di probabilità di 95%. Ciò significa che il richiamo stimato effettivamente il 75-85% e questa stima con confidenza 95%. Maggiore sarà il set di valutazione, il margine di errore diventa più piccolo e le statistiche sono più precise.</span><span class="sxs-lookup"><span data-stu-id="2946f-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="2946f-p106">Dopo l'esperto viene esaminato un insieme di valutazione iniziale dei file di 500, pertinenza è in grado di determinare il margine di errore dei valori richiamo corrente. Pertinenza inoltre viene impostato un margine di errore che consiglia di raggiungere per ottimizzare il set di valutazione predefinito. Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="2946f-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="2946f-124">Se la valutazione già impostata hanno restituito un margine di errore più o meno pari al 10% del, pertinenza indicazioni per passare alla formazione (non è necessaria alcuna revisione valutazione complementare).</span><span class="sxs-lookup"><span data-stu-id="2946f-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="2946f-125">Se il set di valutazione avesse portato a un margine di errore più o meno 13% del, pertinenza potrebbe essere consigliabile la revisione di un altro set di file di valutazione di raggiungere un margine inferiore.</span><span class="sxs-lookup"><span data-stu-id="2946f-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="2946f-126">Se complessità è insufficiente, pertinenza potrebbe essere consigliabile arresto assessment anche se il margine di errore è di grandi dimensioni (effettua le statistiche realizzabile), in quanto il set di valutazione consentono di raggiungere un utile margine di errore è troppo grande.</span><span class="sxs-lookup"><span data-stu-id="2946f-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="2946f-p107">Ogni problema con il proprio complessità, corrente margine di errore e di conseguenza, il numero stimato dei file di valutazione aggiuntive. Valutazione della serie successiva viene creato in base al numero massimo di file (fino a 1.000 in un unico insieme).</span><span class="sxs-lookup"><span data-stu-id="2946f-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="2946f-p108">È possibile accettare i suggerimenti di pertinenza o regolare il margine di errore corrente in base alle proprie esigenze. Il margine di errore corrente predefinito viene determinato per il richiamo è uguale o superiore al 75%.</span><span class="sxs-lookup"><span data-stu-id="2946f-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2946f-p109">La fase di valutazione può essere ignorata nel **pertinenza \> traccia** scheda nella visualizzazione espansa per un problema, deselezionare la casella di controllo di **valutazione** per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci sarà alcun le statistiche per questo problema. > Deselezionando la casella di controllo **Assessment** può essere eseguita solo prima dell'esecuzione di valutazione. Quando sono presenti più problemi in un caso, valutazione viene ignorato solo se la casella di controllo è deselezionata per ogni problema</span><span class="sxs-lookup"><span data-stu-id="2946f-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2946f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2946f-135">See also</span></span>

[<span data-ttu-id="2946f-136">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2946f-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2946f-137">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="2946f-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2946f-138">Tagging e formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="2946f-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2946f-139">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="2946f-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2946f-140">Stabilire in base ai risultati</span><span class="sxs-lookup"><span data-stu-id="2946f-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2946f-141">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="2946f-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

