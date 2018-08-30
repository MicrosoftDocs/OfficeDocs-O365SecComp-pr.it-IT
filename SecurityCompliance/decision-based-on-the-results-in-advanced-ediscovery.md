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
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>Decisione basata sui risultati in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 In eDiscovery avanzate, la scheda stabilire fornisce informazioni aggiuntive per la visualizzazione e utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di verifica dei file maiuscole. 
  
## <a name="using-the-decide-tab"></a>Nella scheda stabilire

![Decisione di pertinenza](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
In questa scheda include le operazioni seguenti:
  
- **Problema**: da qui è possibile selezionare il problema di interesse dall'elenco. 
    
- **Rapporto richiamo revisione**: confronto delle avanzate eDiscovery revisione in base alle punteggio di pertinenza. Il punto limite nel grafico rappresenta la percentuale di file da esaminare, mappato a un punteggio di pertinenza. Nella fase di Test di pertinenza e come una soglia di esportazione viene utilizzato per l'eliminazione selettiva. Il punto limite predefinito, il numero di file di riferimento è in corrispondenza del punto in cui l'equilibrio tra la precisione e richiamo è ottimale. Il punto limito effettivo dovrebbe essere determinato dall'utente in base agli obiettivi e compromesso costo (% review) e rischi (% richiamo). Il dispositivo di scorrimento consente di modificare il punto di taglio e verificare l'effetto sui parametri e grafico durante l'aggiustamento % dei file pertinenti da recuperare e prima di convalidare una decisione.
    
- **Parametro**: leggere, tenere presente, parametri pertinenti e totale successiva sono cumulative calcolate statistiche relative alla revisione imposta in relazione alla raccolta per l'intera case. Definizioni di questi parametri sono i seguenti:
    
    **Esaminare**: percentuale di file da esaminare basato su questo limite. 
    
    **Richiamo**: percentuale di file rilevanti nel set di revisione. 
    
    **Successivo pertinenti**: costo per esaminare e identificare un altro file pertinente che non è attualmente la revisione impostato. 
    
    **Costo totale**: costi per la revisione questa percentuale dei file maiuscole. Impostazioni dei parametri costi può essere impostati dal responsabile delle maiuscole.
    
- **Distribuzione per punteggio di pertinenza**: file visualizzati in grigio scuro a sinistra nella sono sotto il limite punteggio. Descrizione comando viene visualizzato il punteggio di pertinenza e la percentuale correlata dei file nel file di revisione impostato in base al numero totale di file.
    
Riquadro dei dettagli espanso consente di visualizzare dettagli aggiuntivi. File nelle figure insieme non includono file vuoti o piuttosto vago. Figure della famiglia file rappresentano i file che vengono caricati in pertinenza non ancora ancora conteggiati come parte della famiglia di prodotti.
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Esecuzione di formazione di pertinenza](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

