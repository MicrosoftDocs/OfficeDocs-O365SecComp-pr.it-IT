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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: 'Informazioni sugli elementi indicizzati in Exchange e SharePoint che è possibile includere in una ricerca di contenuto eseguire tramite di protezione di Office 365 &amp; centro conformità. '
ms.openlocfilehash: 4624985a9c80313d0222470e6cfb2c56495f2142
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530328"
---
# <a name="partially-indexed-items-in-content-search-in-office-365"></a>Partially indexed items in Content Search in Office 365 (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

Una ricerca di contenuto che viene eseguita da Office 365 Security &amp; centro conformità include automaticamente elementi indicizzati parzialmente nei risultati della ricerca stimati quando si esegue una ricerca. Elementi indicizzati parzialmente sono elementi della cassetta postale di Exchange e documenti in SharePoint e OneDrive per i siti che, per qualche motivo, non sono stati completamente indicizzati per la ricerca. In Exchange un elemento indicizzato parzialmente in genere contiene un file, ovvero di un tipo di file che non possono essere indicizzato, che è associato a un messaggio di posta elettronica. Ecco alcuni motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi indicizzati parzialmente quando si esegue una ricerca: 
  
- Il tipo di file non riconosciuto o non supportato per l'indicizzazione.
    
-  I messaggi sono un file allegato senza un gestore valido, ad esempio file di immagine. Questa è la causa più comune di elementi di posta elettronica parzialmente indicizzati. 
    
- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per un file specifico.
    
- È stato allegato un numero eccessivo di file a un messaggio di posta elettronica.
    
- Le dimensioni di un file allegato a un messaggio di posta elettronica sono eccessive.
    
- Un file è crittografato con tecnologie non Microsoft.
    
- Un file è protetto da password.
    
> [!NOTE]
> Per volume e inferiore a 12%, la maggior parte delle organizzazioni di Office 365 hanno meno dell'1% del contenuto di dimensione parzialmente indicizzato. Il motivo per la differenza tra volume e la dimensione è che i file di dimensioni maggiori probabilità di che include contenuto che non possono essere indicizzato completamente. 
  
