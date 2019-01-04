---
title: Limiti per la ricerca del contenuto in Office 365 protezione &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: 'Informazioni sui limiti valido per la funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità, ad esempio il numero massimo di ricerche simultanee. '
ms.openlocfilehash: 79142edf2e80378bf6f22474fca55c54fe5cc776
ms.sourcegitcommit: ea625737c4be14927f69aa71d4fbd7d7d94d9334
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2019
ms.locfileid: "27544107"
---
# <a name="limits-for-content-search-in-the-office-365-security-amp-compliance-center"></a>Limiti per la ricerca del contenuto in Office 365 protezione &amp; centro conformità

> [!NOTE]
> I limiti riportati in questo argomento sono diversi da quelli correnti per eDiscovery In locale in Exchange Online e per il centro eDiscovery in SharePoint Online. 
  
Limiti vari vengono applicati alla funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità. In questo ricerche include eseguire nella pagina di **ricerca del contenuto** e le ricerche associati a un caso eDiscovery. Questi limiti utili per mantenere l'integrità e la qualità dei servizi forniti per organizzazioni di Office 365. Esistono limiti relativi all'indicizzazione di messaggi di posta elettronica di Exchange Online per la ricerca. Non è possibile modificare la ricerca del contenuto o posta elettronica indicizzazione limiti, ma è necessario tenere conto di essi in modo che è possibile eseguire questi limiti in considerazione durante la pianificazione, l'esecuzione e la risoluzione dei problemi di ricerche di contenuto. 
  
## <a name="content-search-limits"></a>Limiti relativi alla ricerca di contenuto

Nella tabella seguente sono elencati i limiti di ricerca nella protezione &amp; centro conformità.
  
|**Descrizione del limite**|**Tipo di limite**|
|:-----|:-----|
|Il numero massimo di cassette postali o siti che possono essere ricercati in una singola ricerca contenuto  <br/> |Nessun limite  <br/> |
|Il numero massimo di ricerche di contenuto che è possibile eseguire contemporaneamente all'interno dell'organizzazione.  <br/> |Nessun limite  <br/> |
|Il numero massimo di ricerche di contenuto che un singolo utente possono essere avviati contemporaneamente. Si noti che questo limite viene raggiunto più comodo quando l'utente tenta di avviare più ricerche utilizzando il **Get-ComplianceSearch \| Start ComplianceSearch** comando PowerShell centro conformità e sicurezza.<br/> |10   <br/> |
|Il numero massimo di elementi per ogni cassetta postale dell'utente che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.  <br/> |100  <br/> |
|Numero massimo di elementi disponibili in tutte le cassette postali degli utenti che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto. Vengono visualizzati gli elementi più recenti.  <br/> |1,000  <br/> |
|Il numero massimo di cassette postali degli utenti che possono essere visualizzati in anteprima dei risultati della ricerca. Se sono presenti più di 1000 cassette postali che includono contenuto corrispondente alla query di ricerca, solo le prime 1000 cassette postali con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.  <br/> |1,000  <br/> |
|Numero massimo di elementi disponibili in SharePoint e OneDrive per i siti che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto. Vengono visualizzati gli elementi più recenti.  <br/> |200  <br/> |
|Il numero massimo di siti (in SharePoint e OneDrive for Business) che può essere visualizzata l'anteprima dei risultati della ricerca. Se sono presenti più di 200 siti totali che includono contenuto corrispondente alla query di ricerca, solo i siti principali 200 con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.  <br/> |200  <br/> |
|Il numero massimo di elementi per ogni cassetta postale di cartelle pubbliche che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.  <br/> |100  <br/> |
|Numero massimo di elementi disponibili in tutte le cassette postali di cartelle pubbliche che vengono visualizzate nella pagina di anteprima durante l'anteprima dei risultati di ricerca del contenuto.  <br/> |200  <br/> |
|Il numero massimo di cassette postali pubbliche possono visualizzare in anteprima dei risultati della ricerca. Se sono presenti più di 500 cassette postali delle cartelle pubbliche che includono contenuto corrispondente alla query di ricerca, solo le prime 500 cartelle pubbliche cassette postali con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.  <br/> |500  <br/> |
|Numero massimo di caratteri per la query di ricerca (inclusi gli operatori e condizioni) per una ricerca di contenuto.  <br/><br/> **Nota:** Questo limite avrà effetto dopo la query viene espansa, ovvero le che query verrà ottenere espansa per ognuna delle parole chiave. Ad esempio, se una query di ricerca è 15 parole chiave e parametri aggiuntivi e le condizioni, la query viene espanso 15 volte, ognuno con gli altri parametri e le condizioni nella query. Anche se il numero di caratteri inclusi nella query di ricerca può essere inferiore al limite, è la query espansa che può contribuire alla se si supera questo limite.<br/> |**Le cassette postali:** 10.000  <br/> **Siti:** 4.000 durante la ricerca di tutti i siti o 2.000 durante la ricerca un massimo di 20 siti <sup>1</sup> <br/> |
|Numero massimo di valori Variant restituiti quando si utilizza un prefisso con caratteri jolly per cercare una frase specifica in una query di ricerca o quando si utilizza un carattere jolly prefisso e l'operatore booleano **NEAR** o **ONEAR** .  <br/> |10.000 <sup>2</sup> <br/> |
|Il numero minimo di caratteri alfabetici per i caratteri jolly prefisso; ad esempio `time*`, `one*`, o `set*`.  <br/> |3  <br/> |
|Il numero massimo di cassette postali in una ricerca di contenuto che è possibile eliminare gli elementi nel eseguendo un'azione "cercare ed eliminare" (utilizzando il **ComplianceSearchAction New-eliminare** comando). Se la ricerca del contenuto che si sta eseguendo un'azione di eliminazione per dispone di più cassette postali di origine questo limite, l'azione di eliminazione avrà esito negativo. Per ulteriori informazioni sulla ricerca ed eliminazione, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione Office 365](search-for-and-delete-messages-in-your-organization.md).<br/> |50.000  <br/> |
   
