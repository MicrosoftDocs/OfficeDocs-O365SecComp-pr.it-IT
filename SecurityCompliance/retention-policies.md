---
title: Panoramica dei criteri di conservazione
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con i criteri di conservazione, è possibile decidere in modo proattivo se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente, se applicare un singolo criterio all'intera organizzazione o solo a posizioni o utenti specifici e se applicare un criterio a tutti i contenuti o solo al contenuto che soddisfa determinate condizioni.
ms.openlocfilehash: 55680f16e92d33c2cbf612b6aabae1f51778f93a
ms.sourcegitcommit: 799a958fcac643f62dfac6fa04020f2f4758635c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "30997142"
---
# <a name="overview-of-retention-policies"></a>Panoramica dei criteri di conservazione

Per la maggior parte delle organizzazioni, il volume e la complessità dei dati aumentano giorno dopo giorno, per via di posta elettronica, documenti, messaggi istantanei e altro ancora. La gestione o il controllo efficace di queste informazioni è importante perché è necessario:
  
- **Conformarsi in modo proattivo alle normative del settore e ai criteri interni** che richiedono di conservare il contenuto per un periodo di tempo minimo, ad esempio la norma Sarbanes-Oxley Act richiede che alcuni tipi di contenuto vengano conservati per sette anni. 
    
- **Ridurre i rischi in caso di controversie legali o di violazioni della sicurezza** eliminando definitivamente i contenuti obsoleti che non è più necessario mantenere. 
    
- **Aiutare l'organizzazione a condividere le informazioni in modo efficace e a essere più flessibile** assicurando che gli utenti usino solo contenuti aggiornati e pertinenti. 
    
Un criterio di conservazione consente di raggiungere tutti questi obiettivi. La gestione dei contenuti in genere richiede due azioni:
  
- **Conservare** il contenuto in modo che non possa essere eliminato definitivamente prima del termine del periodo di conservazione. 
    
- **Eliminare** il contenuto in modo permanente alla fine del periodo di conservazione. 
    
Con i criteri di conservazione è possibile:
  
- Decidere proattivamente se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente.
    
- Applicare un singolo criterio all'intera organizzazione o solo a posizioni o utenti specifici.
    
- Applicare i criteri a tutti i contenuti o solo al contenuto che soddisfa determinate condizioni, ad esempio che contiene parole chiave specifiche o [tipi specifici di informazioni riservate](what-the-sensitive-information-types-look-for.md).
    
Quando si impostano criteri di conservazione per il contenuto, gli utenti possono continuare a modificare e usare il contenuto come sempre perché il contenuto viene mantenuto nella posizione originale. Se però qualcuno modifica o elimina il contenuto soggetto ai criteri, ne viene salvata una copia in una posizione sicura dove viene conservata finché restano in vigore i criteri.
  
È infine possibile che alcune organizzazioni debbano conformarsi a normative come la regola 17a-4 della SEC (Securities and Exchange Commission), in base alla quale i criteri di conservazione attivati non possono essere disattivati o resi meno restrittivi. Per soddisfare questo requisito, è possibile usare la caratteristica Protezione dell'archiviazione. Dopo aver bloccato i criteri, nessuno, incluso l'amministratore, può disattivarli o renderli meno restrittivi.
  
Creare e gestire i criteri di conservazione sulla:

- Pagina **Criteri** pagina nel Centro conformità Microsoft 365.
- Pagina **Conservazione** sotto **Governance dei dati** nel centro sicurezza&amp; e conformità di Office 365.
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a>Funzionamento dei criteri di conservazione con il contenuto presente

Quando si include una posizione, ad esempio un sito o una cassetta postale, nei criteri di conservazione, il contenuto rimane nella posizione originale. Gli utenti possono continuare a lavorare normalmente con i propri documenti o messaggi di posta elettronica. Tuttavia, se modificano o eliminano il contenuto incluso nei criteri, viene conservata una copia del contenuto al momento dell'applicazione dei criteri.
  
Per le raccolte siti di SharePoint una copia del contenuto originale viene conservata nella raccolta di archiviazione quando gli utenti modificano o eliminano il contenuto. Per la posta elettronica e le cartelle pubbliche la copia viene conservata nella cartella Elementi ripristinabili. Queste posizioni sicure e il contenuto conservato non sono visibili alla maggior parte degli utenti. Con i criteri di conservazione non è neanche necessario che gli utenti sappiano che il contenuto è soggetto a criteri.
  
Note:
  
- Il contenuto Skype è archiviato in Exchange, dove i criteri sono applicati in base al tipo di messaggio (posta elettronica o conversazione).
    
- I criteri di conservazione applicati a un gruppo di Office 365 includono sia la cassetta postale del gruppo che il sito.
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a>Contenuto negli account di OneDrive e nei siti di SharePoint

