---
title: Aggiunta di tag e training per la rilevanza in Office 365 Advanced eDiscovery
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 'Informazioni sulle procedure di tag e quindi con un campione di formazione di 40 file durante la fase di formazione di pertinenza di Office 365 avanzate eDiscovery.  '
ms.openlocfilehash: 90272452c8c1317957e542eba07bc43722f9c0e9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530835"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Aggiunta di tag e training per la rilevanza in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questo argomento viene descritta la procedura per l'utilizzo con il modulo di formazione avanzato eDiscovery pertinenza. 
  
Dopo la valutazione completata di eDiscovery avanzate e si immette la fase di formazione di pertinenza, un campione di formazione di 40 file messa scheda Tag per il tagging. 
  
## <a name="performing-relevance-training"></a>Esecuzione di formazione di pertinenza

1. Nella **pertinenza \> Tag** riquadro Tagging scheda viene visualizzata per impostazione predefinita nel riquadro a sinistra e il codice di esempio vengono visualizzati i file, uno alla volta per il tagging. 
    
    ![Pannello Tag di pertinenza](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Nella scheda **Tag** viene visualizzato il nome del file visualizzato. Potrebbe trattarsi di percorso, subject di posta elettronica, il titolo o nome definito dall'utente. L'ID, percorso del file o percorso testo può essere copiato facendo clic sul percorso del file. 
    
    La scheda **Tag** tagging statistiche Mostra il numero di esempio di file (nella parte superiore del riquadro di sinistra), il numero di file attualmente visualizzato da totale file di esempio (parte inferiore del riquadro a destra) e il numero totale corrente dei file contrassegnati nel modello (in basso di t il riquadro sinistra), che cambia come si contrassegno i file. Ciò è valido per il tagging qualsiasi pertinenza eseguita nella valutazione, formazione, aggiornamento o di testing. 
    
    Vengono visualizzate icone che indica l'esistenza di commenti, tag e i file della famiglia di visualizzazione del file in una barra sopra il file.
    
2. Determinare la pertinenza del file per il problema di maiuscole e tag il file utilizzando i pulsanti di icona opzione Tagging o tasti di scelta rapida, come illustrato nella tabella riportata di seguito:
    
| |
|**Opzione tagging**|**Descrizione**|**Tasti di scelta rapida**|**Per i problemi più - blocco tasti di scelta rapida di tag**|
|:-----|:-----|:-----|:-----|
|R  <br/> |Rilevanti  <br/> |Z  <br/> |MAIUSC + Z  <br/> |
|NR  <br/> |Non rilevanti  <br/> |X  <br/> |MAIUSC + X  <br/> |
|Elementi da ignorare  <br/> |Elementi da ignorare  <br/> |C  <br/> |MAIUSC + a  <br/> |
   
  - Quando sono presenti più problemi per un file dopo tagging di un problema, la selezione si sposta il problema successivo (se esistenti). 
    
  - Parole chiave che sono state definite dall'amministratore o responsabile maiuscole quando l'evidenziazione parole chiave (il programma di installazione di pertinenza \> evidenziate le parole chiave), verrà visualizzato (in colori specificati) che consentono di identificare i file rilevanti durante l'assegnazione dei tag. Se una parola chiave include una sottolineatura doppia, possono essere selezionato per visualizzare una descrizione comandi con la descrizione della parola chiave. 
    
    Facoltativamente, nella scheda **Tag** , fare clic su **Impostazioni** per impostare le opzioni seguenti: 
    
    ![Impostazioni Tag di pertinenza](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **Tag di massa**: selezionare questa opzione per assegnare più problemi per un file selezionando **tutti** per impostare il tag per il file selezionato per tutti i problemi (problemi già contrassegnati sostituzioni) o selezionando **il resto** per applicare tag per i problemi senza tag rimanenti. L'opzione selezionata rimane attiva per tutti i casi dell'utente fino a quando non modificati dall'utente (l'impostazione è per utente per i casi dell'utente). 
    
  - **Tag automatico**: selezionare questa casella di controllo per impostare altri problemi di un file come non rilevanti dopo un singolo tagging pertinenti.
    
  - **Avanzamento automatico**: selezionare questa casella di controllo per spostare la selezione dei file visualizzata sul file successivo quando si aggiungono tag l'ultima o un solo problema senza tag. 
    
    File ignorati non verranno considerati per scopi di punteggio di pertinenza e formazione di pertinenza.
    
3. Commenti descrittivo, associati a un file, possono essere visualizzati e modificati tramite l'opzione **commento** nell'elenco a discesa del riquadro sinistro. (facoltativo) 
    
4. Linee guida per il tagging possono essere visualizzate selezionando l'opzione **linee guida per il Tagging** nell'elenco a discesa del riquadro sinistro. 
    
5. Dopo aver fine tagging tutti i file nell'elenco e si è pronti per calcolare i risultati, fare clic su **Calcola**. Viene visualizzata la scheda di **traccia** . 
    
## <a name="working-with-the-sample-files-list"></a>Utilizzo dell'elenco di file di esempio

Elenco di file di esempio consente di visualizzare un elenco dei file in un esempio di formazione ed eseguire azioni diverse in uno o più file. Nella **pertinenza** \> scheda **Tag** , riquadro a sinistra **i file di esempio** viene visualizzato un elenco dei file di esempio per l'elaborazione di processi con valutazione, formazione, aggiornamento e le incoerenze. 
  
1. Nella **pertinenza \> Tag** selezionare i file di esempio nell'elenco a discesa del riquadro sinistro. I file di esempio sono elencati nel riquadro sinistro. 
    
    ![Elenco di file campione per Tag di pertinenza](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Selezionare un numero specifico di esempio o file immettendo o selezionando il relativo numero di finestre di **esempio** e **File** . 
    
  -   - Un numero di sequenza di file è elencato nella colonna di sinistra dell'elenco di file visualizzato nella scheda **Tag** . Se si sceglie l'intestazione, l'ordine di visualizzazione originale dei file restituisce ordine originale. 
    
  - Per visualizzare il relativo contenuto nel riquadro destro, fare clic su una riga del file.
    
  - Spostarsi tra i file di esempio corrente utilizzando le opzioni di barra dei menu inferiore. Scelte rapide da tastiera esplorativa sono inoltre disponibili:
    
    Per passare al primo file nel campione: Maiusc + Ctrl +\<
    
    Per selezionare il file precedente nel campione: MAIUSC +\<
    
    Per selezionare il file successivo nel campione: MAIUSC +\>
    
    Per passare all'ultimo file di esempio: Maiusc + Ctrl +\>
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

