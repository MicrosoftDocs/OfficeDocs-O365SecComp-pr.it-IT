---
title: Differenze tra i risultati della ricerca eDiscovery stimato ed effettivo in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/13/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- SPO160
- MOE150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: 'Informazioni sui motivi per cui risultati di ricerca stimati ed effettivi possono variare nelle ricerche eseguite con gli strumenti di eDiscovery in Office 365. '
ms.openlocfilehash: b68f5ea2a24d3229a65b360f390284374a1efd39
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037999"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results-in-office-365"></a>Differenze tra i risultati della ricerca eDiscovery stimato ed effettivo in Office 365

In questo argomento si applica alle ricerche che è possibile eseguire utilizzando uno dei seguenti strumenti di eDiscovery di Microsoft:  <br/>  
- Ricerca di Office 365 protezione del contenuto &amp; centro conformità  <br/>  
- In-Place eDiscovery nell'interfaccia di amministrazione di Exchange (EAC)  <br/>  
- Centro eDiscovery in SharePoint Online  <br/> 
   
Quando si esegue una ricerca eDiscovery, lo strumento che si sta utilizzando restituirà una stima del numero di elementi (e le dimensioni totali) che soddisfano i criteri di ricerca. Ad esempio, quando si esegue una ricerca per la protezione &amp; centro conformità, la ricerca stimati i risultati vengono visualizzati nel riquadro dei dettagli per la ricerca selezionata.
  