I criteri di conservazione vengono applicati a livello di raccolta siti. Quando si include una raccolta siti di SharePoint o un account di OneDrive nei criteri di conservazione, viene creata una raccolta di archiviazione, se non ne esiste già una. È possibile visualizzare questa raccolta nella pagina **Contenuto del sito** del sito di primo livello della raccolta siti. La raccolta di archiviazione non è visibile a tutti gli utenti, ma solo agli amministratori della raccolta siti.
  
Se un utente prova a modificare o eliminare il contenuto in un sito soggetto a criteri di conservazione, prima di tutto viene verificato se il contenuto è stato modificato dal momento dell'applicazione dei criteri. Se si tratta della prima modifica dall'applicazione dei criteri di conservazione, il contenuto viene copiato nella raccolta di archiviazione prima di consentire all'utente di modificare o eliminare il contenuto originale. Tutto il contenuto della raccolta siti può essere copiato nella raccolta di archiviazione, anche se non corrisponde alla query usata dai criteri di conservazione.
  
Un processo timer pulisce quindi la raccolta di archiviazione. Questo processo viene eseguito periodicamente e confronta tutto il contenuto della raccolta di archiviazione con le query usate dai criteri di conservazione nel sito. A meno che il contenuto non corrisponda ad almeno una delle query, il processo timer elimina definitivamente il contenuto dalla raccolta di archiviazione.
  
Quanto descritto in precedenza vale per il contenuto esistente al momento dell'applicazione dei criteri di conservazione. Inoltre, tutto il nuovo contenuto creato o aggiunto alla raccolta siti dopo che è stato incluso nei criteri verrà conservato dopo l'eliminazione. Il nuovo contenuto non viene copiato nella raccolta di archiviazione alla prima modifica, ma solo quando viene eliminato. Per conservare tutte le versioni di un file, è necessario attivare il controllo delle versioni, come descritto nella sezione seguente.
  
Tenere presente che, se si prova a eliminare una raccolta, un elenco, una cartella o un sito soggetto a criteri di conservazione, viene visualizzato un messaggio di errore. Un utente può eliminare una cartella se prima di tutto sposta o elimina tutti i file presenti nella cartella soggetta ai criteri. Tenere presente anche che la raccolta di archiviazione viene creata solo quando è necessario creare il primo elemento nella raccolta e non quando si creano i criteri di conservazione. Per testare i criteri, è quindi necessario modificare o eliminare un documento in un sito soggetto ai criteri e quindi passare alla raccolta di archiviazione per visualizzare la copia conservata.
  
![Diagramma del flusso di conservazione in SharePoint e OneDrive](media/858702f8-5a09-4464-86d0-3b16fed800f3.png)
  
Dopo che i criteri di conservazione vengono assegnati a un account di OneDrive o a un sito di SharePoint, il contenuto può seguire uno dei due percorsi seguenti:
  
1. **Se il contenuto viene modificato o eliminato** durante il periodo di conservazione, una copia del contenuto originale al momento dell'assegnazione dei criteri di conservazione viene creata nella raccolta di archiviazione. In questa raccolta viene eseguito a intervalli regolari un processo timer che identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro sette giorni dalla data di fine del periodo di conservazione. 
    
2. **Se il contenuto non viene modificato o eliminato** durante il periodo di conservazione, viene spostato nel Cestino di primo livello alla fine del periodo di conservazione. Se un utente elimina il contenuto da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Il Cestino non è indicizzato, quindi la ricerca non rileva alcun contenuto al suo interno. Ciò significa che un blocco di eDiscovery non può rilevare contenuto da bloccare nel Cestino. 
    
### <a name="content-in-mailboxes-and-public-folders"></a>Contenuto in cassette postali e cartelle pubbliche

Per la posta elettronica, il calendario e altri elementi di un utente, i criteri di conservazione vengono applicati a livello di cassetta postale. Per una cartella pubblica, i criteri di conservazione vengono applicati a livello di cartella e non di cassetta postale. Per conservare gli elementi sia di una cassetta postale che di una cartella pubblica viene utilizzata la cartella Elementi ripristinabili. Solo gli utenti a cui sono state assegnate autorizzazioni di eDiscovery possono visualizzare gli elementi nella cartella Elementi ripristinabili di un altro utente.
  
Per impostazione predefinita, quando un utente elimina un messaggio in una cartella diversa dalla cartella Posta eliminata, il messaggio viene spostato nella cartella Posta eliminata. Quando un utente elimina un elemento dalla cartella Posta eliminata, il messaggio viene spostato nella cartella Elementi ripristinabili. Un utente può anche eliminare temporaneamente un elemento (MAIUSC+CANC) in qualsiasi cartella. Con questa operazione la cartella Posta eliminata viene ignorata e l'elemento viene inserito direttamente nella cartella Elementi ripristinabili.
  
Un processo verifica periodicamente gli elementi nella cartella Elementi ripristinabili. Se un elemento non corrisponde alle regole specificate in almeno un criterio di conservazione, viene eliminato definitivamente dalla cartella Elementi ripristinabili.
  
