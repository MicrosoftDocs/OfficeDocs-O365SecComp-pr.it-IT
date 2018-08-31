---
title: Deduplicazione nei risultati della ricerca di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: È possibile duplicare deprovisioning dei risultati della ricerca eDiscovery che vengono esportati in modo che solo una copia di un messaggio di posta elettronica verrà esportata anche se potrebbe essere più istanze dello stesso messaggio sono state trovate nelle diverse cassette postali.
ms.openlocfilehash: 02a4f9f6db0fb8831d5e5cc13adaffbd0c4dcecc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531342"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Deduplicazione nei risultati della ricerca di eDiscovery

In questo articolo viene descritto il funzionamento deduplicazione dei risultati della ricerca di eDiscovery e vengono illustrati i limiti dell'algoritmo deduplicazione.
  
Quando si utilizzano gli strumenti di Office 365 eDiscovery per esportare i risultati di una ricerca eDiscovery, è possibile duplicare deprovisioning i risultati vengono esportati. Cosa significa? Quando si abilita deduplicazione (per impostazione predefinita, la deduplicazione non è abilitata), solo una copia di un messaggio di posta elettronica verrà esportata anche se potrebbe essere più istanze dello stesso messaggio sono state trovate nelle cassette postali in cui sono stati una ricerca. Deduplicazione consente di risparmiare tempo e ridurre il numero di elementi che è necessario esaminare e analizzare dopo che vengono esportati i risultati della ricerca. Ma è importante comprendere il funzionamento deduplicazione e tenere presente che non esistono limiti all'algoritmo che possono causare un elemento univoco deve essere contrassegnato come duplicato durante il processo di esportazione.
  
## <a name="how-duplicate-messages-are-identified"></a>Come vengono identificati i messaggi duplicati

Gli strumenti di Office 365 eDiscovery utilizzano una combinazione delle proprietà del messaggio di posta elettronica seguenti per determinare se un messaggio è un duplicato:
  
- **InternetMessageId** - questa proprietà specifica l'identificatore di messaggio Internet del messaggio di posta elettronica, è un identificatore univoco globale che fa riferimento a una versione specifica di un messaggio specifico. Questo ID viene generato dal sistema di posta elettronica host che invia il messaggio o programma client di posta elettronica del mittente. Se un utente invia un messaggio a più di un destinatario, l'ID messaggio Internet saranno uguali per ogni istanza del messaggio. Le revisioni successive al messaggio originale verranno visualizzato un identificatore di messaggio diverso. 
    
- **ConversationTopic** - la proprietà specifica l'oggetto del thread di conversazione di un messaggio. Il valore della proprietà **ConversationTopic** è la stringa che descrive l'argomento complessiva della conversazione. Una conservazione è costituita da un messaggio iniziale e tutti i messaggi inviati in risposta al messaggio iniziale. I messaggi nella stessa conversazione hanno lo stesso valore della proprietà **ConversationTopic** . Il valore di questa proprietà è in genere la riga dell'oggetto del messaggio iniziale che ha generato la conversazione. 
    
- **BodyTagInfo** - una proprietà di archiviazione Exchange interni. Il valore di questa proprietà viene calcolato controllando vari attributi nel corpo del messaggio. Questa proprietà viene utilizzata per rilevare differenze nel corpo dei messaggi. 
    
Durante il processo di esportazione di eDiscovery, queste tre proprietà vengono confrontate per ogni messaggio che genera una corrispondenza per i criteri di ricerca. Se queste proprietà sono identiche per i messaggi di due (o più), i messaggi sono determinati come duplicati e il risultato è che verrà esportata solo una copia del messaggio se è abilitata la deduplicazione. Il messaggio viene esportato è noto come "item origine". Informazioni sui messaggi duplicati sono incluso nei rapporti **Results.csv** e **manifest** inclusi con i risultati della ricerca esportato. Nel file **Results.csv** un messaggio duplicato è identificato da con un valore nella colonna **duplicati all'elemento** . Il valore di questa colonna corrisponde al valore nella colonna **Identità elemento** per il messaggio è stato esportato. 
  
