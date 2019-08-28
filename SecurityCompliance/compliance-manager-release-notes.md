---
title: Note sulla versione di Microsoft Compliance Manager
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 196118972079f83ba2f6a59ce1ae1514d9616599
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643238"
---
# <a name="release-notes-for-compliance-manager-preview"></a>Note sulla versione per Compliance Manager (anteprima)

L'anteprima pubblica di Compliance Manager fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti.

È possibile utilizzare lo strumento di [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) aggiornato nel [Service Trust Portal](https://servicetrust.microsoft.com) per tenere conto, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.

## <a name="whats-new-in-compliance-manager-preview"></a>Novità di Compliance Manager (anteprima)

- **Integrazione con Microsoft Secure Score:** Compliance Manager supporta l'integrazione con [Microsoft Secure Score](microsoft-secure-score.md) tramite la mappatura delle azioni gestite dai clienti a più di 50 operazioni di valutazione sicure. Quando si completa un'azione mappata in Secure score, l'azione corrispondente di Compliance Manager viene aggiornata automaticamente.

- **Importare valutazioni personalizzate:** Oltre alle valutazioni predefinite, Compliance Manager ora supporta l'importazione di modelli personalizzati. È possibile creare valutazioni personalizzate per qualsiasi prodotto o servizio e per qualsiasi norma o regolamento.

- **Elementi Actions:** Gli elementi azione sono ora singoli elementi e molti includono la raccolta di telemetria dall'API Microsoft Secure Score Graph. Se possibile, le raccomandazioni per l'azione tecnica sono ora collegate alla pagina di configurazione applicabile nel servizio Office 365.

- **Gestione tenant:** Nuova interfaccia per la gestione dei nuovi elementi dati in Compliance Manager (Preview):
    - **Dimensioni:** Consente di visualizzare, aggiungere e personalizzare i metadati per i modelli, le valutazioni e gli elementi di azione che consentono di creare pivot personalizzati per i filtri.
    - **Proprietari:** Specificare un proprietario per ogni elemento di azione.
    - **Azioni dei clienti:** Gestire l'elenco completo degli elementi delle azioni inclusi in Compliance Manager (Preview) e abilitare/disabilitare il monitoraggio del Punteggio sicuro per gli elementi azione integrati con Secure score.

- **Punteggio di conformità aggiornato**: la metodologia è stata modificata per supportare la sincronizzazione con Microsoft Secure score. Il sistema di Punteggio rimuove i crediti di controllo gestiti da Microsoft e si concentra esclusivamente sul completamento dei controlli gestiti dal cliente.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemi noti in Compliance Manager (anteprima)

Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni di Compliance Manager.

### <a name="compliance-score"></a>Punteggio di conformità

- Per gli elementi azione contrassegnati come **non nell'ambito**, il punteggio assegnato all'elemento azione non è escluso dal calcolo del Punteggio di conformità. Gli elementi azione contrassegnati **non nell'ambito** non aumentano il Punteggio di conformità.

### <a name="secure-score"></a>Secure Score

- I risultati del Punteggio sicuro non sono disponibili per alcuni elementi di azioni in determinate sottoscrizioni di Microsoft 365 e Office 365. Il risultato del Punteggio sicuro è' non è stato possibile rilevare ' in questi casi.
- A volte vengono restituiti risultati di Punteggio sicuro per i criteri corrispondenti e gli elementi di azione non completati.

### <a name="microsoft-managed-controls"></a>Controlli gestiti da Microsoft

- La data di test per i controlli gestiti da Microsoft non viene visualizzata nell'interfaccia utente, anche se inclusa nella valutazione. Per visualizzare le informazioni relative alla data di test, è necessario esportare la valutazione.

### <a name="customization"></a>Personalizzazione

- L'aggiunta di controlli personalizzati consente di aggiungere un nuovo controllo a una famiglia di controlli esistente, ma non consente di aggiungere una nuova famiglia di controlli.
- Questa versione non supporta il collegamento di elementi azione o l'aggiunta di elementi o controlli di azioni a una valutazione.
- Se si crea un'azione personalizzata, non è possibile modificarla o eliminarla.

### <a name="control-families-not-shown-in-assessments"></a>Famiglie di controllo non visualizzate nelle valutazioni

- Quando si importa un modello, tutte le valutazioni basate su tale modello riflettono tutte le famiglie di controlli facenti parte del modello. Tuttavia, se si aggiungono nuove famiglie di controlli al modello, tutte le valutazioni esistenti non riflettono le modifiche. Solo le nuove valutazioni create al di fuori del modello aggiornato riflettono le modifiche.

### <a name="filters"></a>Filtri

- Il filtro sugli elementi o sui controlli di azione non produce in modo coerente risultati corretti.

### <a name="templates"></a>Modelli

- I modelli archiviati sono modificabili e non devono essere modificabili.
- I modelli bloccati consentono la creazione di una valutazione quando non dovrebbero. Il blocco di un modello deve impedire che venga utilizzato per creare valutazioni.

### <a name="export"></a>Esportazione

- L'esportazione dei modelli in JSON ha esito negativo quando lo stato del modello è impostato su **importazione** o **in attesa di approvazione**.

### <a name="supported-browsers"></a>Browser supportati

- Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.
- Possono verificarsi casi in cui i dati aggiornati non vengono visualizzati fino a quando il browser non viene aggiornato.
- La versione di anteprima di Microsoft Edge non è supportata ma non ha problemi noti.
- Internet Explorer non è supportato.

### <a name="session-timeout"></a>Timeout sessione

- Quando si verifica un timeout di una sessione, potrebbe essere visualizzato un errore "qualcosa è andato storto". Per risolvere il caso, passare a [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) e accedere di nuovo.
 
### <a name="language-support"></a>Supporto lingue

- Tutte le lingue non sono supportate per tutte le pagine Web. Se la lingua locale non è supportata, visualizzarla in inglese (Stati Uniti).