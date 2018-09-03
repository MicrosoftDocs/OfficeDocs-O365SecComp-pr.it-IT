---
title: Ricerca del contenuto in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Utilizzare la ricerca di contenuto in Office 365 Security &amp; centro conformità per la ricerca per il contenuto delle cassette postali, siti di SharePoint Online, gli account di OneDrive, Teams Microsoft, gruppi di Office 365 e Skype per le conversazioni di Business. È possibile utilizzare le query di ricerca di parola chiave e criteri di ricerca per limitare i risultati di ricerca. È quindi possibile visualizzare in anteprima ed esportare i risultati della ricerca. Ricerca del contenuto è anche uno strumento efficace per ricercare contenuto correlati a una richiesta di oggetto PILR dati.
ms.openlocfilehash: 11e96c6a11dd66c0095b7c624413e9e39036d8d6
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782083"
---
# <a name="content-search-in-office-365"></a>Ricerca del contenuto in Office 365

È possibile utilizzare lo strumento di eDiscovery di ricerca del contenuto in Office 365 Security &amp; centro conformità per cercare gli elementi sul posto, ad esempio posta elettronica, documenti e nella propria organizzazione Office 365 conversazioni di messaggistica immediata. Utilizzare questo strumento per la ricerca per gli elementi di questi servizi di Office 365:
  
- Cassette postali di Exchange Online e le cartelle pubbliche
    
- OneDrive per gli account aziendali e siti di SharePoint Online
    
- Skype per le conversazioni aziendali
    
- Microsoft Teams 
    
- Gruppi di Office 365
    
Dopo aver eseguito una ricerca di contenuto, il numero di percorsi di contenuti e un numero stimato di risultati della ricerca viene visualizzato nel profilo di ricerca. È possibile visualizzare le statistiche, anche rapidamente, ad esempio i percorsi di contenuti con la maggior parte degli elementi che corrispondono alla query di ricerca. Dopo aver eseguito la ricerca, è possibile visualizzare in anteprima i risultati o le Esporta in un computer locale.


## <a name="create-a-new-search"></a>Creare una nuova ricerca

Per accedere alla pagina **ricerca contenuto** per eseguire ricerche e preview ed esportare i risultati della ricerca, un amministratore, responsabile della conformità o manager eDiscovery deve essere un membro del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità. Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere utilizzando l'indirizzo di posta elettronica di Office 365 e la password. 
    
3. In sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **ricerca del contenuto**.
    