Il grafico seguente Mostra messaggi come duplicati vengono visualizzati nei rapporti **Results.csv** e **file manifest. XML** che vengono esportati con i risultati della ricerca. Questi rapporti non includono le proprietà di posta elettronica descritte in precedenza, che vengono utilizzate per l'algoritmo deduplicazione. Invece, i report includono la proprietà **Identity di elemento** che viene assegnata agli elementi dall'archivio di Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Rapporto Results.csv (visualizzato in Excel)
  
![Visualizzazione delle informazioni sugli elementi duplicati nel rapporto Results.csv](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Rapporto manifest (visualizzato in Excel)
  
![Visualizzazione delle informazioni sugli elementi duplicati nel rapporto manifest. Xml](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Inoltre, sono incluse altre proprietà dai messaggi duplicati nei report di esportazione. Sono incluse la cassetta postale che si trova il messaggio duplicato, se il messaggio è stato inviato a un gruppo di distribuzione e, se il messaggio è stato necessario Cc o Ccn geograficamente a un altro utente.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitazioni dell'algoritmo deduplicazione

Esistono alcune limitazioni note dell'algoritmo deduplicazione che possono causare elementi univoci ottenere contrassegnato come duplicati. È importante comprendere tali limitazioni, in modo che è possibile decidere se utilizzare la funzionalità deduplicazione facoltativo o meno.
  
Esiste una situazione nella caratteristica deduplicazione potrebbe erroneamente identificare un messaggio come duplicato e non esportare il certificato (ma ancora citazione come duplicato nei report di esportazione). Questi sono messaggi che un utente modifica, ma non invia. Si supponga, ad esempio, un utente seleziona un messaggio di Outlook, copia il contenuto del messaggio e quindi incollarlo in un nuovo messaggio. Quindi l'utente modifica una delle copie rimozione o aggiunta di un allegato o modificare la riga dell'oggetto o nel corpo stesso. Se questi due messaggi corrispondono alla query di una ricerca eDiscovery, verrà esportato solo uno dei messaggi se deduplicazione è abilitata quando vengono esportati i risultati della ricerca. Anche se il messaggio originale o copiato messaggio è stato modificato, in modo non revisionati messaggi inviati e pertanto non sono stati aggiornati i valori delle proprietà **InternetMessageId**, **ConversationTopic** e **BodyTagInfo** . Ma come indicato in precedenza, entrambi i messaggi verranno elencati in rapporti di esportazione 
  
Si noti che i messaggi univoci possono essere contrassegnati anche come duplicati quando è abilitata la funzionalità di protezione di pagina copia in scrittura, come nel caso di una cassetta postale si trova su conservazione per controversia legale o archiviazione sul posto. La funzionalità di copia in scrittura consente di copiare il messaggio originale (e vengono salvate nella cartella versioni della cartella elementi ripristinabili dell'utente) prima del salvataggio di revisione all'elemento originale. In questo caso, la copia rivista e il messaggio originale (nella cartella elementi ripristinabili) potrebbe essere considerati come messaggi duplicati e pertanto solo uno di essi verrà esportato.
  
> [!IMPORTANT]
> Se i limiti dell'algoritmo deduplicazione potrebbero influire sulla qualità dei risultati della ricerca, non devono abilitare la deduplicazione durante l'esportazione di elementi. Se le situazioni descritte in questa sezione sono probabilmente un fattore nei risultati della ricerca non e si desidera ridurre il numero di elementi più probabilmente duplicati, potrebbe essere opportuno attivare deduplicazione. 
  
## <a name="more-information"></a>Ulteriori informazioni

- Le informazioni contenute in questo articolo sono applicabile per l'esportazione dei risultati della ricerca mediante uno degli strumenti di eDiscovery seguenti:
    
  - Ricerca del contenuto in Office 365 Security &amp; centro conformità
    
  - eDiscovery sul posto in Exchange Online
    
  - Centro eDiscovery in SharePoint Online
    
- Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere:
    
  - [Esportare i risultati della ricerca di Office 365 Security &amp; centro conformità](export-search-results.md)
    
  - [Esportare un report di ricerca del contenuto da Office 365 Security &amp; centro conformità](export-a-content-search-report.md)
    
  - [Risultati di ricerca di esportazione In-Place eDiscovery in un file PST](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [Esportare il contenuto e creare report nel centro eDiscovery](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