Quando un utente prova a modificare determinate proprietà di un elemento della cassetta postale, ad esempio, l'oggetto, il corpo, gli allegati, i mittenti, i destinatari o la data di invio o di ricezione di un messaggio, una copia dell'elemento originale viene salvata nella cartella Elementi ripristinabili prima che la modifica diventi effettiva. Questa procedura si applica anche alle modifiche successive. Al termine del periodo di conservazione, le copie presenti nella cartella Elementi ripristinabili vengono eliminate definitivamente.
  
Se un utente lascia l'organizzazione e la sua cassetta postale è inclusa nei criteri di conservazione, la cassetta postale diventa inattiva quando viene eliminato l'account di Office 365 dell'utente. Il contenuto di una cassetta postale inattiva è comunque soggetto ai criteri di conservazione applicati alla cassetta postale prima della sua disattivazione ed è disponibile per una ricerca eDiscovery. Per ulteriori informazioni, vedere [Cassette postali inattive in Exchange Online](https://go.microsoft.com/fwlink/?linkid=846909).
  
![Diagramma del flusso di conservazione nelle cartelle di posta elettronica e pubblica](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)
  
Dopo che i criteri di conservazione vengono assegnati a una cassetta postale o a una cartella pubblica, il contenuto può seguire uno dei due percorsi seguenti:
  
1. **Se l'elemento viene modificato o eliminato** definitivamente dall'utente (con MAIUSC+CANC o eliminandolo da Posta eliminata) durante il periodo di conservazione, viene spostato (o copiato, in caso di modifica) nella cartella Elementi ripristinabili. In questa raccolta a intervalli regolari viene eseguito un processo che identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni. 
    
2. **Se l'elemento non viene modificato o eliminato** durante il periodo di conservazione, lo stesso processo viene eseguito periodicamente in tutte le cartelle della cassetta postale e identifica i messaggi il cui periodo di conservazione è scaduto. Questi elementi vengono eliminati definitivamente entro 14 giorni dalla data di fine del periodo di conservazione. 14 giorni è l'impostazione predefinita, ma può essere configurato un valore fino a 30 giorni. 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Funzionamento dei criteri di conservazione con le versioni del documento in una raccolta siti