Per le indagini legali, potrebbe essere necessario esaminare elementi indicizzati parzialmente nell'organizzazione. È inoltre possibile specificare se includere elementi indicizzati parzialmente quando si Esporta risultati della ricerca in un computer locale o quando si preparano i risultati per l'analisi con Office 365 avanzate eDiscovery. Per ulteriori informazioni, vedere [Investigating indicizzato parzialmente gli elementi di eDiscovery di Office 365](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipi di file non indicizzati per la ricerca

Alcuni tipi di file, ad esempio Bitmap o MP3, non contengono contenuto che può essere indicizzato. Di conseguenza, la ricerca di indicizzazione di Exchange Server e SharePoint non eseguono indice full-text su questi tipi di file. Questi tipi di file vengono considerati come tipi di file non supportati. Vi sono inoltre i tipi di file per cui indice full-text è stato disattivato, per impostazione predefinita o da un amministratore. Tipi di file non supportati e disabilitata sono contrassegnati come elementi non indicizzati di ricerche di contenuto. Come detto in precedenza, parzialmente indicizzati elementi possono essere inclusi nel set di risultati di ricerca quando si esegue una ricerca, esportare i risultati della ricerca in un computer locale o preparare i risultati della ricerca eDiscovery avanzate. 
  
Per un elenco dei formati di file supportati e disattivati, vedere gli argomenti seguenti:
  
- **Exchange** - [formati di File indicizzati da ricerca di Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)
    
- **Exchange** - [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)
    
- **SharePoint** - [estensioni di file a ricerca per indicizzazione e tipi di file in SharePoint analizzati predefiniti](https://go.microsoft.com/fwlink/p/?LinkID=404033)
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>I messaggi e documenti con parzialmente indicizzati file tipi possono essere restituiti nei risultati della ricerca

Non ogni messaggio di posta elettronica con un allegato di file indicizzati parzialmente o ogni documento SharePoint parzialmente indicizzato automaticamente viene restituito come elemento parzialmente indicizzato. Significa che l'altro messaggio o proprietà del documento, ad esempio la proprietà **Subject** nei messaggi di posta elettronica e la proprietà **titolo** o **autore** per i documenti sono indicizzate e disponibili per eseguire la ricerca. Ad esempio, una parola chiave cercare "finanziarie" verrà restituiti gli elementi con un allegato di file indicizzati parzialmente se la parola chiave verrà visualizzato nell'oggetto del messaggio di posta elettronica o il nome di file o il titolo di un documento. Tuttavia, se la parola chiave è presente solo nel corpo del file, il messaggio o il documento vengono restituito come elemento parzialmente indicizzato. 
  
Allo stesso modo, i messaggi con allegati di file indicizzati parzialmente e i documenti di un tipo di file parzialmente indicizzati vengono inclusi nei risultati della ricerca quando altre proprietà di un documento o messaggio sono indicizzate e supportano la ricerca, soddisfa i criteri di ricerca. Proprietà messaggi indicizzati per la ricerca includono date inviate e ricevute, mittente e destinatario, il nome di file di un allegato e il testo nel corpo del messaggio. Proprietà documento indicizzata per la ricerca include le date di creazione e di modificate. In modo anche se un allegato del messaggio può essere un elemento indicizzato parzialmente, il messaggio verrà inclusa nei risultati della ricerca regolare, se il valore di altre proprietà di un documento o messaggio genera una corrispondenza per i criteri di ricerca.
  
Per un elenco delle proprietà di posta elettronica e documenti che è possibile cercare utilizzando la funzionalità di ricerca in sicurezza &amp; centro conformità, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).
  

  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementi indicizzati parzialmente inclusi nei risultati della ricerca
<a name="unindexeditemsresults"> </a>

L'organizzazione potrebbe essere necessaria per identificare ed eseguire ulteriore analisi sugli elementi parzialmente indicizzati per determinare quali sono, il relativo contenuto e utilizzano pertinenti per una specifica indagini. Come indicato in precedenza, gli elementi indicizzati parzialmente nei percorsi di contenuto che vengono eseguita la ricerca vengono inclusi automaticamente con i risultati di ricerca stimati. È possibile includere questi elementi parzialmente indicizzati durante l'esportazione dei risultati di ricerca o prepara i risultati della ricerca eDiscovery avanzate. Per includere elementi indicizzati parzialmente quando si sta esportazione dei risultati di ricerca o li preparazione eDiscovery avanzate, selezionare una delle opzioni per includere gli elementi che dispongono di un formato non riconosciuto, vengono crittografati o non indicizzati per altri motivi.
  
Tenere presente sugli elementi indicizzati parzialmente le operazioni seguenti:
  
- Quando si esegue una ricerca di contenuto, il numero totale e le dimensioni di elementi indicizzati parzialmente (restituito dalla query di ricerca) vengono visualizzati in statistiche ricerca nel riquadro dei dettagli, come contrassegnati come "elementi indicizzati".
    
- Quando si esportano i risultati della ricerca e includono elementi indicizzati parzialmente, elementi di Exchange parzialmente indicizzati vengono esportati in un file PST separato per ogni cassetta postale in cui si trovano o come singoli messaggi se si seleziona l'opzione per scaricare gli elementi di Exchange come messaggi. elementi di SharePoint parzialmente indicizzati vengono esportati in una cartella denominata **Uncrawlable**.
    
- Se la ricerca per l'esportazione dei risultati di ricerca dei percorsi di contenuti specifici o tutti i percorsi di contenuti nell'organizzazione, verranno esportati solo gli elementi indicizzati da percorsi di contenuti che includono gli elementi che soddisfano i criteri di ricerca. In altre parole, se alcun risultato di ricerca non presenti in una cassetta postale o un sito, quindi gli elementi indicizzati in tale cassetta postale o un sito non verranno esportati. Il motivo di ciò è che l'esportazione di elementi indicizzati parzialmente da una quantità elevata di posizioni all'interno dell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo che necessario per l'esportazione e scaricare i risultati della ricerca.
    
    Per esportare elementi parzialmente indicizzati da tutti i percorsi di contenuti per eseguire una ricerca, configurare la ricerca per restituire tutti gli elementi (rimuovendo le parole chiave di query di ricerca) e quindi esportare solo parzialmente voci indicizzate quando si esportano i risultati della ricerca (facendo clic su solo ** gli elementi con un formato non riconosciuto, vengono crittografate o non indicizzate per altri motivi** in **Opzioni di Output**).
    
- Se si sceglie di includere tutti gli elementi della cassetta postale nei risultati della ricerca o se una query di ricerca non consente di specificare le parole chiave o solo specifica un intervallo di date, non elementi indicizzati parzialmente potrebbe essere copiati i file PST contenente gli elementi indicizzati parzialmente. Ciò avviene perché tutti gli elementi, inclusi gli elementi indicizzati parzialmente, verranno automaticamente incluso nei risultati della ricerca regolari.
    
- Elementi indicizzati parzialmente non sono disponibili da visualizzare in anteprima. È necessario esportare i risultati della ricerca per visualizzare elementi indicizzati parzialmente restituiti dalla ricerca.

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementi indicizzati parzialmente esclusi dai risultati della ricerca

Se un elemento viene indicizzato parzialmente, ma non soddisfa i criteri di query di ricerca, non sarà incluso come voce parzialmente indicizzata nei risultati della ricerca. In altre parole, l'elemento viene escluso dai risultati della ricerca. Si supponga, ad esempio si esegue una ricerca e non include le parole chiave o proprietà, dal momento che si desidera includere tutto il contenuto. Ma è includere una condizione di intervallo di date per la query. Se un elemento parzialmente indicizzato non rientra tale intervallo di date, non sarà incluso come voce parzialmente indicizzata. Gli intervalli di date sono un modo efficace per escludere elementi indicizzati parzialmente dai risultati della ricerca.
  
In modo analogo, se si sceglie di includere elementi indicizzati parzialmente quando si esportano i risultati della ricerca, non vengono esportati elementi indicizzati parzialmente esclusi dai risultati della ricerca.
  
Solo un'eccezione a questa regola è quando si crea una conservazione basata su query associata a un caso eDiscovery. Se si crea una conservazione basata su query, tutti gli elementi indicizzati parzialmente vengono messa in attesa. Sono incluse parzialmente indicizzati gli elementi che non soddisfano i criteri di query di ricerca e parzialmente indicizzata che potrebbe essere si trovano all'esterno di una condizione di intervallo di date. Per ulteriori informazioni sulla creazione basate su query mantiene, vedere il passaggio 4 in [casi di eDiscovery nel centro conformità protezione di Office 365](ediscovery-cases.md#step-4-place-content-locations-on-hold).
  
## <a name="indexing-limits-for-messages-in-content-search"></a>Limiti di indicizzazione per i messaggi di ricerca del contenuto

Nella tabella seguente vengono descritti i limiti di indicizzazione che possono causare tempi di un messaggio di posta elettronica viene restituito come elemento parzialmente indicizzato in una ricerca di contenuto in Office 365.
  
Per un elenco di indicizzazione limiti per i documenti di SharePoint, vedere [limiti relativi alla ricerca per SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f).
  
|**Limite di indicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensione massima degli allegati (esclusi i file di Excel)  <br/> |150 MB  <br/> |La dimensione massima di un allegato di posta elettronica che consente di analizzare per l'indicizzazione. Gli allegati che superano questo limite non vengono analizzati per l'indicizzazione e il messaggio con allegato viene contrassegnato come parzialmente indicizzato.<br/><br/> **Nota:** L'analisi è il processo di cui il servizio di indicizzazione estrae il testo dalla allegato, rimuove i caratteri non necessari, ad esempio i segni di punteggiatura e spazi e quindi lo divide il testo in parole (in un processo denominato la suddivisione in token), che vengono memorizzati in corrispondenza dell'indice.           |
|Dimensione massima dei file di Excel  <br/> |4 MB  <br/> |La dimensione massima di un file di Excel presente in un sito o associato a un messaggio di posta elettronica che viene analizzato per l'indicizzazione. Eventuali file di Excel che è maggiore della non verrà analizzato questo limite e il file o messaggio di posta elettronica che il messaggio con allegato il file verrà contrassegnato come non indicizzate.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegato al messaggio di posta elettronica che viene analizzato per l'indicizzazione. Se un messaggio non ha più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio è contrassegnato come parzialmente indicizzato perché era allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Il numero massimo di allegati nidificati che vengono analizzati. Ad esempio, se un messaggio di posta elettronica con un altro messaggio associato e il messaggio allegato è un documento di Word, il documento di Word e il messaggio allegato verrà essere indicizzati. Questo comportamento continua per gli allegati annidati fino a 30.  <br/> |
|Numero massimo di immagini associate  <br/> |0  <br/> |Immagine in cui è associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.  <br/> |
|Tempo massimo trascorso per l'analisi di un elemento  <br/> |30 secondi  <br/> |È trascorso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento è contrassegnato come parzialmente indicizzato.  <br/> |
|Output parser massimo  <br/> |2 milioni di caratteri  <br/> |La quantità massima di output di testo da parser indicizzato. Ad esempio, se il parser estratto 8 milioni di caratteri da un documento, solo i primi 2 milioni di caratteri vengono indicizzati.  <br/> |
|Token di annotazione massimo  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica è indicizzato, ogni parola con annotazioni con istruzioni di elaborazione diversi che specificano come deve essere indicizzato da word. Ogni set di istruzioni di elaborazione viene chiamato un token di annotazione. Per garantire la qualità del servizio di Office 365, non esiste un limite di token di annotazione 2 milioni per un messaggio di posta elettronica.  <br/> |
|Dimensioni massime del corpo nell'indice  <br/> |67 milioni di caratteri  <br/> |Numero totale di caratteri nel corpo del messaggio di posta elettronica e tutti i suoi allegati. Quando un messaggio di posta elettronica è indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati è concatenato in un'unica stringa. La dimensione massima della stringa indicizzato è 67 milioni di caratteri.  <br/> |
|Token univoco massimo nel corpo  <br/> |1 milione  <br/> |Come precedentemente illustrato, token sono il risultato di estrazione del testo rispetto al contenuto, rimuovendo i segni di punteggiatura e spazi e quindi la suddivisione in parole (noti come token) che vengono archiviate in corrispondenza dell'indice. Ad esempio, la frase `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 questi sono i token univoci. Non esiste un limite di 1 milione token univoco per ogni messaggio di posta elettronica, che consente di impedire l'indice di Guida troppo grande con token casuale.<br/> |
   

  
## <a name="more-information-about-partially-indexed-items"></a>Ulteriori informazioni sugli elementi parzialmente indicizzati
<a name="moreinfo"> </a>

- Come descritto in precedenza, poiché sono indicizzati a documenti e messaggi proprietà e i relativi metadati, una ricerca per parole chiave può restituire risultati se viene visualizzata la parola chiave nei metadati indicizzati. Tuttavia, tale ricerca tramite parola chiave stesso potrebbe non restituire stesso elemento di se la parola chiave è presente solo nel contenuto di un elemento con un tipo di file non supportati. In questo caso, l'elemento verrebbe restituito come elemento parzialmente indicizzato.
    
- Se un elemento parzialmente indicizzato è incluso nei risultati della ricerca, dal momento che soddisfano i criteri di query di ricerca (e non è stato escluso) non viene incluso come elemento parzialmente indicizzato in statistiche ricerca stimati. Inoltre, non sarà incluso in elementi indicizzati parzialmente quando si esportano i risultati della ricerca.
    
- Benché per un tipo di file supportato per l'indicizzazione ed è indicizzato, possono essere presenti errori di ricerca o indicizzazione che causano un file come elemento parzialmente indicizzato da restituire. Ad esempio, la ricerca di un file di Excel molto grande potrebbe essere completata parzialmente (dal momento che vengono indicizzati i primi 4 MB), ma il avrà esito negativo poiché viene superato il limite di dimensione file. In questo caso, è possibile che venga restituito lo stesso file con i risultati della ricerca e come elemento parzialmente indicizzato.
    
- File allegati crittografati con tecnologie Microsoft sono indicizzati e possono essere ricercati. File crittografati con tecnologie non Microsoft parzialmente vengono indicizzati.
    
- Parzialmente sono indicizzati a messaggi di posta elettronica crittografati con S/MIME. Sono inclusi i messaggi crittografati con o senza allegati.
    
- I messaggi protetti con la funzionalità IRM (Information Rights Management) vengono indicizzati e saranno inclusi nei risultati della ricerca se corrispondono alla query di ricerca.

## <a name="see-also"></a>Vedere anche

[Investigating partially indexed items in Office 365 eDiscovery](investigating-partially-indexed-items-in-ediscovery.md) (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)

