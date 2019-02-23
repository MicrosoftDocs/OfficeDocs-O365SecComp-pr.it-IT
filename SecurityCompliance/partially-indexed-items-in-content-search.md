---
title: Partially indexed items in Content Search in Office 365 (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/11/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: 'Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere in una ricerca di contenuto eseguita tramite il Centro sicurezza &amp; e conformità di Office 365. '
ms.openlocfilehash: 028a0468e352121c64e12fbec209658dc32f9bbe
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219496"
---
# <a name="partially-indexed-items-in-content-search-in-office-365"></a>Partially indexed items in Content Search in Office 365 (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

Una ricerca di contenuto eseguita dal centro sicurezza &amp; e conformità di Office 365 include automaticamente gli elementi parzialmente indicizzati nei risultati della ricerca stimati durante l'esecuzione di una ricerca. Gli elementi parzialmente indicizzati sono gli elementi della cassetta postale di Exchange e i documenti sui siti di SharePoint e OneDrive for business che per qualche motivo non sono stati completamente indicizzati per la ricerca. In Exchange, un elemento parzialmente indicizzato in genere contiene un file, di un tipo di file che non può essere indicizzato, che è associato a un messaggio di posta elettronica. Di seguito sono riportati alcuni motivi per i quali gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati durante l'esecuzione di una ricerca: 
  
- Il tipo di file non è riconosciuto o non è supportato per l'indicizzazione.
    
-  I messaggi dispongono di un file allegato privo di un gestore valido, ad esempio file di immagine. Questa è la causa più comune degli elementi di posta elettronica parzialmente indicizzati. 
    
- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per un file specifico.
    
- È stato allegato un numero eccessivo di file a un messaggio di posta elettronica.
    
- Le dimensioni di un file allegato a un messaggio di posta elettronica sono eccessive.
    
- Un file è crittografato con tecnologie non Microsoft.
    
- Un file è protetto da password.
    
> [!NOTE]
> La maggior parte delle organizzazioni di Office 365 ha meno dell'1% del contenuto in base al volume e meno del 12% in base alle dimensioni parzialmente indicizzate. Il motivo della differenza tra volume e dimensioni consiste nel fatto che i file più grandi hanno una probabilità maggiore di contenere contenuto che non può essere completamente indicizzato. 
  
Per le indagini legali, è possibile che l'organizzazione debba esaminare gli elementi parzialmente indicizzati. È inoltre possibile specificare se includere gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca in un computer locale o quando si preparano i risultati per l'analisi con Office 365 Advanced eDiscovery. Per ulteriori informazioni, vedere [analisi degli elementi parzialmente indicizzati in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipi di file non indicizzati per la ricerca

Alcuni tipi di file, ad esempio file bitmap o MP3, non contengono contenuto che può essere indicizzato. Di conseguenza, i server di indicizzazione della ricerca in Exchange e SharePoint non eseguono indicizzazione full-text su questi tipi di file. Questi tipi di file sono considerati tipi di file non supportati. Sono inoltre disponibili tipi di file per i quali l'indicizzazione di testo completo è stata disattivata, per impostazione predefinita o da un amministratore. I tipi di file non supportati e disabilitati sono etichettati come elementi non indicizzati nelle ricerche di contenuto. Come indicato in precedenza, gli elementi parzialmente indicizzati possono essere inclusi nel set di risultati della ricerca durante l'esecuzione di una ricerca, esportare i risultati della ricerca in un computer locale oppure preparare i risultati della ricerca per Advanced eDiscovery. 
  
Per un elenco dei formati di file supportati e disattivati, vedere gli argomenti seguenti:
  
- **** - [Formati di file di Exchange indicizzati da ricerca di Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)
    
- **Exchange** - [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)
    
- **** Estensioni del[nome di file sottoposte a ricerca per indicizzazione e tipi di file analizzati in SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)  - 
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>I messaggi e i documenti con tipi di file parzialmente indicizzati possono essere restituiti nei risultati della ricerca

Non tutti i messaggi di posta elettronica con un allegato di file parzialmente indicizzato o tutti i documenti di SharePoint parzialmente indicizzati vengono restituiti automaticamente come elementi parzialmente indicizzati. Ciò è dovuto al fatto che altre proprietà del messaggio o del documento, ad esempio la proprietà **Subject** nei messaggi di posta elettronica e le proprietà **title** o **Author** per i documenti, sono indicizzate e sono disponibili per la ricerca. Ad esempio, una parola chiave Search for "Financial" restituirà gli elementi con un allegato di file parzialmente indicizzato se tale parola chiave viene visualizzata nell'oggetto di un messaggio di posta elettronica o nel nome o nel titolo di un documento. Tuttavia, se la parola chiave è presente solo nel corpo del file, il messaggio o il documento verrebbe restituito come elemento parzialmente indicizzato. 
  
Analogamente, i messaggi con allegati di file parzialmente indicizzati e i documenti di un tipo di file parzialmente indicizzato vengono inclusi nei risultati della ricerca quando altre proprietà del messaggio o del documento, indicizzate e ricercabili, soddisfano i criteri di ricerca. Le proprietà del messaggio indicizzate per la ricerca includono le date di invio e ricezione, il mittente e il destinatario, il nome del file di un allegato e il testo nel corpo del messaggio. Le proprietà del documento indicizzate per la ricerca includono date create e modificate. Pertanto, anche se un allegato del messaggio può essere un elemento parzialmente indicizzato, il messaggio verrà incluso nei risultati della ricerca normali se il valore di altre proprietà del messaggio o del documento corrisponde ai criteri di ricerca.
  
Per un elenco delle proprietà di posta elettronica e di documento che è possibile cercare utilizzando la funzionalità di ricerca nel &amp; Centro sicurezza e conformità, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).
  

  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementi parzialmente indicizzati inclusi nei risultati della ricerca
<a name="unindexeditemsresults"> </a>

L'organizzazione potrebbe essere necessaria per identificare ed eseguire un'analisi aggiuntiva sugli elementi parzialmente indicizzati per determinare quali sono, cosa contengono e se sono rilevanti per un'indagine specifica. Come spiegato in precedenza, gli elementi parzialmente indicizzati nei percorsi di contenuto in cui viene eseguita la ricerca vengono inclusi automaticamente nei risultati della ricerca stimati. È possibile includere questi elementi parzialmente indicizzati quando si esportano i risultati della ricerca o si preparano i risultati della ricerca per Advanced eDiscovery. Per includere gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca o li si prepara per le eDiscovery avanzate, selezionare una delle opzioni per includere gli elementi con un formato non riconosciuto, che sono crittografati o che non sono stati indicizzati per altri motivi.
  
Tenere presente quanto segue sugli elementi parzialmente indicizzati:
  
- Quando si esegue una ricerca di contenuto, il numero totale e le dimensioni degli elementi parzialmente indicizzati (restituiti dalla query di ricerca) vengono visualizzati nelle statistiche di ricerca nel riquadro dei dettagli, come indicato come "elementi non indicizzati".
    
- Quando si esportano i risultati della ricerca e si includono gli elementi parzialmente indicizzati, gli elementi di Exchange parzialmente indicizzati vengono esportati in un file PST separato per ogni cassetta postale in cui sono ubicati o come singoli messaggi se si seleziona l'opzione per scaricare gli elementi di Exchange come messaggi. gli elementi di SharePoint parzialmente indicizzati vengono esportati **** in una cartella denominata non indicizzabile.
    
- Se la ricerca da cui si stanno esportando i risultati è stata una ricerca di percorsi di contenuto specifici o di tutti i percorsi di contenuto dell'organizzazione, verranno esportati solo gli elementi non indicizzati provenienti da percorsi di contenuto che contengono elementi che corrispondono ai criteri di ricerca. In altre parole, se non sono presenti risultati della ricerca in una cassetta postale o in un sito, tutti gli elementi non indicizzati in tale cassetta postale o sito non verranno esportati. Il motivo è che l'esportazione di elementi parzialmente indicizzati da un numero elevato di posizioni nell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo necessario per esportare e scaricare i risultati della ricerca.
    
    Per esportare gli elementi parzialmente indicizzati da tutti i percorsi di contenuto per una ricerca, configurare la ricerca in modo che restituisca tutti gli elementi (rimuovendo le parole chiave dalla query di ricerca) e quindi esportare solo gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca (facendo clic su **solo gli elementi che dispongono di un formato non riconosciuto sono crittografati o non sono stati indicizzati per altri motivi** in **Opzioni di output**.
    
- Se si sceglie di includere tutti gli elementi delle cassette postali nei risultati della ricerca o se una query di ricerca non specifica parole chiave o specifica un intervallo di date, è possibile che gli elementi parzialmente indicizzati non vengano copiati nel file PST che contiene gli elementi parzialmente indicizzati. Ciò è dovuto al fatto che tutti gli elementi, compresi gli elementi parzialmente indicizzati, verranno inclusi automaticamente nei risultati di ricerca normali.
    
- Gli elementi parzialmente indicizzati non sono disponibili per la visualizzazione in anteprima. È necessario esportare i risultati della ricerca per visualizzare gli elementi parzialmente indicizzati restituiti dalla ricerca.

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementi parzialmente indicizzati esclusi dai risultati della ricerca

Se un elemento è parzialmente indicizzato ma non soddisfa i criteri di query di ricerca, non verrà incluso come elemento parzialmente indicizzato nei risultati della ricerca. In altre parole, l'elemento è escluso dai risultati della ricerca. Ad esempio, si supponga di eseguire una ricerca e non includere parole chiave o proprietà perché si desidera includere tutto il contenuto. Tuttavia, è inclusa una condizione dell'intervallo di date per la query. Se un elemento parzialmente indicizzato rientra all'esterno dell'intervallo di date, non verrà incluso come elemento parzialmente indicizzato. Gli intervalli di date rappresentano un modo efficace per escludere gli elementi parzialmente indicizzati dai risultati della ricerca.
  
Analogamente, se si sceglie di includere gli elementi parzialmente indicizzati quando si esportano i risultati di una ricerca, gli elementi parzialmente indicizzati esclusi dai risultati della ricerca non verranno esportati.
  
Una delle eccezioni a questa regola è quando si crea un blocco basato su query associato a un caso di eDiscovery. Se si crea un blocco basato su query, tutti gli elementi parzialmente indicizzati vengono inseriti in attesa. Sono inclusi gli elementi parzialmente indicizzati che non corrispondono ai criteri di query di ricerca e gli elementi parzialmente indicizzati che potrebbero non essere compresi in una condizione dell'intervallo di date. Per ulteriori informazioni sulla creazione di esenzioni basate su query, vedere il passaggio 4 nei [casi di eDiscovery nel centro conformità _AMP_ sicurezza di Office 365](ediscovery-cases.md#step-4-place-content-locations-on-hold).
  
## <a name="indexing-limits-for-messages-in-content-search"></a>Limiti di inDicizzazione per i messaggi nella ricerca contenuto

Nella tabella seguente vengono descritti i limiti di indicizzazione che possono comportare la restituzione di un messaggio di posta elettronica come elemento parzialmente indicizzato in una ricerca di contenuto in Office 365.
  
Per un elenco dei limiti di indicizzazione per i documenti di SharePoint, vedere [limiti della ricerca per SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f).
  
|**Limite di inDicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensione massima degli allegati (esclusi i file di Excel)  <br/> |150 MB  <br/> |Le dimensioni massime di un allegato di posta elettronica che analizzerà l'indicizzazione. Qualsiasi allegato che è più grande di questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato.<br/><br/> **Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae il testo dall'allegato, rimuove i caratteri non necessari come la punteggiatura e gli spazi e quindi divide il testo in parole (in un processo denominato tokenation), che vengono quindi memorizzate nell'indice.           |
|Dimensioni massime dei file di Excel  <br/> |4 MB  <br/> |La dimensione massima di un file di Excel che si trova in un sito o collegato a un messaggio di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi file di Excel di dimensioni superiori a questo limite non verrà analizzato e il file o l'indirizzo di posta elettronica il messaggio con l'allegato file verrà contrassegnato come non indicizzato.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come indicizzato parzialmente perché aveva allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Numero massimo di allegati nidificati analizzati. Ad esempio, se a un messaggio di posta elettronica è associato un altro messaggio e al messaggio allegato è associato un documento di Word, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà fino a 30 allegati nidificati.  <br/> |
|Numero massimo di immagini collegate  <br/> |0  <br/> |Un'immagine associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.  <br/> |
|Tempo massimo per l'analisi di un elemento  <br/> |30 secondi  <br/> |Viene speso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.  <br/> |
|Output del parser massimo  <br/> |2 milioni di caratteri  <br/> |La quantità massima di output di testo del parser indicizzato. Ad esempio, se il parser ha Estratto 8 milioni caratteri da un documento, solo i primi 2 milioni di caratteri vengono indicizzati.  <br/> |
|Token di annotazione massimi  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, è presente un limite di 2 milioni token di annotazione per un messaggio di posta elettronica.  <br/> |
|Dimensione massima del corpo nell'indice  <br/> |67 milioni caratteri  <br/> |Il numero totale di caratteri presenti nel corpo di un messaggio di posta elettronica e di tutti gli allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in una singola stringa. Le dimensioni massime della stringa indicizzata sono 67 milioni caratteri.  <br/> |
|Numero massimo di token univoci nel corpo  <br/> |1 milione  <br/> |Come spiegato in precedenza, i token sono il risultato dell'estrazione del testo dal contenuto, la rimozione della punteggiatura e degli spazi e quindi la suddivisione in parole (denominate token) memorizzate nell'indice. Ad esempio, la frase `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Vi è un limite di 1 milione token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice venga troppo esteso con token casuali.<br/> |
   

  
## <a name="more-information-about-partially-indexed-items"></a>Ulteriori informazioni sugli elementi parzialmente indicizzati
<a name="moreinfo"> </a>

- Come indicato in precedenza, poiché le proprietà del messaggio e del documento e i relativi metadati sono indicizzate, una ricerca per parola chiave potrebbe restituire risultati se la parola chiave viene visualizzata nei metadati indicizzati. Tuttavia, la stessa ricerca con parole chiave potrebbe non restituire lo stesso elemento se la parola chiave viene visualizzata solo nel contenuto di un elemento con un tipo di file non supportato. In questo caso, l'elemento verrebbe restituito come elemento parzialmente indicizzato.
    
- Se un elemento parzialmente indicizzato è incluso nei risultati della ricerca, poiché ha soddisfatto i criteri di query di ricerca e non è stato escluso, non verrà incluso come elemento parzialmente indicizzato nelle statistiche di ricerca stimate. Inoltre, non verrà incluso con gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca.
    
- Anche se un tipo di file è supportato per l'indicizzazione ed è indicizzato, è possibile che si verifichino errori di indicizzazione o di ricerca che provochino la restituzione di un file come elemento parzialmente indicizzato. Ad esempio, la ricerca di un file di Excel di dimensioni molto grandi potrebbe avere esito positivo, in quanto i primi 4 MB sono indicizzati, ma quindi ha esito negativo a causa del superamento del limite di dimensione del file. In questo caso, è possibile che lo stesso file venga restituito con i risultati della ricerca e come elemento parzialmente indicizzato.
    
- I file allegati crittografati con Microsoft Technologies sono indicizzati e possono essere ricercati. I file crittografati con tecnologie non Microsoft sono parzialmente indicizzati.
    
- I messaggi di posta elettronica crittografati con S/MIME sono parzialmente indicizzati. Sono inclusi i messaggi crittografati con o senza allegati di file.
    
- I messaggi protetti con la funzionalità IRM (Information Rights Management) vengono indicizzati e saranno inclusi nei risultati della ricerca se corrispondono alla query di ricerca.

## <a name="see-also"></a>Vedere anche

[Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md) (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)

