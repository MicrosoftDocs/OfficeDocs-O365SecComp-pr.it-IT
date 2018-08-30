---
title: Decisione basata sui risultati in Office 365 Advanced eDiscovery
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
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Informazioni su come la scheda stabilire in Office 365 avanzate eDiscovery fornisce dati che consentono di determinano le dimensioni corrette del set di verifica dei file maiuscole. '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530515"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="04203-103">Decisione basata sui risultati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="04203-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="04203-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="04203-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="04203-106">In eDiscovery avanzate, la scheda stabilire fornisce informazioni aggiuntive per la visualizzazione e utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di verifica dei file maiuscole.</span><span class="sxs-lookup"><span data-stu-id="04203-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="04203-107">Nella scheda stabilire</span><span class="sxs-lookup"><span data-stu-id="04203-107">Using the Decide tab</span></span>

![Decisione di pertinenza](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="04203-109">In questa scheda include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04203-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="04203-110">**Problema**: da qui è possibile selezionare il problema di interesse dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="04203-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="04203-p102">**Rapporto richiamo revisione**: confronto delle avanzate eDiscovery revisione in base alle punteggio di pertinenza. Il punto limite nel grafico rappresenta la percentuale di file da esaminare, mappato a un punteggio di pertinenza. Nella fase di Test di pertinenza e come una soglia di esportazione viene utilizzato per l'eliminazione selettiva. Il punto limite predefinito, il numero di file di riferimento è in corrispondenza del punto in cui l'equilibrio tra la precisione e richiamo è ottimale. Il punto limito effettivo dovrebbe essere determinato dall'utente in base agli obiettivi e compromesso costo (% review) e rischi (% richiamo). Il dispositivo di scorrimento consente di modificare il punto di taglio e verificare l'effetto sui parametri e grafico durante l'aggiustamento % dei file pertinenti da recuperare e prima di convalidare una decisione.</span><span class="sxs-lookup"><span data-stu-id="04203-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="04203-p103">**Parametro**: leggere, tenere presente, parametri pertinenti e totale successiva sono cumulative calcolate statistiche relative alla revisione imposta in relazione alla raccolta per l'intera case. Definizioni di questi parametri sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="04203-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="04203-118">**Esaminare**: percentuale di file da esaminare basato su questo limite.</span><span class="sxs-lookup"><span data-stu-id="04203-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="04203-119">**Richiamo**: percentuale di file rilevanti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="04203-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="04203-120">**Successivo pertinenti**: costo per esaminare e identificare un altro file pertinente che non è attualmente la revisione impostato.</span><span class="sxs-lookup"><span data-stu-id="04203-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="04203-p104">**Costo totale**: costi per la revisione questa percentuale dei file maiuscole. Impostazioni dei parametri costi può essere impostati dal responsabile delle maiuscole.</span><span class="sxs-lookup"><span data-stu-id="04203-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="04203-p105">**Distribuzione per punteggio di pertinenza**: file visualizzati in grigio scuro a sinistra nella sono sotto il limite punteggio. Descrizione comando viene visualizzato il punteggio di pertinenza e la percentuale correlata dei file nel file di revisione impostato in base al numero totale di file.</span><span class="sxs-lookup"><span data-stu-id="04203-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="04203-p106">Riquadro dei dettagli espanso consente di visualizzare dettagli aggiuntivi. File nelle figure insieme non includono file vuoti o piuttosto vago. Figure della famiglia file rappresentano i file che vengono caricati in pertinenza non ancora ancora conteggiati come parte della famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="04203-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="04203-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04203-128">See also</span></span>

[<span data-ttu-id="04203-129">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="04203-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="04203-130">Informazioni sulla valutazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="04203-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="04203-131">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="04203-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="04203-132">Esecuzione di formazione di pertinenza</span><span class="sxs-lookup"><span data-stu-id="04203-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="04203-133">Analisi di pertinenza di verifica</span><span class="sxs-lookup"><span data-stu-id="04203-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="04203-134">Test di analisi di pertinenza</span><span class="sxs-lookup"><span data-stu-id="04203-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