> [!NOTE]
> <sup>1</sup> durante la ricerca di SharePoint e OneDrive per i percorsi di Business, gli URL dei siti in cui cercare i caratteri vengono contati su questo limite.<br/> <sup>2</sup> per le query non frase (un valore parola chiave che non utilizza le virgolette doppie) viene utilizzato un indice prefisso speciale. Ciò indica che si verifica una parola in un documento, ma non dove si trova nel documento. Per eseguire una query di frase (un valore di parola chiave con le virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole nella frase. Ciò significa che è possibile utilizzare l'indice di prefisso per le query di frase. In questo caso, è internamente espandere le query con tutte le parole possibili che si espande il prefisso per; ad esempio `"time*"` possibile espandere a `"time OR timer OR times OR timex OR timeboxed OR …"`. 10.000 è il numero massimo di valori Variant che può espandere la parola e non il numero di documenti che soddisfano la query. Non esiste alcun limite massimo di termini non frase. 
  
## <a name="indexing-limits-for-email-messages"></a>Limiti di indicizzazione per i messaggi di posta elettronica

Nella tabella seguente vengono descritti i limiti di indicizzazione che possono causare tempi di un messaggio di posta elettronica vengono restituito come un elemento non indicizzato o un elemento indicizzato parzialmente nei risultati della ricerca di contenuto.
  
|**Limite di indicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensione massima degli allegati (esclusi i file di Excel)  <br/> |150 MB  <br/> |La dimensione massima di un allegato di posta elettronica che consente di analizzare per l'indicizzazione. Gli allegati che superano questo limite non vengono analizzati per l'indicizzazione e il messaggio con allegato viene contrassegnato come parzialmente indicizzato.<br/> <br/>**Nota:** L'analisi è il processo di cui il servizio di indicizzazione estrae il testo dalla allegato, rimuove i caratteri non necessari, ad esempio i segni di punteggiatura e spazi e quindi lo divide il testo in parole (in un processo denominato la suddivisione in token), che vengono memorizzati in corrispondenza dell'indice.           |
|Dimensione massima dei file di Excel  <br/> |4 MB  <br/> |La dimensione massima di un file di Excel presente in un sito o associato a un messaggio di posta elettronica che viene analizzato per l'indicizzazione. Eventuali file di Excel che è maggiore della non verrà analizzato questo limite e il file o messaggio di posta elettronica che il messaggio con allegato il file verrà contrassegnato come non indicizzate.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegato al messaggio di posta elettronica che viene analizzato per l'indicizzazione. Se un messaggio non ha più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio è contrassegnato come parzialmente indicizzato perché era allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Il numero massimo di allegati nidificati che vengono analizzati. Ad esempio, se un messaggio di posta elettronica con un altro messaggio associato e il messaggio allegato è un documento di Word, il documento di Word e il messaggio allegato verrà essere indicizzati. Questo comportamento continua per gli allegati annidati fino a 30.  <br/> |
|Numero massimo di immagini associate  <br/> |0  <br/> |Immagine in cui è associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.  <br/> |
|Tempo massimo trascorso per l'analisi di un elemento  <br/> |30 secondi  <br/> |È trascorso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento è contrassegnato come parzialmente indicizzato.  <br/> |
|Output parser massimo  <br/> |2 milioni di caratteri  <br/> |La quantità massima di output di testo da parser indicizzato. Ad esempio, se il parser estratto 8 milioni di caratteri da un documento, solo i primi 2 milioni di caratteri vengono indicizzati.  <br/> |
|Token di annotazione massimo  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica è indicizzato, ogni parola con annotazioni con istruzioni di elaborazione diversi che specificano come deve essere indicizzato da word. Ogni set di istruzioni di elaborazione viene chiamato un token di annotazione. Per garantire la qualità del servizio di Office 365, non esiste un limite di token di annotazione 2 milioni per un messaggio di posta elettronica.  <br/> |
|Dimensioni massime del corpo nell'indice  <br/> |67 milioni di caratteri  <br/> |Numero totale di caratteri nel corpo del messaggio di posta elettronica e tutti i suoi allegati. Quando un messaggio di posta elettronica è indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati è concatenato in un'unica stringa. La dimensione massima della stringa indicizzato è 67 milioni di caratteri.  <br/> |
|Token univoco massimo nel corpo  <br/> |1 milione  <br/> |Come precedentemente illustrato, token sono il risultato di estrazione del testo rispetto al contenuto, rimuovendo i segni di punteggiatura e spazi e quindi la suddivisione in parole (noti come token) che vengono archiviate in corrispondenza dell'indice. Ad esempio, la frase `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 questi sono i token univoci. Non esiste un limite di 1 milione token univoco per ogni messaggio di posta elettronica, che consente di impedire l'indice di Guida troppo grande con token casuale.<br/> |
  
## <a name="more-information"></a>Ulteriori informazioni

Esistono limiti aggiuntive correlate a diversi aspetti di ricerca di contenuti, ad esempio l'esportazione dei risultati di ricerca e indicizzazione del contenuto. Per una descrizione di questi limiti, vedere gli argomenti seguenti:
  
- [Esportare i risultati della Ricerca contenuto](export-search-results.md#export-limits)
    
- [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)
    
- [Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md) (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)
    
- [Limiti relativi alla ricerca per SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
Per informazioni sulle ricerche del contenuto, vedere:
  
- [Ricerca del contenuto in Office 365](content-search.md)
    
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