Il controllo delle versioni è una funzionalità di tutte le raccolte documenti in SharePoint Online e OneDrive for Business. Per impostazione predefinita, il controllo delle versioni conserva almeno cinquecento versioni principali, sebbene sia possibile aumentare questo limite. Per ulteriori informazioni, vedere [Abilitare e configurare il controllo delle versioni per un elenco o una raccolta](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
I criteri di conservazione consentono di conservare tutte le versioni di un documento in una raccolta siti di SharePoint o in un account OneDrive. Ogni volta che un documento soggetto a criteri di conservazione viene modificato o eliminato, una versione viene copiata nella raccolta di archiviazione. Ogni versione di un documento nella raccolta di archiviazione esiste come elemento separato con il proprio periodo di conservazione:
  
- Se i criteri di conservazione si basano sulla data di creazione del contenuto, ciascuna versione ha la stessa data di scadenza del documento originale. Il documento originale e le sue versioni scadono tutti allo stesso tempo.
    
- Se i criteri di conservazione si basano sulla data dell'ultima modifica del contenuto, ciascuna versione ha la propria data di scadenza in base a quando il documento originale è stato modificato per creare quella versione. I documenti originali e le relative versioni scadono indipendentemente l'uno dall'altro.
    
## <a name="retaining-content-for-a-specific-period-of-time"></a>Conservazione del contenuto per un periodo di tempo specifico

Grazie ai criteri di conservazione è possibile conservare il contenuto per un periodo di tempo indefinito o per un numero specifico di giorni, mesi o anni. Il calcolo relativo al periodo di conservazione del contenuto è basato sulla data di modifica del contenuto e non sulla data di applicazione dei criteri di conservazione. È possibile scegliere se calcolare questo periodo a partire dalla creazione del contenuto o, per OneDrive e SharePoint, dalla data dell'ultima modifica.
  
Se, ad esempio, si vuole conservare il contenuto di una raccolta siti per sette anni dall'ultima modifica e un documento presente in questa raccolta siti non è stato modificato per sei anni, il documento verrà conservato solo per un altro anno, se non viene modificato. Se il documento viene nuovamente modificato, il periodo di conservazione verrà ricalcolato in base alla nuova data di modifica e il documento verrà conservato per altri sette anni.
  
Analogamente, se si desidera conservare il contenuto di una cassetta postale per sette anni e un messaggio è stato inviato sei anni fa, il messaggio verrà conservato solo per un altro anno. Per il contenuto di Exchange, il periodo si basa sempre sulla data di ricezione o di invio, che corrispondono. La conservazione del contenuto in base all'ultima modifica si applica solo al contenuto del sito di OneDrive e SharePoint.
  
È possibile scegliere se eliminare definitivamente il contenuto alla fine del periodo di conservazione. I criteri di conservazione possono anche eliminare semplicemente il vecchio contenuto senza conservarlo. Vedere la sezione successiva.
  
![Pagina delle impostazioni di conservazione](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminazione di contenuto antecedente a una data specifica

I criteri di conservazione possono conservare e quindi eliminare il contenuto successivamente o semplicemente eliminare il contenuto obsoleto senza conservarlo.
  
Se i criteri di conservazione eliminano il contenuto, è importante tenere presente che il periodo di tempo specificato per i criteri di conservazione viene calcolato dal momento in cui il contenuto è stato creato o modificato, non dal momento dell'assegnazione dei criteri.
  
![Impostazioni di eliminazione](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
Ad esempio, si supponga di creare criteri di conservazione che eliminano il contenuto dopo tre anni e quindi di assegnarli a tutti gli account di OneDrive, che includono grandi quantità di contenuti creati quattro o cinque anni fa. In questo caso, molti contenuti verranno eliminati subito dopo la prima assegnazione dei criteri di conservazione. Per questo motivo, **i criteri di conservazione che eliminano il contenuto possono avere un impatto notevole**. 
  
Prima di assegnare criteri di conservazione a una raccolta siti per la prima volta, è quindi consigliabile considerare il tempo trascorso dalla creazione del contenuto esistente e l'impatto dei criteri sul contenuto. È anche opportuno comunicare l'introduzione dei nuovi criteri agli utenti prima di assegnarli, in modo che possano valutarne l'impatto. Questo avviso viene visualizzato quando si esaminano le impostazioni per i criteri di conservazione prima di crearli.
  
![Avviso riguardante l'eliminazione del contenuto](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a>Impostazioni avanzate che applicano i criteri solo a contenuti che soddisfano determinate condizioni

I criteri di conservazione possono essere applicati a tutto il contenuto nelle posizioni incluse oppure solo al contenuto che contiene parole chiave specifiche o [tipi specifici di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
![Opzioni avanzate di conservazione](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a>Conservare il contenuto che include parole chiave specifiche

È possibile applicare i criteri di conservazione solo al contenuto che soddisfa determinate condizioni e quindi eseguire azioni di conservazione solo su tale contenuto. Le condizioni disponibili ora supportano l'applicazione di criteri di conservazione al contenuto che include parole o frasi specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT. Per ulteriori informazioni sugli operatori, vedere [Query con parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md).
  
Il supporto delle proprietà disponibili per le ricerche (ad esempio, **subject:**) sarà disponibile a breve.
  
Si noti che i criteri di conservazione basati su query usano l'indice di ricerca per identificare il contenuto.
  
![Editor di query](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a>Conservare il contenuto che include informazioni riservate

È possibile applicare i criteri di conservazione anche solo al contenuto che contiene [tipi specifici di informazioni riservate](what-the-sensitive-information-types-look-for.md). Ad esempio, è possibile scegliere di applicare requisiti di conservazione univoci solo al contenuto che contiene informazioni personali come codici identificativi dei singoli contribuenti, codici di previdenza sociale o numeri di passaporto.
  
![Pagina riguardante i tipi di informazioni riservate](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
Note:
  
- I criteri di conservazione avanzati per le informazioni riservate non si applicano alle cartelle pubbliche di Exchange o a Skype for Business perché queste posizioni non supportano i tipi di informazioni riservate.
    
- Exchange Online, infatti, usa le regole di flusso di posta (note anche come regole di trasporto) per identificare le informazioni riservate e quindi funziona solo per i messaggi in transito, non per tutti gli elementi già archiviati in una cassetta postale. Per Exchange Online, questo significa che i criteri di conservazione possono identificare le informazioni riservate e possono eseguire azioni di conservazione solo nei messaggi ricevuti **dopo** l'applicazione dei criteri alla cassetta postale. I criteri di conservazione basati su query descritti nella sezione precedente non hanno questa limitazione perché usano l'indice di ricerca per identificare il contenuto. 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>Applicazione di criteri di conservazione a un'intera organizzazione o a posizioni specifiche

È possibile applicare facilmente i criteri di conservazione a un'intera organizzazione, a intere posizioni oppure a posizioni o utenti specifici.
  
### <a name="org-wide-policy"></a>Criteri a livello di organizzazione

Una delle caratteristiche più efficaci dei criteri di conservazione riguarda la possibilità di applicare automaticamente i criteri alle posizioni in Office 365, tra cui:
  
- Posta elettronica di Exchange
    
- Raccolte siti di SharePoint
    
- Account di OneDrive
    
- Gruppi di Office 365 (si applica al contenuto della cassetta postale, del sito e dei documenti del gruppo). Il supporto per il contenuto in Planner, Yammer e CRM sarà disponibile a breve.
    
- Cartelle pubbliche di Exchange
    
![Opzione Tutte le posizioni](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
Altre caratteristiche importanti di un criterio di conservazione a livello di organizzazione includono:
  
- Non sono previsti limiti al numero di cassette postali o di siti inclusi nel criterio.
    
- Per Exchange, le nuove cassette postali create dopo l'applicazione del criterio ereditano automaticamente il criterio.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>Criteri validi per intere posizioni

Quando si scelgono le posizioni, è possibile includere o escludere facilmente un'intera posizione, ad esempio la posta elettronica di Exchange o gli account di OneDrive. A questo scopo, è sufficiente attivare o disattivare lo **Stato** di tale posizione. 
  
Come per i criteri a livello di organizzazione, un criterio applicabile a una qualsiasi combinazione di posizioni complete può includere un numero illimitato di cassette postali o siti. Ad esempio, se un criterio include tutta la posta elettronica di Exchange e tutti i siti di SharePoint, verranno inclusi tutti i siti e tutte le cassette postali, indipendentemente dal numero. Inoltre, per Exchange, le nuove cassette postali create dopo l'applicazione del criterio ereditano automaticamente il criterio.
 
![Pagina Seleziona posizioni](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Criteri con specifiche inclusioni o esclusioni

È anche possibile applicare i criteri di conservazione a specifici utenti. A questo scopo, attivare lo **Stato** di tale posizione e quindi usare i collegamenti per includere o escludere determinati utenti, gruppi di Office 365 o posizioni. 
  
Si noti però che sono previsti i limiti seguenti per i criteri di conservazione che includono o escludono più di 1.000 utenti specifici:
  
- I criteri di conservazione di questo tipo non possono contenere più di 1.000 cassette postali e 100 raccolte siti.
    
- Un tenant non può contenere più di 10.000 criteri di conservazione.
    
Anche se questi limiti esistono, è importante sapere che possono essere superati applicando criteri a livello di organizzazione o criteri validi per intere posizioni.
  
### <a name="skype-locations"></a>Posizioni Skype

A differenza della posta elettronica di Exchange, non è possibile semplicemente attivare lo stato della posizione Skype per includere tutti gli utenti, ma è possibile attivare la posizione e quindi scegliere manualmente gli utenti di cui si desidera conservare le conversazioni.
  
Quando si scelgono gli utenti di Skype for Business, è possibile includere rapidamente tutti gli utenti selezionando la casella **Nome** nell'intestazione di colonna. Tuttavia, è importante tenere presente che ogni utente viene conteggiato come una specifica inclusione nei criteri. Di conseguenza, se si includono più di 1.000 utenti, si applicano i limiti indicati nella sezione precedente. La selezione di tutti gli utenti di Skype da questa posizione non coincide con la procedura che prevede l'inclusione predefinita di tutti gli utenti di Skype con i criteri a livello di organizzazione. 
  
![Pagina di scelta utenti Skype](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Si noti che**Cronologia conversazioni**, una cartella di Outlook, è una funzionalità che non ha nulla a che fare con l'archiviazione di Skype. **Cronologia conversazioni** può essere disattivata dall'utente finale, mentre l'archiviazione per Skype avviene memorizzando una copia delle conversazioni di Skype in una cartella nascosta che è inaccessibile all'utente, ma disponibile per eDiscovery.

### <a name="office-365-groups-locations"></a>Posizioni dei gruppi di Office 365

Per conservare il contenuto di un gruppo di Office 365 è necessario usare la posizione dei gruppi di Office 365. Anche se un gruppo di Office 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso di Exchange non includerà il contenuto nelle cassette postali del gruppo di Office 365. I criteri di conservazione applicati a un gruppo di Office 365 includono sia la cassetta postale del gruppo che il sito.

Inoltre, non è possibile usare il percorso di Exchange per includere o escludere una specifica cassetta postale del gruppo. Anche se il percorso di Exchange consente inizialmente di selezionare una cassetta postale del gruppo, quando si prova a salvare il criterio di conservazione, si riceverà un messaggio di errore che segnala che "RemoteGroupMailbox" non è una selezione valida per il percorso di Exchange. 
  
### <a name="teams-locations"></a>Posizioni di Teams

È possibile usare i criteri di conservazione per conservare chat e messaggi del canale in Teams. Le chat di Teams vengono archiviate in una cartella nascosta della cassetta postale di ogni utente, incluso nella chat e i messaggi del canale di Teams vengono archiviati in un'analoga cartella nascosta della cassetta postale del gruppo per il team. Tuttavia, è importante sapere che Teams usa un servizio di chat con tecnologia Azure che archivia anche questi dati e che, per impostazione predefinita, questo servizio archivia i dati per sempre. Per questo motivo, è consigliabile usare il percorso di Teams per mantenere ed eliminare i dati di Teams. Con il percorso di Teams, i dati verranno eliminati definitivamente dalle cassette postali di Exchange e dal servizio di chat con tecnologia Azure sottostante. Per ulteriori informazioni, vedere [Panoramica di sicurezza e conformità in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258).
  
Le chat e i messaggi del canale di Teams non sono interessati dai criteri di conservazione applicati alle cassette postali di utenti o gruppi dei percorsi di Exchange o dei gruppi di Office 365. Anche se le chat e i messaggi del canale di Teams vengono archiviati in Exchange, sono interessati solo dai criteri di conservazione applicati al percorso di Teams.
  
Microsoft sta ancora lavorando sulla conservazione in Teams e renderà presto disponibili altre funzionalità. Nel frattempo, ecco alcune limitazioni da tenere presenti:
  
- **Teams richiede criteri di conservazione distinti:** quando si creano i criteri di conservazione e si attiva il percorso di Teams, tutti gli altri percorsi vengono disattivati. I criteri di conservazione che includono Teams possono includere solo Teams e non altri percorsi. 
    
- **Teams non è incluso in un criterio a livello di organizzazione:** se si crea un criterio a livello di organizzazione, Teams non viene incluso perché richiede criteri di conservazione specifici. 
    
- **Teams non supporta la conservazione avanzata:** quando si creano i criteri di conservazione, se si scelgono le [impostazioni avanzate che applicano criteri solo a contenuti che soddisfano determinate condizioni](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions), il percorso di Teams non è disponibile. Al momento, la conservazione in Teams si applica a tutto il contenuto di chat e messaggi del canale.
    
- **Per essere eliminato, il contenuto di Teams deve risalire ad almeno 30 giorni:** al momento, non è supportata la creazione di un criterio per eliminare il contenuto di Teams che ha meno di 30 giorni. Per applicare questo criterio al contenuto di Teams, specificare un periodo di conservazione uguale o maggiore di 30 giorni. 
    
- **Teams può richiedere fino a 30 giorni per la pulizia del contenuto conservato:** i criteri di conservazione applicati a Teams elimineranno il contenuto da tutti i percorsi di archiviazione pertinenti. Tuttavia, subito dopo il lancio, potrebbero servire fino a 30 giorni per pulire il contenuto nei client di Teams in base ai criteri di conservazione. Ciononostante, anche se viene ancora visualizzato nei client di Teams, il contenuto non sarà presente nelle ricerche o in eDiscovery al termine del periodo di conservazione. 
    
In un team i file condivisi in chat vengono archiviati nell'account di OneDrive dell'utente che ha condiviso il file. I file caricati nei canali vengono archiviati nel sito di SharePoint del team. Di conseguenza, per conservare o eliminare i file in un team, è necessario creare un criterio di conservazione che si applica ai percorsi di SharePoint e OneDrive. Per applicare un criterio ai file di un solo team, è possibile scegliere il sito di SharePoint per il team e gli account di OneDrive per gli utenti del team.
  
I criteri di conservazione che si applicano a Teams possono usare la [protezione dell'archiviazione](#locking-a-retention-policy).
  
![Posizioni Teams per chat e messaggi del canale](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Esclusione di specifici tipi di elementi di Exchange dai criteri di conservazione
È possibile usare PowerShell per escludere specifici tipi di elementi di Exchange dai criteri di conservazione. Ad esempio, è possibile escludere i messaggi vocali, le conversazioni di messaggistica istantanea e altri contenuti di Skype for Business Online nelle cassette postali. Si possono anche escludere elementi del calendario, note e attività. Questa funzionalità è disponibile solo tramite PowerShell, non è disponibile nell'interfaccia utente quando si crea un criterio di conservazione.
  
A questo scopo, usare il parametro `ExcludedItemClasses` dei cmdlet `New-RetentionComplianceRule` e `Set-RetentionComplianceRule`. Per ulteriori informazioni su PowerShell, vedere la sezione [Trovare i cmdlet di PowerShell per i criteri di conservazione](#find-the-powershell-cmdlets-for-retention-policies) più avanti.
  
## <a name="locking-a-retention-policy"></a>Blocco dei criteri di conservazione
È possibile che alcune organizzazioni debbano attenersi ai regolamenti definiti da enti normativi, come il regolamento 17a-4 della SEC (Securities and Exchange Commission), in base al quale i criteri di conservazione attivati non possono essere disattivati o resi meno restrittivi. La funzionalità di protezione dell'archiviazione consente di bloccare i criteri in modo che nessuno, incluso l'amministratore, possa disattivarli o renderli meno restrittivi.
  
Dopo il blocco dei criteri, nessuno può disattivarli, né rimuovere le posizioni dai criteri. Inoltre, non è possibile modificare o eliminare contenuti soggetti ai criteri durante il periodo di conservazione. Se i criteri sono stati bloccati, l'unico modo per modificarli è aggiungere posizioni oppure prolungarne la durata. I criteri bloccati possono essere aumentati o prolungati, ma non ridotti o disattivati.
  
Prima di bloccare i criteri di conservazione è quindi **essenziale** conoscere i requisiti di conformità dell'organizzazione e **non bloccare i criteri** a meno che non sia strettamente necessario.

### <a name="lock-a-retention-policy-by-using-powershell"></a>Bloccare i criteri di conservazione con PowerShell
  
È possibile bloccare i criteri di conservazione solo con PowerShell.

Prima di tutto, [connettersi a PowerShell in Centro sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/p/?LinkID=799771).

In secondo luogo, per visualizzare un elenco dei criteri di conservazione e trovare il nome dei criteri che si intende bloccare, eseguire `Get-RetentionCompliancePolicy`.

![Elenco dei criteri di conservazione in PowerShell](media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

Infine, per applicare la protezione dell'archiviazione sui criteri di conservazione, eseguire `Set-RetentionCompliancePolicy` con il parametro `RestrictiveRetention` impostato su true, ad esempio:

`Set-RetentionCompliancePolicy -Identity “<Name of Policy>” – RestrictiveRetention $true`

![Parametro RestrictiveRetention in PowerShell](media/retention-policy-preservation-lock-restrictiveretention.PNG)

Dopo aver eseguito questo cmdlet, viene visualizzata una richiesta di conferma. Scegliere **Sì a tutti**.

![Richiesta di conferma del blocco dei criteri di conservazione in PowerShell](media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Sui criteri di conservazione è ora applicata la protezione dell'archiviazione. Se si esegue `Get-RetentionCompliancePolicy`, il parametro `RestrictiveRetention` è impostato su true, ad esempio:

`Get-RetentionCompliancePolicy -Identity “<Name of Policy>” |Fl`

![Criteri bloccati con tutti i parametri visualizzati in PowerShell](media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Precedenza nei principi di conservazione

È possibile, o addirittura probabile, che al contenuto siano applicati più criteri di conservazione con azioni (conservare, eliminare o entrambi) e periodi di conservazione diversi. Quali sono i criteri che hanno la precedenza? Al livello più alto, un contenuto che viene conservato in base a un particolare criterio non può essere eliminato definitivamente da un altro criterio.
  
![Diagramma dei principi di conservazione](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Per comprendere in che modo i diversi criteri di conservazione vengono applicati al contenuto, tenere presente questi principi di conservazione:
  
1. **La conservazione prevale sull'eliminazione.** Si supponga di avere un criterio di conservazione che indica di eliminare la posta elettronica di Exchange dopo tre anni e un altro criterio di conservazione che indica di conservare la posta elettronica di Exchange per cinque anni e quindi eliminarla. Il contenuto che supera i tre anni verrà eliminato e nascosto agli utenti, ma comunque conservato nella cartella Elementi ripristinabili fino a raggiungere i cinque anni, quando verrà eliminato definitivamente. 
    
2. **Prevale il periodo di conservazione più lungo.** Se un contenuto è soggetto a più criteri di conservazione, verrà mantenuto fino al termine del periodo di conservazione più lungo. 
    
3. **L'inclusione esplicita prevale sull'inclusione implicita.** Questo significa che: 
    
    1. Se un utente assegna manualmente un'etichetta con impostazioni di conservazione a un elemento, ad esempio un messaggio di posta elettronica di Exchange o un documento di OneDrive, l'etichetta ha la precedenza sui criteri assegnati a livello di sito o di cassetta postale e su un'etichetta predefinita assegnata tramite la raccolta documenti. Ad esempio, se l'etichetta esplicita indica un periodo di conservazione di dieci anni, ma i criteri assegnati dal sito indicano di conservare solo per cinque anni, l'etichetta ha la precedenza. Si noti che le etichette applicate automaticamente sono considerate implicite e non esplicite, perché vengono applicate automaticamente da Office 365.
    
    2. Se un criterio di conservazione include una posizione specifica, ad esempio la cassetta postale o l'account di OneDrive for Business di un particolare utente, il criterio ha la precedenza su un altro criterio di conservazione applicato alle cassette postali o agli account di OneDrive for Business di tutti gli utenti, ma che non include specificamente la cassetta postale di quell'utente.
    
4. **Prevale il periodo di eliminazione più breve.** Analogamente, se un contenuto è soggetto a più criteri di eliminazione (senza conservazione), verrà eliminato alla fine del periodo di conservazione più breve. 
    
I principi di conservazione funzionano come un flusso di risoluzione di conflitti dall'alto verso il basso: se le regole applicate da tutti i criteri o le etichette sono le stesse in un determinato livello, il flusso si sposta verso il basso al livello successivo per determinare la priorità di applicazione di ogni regola.
  
Infine, un criterio o un'etichetta di conservazione non può eliminare definitivamente qualsiasi contenuto che si trovi in stato di blocco per eDiscovery. Quando il blocco viene rilasciato, il contenuto torna idoneo per il processo di pulizia descritto in precedenza.
  
## <a name="use-a-retention-policy-instead-of-these-features"></a>Usare i criteri di conservazione invece di queste caratteristiche

Un singolo criterio di conservazione può essere facilmente applicato a un'intera organizzazione e alle posizioni in Office 365, tra cui Exchange Online, SharePoint Online, OneDrive for Business e Gruppi di Office 365. Se si desidera conservare o eliminare il contenuto in una posizione qualsiasi di Office 365, è consigliabile usare i criteri di conservazione. È anche possibile usare le etichette con impostazioni di conservazione. Per ulteriori informazioni, vedere [Panoramica delle etichette](labels.md).
  
Per conservare o eliminare il contenuto in Office 365 in passato sono state usate diverse altre caratteristiche, elencate di seguito, che continueranno a funzionare insieme ai criteri di conservazione e alle etichette. In futuro, tuttavia, per la governance dei dati si consiglia di usare i criteri di conservazione o le etichette invece di queste caratteristiche. I criteri di conservazione sono l'unica caratteristica che può sia conservare che eliminare il contenuto in Office 365.
  
### <a name="exchange-online"></a>Exchange Online

- [Gestione di casi di eDiscovery nel Centro sicurezza e conformità di Office 365](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (blocco di eDiscovery) 
    
- [Blocco sul posto e blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=846124) (blocco di eDiscovery) 
    
- [Tag di conservazione e criteri di conservazione](https://go.microsoft.com/fwlink/?linkid=846125), noti anche come [gestione record di messaggistica](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminazione) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

- [Gestione di casi di eDiscovery nel Centro sicurezza e conformità di Office 365](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (blocco di eDiscovery) 
    
- [Aggiunta di un contenuto a un caso e archiviare origini blocco nel centro eDiscovery](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (blocco di eDiscovery) 
    
- [Panoramica dei criteri di eliminazione dei documenti](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (solo eliminazione) 
    
- [Configurazione di gestione dei record sul posto](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (conservazione) 
    
- [Usare criteri per la chiusura e l'eliminazione di siti](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (solo eliminazione) 
    
- [Criteri di gestione delle informazioni ](intro-to-info-mgmt-policies.md) (solo eliminazione) 
    
Se in passato sono stati usati blocchi di eDiscovery per la governance dei dati, per garantire una conformità proattiva ora si devono usare invece i criteri di conservazione. È consigliabile usare un solo blocco per eDiscovery.
  
### <a name="retention-policies-override-information-management-policies"></a>I criteri di conservazione sostituiscono i criteri di gestione delle informazioni

Nei siti di SharePoint potrebbero essere usati [criteri di gestione delle informazioni](intro-to-info-mgmt-policies.md) per conservare il contenuto. Se si applicano criteri di conservazione dei documenti a un sito che già usa criteri tipo di contenuto o criteri di gestione delle informazioni per un elenco o una raccolta, tali criteri vengono ignorati e vengono applicati i criteri di eliminazione dei documenti. 
  
## <a name="what-happened-to-preservation-policies"></a>Modifiche apportate ai criteri di conservazione

Se si usavano i precedenti criteri di conservazione, questi criteri ora vengono convertiti automaticamente nei nuovi criteri di conservazione che usano solo l'azione di conservazione. I criteri non eliminano il contenuto. I criteri di conservazione continueranno a funzionare e conservare il contenuto senza bisogno di interventi da parte dell'utente. Questi criteri sono disponibili nella pagina **Criteri** nel Centro conformità di Microsoft 365, o nella pagina **Conservazione** sotto **Governance dei dati** del centro sicurezza &amp;e conformità. È possibile cambiare i criteri di conservazione per modificare il periodo di conservazione, ma non è possibile apportare altre modifiche, ad esempio l'aggiunta o la rimozione delle posizioni. 
  
## <a name="permissions"></a>Autorizzazioni

Ai membri del team di conformità che creeranno criteri di conservazione è necessario assegnare autorizzazioni per il Centro sicurezza e conformità. Per impostazione predefinita, l'amministratore del tenant avrà accesso a questa posizione e potrà fornire ai responsabili della conformità e ad altre persone l'accesso al Centro sicurezza e conformità, senza concedere tutte le autorizzazioni di un amministratore del tenant. A questo scopo, è consigliabile accedere alla pagina **Autorizzazioni** del Centro sicurezza e conformità, modificare il gruppo di ruoli **Amministratore conformità** e aggiungere membri a tale gruppo di ruoli. 
  
Per ulteriori informazioni, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie solo per creare e applicare i criteri di conservazione. L'applicazione dei criteri non richiede l'accesso al contenuto.
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>Trovare i cmdlet di PowerShell per i criteri di conservazione

Per usare i cmdlet dei criteri di conservazione, è necessario:
  
1. [Connettersi al Centro sicurezza e conformità Office 365 utilizzando sessione remota di PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409).
    
2. Usare questi cmdlet del [Centro sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica delle etichette](labels.md)
    

