---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155188"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a>Set up Attorney-Client Privilege Detection (Preview) in Advanced eDiscovery

Un aspetto importante e costoso della parte di revisione di qualsiasi processo di individuazione consiste nell'esaminare il contenuto con privilegi. Advanced eDiscovery fornisce un rilevamento basato sui contenuti con privilegi AI nel caso in cui è possibile rendere più efficiente questo processo. Poiché questa funzionalità è attualmente in fase di beta, un amministratore di eDiscovery deve scegliere la funzionalità per utilizzarla.

## <a name="how-does-it-work"></a>Funzionamento.

Quando la funzionalità è attivata, quando si analizza un set di revisione all'interno di un caso, tutti i documenti vengono eseguiti tramite il modello di rilevamento dei privilegi avvocato-client. Il modello analizza due elementi:

- Content: il modello ML determina la probabilità che il contenuto del documento sia di natura legale.

- Partecipanti: se è presente un elenco di avvocati caricato dall'utente per il tenant, il modello Confronta i partecipanti del documento in base all'elenco per determinare se il documento ha almeno un partecipante all'avvocato.
Il modello restituisce tre valori per ogni documento, che saranno tutti ricercabili all'interno di un set di Revisione:

- Punteggio contenuto: la probabilità che il documento sia di natura legale (Punteggio compreso tra 0 e 1)

- Ha un avvocato: true se uno dei partecipanti è presente nell'elenco dei procuratori caricati, false in caso contrario o se non è presente un elenco di avvocati.

-  Potenzialmente privilegiato: true se il Punteggio di contenuto è al di sopra della soglia o ha un partecipante all'avvocato, false in caso contrario.

## <a name="opting-into-attorney-client-privilege-detection"></a>Scelta del rilevamento dei privilegi del procuratore-client

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a>Passaggio 1: opt-in Attorney-Client Privilege Detection (eDiscovery admin)

Poiché il rilevamento dei privilegi di avvocato-client è una funzionalità di anteprima, l'amministratore di eDiscovery deve scegliere di rendere disponibile la funzionalità nei casi.

- Passare a "configurare le funzionalità sperimentali" dalla pagina eDiscovery avanzata

- Fare clic su "Gestisci rilevamento dei privilegi di avvocato-client".

- Fare clic sull'interruttore per attivare la funzionalità.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Passaggio 2: caricare un elenco di avvocati (facoltativo)

Per sfruttare al meglio il rilevamento dei privilegi di avvocato-client, è consigliabile fornire un elenco di indirizzi di posta elettronica avvocati o persone giuridiche che lavorano per la società. L'elenco deve essere un formato CSV senza intestazione, con un solo indirizzo di posta elettronica per riga.

## <a name="leveraging-attorney-client-privilege-detection"></a>Utilizzo del rilevamento dei privilegi avvocato-client 

### <a name="step-1-analyze-a-review-set"></a>Passaggio 1: analizzare un set di Revisione

Quando si analizza il set di revisione, verrà eseguito anche il rilevamento dei privilegi del procuratore-client. Per ulteriori informazioni sull'analisi dei dati nel set di revisione, fare riferimento a [analyze data in a Review set in Advanced eDiscovery](analyzing-data-in-review-set.md).

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Passaggio 2: creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client

Uno dei modi principali in cui è possibile utilizzare i risultati del rilevamento dei privilegi di avvocato-client nel processo di revisione è l'utilizzo di un gruppo di smart tag. I gruppi di smart tag prevedono i risultati di un modello ML e mostrano i risultati del modello in linea accanto ai tag, in modo da poter facilmente utilizzare i risultati del modello, se necessario, e usare i tag del processo di revisione come se si trattasse di qualsiasi altro tag nel pannello di tagging. Per ulteriori informazioni, fare riferimento a [impostare gli smart tag per la revisione ml-assistita in Advanced eDiscovery](smart-tags.md) .

- In "Gestisci tag", fare clic su "Aggiungi sezione Smart tag".

- Selezionare "rilevamento dei privilegi del procuratore dei clienti". Si vedrà che sono stati creati un gruppo di tag e due tag, corrispondenti ai possibili risultati del modello.

- Rinominare il gruppo di tag e i tag come riesci a vedere adatta per la tua recensione.

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a>Passaggio 3: utilizzare il gruppo smart tag per la revisione dei privilegi

Quando si esamina un documento, se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente esporrà il risultato:

- Se il documento contiene contenuto che potrebbe essere di natura legale, accanto allo smart tag corrispondente verrà visualizzata un'etichetta "contenuto legale".

- Se il documento ha un partecipante che si trova nell'elenco dei procuratori caricati, accanto allo smart tag corrispondente verrà visualizzata un'etichetta "procuratore".