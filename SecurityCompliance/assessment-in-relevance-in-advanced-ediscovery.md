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
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>Informazioni sulla valutazione in Rilevanza di Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
EDiscovery avanzate consente anticipata valutazione, ad esempio, per i problemi definiti e i dati importati per un caso. EDiscovery avanzate consente esperto per prendere decisioni relative a un approccio adottato e applicarle al progetto di revisione del documento.
  
## <a name="understanding-assessment"></a>Valutazione di informazioni

Nella valutazione, esperto viene esaminato un insieme casuale di almeno 500 file, che vengono utilizzati per determinare la complessità dei problemi e per generare statistiche che riflettono i risultati di formazione. Quando vengono rilevati file sufficienti pertinenti per raggiungere un livello statistico utili avanzate eDiscovery pertinenza per fornire statistiche accurate e determinare in modo efficace il punto stabilizzazione nel processo di formazione, valutazione ha esito positivo. 
  
Maggiore che del numero dei pertinenti file nel set di valutazione, più precise le statistiche e l'efficacia dell'algoritmo stabilità. Il numero di file pertinenti all'interno dei file di valutazione dipende dalla quantità del problema. Complessità è % stimate del file rilevanti nel set di interesse per un problema. Problemi con maggiore complessità verranno raggiunta più velocemente rispetto a problemi di un numero elevato di file rilevanti con complessità inferiore. Problemi di complessità estremamente basso (ad esempio, % 2 o meno) richiederà una valutazione molto grande set di raggiungere un numero significativo di file rilevanti.
  
Le statistiche, sono disponibili nelle schede tenere traccia e stabilire durante la formazione e dopo il calcolo Batch, includono stime della richiamo per la revisione diversi set. In statistiche, stime basate su un campione impostato (in questo caso, i file di valutazione) includono il margine di errore e il livello di probabilità di tale margine di errore. Richiamo stimato di 80%, ad esempio, potrebbe essere un margine di errore più o meno il 5% del con un livello di probabilità di 95%. Ciò significa che il richiamo stimato effettivamente il 75-85% e questa stima con confidenza 95%. Maggiore sarà il set di valutazione, il margine di errore diventa più piccolo e le statistiche sono più precise. 
  
Dopo l'esperto viene esaminato un insieme di valutazione iniziale dei file di 500, pertinenza è in grado di determinare il margine di errore dei valori richiamo corrente. Pertinenza inoltre viene impostato un margine di errore che consiglia di raggiungere per ottimizzare il set di valutazione predefinito. Di seguito sono riportati alcuni esempi:
  
- Se la valutazione già impostata hanno restituito un margine di errore più o meno pari al 10% del, pertinenza indicazioni per passare alla formazione (non è necessaria alcuna revisione valutazione complementare). 
    
- Se il set di valutazione avesse portato a un margine di errore più o meno 13% del, pertinenza potrebbe essere consigliabile la revisione di un altro set di file di valutazione di raggiungere un margine inferiore. 
    
- Se complessità è insufficiente, pertinenza potrebbe essere consigliabile arresto assessment anche se il margine di errore è di grandi dimensioni (effettua le statistiche realizzabile), in quanto il set di valutazione consentono di raggiungere un utile margine di errore è troppo grande.
    
Ogni problema con il proprio complessità, corrente margine di errore e di conseguenza, il numero stimato dei file di valutazione aggiuntive. Valutazione della serie successiva viene creato in base al numero massimo di file (fino a 1.000 in un unico insieme).
  
È possibile accettare i suggerimenti di pertinenza o regolare il margine di errore corrente in base alle proprie esigenze. Il margine di errore corrente predefinito viene determinato per il richiamo è uguale o superiore al 75%.
  
> [!NOTE]
> La fase di valutazione può essere ignorata nel **pertinenza \> traccia** scheda nella visualizzazione espansa per un problema, deselezionare la casella di controllo di **valutazione** per ogni problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non ci sarà alcun le statistiche per questo problema. > Deselezionando la casella di controllo **Assessment** può essere eseguita solo prima dell'esecuzione di valutazione. Quando sono presenti più problemi in un caso, valutazione viene ignorato solo se la casella di controllo è deselezionata per ogni problema 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

