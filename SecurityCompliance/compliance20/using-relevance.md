---
title: Utilizzare la funzionalità di pertinenza per analizzare i dati di eDiscovery avanzate (Preview)
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
ms.openlocfilehash: 56e83a1f8a951fd6e14172122a5e86447c6f2ccf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695172"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery-preview"></a>Utilizzare la funzionalità di pertinenza per analizzare i dati di eDiscovery avanzate (Preview)

In eDiscovery avanzate (anteprima), la funzionalità di pertinenza include i pertinenza e verifica dei file correlati a un caso. Il flusso di lavoro di pertinenza è illustrato e descritto di seguito:
  
![Flusso di lavoro di pertinenza](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Cicli di valutazione e monitoraggio**:
    
  - **Valutazione**: Abilita assessment anticipati in base a un campione casuale di file e viene utilizzata questa valutazione per applicare le decisioni per determinare le prestazioni del processo di codifica predittiva. 
    
  - **Tenere traccia degli**: calcolare e visualizzare i risultati della valutazione durante il monitoraggio statistiche validità del processo di. 
    
- **Cicli di verifica e corsi di formazione**
    
  - **Tag**: criteri di pertinenza specifici per ogni problema sulla base iterativo verifica dell'esperto e tagging dei singoli file acquisita dalla eDiscovery avanzate (Preview).
    
  - **Tenere traccia degli**: calcolare e visualizzare i risultati della formazione pertinenza durante il monitoraggio statistiche validità del processo. 
    
- **Calcolo batch**: I criteri di pertinenza accumulati e acquisiti viene applicato all'intero insieme di file e per ogni file viene generato un punteggio di pertinenza.
    
- **Stabilire**: I risultati dell'analisi applicata al caso intera viene visualizzata dopo il calcolo Batch e dati utilizzati per prendere decisioni revisione documento vengono visualizzati.
    
- **Test**: risultati devono essere provati per verificare la validità e l'efficacia dell'elaborazione eDiscovery avanzate (Preview).

- **Ricerca**: una volta completato il flusso di lavoro di pertinenza, è possibile utilizzare l'output, ad esempio percentile lettura di un documento per il problema quando si esegue una query all'interno del set di lavoro.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Linee guida per la revisione e formazione di pertinenza

Di seguito è fornita una panoramica delle linee guida per la revisione e formazione di pertinenza:
  
- **Errori ed incoerenze**: se errori tagging vengono apportati durante la formazione, tornare alla precedente esempi di file per correggerli. Se sono presenti troppi errori da correggere o non esiste un nuovo punto di vista del case o problema, i criteri di pertinenza devono essere ridefiniti dall'amministratore e riavviata la formazione di pertinenza.
    
- **Formazione e utilizzo dei tag**: 
    
  - File devono essere contrassegnati in base al contenuto solo. È consigliabile non metadati, ad esempio depositaria, date o percorso del file. 
    
  - Non prende in considerazione data indicazioni intervallo nel testo tagging file.
    
  - Non prende in considerazione incorporate immagini grafiche tagging file.
     
  - Ignora testo applicato a seconda della pertinenza verrà rimosso al contenuto del file visualizzato nella visualizzazione di testo di pertinenza. Se sono stati definiti i valori per il testo Ignora dopo la pertinenza già formazione introduttiva, il nuovo testo ignorato verrà applicato al file di esempio creati dal punto in cui è stata definita. La caratteristica di ignorare il testo deve essere utilizzata attenzione, poiché il suo utilizzo può consentire una riduzione delle prestazioni di analisi dei file
    
  - Utilizzare l'opzione **Ignora tagging** solo quando necessario. EDiscovery avanzate (Preview) istruire non basato su file ignorati. Nella valutazione, se è difficile stabilire se un file è rilevante, è preferibile tag come Relevant (R) o non rilevanti (NR) ogni volta che è possibile invece selezionando **Ignora**. Quando eDiscovery avanzate (Preview) valuta formazione, può quindi essere visualizzato adeguatezza questi tipi di file sono stati elaborati.
    
  - Anche i file con dimensioni molto piccole quantità di testo estratto essere contrassegnati di formazione come R/NR anziché come "Ignora", se possibile. 
    
  - Assegnazione dei tag che possono influire sugli classificatore, purché il file può essere letta e può essere contrassegnato come R/NR.
    
  - Il numero di sequenza file presente nell'elenco di file di esempio visualizzato nella scheda **Tag** consente all'utente restituire l'ordine di visualizzazione originale dei file. 
    
  - È possibile tornare a un campione e modificare il contrassegno della valutazione e formazione imposta i file. Le modifiche verranno applicate quando si crea il codice di esempio successivo.
    
  - Analizzate Excel i file in formato PDF devono essere considerato come file di Excel nativi quando i file di tagging.
    
  - In caso di dubbi sulle tagging pertinenza di un file, rivolgersi a un esperto. Tagging non corretto durante la formazione pertinenza possono causare perdite di tempo durante il processo e può inoltre avere un impatto negativo sulla qualità dei risultati complessivi.
    
  - Parole chiave che sono state definite nella parola chiave elenchi verranno visualizzati in colori per consentire all'utente di identificare i file rilevanti durante l'assegnazione dei tag.
    
- **Calcolo batch**: i file che sono stati contrassegnati come R/NR da un esperto ricevono un punteggio pari a 0 o 100. Ciò vale per prendere prima calcolo Batch per il tagging. Se l'esperto trasferito il problema su inattivo dopo il calcolo Batch e continuato tagging questo problema, i punteggi appena contrassegnati non saranno 100/0, ma piuttosto il punteggio originale.
    
- **Problemi e campionamento delle modalità**: problemi sono in genere disattivate al termine lavoro su esse formazione di pertinenza è stabile e calcolo Batch è stato eseguito, quando vengono annullati i problemi o in un altro utente è impegnato nei problemi.
    
## <a name="steps-in-relevance-training"></a>Procedure di formazione di pertinenza

Nella **pertinenza \> traccia** scheda Avanzate eDiscovery vengono forniti suggerimenti su come procedere per l'elaborazione, con i seguenti passaggi successivi. Le implicazioni sono descritti di seguito per ognuna delle procedure seguenti è consigliabile nel processo di formazione di pertinenza. 
  
- Contrassegno /continue. tagging: verifica File e pertinenza tagging eseguita da un esperto per ogni file, quindi inviare all'interno di un campione.
    
  - Implicazioni: Un esempio esistente deve essere contrassegnato.
    
- Valutazione /continue. assessment: consente la convalida anticipata del problema maiuscole pertinenza e una visualizzazione preliminare di pertinenza della popolazione file importati per il case corrente.
    
  - Implicazioni: Assessment ulteriori è necessario o consigliato.
    
- Formazione /continue. formazione: processo durante i Advanced eDiscovery apprendimento da esperto che è il file di tagging esempi e acquisisce la possibilità di identificare i criteri di rilevanza pertinenti per ogni problema nel contesto di ogni caso.
    
  - Implicazioni: Il problema è necessario ulteriore formazione; Nell'esempio successivo deve essere creato e contrassegnato. 
    
- Blocco calcolo: processo di pertinenza in quali avanzate eDiscovery accetta le conoscenze acquisite durante la fase di formazione e viene applicato alla popolazione intero file. Tutti i file nel gruppo di file pertinenti vengono valutati per pertinenza e assegnati un punteggio di pertinenza.
    
  - Implicazioni: Il problema è diventato stabile e calcolo Batch può essere eseguito.
    
- Aggiornamento: Pertinenza indica quando un esperto vengono esaminati tag e un esempio di file selezionati da un carico aggiuntivo file durante uno scenario di distribuzione viene caricato.
    
  - Implicazioni: È stato aggiunto un nuovo caricamento e aggiornamento è necessario per continuare a funzionare.
    
- Contrassegnare le incoerenze: processo consente di identificare, tramite un algoritmo di eDiscovery avanzate incoerenze nel file di tagging del processo che può influire negativamente sull'analisi.
    
  - Implicazioni: Nell'esempio successivo includerà i file che sono stati applicati i tag negli esempi precedenti e il contrassegno deve essere ripetute.
    
- Aggiornare classificatore: consente di applicare tagging o le modifiche di seeding.
    
  - Implicazioni: Tagging e il seeding modifiche possono essere applicate senza dover eseguire manualmente un ulteriore esempio di pertinenza.
    
- In attesa: completamento del processo formazione la pertinenza.
    
  - Implicazioni: Nessun formazione di pertinenza è necessaria a questo punto.
    
Sebbene eDiscovery avanzate viene descritto il processo con altri passaggi consigliati nelle diverse fasi, consente inoltre per esplorare le pagine e schede e per effettuare le scelte a situazioni indirizzo che possono essere pertinenti al caso singolo problema, o processo di revisione documento. 
  
È possibile accettare o ignorare opportune eDiscovery avanzate scelte di elaborazione. Se si desidera eseguire un passaggio oltre il passaggio successivo consigliato, fare clic sul **passaggio successivo** elencate nella visualizzazione problema espansa nella finestra di dialogo, fare clic sul pulsante **Modifica** accanto al passaggio successivo e selezionare un'altra opzione passaggio successiva. 
  
> [!NOTE]
> Alcune opzioni continuino a restituire disabilitati dopo lo sblocco come non supportati per l'utilizzo a questo punto del processo. 
  
## <a name="more-information"></a>Ulteriori informazioni

[Informazioni sulla valutazione di pertinenza](../assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](../tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](../tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](../track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](../decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](../test-relevance-analysis-in-advanced-ediscovery.md)

[Eseguire una query all'interno di working set](working-set-search.md)