![Stima dei risultati visualizzati nel riquadro dei dettagli della ricerca selezionata](media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Questa è la stessa stima delle dimensioni totali e il numero di elementi che viene visualizzato in eDiscovery strumento di esportazione quando si esportano i risultati in un computer locale e nel rapporto riepilogativo di esportazione che può essere scaricato con i risultati della ricerca.
  
**Risultati stimati di strumento di esportazione di eDiscovery**

![Risultati stimati nello strumento di esportazione di eDiscovery](media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Risultati stimati nel rapporto riepilogativo di esportazione**

![I risultati della ricerca stimati sono inclusi nel report Riepilogo esportazione](media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Come si noterà che nella schermata precedente del rapporto di riepilogo esportazione, dimensioni e il numero effettivo dei risultati della ricerca che è possibile scaricare effettivamente sono diversi rispetto alle dimensioni e numero di risultati di ricerca stimati. 
  
![Differenza tra i risultati della ricerca stimati e scaricati](media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Ecco alcuni dei motivi queste differenze:
  
- **I risultati del modo in cui sono stimati** - una stima dei risultati della ricerca sono semplicemente che, una stima e non un conteggio effettivo degli elementi che soddisfano i criteri di query di ricerca. Per compilare la stima degli elementi di Exchange, un elenco di ID che soddisfano i criteri di ricerca il messaggio viene richiesta dal database di Exchange tramite lo strumento di eDiscovery in uso. Ma quando si esportano i risultati della ricerca, la ricerca viene nuovamente eseguita e i messaggi effettivi vengono recuperati dal database di Exchange. Pertanto le differenze potrebbero verificarsi a causa di determinazione il numero stimato di elementi e il numero effettivo di elementi. 
    
- **Le modifiche che si verificano tra il momento in cui la stima ed esportazione di risultati della ricerca** - quando si esportano i risultati della ricerca, la ricerca viene riavviata la raccolta che più recenti degli elementi nell'indice di ricerca che soddisfano i criteri di ricerca. È possibile sono disponibili ulteriori elementi sono stati creati, inviato o ricevuto che soddisfano i criteri di ricerca nel tempo tra cui sono stati raccolti i risultati di ricerca stimati e se sono stati esportati i risultati della ricerca. È inoltre possibile che gli elementi presenti nell'indice di ricerca quando sono stati stimati i risultati della ricerca non sono più disponibili dal momento che sono stati eliminati dal percorso del contenuto prima che vengono esportati i risultati della ricerca. Per ovviare a questo problema è per specificare un intervallo di date per una ricerca eDiscovery. Un altro modo deve impostare un blocco sui percorsi di contenuti in modo che gli elementi vengono mantenuti e non possono essere eliminati. 
    
- **Elementi indicizzati** - gli elementi non indicizzate per la ricerca può causare differenze tra i risultati della ricerca stimato ed effettivo. Ad esempio, In-Place eDiscovery in Exchange e il centro eDiscovery in SharePoint non include elementi indicizzati (che non soddisfano i criteri di ricerca) quando si esegue una ricerca per valutare i risultati della ricerca. Ma è possibile includere elementi indicizzati quando si esportano i risultati della ricerca. Se si includono gli elementi non indicizzati per l'esportazione dei risultati della ricerca, potrebbero verificarsi ulteriori elementi che vengono esportati. In questo modo una differenza tra i risultati della ricerca stimati ed esportato. 
    
    Quando si utilizza lo strumento di ricerca del contenuto per la protezione &amp; centro conformità, è possibile includere gli elementi indicizzati nella stima ricerca. Il numero di elementi indicizzati restituiti dalla ricerca è elencato nel riquadro dei dettagli insieme ad altri risultati di ricerca stimati. Gli elementi non indicizzati potrebbero essere inclusi anche nelle dimensioni totali dei risultati di ricerca stimati. Quando si Esporta risultati della ricerca, è possibile includere o escludere elementi indicizzati. Come configurare queste opzioni possono causare tempi di differenze tra stimato e risultati di ricerca effettiva che sono stati scaricati. 
    
- **Esportare i risultati di una ricerca di contenuto che include tutti i percorsi contenuti** - se la ricerca per l'esportazione dei risultati di ricerca di tutti i percorsi di contenuti nell'organizzazione e quindi solo gli elementi indicizzati da percorsi di contenuti che includono è stato elementi corrispondenti ai criteri di ricerca verranno esportati. In altre parole, se alcun risultato di ricerca non presenti in una cassetta postale o un sito, quindi gli elementi indicizzati in tale cassetta postale o un sito non verranno esportati. Tuttavia, gli elementi indicizzati da tutti i percorsi contenuti, anche quelli che non contengono elementi che corrispondono alla query di ricerca, verranno inclusi nei risultati della ricerca stimati. 
    
    In alternativa, se la ricerca per l'esportazione dei risultati di inclusi i percorsi di contenuti specifici, quindi elementi indicizzati (che non sono esclusi dai criteri di ricerca) da tutti i percorsi contenuti specificati nella ricerca verranno esportati. In questo caso, il numero stimato di elementi indicizzati e il numero di elementi indicizzati effettivamente esportato devono coincidere.
    
    Il motivo dell'esportazione non di elementi indicizzati da qualunque posizione all'interno dell'organizzazione è perché potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo che necessario per l'esportazione e scaricare i risultati della ricerca.
    
- **Formati di file non elaborati e formati di file esportato** - elementi di Exchange, le dimensioni stimate dei risultati della ricerca viene calcolato utilizzando le dimensioni dei messaggi di Exchange non elaborati. Tuttavia, i messaggi di posta elettronica vengono esportati in un file PST o come singoli messaggi (in cui vengono formattati come file EML). Entrambe queste opzioni di esportazione usano un file diverso formato che non elaborati i messaggi di Exchange, le dimensioni totali file esportato da diverse rispetto alle dimensioni file stimate. 
    
- **Le versioni dei documenti** - documenti di SharePoint, più versioni di un documento non vengono inclusi nei risultati della ricerca stimati. Ma è possibile includere tutte le versioni dei documenti quando si esportano i risultati della ricerca, che aumentano il numero effettivo e dimensioni totali dei documenti esportati. 
    
- **Deduplicazione** - degli elementi di Exchange, deduplicazione riduce il numero di elementi che vengono esportate. È possibile duplicare deprovisioning i risultati della ricerca quando si esporta. Per i messaggi di Exchange, ciò significa che viene esportata una sola istanza di un messaggio, anche se tale messaggio può essere situato in più cassette postali. I risultati di ricerca stimati includono tutte le istanze di un messaggio. In modo che se si sceglie l'opzione deduplicazione per l'esportazione dei risultati della ricerca, il numero effettivo di elementi che vengono esportate potrebbe essere notevolmente inferiore rispetto al numero stimato di elementi. 
    
    Un altro elemento da tenere presenti se si sceglie l'opzione deduplicazione è che tutti gli elementi di Exchange vengono esportati in un unico file PST e non viene mantenuta la struttura di cartelle dalle cassette postali di origine. Il file PST esportato include solo gli elementi di posta elettronica. Tuttavia, un rapporto di risultati di ricerca contiene una voce per ogni messaggio esportato che identifica la cassetta postale di origine in cui si trova il messaggio. Consente di identificare tutte le cassette postali che contengono un messaggio duplicato. Se non si attiva la deduplicazione, viene esportato un file PST separato per ciascuna cassetta postale incluse nella ricerca. 
    
## <a name="exporting-unindexed-items-from-the-ediscovery-center-in-sharepoint-online"></a>Esportazione di elementi indicizzati da eDiscovery Center in SharePoint Online

In Centro eDiscovery di SharePoint Online, è possibile includere il contenuto non indicizzato (da Exchange e SharePoint) quando si esporta i risultati di una ricerca eDiscovery. Ottenere questo risultato selezionando l'opzione **Includi elementi che vengono crittografati o hanno un formato non riconosciuto** . Elementi indicizzati (denominati anche uncrawlable in SharePoint) sono elementi in Exchange e SharePoint che, per qualche motivo, non indicizzato per la ricerca. Nel rapporto **Errori indice Exchange** che ha incluso quando si esportano i risultati della ricerca sono elencati gli elementi non indicizzati di Exchange. Analogamente, non indicizzate SharePoint elementi disponibili nel rapporto **Errori dell'indice di SharePoint** . Quando si esportano elementi indicizzati, viene scaricati in una cartella denominata **Uncrawlable**. Gli elementi di Exchange non indicizzati vengono inclusi in un file PST. tutti i documenti indicizzati da SharePoint viene scaricato troppo. Il numero di elementi indicizzati (se disponibili) sono elencati in ogni rapporto errori di indice. Il numero di elementi indicizzati nei rapporti deve corrispondere il numero di elementi indicizzati che sono stati scaricati. 
  
 **Quali sono alcuni dei motivi se il numero di elementi indicizzati esportati non corrisponde al numero di elementi nella segnalazione di errori indice?** Come indicato in precedenza, è possibile che gli elementi sono stati eliminati da Office 365 tra il momento in cui che è stata eseguita la stima di ricerca e l'ora in cui che sono stati esportati i risultati della ricerca. Può verificarsi una discrepanza simile per gli elementi indicizzati. L'indice di ricerca, ad esempio, potrebbe essere fuori data quando vengono esportati i risultati della ricerca. Ciò significa che un elemento non indicizzato che era stato esportato con i risultati della ricerca potrebbe non essere elencato nel rapporto errori indice perché l'elemento non è stato indicizzato al momento che sono stati esportati i risultati della ricerca. In questo modo, gli elementi più indicizzati da export rispetto a quelle elencate nella segnalazione di errori dell'indice. Analogamente, un elemento non indicizzato elencato nella segnalazione di errori indice potrebbe sono stati rimossi da Office 365 prima che sia stato aggiornato l'indice di ricerca. In questo modo, meno elementi indicizzati da export rispetto a quelle elencate nella segnalazione di errori dell'indice. 
  
> [!NOTE]
> Se non si seleziona l'opzione **Includi elementi che vengono crittografati o hanno un formato non riconosciuto** quando si esportano i risultati di ricerca o solo scaricare i report, i rapporti di errore di indice vengono scaricati ma non dispongono di tutte le voci. Ciò non significa che non vi sono errori indicizzazione. Significa semplicemente che gli elementi indicizzati non sono stati inclusi nell'esportazione. 
  