4. Nella pagina di **ricerca** , fare clic sulla freccia accanto a ![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**. 
    
    ![Il nuovo elenco a discesa ricerca](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    È possibile scegliere una delle seguenti opzioni:
    
  - **Ricerca guidato** - questa opzione consente di avviare una procedura guidata che viene descritta la creazione di ricerca. L'interfaccia utente di selezionare i percorsi di contenuti e creare la query di ricerca sono gli stessi come opzione di **ricerca di nuovo** . 
    
  - **Nuova ricerca** - questa opzione consente di visualizzare un'interfaccia utente aggiornata per creare una nuova ricerca. Si tratta dell'opzione predefinita se si fa clic su **nuova ricerca**.
    
  - **ID elenco Cerca per** - questa opzione consente di cercare messaggi di posta elettronica specifico e altri elementi delle cassette postali utilizzando un elenco di ID di Exchange. Per creare una ricerca di elenco di ID (denominata formalmente una ricerca di destinazione), è inviare un file virgole (CSV) virgola che identifica gli elementi della cassetta postale specifica da cercare. Per ulteriori informazioni, vedere [Preparazione di un file CSV per un elenco degli ID di ricerca del contenuto in Office 365](csv-file-for-an-id-list-content-search.md).
    
    Nella parte restante di questa procedura verrà eseguiti nuova ricerca flusso di lavoro predefinito.
    
5. Fare clic su **nuova ricerca** nell'elenco a discesa. 
    
6. In **query di ricerca**, specificare quanto segue.
    
    ![Specificare le parole chiave, le condizioni e percorsi per la ricerca](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
- **Parole chiave per cercare** - tipo di una ricerca eseguire una query nella casella **parole chiave** . È possibile specificare le parole chiave, messaggio proprietà come inviati e ricevuti, date o proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È possibile utilizzare una query più complesse che utilizzano un operatore booleano, ad esempio **AND**, **OR**, **non**e **NEAR**. È inoltre possibile cercare informazioni sensibili (ad esempio numeri di previdenza sociale) nei documenti o ricerca per i documenti condivisi esternamente. Se si lascia vuota la casella parole chiave, tutto il contenuto disponibile nei percorsi di contenuto specificati sarà incluse nei risultati della ricerca.
    
    In alternativa, è possibile selezionare la casella di controllo **Mostra elenco di parole chiave** e il tipo di una parola chiave in ogni riga. In questo caso, le parole chiave in ogni riga sono connessi tramite un operatore logico ( **c:s**) che è simile all'operatore **OR** nella query di ricerca che viene creata. 
    
    Perché utilizzare l'elenco delle parole chiave? È possibile ottenere le statistiche che mostra il numero di elementi corrispondenti a ogni parola chiave. Ciò consente di identificare rapidamente i quali le parole chiave sono il massimo (e almeno) efficaci. È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga. Per ulteriori informazioni sulle statistiche di ricerca, vedere [visualizzare le statistiche delle parole chiave per i risultati di ricerca del contenuto](view-keyword-statistics-for-content-search.md).
    
- **Condizioni** - è possibile aggiungere le condizioni di ricerca per restringere la ricerca e restituire un set di risultati più dettagliato. Ogni condizione aggiunge una clausola di query di ricerca che viene creata ed eseguita quando si avvia la ricerca. Una condizione è connesso logicamente per le query con parole chiave (specificata nella casella parole chiave) da un operatore logico ( **c:c**) funzionalità analogo all'operatore **AND** . Ciò significa che gli elementi presentano soddisfare le query con parole chiave sia una o più condizioni da includere nei risultati. Si tratta come condizioni consentono di limitare i risultati. Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "Criteri di ricerca" in [condizioni di ricerca per la ricerca del contenuto e query con parole chiave](keyword-queries-and-search-conditions.md#search-conditions).
    
- **Percorsi** : scegliere i percorsi di contenuti per la ricerca.
    
  - **Tutti i percorsi** - utilizzare questa opzione per cercare tutti i percorsi di contenuti nell'organizzazione. Messaggio di posta elettronica sono incluse in tutte le cassette postali di Exchange (incluse tutte le cassette postali inattive, le cassette postali per tutti i gruppi di Office 365, le cassette postali per tutti i Teams Microsoft), tutte le Skype per le conversazioni aziendali, tutti i OneDrive per i siti (inclusi i siti e SharePoint per tutti i gruppi di Office 365 e Microsoft Teams) e gli elementi in tutte le cartelle pubbliche di Exchange.
    
  - **Percorsi specifici** : utilizzare questa opzione per cercare i percorsi di contenuti specifici. È possibile cercare tutti i percorsi di contenuti per un servizio specifico di Office 365 (ad esempio la ricerca di tutte le cassette postali di Exchange o cercare tutti i siti di SharePoint) o per ricercare i percorsi specifici in uno dei servizi di Office 365 che vengono visualizzati. 
    
    ![Interfaccia utente di scegliere i percorsi di contenuti per la ricerca](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
    Si noti che è anche possibile aggiungere gruppi di distribuzione all'elenco delle cassette postali di Exchange per la ricerca. Per i gruppi di distribuzione, le cassette postali dei membri del gruppo vengono eseguita la ricerca. Si noti che non sono supportati i gruppi di distribuzione dinamico.
    
    **Importante:** Quando si esegue la ricerca tutti i percorsi delle cassette postali o cassette postali solo specifiche, dati di MyAnalytics e altre applicazioni di Office 365 che ha salvato cassette postali degli utenti verranno inclusi quando si esportano i risultati di ricerca di contenuto. Questi dati non vengono inclusi nei risultati della ricerca stimati e non sarà disponibile per l'anteprima. Solo verranno incluso quando si esportano e scaricare i risultati di ricerca. vedere [esportazione dei dati da MyAnalytics e altre applicazioni di Office 365](#exporting-data-from-myanalytics-and-other-office-365-applications) nella sezione "Ulteriori informazioni sulla ricerca contenuto". 
    
7. Dopo aver configurato la query di ricerca, fare clic su **salvare &amp; eseguire**.
    
8. Nella pagina **Salva ricerca** digitare un nome per la ricerca e una descrizione facoltativa che consente di identificare la ricerca. Si noti che il nome della ricerca deve essere univoco all'interno dell'organizzazione. 
    
9. Fare clic su **Salva** per avviare la ricerca. 
    
    Dopo avere salvato ed eseguire la ricerca, eventuali risultati restituiti dalla ricerca vengono visualizzati nel riquadro dei risultati. A seconda impostazione preview configurata, è necessario fare clic su **Anteprima risultati** per visualizzarli i risultati della ricerca sono visualizzato. Vedere la sezione seguente per informazioni dettagliate. 
    
Per accedere nuovamente per la ricerca di contenuto o accedere altri ricerche contenuti elencati nella pagina **contenuto di ricerca** , selezionare la ricerca e quindi fare clic su **Apri**. 
  
Per cancellare i risultati o creare una nuova ricerca, fare clic su ![sull'icona Aggiungi](media/O365-MDM-CreatePolicy-AddIcon.gif) **nuova ricerca**. 

  
## <a name="preview-search-results"></a>Anteprima dei risultati della ricerca

Esistono due impostazioni di configurazione per l'anteprima dei risultati della ricerca. Dopo aver eseguito un nuovo una nuova ricerca o aprire una ricerca esistente, fare clic su * * i singoli risultati * * per visualizzare le impostazioni di anteprima seguenti: 
  
![Impostazioni dei risultati di ricerca di anteprima](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Visualizzare in anteprima i risultati automaticamente** - questa impostazione consente di visualizzare i risultati della ricerca dopo l'esecuzione di un'una ricerca.
    
2. **Visualizzare in anteprima i risultati manualmente** - questa impostazione segnaposto viene visualizzato nel riquadro risultati della ricerca e viene visualizzato il pulsante **Anteprima risultati** che è necessario fare clic qui per visualizzare i risultati della ricerca. Si tratta dell'impostazione predefinita; Consente di migliorare le prestazioni della ricerca per visualizzare i risultati della ricerca non automaticamente quando si apre una ricerca. 
    
Non esistono limiti relativi al numero di elementi è disponibile da visualizzare in anteprima. Per ulteriori informazioni, vedere [limiti per la ricerca in Office 365 Security &amp; centro conformità](limits-for-content-search.md). 
  
Per un elenco dei tipi di file supportati che possono essere visualizzati in anteprima, vedere [visualizzare in anteprima i risultati della ricerca](#previewing-search-results) nella sezione "Ulteriori informazioni sulla ricerca contenuto". Se un tipo di file non è supportato per l'anteprima o per scaricare una copia di un documento, è possibile fare clic su **Download file originale** per scaricarlo nel computer locale. Per le pagine Web. aspx, l'URL per la pagina è incluso anche se non si dispone delle autorizzazioni per accedere alla pagina. 
  
Si noti inoltre che gli elementi indicizzati non sono disponibili per l'anteprima.
  
## <a name="view-information-and-statistics-about-a-search"></a>Visualizzare le informazioni e statistiche sulla ricerca

Dopo aver creato ed eseguire una ricerca di contenuto, è possibile visualizzare le statistiche relative ai risultati di ricerca stimati. Includono un riepilogo dei risultati della ricerca, le statistiche delle query, ad esempio il numero di posizioni contenute con gli elementi che corrispondono alla query di ricerca e il nome dei percorsi di contenuti che contiene elementi più corrispondenti. È possibile visualizzare le statistiche per uno o più ricerche di contenuto. In tal modo si per confrontare i risultati delle ricerche eseguite più rapidamente e prendere decisioni sull'efficacia le query di ricerca.
  
È inoltre possibile scaricare le statistiche di ricerca e statistiche sulle parole chiave in un file CSV. Consente di utilizzare le funzionalità di filtro e ordinamento in Excel per confrontare i risultati e preparare i report dei risultati della ricerca.
  
Per visualizzare le statistiche di ricerca:
  
1. Nella pagina **ricerca contenuto** nella protezione &amp; centro conformità, fare clic su **Apri** e quindi fare clic su ricerca che si desidera visualizzare le statistiche per. 
    
2. In tempo reale pagina, fare clic su **Apri query**. 
    
3. Nell'elenco a discesa **singoli risultati** , fare clic su **profili di ricerca**.
    
4. Nell'elenco a discesa **tipo** , fare clic su una delle seguenti opzioni a seconda che si desidera visualizzare le statistiche di ricerca. 
    
  - **Riepilogo** : statistiche vengono visualizzate per ogni tipo di contenuto percorsi eseguita la ricerca. Questo contenuto il numero di percorsi di contenuti che contiene elementi corrispondenti a query di ricerca e il numero totale e le dimensioni delle voci dei risultati di ricerca. Questo è l'impostazione predefinita.
    
  - **Query** - Visualizza statistiche sulle query di ricerca. Include il tipo di percorso contenuto le statistiche delle query sono applicabili a, parte della query di ricerca le statistiche sono applicabili per (si noti che **principale** indica la query di ricerca intero), il numero di posizioni contenute che contengono gli elementi che soddisfano la query di ricerca e il numero totale e dimensioni e gli elementi che sono stati trovati (nel percorso specificato contenuto) che corrispondono alla query di ricerca. Si noti che verranno visualizzate anche le statistiche per gli elementi non indicizzate (denominati anche elementi indicizzati parzialmente). Tuttavia, solo gli elementi indicizzati parzialmente dalle cassette postali vengono inclusi nelle statistiche. Elementi indicizzati parzialmente di SharePoint e OneDrive non vengono inclusi nelle statistiche.
    
  - **Percorsi principali** - Visualizza statistiche sul numero di elementi che corrispondono alla query di ricerca in ogni sito di contenuto che è stata eseguita la ricerca. Vengono visualizzate le posizioni prime 1000.
    
Per informazioni più dettagliate sulle statistiche di ricerca, vedere [visualizzare le statistiche delle parole chiave per i risultati di ricerca del contenuto](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Esportare i risultati della ricerca

Dopo l'esecuzione di una ricerca, è possibile esportare i risultati della ricerca in un computer locale. Quando si esportano i risultati di posta elettronica, possono essere scaricati al computer come file PST o singoli messaggi (file con estensione msg). Quando si esporta il contenuto dai siti di SharePoint e OneDrive, vengono esportate le copie dei documenti di Office nativi. Sono inoltre ulteriori documenti e che sono inclusi con i risultati della ricerca esportato. È anche appena possibile esportare il report dei risultati di ricerca e non gli elementi effettivi.
  
Per esportare i risultati di ricerca:
  
1. Nella pagina **ricerca contenuto** nella protezione &amp; centro conformità, fare clic su **Apri** e quindi fare clic su ricerca che si desidera esportare i risultati della ricerca. 
    
2. In tempo reale pagina, fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **ulteriori**e quindi fare clic su **Esporta risultati**. Si noti che è anche possibile esportare un report dei risultati della ricerca.
    
3. Completare le sezioni nella pagina a comparsa **Esporta risultati**. Assicurarsi di usare la barra di scorrimento per visualizzare tutte le opzioni di esportazione. 
    
Per istruzioni dettagliate e suggerimenti sulla risoluzione dei problemi, vedere:
  
- [Esportare i risultati della ricerca di Office 365 Security &amp; centro conformità](export-search-results.md)
    
- [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)
    

  
## <a name="more-information-about-content-search"></a>Ulteriori informazioni sulla ricerca contenuto

Vedere le sezioni seguenti per ulteriori informazioni sulle ricerche di contenuto.
  
[Limiti relativi alla ricerca di contenuto](#content-search-limits)
  
[Creazione di una query di ricerca](#building-a-search-query)
  
[Account di ricerca OneDrive](#searching-onedrive-accounts)
  
[Ricerca team di Microsoft e i gruppi di Office 365](#searching-microsoft-teams-and-office-365-groups)
  
[Ricerca delle cassette postali inattive](#searching-inactive-mailboxes)
  
[L'anteprima dei risultati della ricerca](#previewing-search-results)
  
[Elementi indicizzati parzialmente](#partially-indexed-items)
  
[Esportazione di dati da MyAnalytics e altre applicazioni di Office 365](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a>Limiti relativi alla ricerca di contenuto

- Per una descrizione dei limiti applicati alla funzionalità di ricerca del contenuto, vedere [limiti per la ricerca in Office 365 Security &amp; centro conformità](limits-for-content-search.md).
    
- Microsoft raccoglie informazioni sulle prestazioni per le ricerche contenuto eseguiti da tutte le organizzazioni di Office 365. Mentre la complessità della query di ricerca può influire tempi di ricerca, il fattore più importante che influisce sulla durata take ricerche è il numero di cassette postali ricercate. Anche se Microsoft non fornisce un contratto di servizio per tempi di ricerca, nella tabella seguente sono elencati i tempi di ricerca medio per una ricerca di contenuto in base al numero di cassette postali incluse nella ricerca.
    
|**Numero di cassette postali**|**Tempo medio di ricerca**|
|:-----|:-----|
|100  <br/> |30 secondi  <br/> |
|1,000  <br/> |45 secondi  <br/> |
|10,000  <br/> |4 minuti  <br/> |
|25.000  <br/> |10 minuti  <br/> |
|50.000  <br/> |20 minuti  <br/> |
|100,000  <br/> |25 minuti  <br/> |
  
### <a name="building-a-search-query"></a>Creazione di una query di ricerca

Per informazioni dettagliate sulla creazione di una query di ricerca e utilizzo di operatori booleani ricerca e le condizioni di ricerca dei tipi di informazioni riservate e del contenuto condiviso con utenti esterni all'organizzazione, vedere query con parole chiave [e i criteri di ricerca per la ricerca contenuto ](keyword-queries-and-search-conditions.md).
  
Tenere presenti i seguenti aspetti quando si utilizza l'elenco delle parole chiave per creare una query di ricerca.
  
- È necessario selezionare la casella di controllo **Mostra elenco di parole chiave** e quindi digitare ogni parola chiave in una riga separata per creare una query di ricerca in cui le parole chiave (o le frasi di parola chiave) in ogni riga sono connessi tramite l'operatore **OR** . Incolla un elenco delle parole chiave nella casella parole chiave appena o premere **INVIO** dopo avere digitato una parola chiave, non verrà connesso per l'operatore **OR** . Di seguito sono esempi non corretti e corretto dell'aggiunta di un elenco di parole chiave. 
    
    **Non corretto**
    
    ![Il modo non corretto per un elenco delle parole chiave in formato (incollando nell'elenco nella casella parole chiave)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Correggere**
    
    ![Il modo corretto per un elenco delle parole chiave in formato (selezionando la casella di controllo e quindi incollare elenco)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- È possibile anche preparare un elenco di parole chiave o frasi parole chiave in un file di Excel o un file di testo normale e quindi copiare e incollare l'elenco di voci all'elenco. A tale scopo, è necessario selezionare la casella di controllo **Mostra elenco di parole chiave** . Fare clic su prima riga nell'elenco delle parole chiave, quindi incollare l'elenco. Verrà incollato ciascuna riga del file di Excel o un testo per separare le righe nell'elenco delle parole chiave. 
    
- Dopo aver creato una query utilizzando l'elenco delle parole chiave, è opportuno verificare la sintassi di query di ricerca per effettuare query di ricerca sia quello desiderato. Nella query di ricerca che viene visualizzata in **Query** nel riquadro dei dettagli, le parole chiave sono separate dal testo **(c:s)**. Ciò indica che le parole chiave sono connessi tramite un operatore logico funzionalità analogo a operatore **OR** . Analogamente, se la query di ricerca include le condizioni, le parole chiave e le condizioni sono separate dal testo **(c:c)**. Ciò indica che le parole chiave connessi a condizioni con un operatore logico funzionalità analoga a **e** operatore. Di seguito è riportato un esempio di query di ricerca (visualizzati nel riquadro dei dettagli) risultante quando si utilizza l'elenco delle parole chiave e una condizione. 
    
    ![Esempio della query che viene creata quando si utilizza l'elenco delle parole chiave e una condizione](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Quando si esegue una ricerca di contenuto, Office 365 controllato automaticamente la query di ricerca per i caratteri non supportati e per gli operatori booleani che potrebbero non essere in maiuscolo. Caratteri non supportati sono spesso nascoste in genere causano un errore di ricerca o restituiscano risultati imprevisti. Per ulteriori informazioni sui caratteri non supportati che vengono controllati, vedere [verificare la query di ricerca del contenuto per gli errori](check-your-content-search-query-for-errors.md).
    
- Se si dispone di una query di ricerca che contiene le parole chiave per i caratteri non inglesi (ad esempio caratteri cinesi), è possibile fare clic su **Query language nazionali**![sull'icona di lingua/paese Query di ricerca del contenuto](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selezionare un valore del codice paese / lingua lingua per la ricerca. Si noti che la lingua/paese predefinito neutra. Come è possibile stabilire se è necessario modificare l'impostazione della lingua per una ricerca di contenuto? Se si è certi percorsi contenuti contengono caratteri non inglesi che si sta cercando, ma non restituisce alcun risultato della ricerca, la causa potrebbe essere l'impostazione della lingua. 
  
### <a name="searching-onedrive-accounts"></a>Account di ricerca OneDrive

- Per raccogliere un elenco degli URL per i siti di OneDrive nell'organizzazione, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Questo script in questo articolo consente di creare un file di testo contenente un elenco di tutti i siti di OneDrive. Per eseguire questo script, è necessario installare e utilizzare SharePoint Online Management Shell. Assicurarsi di aggiungere l'URL per il dominio dell'organizzazione sito personale per ogni sito OneDrive che si desidera eseguire la ricerca. Si tratta del dominio che contiene tutti i OneDrive; ad esempio `https://contoso-my.sharepoint.com`. Di seguito è riportato un esempio di un URL per il sito di OneDrive dell'utente: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    Nel caso di nome principale una persona (UPN) viene modificato l'URL relativo percorso OneDrive verrà modificata anche per incorporare l'UPN di nuovo. In questo caso, sarà necessario modificare una ricerca di contenuto mediante l'aggiunta nuovo URL dell'utente OneDrive e la rimozione del vecchio.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Ricerca team di Microsoft e i gruppi di Office 365

È possibile cercare la cassetta postale associata a un Team di Microsoft o un gruppo di Office 365. Poiché Microsoft Teams si basano sui gruppi di Office 365, la ricerca li è molto simile. In entrambi i casi, viene eseguita la ricerca solo la cassetta postale gruppo o un team; non vengono effettuate le cassette postali dei membri gruppo o un team. Per effettuare la ricerca, è necessario aggiungerli in modo specifico per la ricerca.
  
Tenere presenti i seguenti aspetti durante la ricerca di contenuto in Microsoft Teams e gruppi di Office 365.
  
- Per eseguire la ricerca per il contenuto disponibile in Microsoft Teams e gruppi di Office 365, è necessario specificare la cassetta postale e un sito di SharePoint associati a un team o un gruppo.
    
- Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà per un Team di Microsoft o un gruppo di Office 365. Si tratta di un modo efficace per ottenere l'URL per il sito di cui è associato un team o un gruppo. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Office 365 denominato Team leader Senior: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroup** , è necessario essere assegnato il ruolo di amministratore destinatari di Exchange Online o essere un membro del gruppo di ruoli che è assegnato il ruolo destinatari di sola visualizzazione. 
  
- Quando viene eseguita la ricerca cassetta postale dell'utente, qualsiasi Team di Microsoft o un gruppo di Office 365 che l'utente è un membro del non viene eseguita la ricerca. Analogamente, la ricerca un Team di Microsoft o un gruppo di Office 365, solo la cassetta postale di gruppo e gruppo sito specificato viene eseguita la ricerca; le cassette postali e OneDrive per gli account Business dei membri del gruppo non vengono effettuate a meno che non è in modo esplicito aggiungerli alla ricerca.
    
- Per ottenere un elenco di membri del Team di Microsoft o un gruppo di Office 365, è possibile visualizzare le proprietà nel **Home \> gruppi** pagina nell'interfaccia di amministrazione di Office 365. In alternativa, è possibile eseguire il seguente comando in Exchange Online PowerShell: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks** , è necessario essere assegnato il ruolo di amministratore destinatari di Exchange Online o essere un membro del gruppo di ruoli che è assegnato il ruolo destinatari di sola visualizzazione. 
  
- Le conversazioni che fanno parte di un canale Teams Microsoft sono archiviate nella cassetta postale di cui è associato il Team di Microsoft. Analogamente, i file che i membri del team di condividere un canale vengono archiviati nel sito di SharePoint del team. Di conseguenza, è necessario aggiungere la cassetta postale del Team di Microsoft e un sito di SharePoint come un percorso di contenuto per la ricerca di conversazioni e i file in un canale.
    
- In alternativa, le conversazioni che fanno parte dell'elenco di Chat di Microsoft Teams sono archiviate nella cassetta postale di Exchange Online degli utenti che partecipano alla chat. E i file che un utente condivide conversazioni Chat vengono archiviati in OneDrive per account aziendale dell'utente che condivide il file. Di conseguenza, è necessario aggiungere tutte le cassette postali degli utenti singoli OneDrive per gli account aziendali come i percorsi di contenuti per la ricerca di conversazioni e i file nell'elenco Chat.
    
    > [!NOTE]
    > Utenti di partecipare a conversazioni che fanno parte dell'elenco di Chat di Microsoft Teams devono avere una Exchange Online (basata su cloud) della cassetta postale in modo che per la ricerca di conversazioni chat. Ciò avviene perché le conversazioni che fanno parte dell'elenco di Chat vengono archiviate nelle cassette postali basate su cloud partecipanti alla chat. Se un partecipante di chat non è una cassetta postale di Exchange Online, non sarà in grado di cercare le conversazioni chat. Ad esempio, in una distribuzione ibrida di Exchange, gli utenti con una cassetta postale locale potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco di Chat di Microsoft Teams. Tuttavia in questo caso, il contenuto da queste conversazione non sono disponibili per le ricerche perché gli utenti non dispongono di cassette postali basate sul cloud. 
  
- Ogni canale Team di Microsoft o un team contiene un Wiki per la collaborazione e gestione delle note. Il contenuto Wiki viene automaticamente salvato in un file in formato con estensione mht. In questo file è archiviato nella raccolta documenti di team Wiki dati nel sito di SharePoint del team. È possibile utilizzare lo strumento di ricerca di contenuto per eseguire la ricerca Wiki specificando del sito del team SharePoint come posizione di contenuto per la ricerca. 
    
    > [!NOTE]
    > La funzionalità di ricerca Wiki per un Team di Microsoft o un canale (quando si esegue la ricerca del sito del team SharePoint) è stata rilasciata il 22 giugno 2017. Wiki pagine che sono state salvate o aggiornate in data o dopo che sono disponibili per eseguire la ricerca. Pagine Wiki ultimo salvataggio o aggiornato prima di tale data non sono disponibili per la ricerca. 
 
- Informazioni di riepilogo per le riunioni e le chiamate in un canale Teams Microsoft vengono inoltre archiviati nelle cassette postali degli utenti che si sono connessi in riunione o chiamata. Di conseguenza, che è possibile utilizzare ricerca contenuto per cercare i record di riepilogo. Informazioni di riepilogo includono: 
  - Data, ora di inizio, l'ora di fine e la durata di una riunione o una chiamata

  - La data e ora di ogni partecipante si è unito o la riunione o una chiamata a sinistra

  - Chiamate inviate alla segreteria telefonica

  - Chiamate senza risposte o senza risposta

  - Trasferimenti di chiamata, sono rappresentati come due chiamate distinte

  Si noti che possono richiedere fino a 8 ore per i record di riepilogo riunione e chiamata sia disponibile per essere eseguita la ricerca.

  Nei risultati della ricerca riepiloghi riunione vengono identificati come **riunione** nel **campo tipo**. riepiloghi di chiamata vengono identificati come **chiamare**. Inoltre, le conversazioni che fanno parte di una chat di canali e 1xN team vengono identificate come **messaggistica immediata** nel campo **tipo** .
  
  ![Le riunioni di team, le chiamate e 1xN chat vengono identificate nel campo tipo](media/O365-ContentSearch-Teams-MessageKind.png)

- Eseguire la ricerca in modo specifico per il contenuto Teams Microsoft, è possibile utilizzare la proprietà di posta elettronica di **tipo** o la condizione di ricerca del **tipo di messaggio** . 
  - Per utilizzare la proprietà **Kind** come parte della query di ricerca parola chiave, nella casella **parole chiave** di una query di ricerca, digitare `kind:microsoftteams`.

    ![Utilizzare il tipo: microsoftteams nella casella parole chiave](media/O365-ContentSearch-Teams-Keywords.png)
  
  - Per utilizzare una condizione di ricerca, aggiungere la condizione di **tipo di messaggio** e utilizzare il valore `microsoftteams`. 

    ![Utilizzare la condizione di tipo di messaggio con il valore microsoftteams.](media/O365-ContentSearch-Teams-MessageKindCondition.png)

Notare che le condizioni sono connessi logicamente per le query con parole chiave per l'operatore **AND** . Ciò significa che un elemento deve corrispondere sia le query con parole chiave e la condizione di ricerca da restituire nei risultati della ricerca. Per ulteriori informazioni, vedere la sezione "Linee guida per l'utilizzo di condizioni" in [query con parole chiave e condizioni di ricerca per la ricerca del contenuto.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)

  
### <a name="searching-inactive-mailboxes"></a>Ricerca delle cassette postali inattive

È possibile eseguire la ricerca delle cassette postali inattive in una ricerca di contenuto. Per ottenere un elenco delle cassette postali inattive all'interno dell'organizzazione, eseguire il comando `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell. In alternativa, è possibile passare alla **governance dati** \> **conservazione** in sicurezza &amp; centro conformità e quindi fare clic su **ulteriori**![puntini di sospensione barra di spostamento](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **delle cassette postali inattive**.
  
Ecco alcuni aspetti da tenere presenti durante la ricerca delle cassette postali inattive.
  
- Se una ricerca di contenuto include una cassetta postale utente e cassetta postale viene quindi rese inattive, ricerca contenuto continua per la ricerca di cassette postali inattive quando si esegue nuovamente la ricerca dopo diventa inattivo.
    
- In alcuni casi, un utente può disporre di una cassetta postale attiva e una cassetta postale inattiva che hanno lo stesso indirizzo SMTP. In questo caso, verrà cercata solo la cassetta postale specifica che si seleziona un percorso per una ricerca di contenuto. In altre parole, se si aggiunge una ricerca cassetta postale dell'utente, non è possibile presupporre che verranno eseguita la ricerca cassette postali attive e inattive, solo la cassetta postale aggiunto in modo esplicito per la ricerca verrà eseguita la ricerca.
    
- È consigliabile evitare di dover delle cassette postali attivi e inattive cassette postali con lo stesso indirizzo SMTP. Se si desidera riutilizzare l'indirizzo SMTP attualmente assegnato a una cassetta postale inattiva, è consigliabile ripristinare la cassetta postale inattiva o ripristinare il contenuto di una cassetta postale inattiva a una cassetta postale attiva (o l'archivio di una cassetta postale attiva) e quindi eliminare il cassette postali inattive. Per ulteriori informazioni, vedere uno degli argomenti seguenti:
    
  - [Ripristinare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md)
    
  - [Ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md)
    
  - [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>L'anteprima dei risultati della ricerca

È possibile visualizzare un'anteprima di tipi di file supportati nel riquadro di anteprima. Se non è supportato un tipo di file, è necessario scaricare una copia del file nel computer locale per visualizzarlo. I seguenti tipi di file supportati e possono essere visualizzati in anteprima nel riquadro risultati della ricerca.
  
- file con estensione txt,. HTML, MHTML
    
- eml
    
- file con estensione doc, docx, con estensione docm
    
- file con estensione pptx, pptm
    
- .pdf
    
Inoltre, sono supportati i seguenti tipi di file contenitore. È possibile visualizzare l'elenco dei file nel contenitore nel riquadro di anteprima.
  
- .zip
    
- con estensione gzip
    
### <a name="partially-indexed-items"></a>Elementi indicizzati parzialmente

- Come indicati in precedenza, parzialmente indicizzati gli elementi nelle cassette postali vengono inclusi nei risultati della ricerca stimati; elementi indicizzati parzialmente di SharePoint e OneDrive non vengono inclusi nei risultati della ricerca stimati. 
    
- Se un oggetto parzialmente elemento corrisponde a eseguire una query di ricerca (perché altre proprietà di un documento o messaggio soddisfa i criteri di ricerca), non sarà incluso il numero stimato di elementi indicizzati. Se un elemento viene escluso per i criteri di ricerca, non anche sarà incluso il numero stimato di elementi indicizzati parzialmente parzialmente. Per ulteriori informazioni, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto in Office 365](partially-indexed-items-in-content-search.md).
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a>Esportazione di dati da MyAnalytics e altre applicazioni di Office 365

- MyAnalytics (ad esempio informazioni su come gli utenti il tempo dedicato alle basato su dati di posta elettronica e calendario nella cassetta postale) e dati da altre applicazioni di Office 365 vengono salvata in un percorso nascosto (in un sottoalbero non IPM) nella cassetta postale basata sul cloud dell'utente. Dopo avere eseguito una ricerca di contenuti, dati non sono incluso nei risultati della ricerca stimati, le statistiche delle query, e non è disponibile per l'anteprima. Tuttavia verranno esportati dati quando si esportano i risultati della ricerca.
    
- I dati MyAnalytics e i dati da altre applicazioni di Office 365 viene esportato in una cartella denominata "Altri dati di Office 365". Questa cartella include le sottocartelle di ogni utente.
  