---
title: Gestire le richieste di oggetto dati PILR con lo strumento maiuscole DSR in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: I PILR consente UE cittadini (denominati persone interessate) diritti specifici per i dati personali. tali diritti includono ottenere una copia di esso, che richiede modifiche apportate all'oggetto, se si restringe l'elaborazione di esso, comporta l'eliminazione o ricezione in formato elettronico. Una richiesta da un dati statistici take formale un'azione dei dati personali viene chiamata una richiesta di oggetto dati o la modalità DSR. È possibile utilizzare la modalità DSR casi in Office 365 Security &amp; centro conformità per gestire indagini DSR dell'organizzazione.
ms.openlocfilehash: c8edee8d377865d46662ebbd7f18a5a6f3015192
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530898"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-office-365-security-amp-compliance-center"></a>Gestire le richieste di oggetto dati PILR con lo strumento maiuscole DSR in Office 365 Security &amp; centro conformità

L'Unione europea generale dati protezione norme (PILR) è sulla protezione e attivazione di diritti di privacy dei singoli all'interno dell'Unione europea (UE). I singoli utenti consente PILR nell'Unione europea, noto come oggetti dati, il diritto di accedere, recuperare, correggere, cancellare o limitare l'elaborazione dei dati personali. In PILR, dati personali: tutte le informazioni relative a una persona fisica identificata o identificabile. Una richiesta formale da una persona alla propria organizzazione per eseguire un'azione dei dati personali viene chiamata una richiesta di oggetto dati o la modalità DSR. Per informazioni dettagliate su come rispondere a dettagliata per i dati in Office 365, vedere [Guida richiedere dati soggetto di Office 365](https://go.microsoft.com/fwlink/?linkid=871169 ).
  
Per gestire le indagini in risposta a una DSR inviate da una persona all'interno dell'organizzazione, è possibile utilizzare lo strumento maiuscole DSR in Office 365 Security &amp; centro conformità per trovare contenuto archiviato in:
  
- Qualsiasi cassetta postale utente nell'organizzazione. Sono incluse Skype per Business conversazioni e le chat dirette Teams Microsoft
    
- Tutte le cassette postali associate a un gruppo di Office 365 e tutte le cassette postali team Teams Microsoft
    
- Tutti i siti di SharePoint Online e gli account di OneDrive for Business nell'organizzazione
    
- Tutti i siti di team e siti di Office 365 gruppo all'interno dell'organizzazione
    
- Tutte le cartelle pubbliche in Exchange Online
    
Utilizzando lo strumento maiuscole DSR consente di:
  
- Creare un caso distinto per ogni indagine DSR.
    
- Controllare quali utenti hanno accesso a caso DSR aggiungendo persone come membri del caso; solo i membri possono accedere il caso e viene visualizzato solo i casi nell'elenco dei casi nella pagina **dei casi la modalità DSR** nella protezione &amp; centro conformità. Inoltre, è possibile assegnare autorizzazioni diverse a diversi membri dello stesso caso. Ad esempio, è possibile consentire alcuni membri visualizzare i risultati di ricerca e case solo e consentire ad altri membri creare ricerche ed esportare i risultati della ricerca. 
    
- Utilizzare l'oggetto incorporato per cercare per tutto il contenuto creati o caricati da un oggetto dati specifico.
    
- Se lo si desidera modificare la query di ricerca predefinita ed eseguire nuovamente la ricerca per restringere i risultati della ricerca.
    
- Aggiungere ulteriori ricerche del contenuto associate al caso DSR. Esse comprendono la creazione di ricerche restituiscono elementi indicizzati parzialmente e i log generati dal sistema da Analitica personali e il servizio di Roaming di Office.
    
- Esportare i dati in risposta a un accesso DSR o richiesta di esportazione.
    
- Eliminare i casi durante il processo di analisi DSR è completo. verranno rimosse tutte le ricerche e i processi associati al caso l'esportazione.
    
Di seguito è il processo di alto livello per l'utilizzo dello strumento di maiuscole DSR per gestire indagini DSR:
  
[Passaggio 1: Assegnare autorizzazioni di eDiscovery a potenziali membri del caso](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Passaggio 2: Creare un caso DSR e aggiungere membri](#step-2-create-a-dsr-case-and-add-members)

[Passaggio 3: Eseguire la query di ricerca](#step-3-run-the-search-query)

[Passaggio 4: Esportare i dati](#step-4-export-the-data)

[(Facoltativo) Passaggio 5: Modificare la query di ricerca predefinita](#optional-step-5-revise-the-built-in-search-query)

[Ulteriori informazioni sull'utilizzo dello strumento di maiuscole DSR](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> Gli strumenti consentono di eseguire l'accesso a DSR o richieste di esportazione per consentire loro di utilizzare la ricerca incorporata ed esportare funzionalità disponibile nello strumento di maiuscole DSR admins. Lo strumento consente di semplificare un metodo sforzo per esportare i dati rilevanti a una richiesta DSR inviata da un oggetto di dati. Tuttavia, è importante tenere presente che i risultati della ricerca possono variare in base al dati argomento o le azioni di amministrazione eseguite che possono influire sulle o meno un elemento potrebbe essere considerato "i dati personali" per scopi di esportazione. Ad esempio, se l'oggetto dati è l'ultima persona che consente di modificare un file è stato creato, il file potrebbe non verranno restituito nei risultati della ricerca. Analogamente, un amministratore può esportare i dati senza includere elementi indicizzati parzialmente o tutte le versioni dei documenti di SharePoint. Di conseguenza, gli strumenti forniti in grado di semplificare l'accesso e l'esportazione le richieste di dati. Tuttavia, i risultati sono soggetti a specifici di amministrazione e dati soggetto gli scenari di utilizzo. 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Passaggio 1: Assegnare autorizzazioni di eDiscovery a potenziali membri del caso

Per impostazione predefinita, un amministratore globale di Office 365 può accedere allo strumento DSR maiuscole nella protezione &amp; centro conformità. Per progettare, gli altri utenti, ad esempio un responsabile della privacy di dati, un responsabile delle risorse umane, o altre persone coinvolte nella indagini DSR non dispongono dell'accesso allo strumento maiuscole DSR e saranno necessario disporre delle autorizzazioni appropriate per accedere allo strumento. Il modo più semplice per eseguire questa operazione viene per passare alla pagina **autorizzazioni** di sicurezza &amp; centro conformità e aggiungere utenti al gruppo di ruoli di gestione di eDiscovery. Si noti che è anche necessario assegnare le autorizzazioni in modo che è possibile aggiungerli come membri del caso DSR creato nel passaggio 2. 
  
Per istruzioni dettagliate, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).
  
> [!NOTE]
> Per impostazione predefinita, un amministratore globale di Office 365 (o gli altri membri del gruppo di ruoli Gestione organizzazione in sicurezza &amp; centro conformità non dispone delle autorizzazioni necessarie per esportare i risultati di ricerca del contenuto (in questo articolo, vedere il passaggio 4). Per risolvere questo problema, gli amministratori possono aggiungere se stessi come membro del gruppo di ruoli di gestione di eDiscovery. 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a>Passaggio 2: Creare un caso DSR e aggiungere membri

Il passaggio successivo consiste nel creare un caso DSR. Quando si crea un caso, è possibile scegliere di avviare la ricerca incorporata o è possibile creare il caso senza avviare la ricerca. La procedura seguente viene richiesto di creare il caso senza avviare la ricerca e quindi viene illustrato come aggiungere membri al caso.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) ed effettuare l'accesso a Office 365 utilizzando l'account di lavoro o della scuola. 
    
2. In sicurezza &amp; centro conformità, fare clic sulla **riservatezza dei dati** \> **dati soggetto richieste**e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **DSR nuovi case**.
    
3. Nella pagina **Nuovo DSR case** comparsa assegnare il caso un nome, digitare una descrizione facoltativa e quindi fare clic su **Avanti**. Si noti che il nome del caso deve essere univoco all'interno dell'organizzazione.
    
    > [!TIP]
    > È possibile aggiungere il nome della persona che ha inviato la richiesta DSR che sta esaminando il nome e/o descrizione del nuovo caso. Si noti che solo i membri di questo case (e agli amministratori di eDiscovery) saranno in grado di visualizzare il caso nell'elenco dei casi nella pagina **dati soggetto richieste** . 
  
4. Nella pagina **Dettagli della richiesta** , in **oggetto dati (la persona che ha presentata la richiesta)**, selezionare la persona che si desidera trovare ed esportare i dati e quindi fare clic su **Avanti**.
    
5. Nella pagina **verificare le impostazioni di maiuscole** è possibile modificare il nome del caso e la descrizione e selezionare un argomento dati diversi. In caso contrario, semplicemente fare clic su **Salva**.
    
    Viene visualizzata una pagina di conferma che è stato creato il nuovo caso DSR.
    
    ![Avviare la ricerca o semplicemente chiudere la pagina nuovo DSR maiuscole](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    A questo punto è possibile effettuare una delle seguenti operazioni:
    
    r. facendo clic su **Mostra me i risultati di ricerca** inizia la ricerca. Questa è la selezione predefinita. Servizio di ricerca predefinita che verrà eseguita quando si seleziona questa opzione e i risultati vengono restituiti sono descritto nel passaggio 3.
    
    b. fare clic su **Finish** chiude il nuovo caso DSR senza avviare la ricerca incorporata. Quando si seleziona questa opzione, il nuovo caso DSR viene visualizzato nella pagina **dati soggetto richieste** .
    
6. In modo che è possibile visualizzare il nuovo caso DSR e aggiungere membri, fare clic su **Fine** . 
    
7. Nella pagina **dati soggetto richieste** fare clic sul nome del caso DSR appena creata. 
    
8. Nella pagina **Gestisci in questo caso** comparsa **Gestisci membri**, fare clic su **Aggiungi**. 
    
    In **utenti**, viene visualizzato un elenco di persone che sono state assegnate le autorizzazioni appropriate eDiscovery. Si noti che le persone che si assegnate autorizzazioni di eDiscovery per nel passaggio 1 verranno visualizzate nell'elenco. 
    
9. Scegliere gli utenti aggiungere come membri del caso DSR, fare clic su **Aggiungi**e quindi salvare le modifiche.
    
    Si noti che è inoltre possibile aggiungere gruppi di ruoli come membri del case DSR facendo clic su **Aggiungi** nel gruppo **Gestisci gruppi di ruoli**. 
    
## <a name="step-3-run-the-search-query"></a>Passaggio 3: Eseguire la query di ricerca

Dopo aver creato un caso DSR e aggiungere membri, il passaggio successivo consiste nell'eseguire la ricerca incorporata che è associato al caso. Questa query di ricerca predefinito esegue le operazioni seguenti:
  
- Esegue la ricerca tutte le cassette postali nell'organizzazione per tutti gli elementi di posta elettronica inviati o ricevuti in base all'oggetto dati. Questa operazione viene eseguita tramite la proprietà di posta elettronica *ai partecipanti* , che consente di cercare l'oggetto dati in tutti i campi di persone in un messaggio di posta elettronica. Questa proprietà restituisce gli elementi in cui la persona si in **da**, **a**, **CC**e **Ccn** . Cartelle pubbliche in Exchange Online vengono cercate anche per i messaggi inviati o ricevuti in base all'oggetto dati. 
    
- Esegue la ricerca tutti i siti all'interno dell'organizzazione per documenti ed elementi creati o caricati dall'oggetto dati. Questa operazione viene eseguita tramite le proprietà seguenti:
    
  - La proprietà *Author* restituisce gli elementi in cui l'oggetto dati è elencato nel campo autore nei documenti di Office. Questo valore viene mantenuto, anche se il documento viene copiato e caricato da un utente. 
    
  - La proprietà *CreatedBy* restituisce gli elementi che sono stati creati o caricati in base all'oggetto dati. 
    
Ecco aspetto le query con parole chiave per la ricerca incorporata che viene creata automaticamente quando si crea un caso DSR.
  
```
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

Ad esempio, se il nome del soggetto dati Ina Leonte, la query con parole chiave potrebbe essere simile al seguente:
  
```
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 **Per eseguire la ricerca di un caso DSR incorporata:**
  
1. In sicurezza &amp; centro conformità, fare clic sulla **riservatezza dei dati** \> **dati soggetto richieste**e quindi fare clic su **Apri** accanto al caso DSR creato nel passaggio 2. 
    
    Fare clic sulla scheda **ricerca** nella parte superiore della pagina e quindi fare clic sulla casella accanto a Cerca incorporato che è stato creato quando è stato creato il nuovo caso DSR. Si noti che la ricerca ha lo stesso nome di case DSR. 
    
2. Nella pagina ricerca tendina fare clic su **Apri query**.
    
    Quando si apre la query, la ricerca sia stata avviata e verrà completata in corso. 
    
3. Una volta completata la ricerca, fare clic su **Anteprima risultati** per visualizzare in anteprima i risultati della ricerca. Per ulteriori informazioni, vedere [Preview search results](content-search.md#preview-search-results).
    
    > [!TIP]
    > È inoltre possibile visualizzare le statistiche di query di ricerca per visualizzare il numero di cassette postali e gli elementi di siti che vengono restituiti dalla ricerca e i percorsi contenuti principali che contengono gli elementi che corrispondono alla query di ricerca. Per ulteriori informazioni, vedere [visualizzare informazioni e statistiche sulla ricerca](content-search.md#view-information-and-statistics-about-a-search). 
  
Si modifica la query di ricerca predefinita, modificare i percorsi di contenuti che vengono eseguita la ricerca e quindi eseguire di nuovo la ricerca. Per ulteriori informazioni, vedere [il passaggio 5](#optional-step-5-revise-the-built-in-search-query) . 
  
## <a name="step-4-export-the-data"></a>Passaggio 4: Esportare i dati

Dopo aver eseguito la ricerca incorporata, è possibile esportare i risultati della ricerca. In alternativa, prima di esportare i dati, è possibile modificare la query per ridurre il numero di risultati di ricerca. Per ulteriori informazioni sulla limitazione dei risultati di ricerca, vedere il passaggio 5.
  
Quando si Esporta risultati della ricerca, gli elementi della cassetta postale possono essere scaricati nei file PST o come singoli messaggi. Quando si esporta il contenuto di SharePoint e OneDrive account, vengono esportate le copie dei documenti di Office nativi e altri documenti. Un file di risultati che contiene informazioni su tutti gli elementi esportati inoltre viene fornito con i risultati della ricerca. Per ulteriori informazioni sull'esportazione, vedere [esportare contenuto di una ricerca di Office 365 protezione &amp; centro conformità](export-search-results.md).
  
> [!NOTE]
> Per impostazione predefinita, un amministratore globale di Office 365 (o gli altri membri del gruppo di ruoli Gestione organizzazione in sicurezza &amp; centro conformità) non dispone delle autorizzazioni necessarie per esportare i risultati della ricerca del contenuto. Per risolvere questo problema, gli amministratori possono aggiungere se stessi come membro del gruppo di ruoli di gestione di eDiscovery. 
  
Il computer utilizzato per esportare i dati deve soddisfare i requisiti di sistema seguenti:
  
- Windows 7 a 32 o 64 bit e versioni successive
    
- Microsoft .NET Framework 4.7
    
- Browser supportato:
    
  - Microsoft Edge
    
    Oppure
    
  - Microsoft Internet Explorer 10 e versioni successive
    
    > [!NOTE]
    > Microsoft non produce delle estensioni di terze parti o componenti aggiuntivi per le applicazioni ClickOnce. Esportazione dei dati di utilizzo di un browser non supportato con le estensioni di terze parti o i componenti aggiuntivi non è supportato. 
  
 **Per esportare i dati di ricerca predefinita in un caso DSR:**
  
1. In sicurezza &amp; centro conformità, fare clic sulla **riservatezza dei dati** \> **dati soggetto richieste**e quindi fare clic su **Apri** accanto al caso DSR che si desidera esportare i dati. 
    
2. Fare clic sulla scheda **ricerca** nella parte superiore della pagina e quindi fare clic sulla casella accanto a Cerca incorporato che è stato creato durante la creazione il caso DSR. Oppure fare clic su Cerca un altro per esportare i dati da che la ricerca. 
    
3. Nella pagina ricerca tendina fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **ulteriori**e quindi seleziona **esportare i risultati** dall'elenco a discesa. 
    
4. Nella pagina **esportazione dei risultati** selezionare le seguenti opzioni consigliate per le richieste di esportazione DSR. 
    
    ![Configurare le impostazioni di esportazione](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    r. in **Opzioni di Output**, selezionare l'opzione prima ( **tutti gli elementi, ad eccezione di quelli che sono quelle che dispongono di un formato non riconosciuto, vengono crittografate o non indicizzate per altri motivi**) per esportare solo gli elementi indicizzati. Il motivo che non si desidera esportare elementi parzialmente indicizzati da ricerca incorporate è che verranno esportati elementi parzialmente indicizzati da altri utenti. Per esportare solo gli elementi parzialmente indicizzati che la persona, è consigliabile creare una ricerca distinto. Per ulteriori informazioni, vedere [esportazione parzialmente voci indicizzate](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems) nella sezione "Ulteriori informazioni sull'utilizzo dello strumento di maiuscole DSR".
    
    b. in **contenuto di Exchange esportare**, selezionare la terza opzione, **i file di un file PST contenente tutti i messaggi in una singola cartella**. Poiché alcuni dei risultati possono essere gli elementi che ha dato origine nella cassetta postale di un altro utente, questa opzione solo elenchi l'elemento in una singola cartella senza che indica la cassetta postale effettiva ed è l'opzione più appropriata da utilizzare quando si duplica deprovisioning dei risultati come consigliato nell'elemento successivo . Questa opzione consente inoltre l'oggetto dati esaminare gli elementi in ordine cronologico (elementi vengono ordinati per data di invio) senza dover passare la struttura di cartelle delle cassette postali originale per ogni elemento.
    
    c. selezionare **Abilita deduplicazione** opzione per esclude i messaggi di posta elettronica duplicati. Questa opzione è consigliata perché la ricerca incorporata ricerche in tutte le cassette postali nell'organizzazione. In modo che se più copie dello stesso messaggio presenti nelle cassette postali in cui sono state ricercate, questa opzione indica che verrà esportata solo una copia di un messaggio. Questa opzione, tra i messaggi esportazione in uno dei risultati di file PST in una singola cartella in un'esperienza utente ottimale per la modalità DSR esporterà richieste. Si noti che il report di esportazione Results.csv verranno elencati tutti i percorsi in cui sono stati trovati messaggi duplicati.
    
    Facoltativamente, è possibile selezionare l'opzione **Includi versioni per i documenti di SharePoint** per esportare tutte le versioni dei documenti di SharePoint e OneDrive. È necessario che il controllo delle versioni è attivato per le raccolte documenti. Questa opzione consente di garantire che vengono esportati tutti i dati pertinenti.
    
5. Dopo aver scelto le impostazioni di esportazione, fare clic su **Esporta**.
    
    I risultati della ricerca sono pronti per il download, il che significa che viene caricati all'area di archiviazione Azure per l'organizzazione nel cloud Microsoft. I passaggi successivi mostrano come scaricare questi dati al computer locale.
    
6. Fare clic sulla scheda **Esporta** per visualizzare il processo di esportazione che appena creata. Si noti che i processi di esportazione avere lo stesso nome corrispondente esegue una ricerca con **Export** aggiunto alla fine del nome di ricerca. 
    
7. Fare clic sul processo di esportazione appena creata per visualizzare la pagina di comparsa di esportazione. In questa pagina vengono visualizzate informazioni sulla ricerca, ad esempio le dimensioni e il numero totale di elementi da esportare e la percentuale di elementi che sono stati trasferiti a un'area di archiviazione Azure. Fare clic su **Aggiorna** per aggiornare le informazioni sullo stato per il caricamento. 
    
8. In **Esporta chiave**, fare clic su **Copia negli Appunti**. Utilizzare questa chiave nel passaggio 11 per scaricare i risultati della ricerca.
    
9. Fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **scaricare i risultati** nella parte superiore della pagina esportazione comparsa. 
    
10. Nella finestra popup nella parte inferiore della pagina, fare clic su **Apri** per aprire **Microsoft Office 365 eDiscovery dello strumento di esportazione**. Verrà installato la prima volta che si scarica i risultati della ricerca **eDiscovery dello strumento di esportazione** . 
    
11. In **eDiscovery dello strumento di esportazione**, incollare la chiave di esportazione che è stato copiato nel passaggio 8 nella casella appropriata.
    
12. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare i file dei risultati della ricerca. 
    
    > [!NOTE]
    > A causa della quantità elevata di attività del disco (letture e scritture), è necessario scaricare i risultati della ricerca in un'unità disco locale, non scaricare tali un'unità di rete o altro percorso di rete. 
  
13. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    **EDiscovery dello strumento di esportazione** viene visualizzato il processo di esportazione, con una stima del numero e dimensione degli altri download di informazioni sullo stato. Una volta completato il processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati. Per ulteriori informazioni sui rapporti disponibili quando si scarica i risultati di ricerca del contenuto, vedere la sezione [informazioni](export-search-results.md#more-information) di "risultati di ricerca di contenuto di esportazione della protezione di Office 365 &amp; centro conformità". 
    
Dopo che i dati vengono esportati, i risultati di ricerca e l'esportazione dei rapporti si trova in una cartella con lo stesso nome di case DSR. I file PST che contengono elementi delle cassette postali si trovano in una sottocartella denominata **Exchange**. Documenti e altri elementi di siti si trovano in una sottocartella denominata **SharePoint**. 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a>(Facoltativo) Passaggio 5: Modificare la query di ricerca predefinita

Dopo aver eseguito la ricerca incorporata, è possibile modificare in modo da limitare il numero per restituire un numero di risultati di ricerca. Tale scopo, si può aggiungere condizioni alla query. Una condizione è connesso logicamente per le query con parole chiave per l'operatore **AND** . È quindi opportuno restituiti nei risultati della ricerca, gli elementi devono soddisfare sia le query con parole chiave e tutte le condizioni si aggiungono. Si tratta come condizioni consentono di limitare i risultati. Se si aggiungono due o più condizioni univoche per una query di ricerca (condizioni che specificano proprietà diverse), le condizioni logicamente sono connessi tramite l'operatore **AND** . Pertanto, vengono restituiti solo gli elementi che soddisfano tutte le condizioni (oltre la query con parole chiave). Se si aggiungono più valori, separati da virgole o punti e virgola, di una singola condizione, questi valori sono connessi tramite l'operatore **OR** . Ciò significa che vengono restituiti gli elementi che contengono uno dei valori specificati per la proprietà nella condizione. 
  
Di seguito sono riportati alcuni esempi delle condizioni che è possibile aggiungere a query di ricerca predefinita di un caso DSR. Parentesi viene visualizzato il nome della proprietà effettiva utilizzata nella query di ricerca.
  
- **Il tipo di file ( `filetype`)** -specifica l'estensione di un documento o un file. Utilizzare questa condizione di ricerca di documenti e i file creati per specifiche applicazioni di Office, come Word, Excel e OneNote. 
    
- **Tipo di messaggio ( `kind`)** -specifica il tipo di elemento di posta elettronica da cercare. Ad esempio, è possibile utilizzare la sintassi `kind:email OR kind:im` per restituire solo i messaggi di posta elettronica e Skype per Business conversazioni o uno chat in Microsoft Teams. 
    
- **Tag di conformità (`compliancetag`)** -consente di specificare un'etichetta assegnata a un messaggio di posta elettronica o di un documento. Questa condizione verrà restituiti gli elementi che sono classificati con un'etichetta specifica. Le etichette vengono utilizzate per classificare i documenti per la governance di dati e posta elettronica e applicare le regole di conservazione in base alla classificazione definita per l'etichetta. Si tratta di una condizione utile per indagini DSR quanto l'organizzazione potrebbe utilizzando le etichette per classificare il contenuto relativo alla privacy di dati o che contiene i dati personali o informazioni riservate. Per il valore di questa condizione, utilizzare il nome dell'etichetta completa o la prima parte del nome di etichetta con un carattere jolly. Per ulteriori informazioni, vedere [Overview of etichette in Office 365](labels.md).
    
Per un elenco e una descrizione di tutte le condizioni disponibili nello strumento di maiuscole DSR, vedere [criteri di ricerca](keyword-queries-and-search-conditions.md#search-conditions) nell'articolo "query con parole chiave e le condizioni di ricerca per la ricerca di contenuto". 
  
### <a name="changing-the-content-locations-that-are-searched"></a>Modifica della posizione del contenuto che vengono eseguita la ricerca

Oltre a revisione ricerca incorporate per un caso DSR, è inoltre possibile modificare i percorsi di contenuti che vengono eseguita la ricerca. Come indicato in precedenza, la ricerca incorporata ricerca alle cassette postali e i siti dell'organizzazione e le cartelle pubbliche di Exchange Online. Ad esempio, è possibile limitare l'ambito di ricerca per eseguire la ricerca solo l'oggetto dati delle cassette postali e account di OneDrive e selezionata siti di SharePoint. Se si esegue una ricerca di siti specifici, è necessario aggiungere ogni sito in cui si desidera eseguire la ricerca.
  
Per modificare i percorsi di contenuti per la ricerca:
  
1. Aprire la ricerca incorporata che si desidera modificare i percorsi di contenuti per.
    
2. Nella query di ricerca in **percorsi**fare clic su **Modifica** accanto all'opzione **percorsi specifici** . 
    
    ![Fare clic su Modifica per modificare le posizioni del contenuto delle query di ricerca predefinita](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    Verrà visualizzata la pagina di comparsa **Modifica percorsi** . Ecco una descrizione dei percorsi contenuti in ricerca incorporate e alcune informazioni su come modificare i percorsi che vengono eseguita la ricerca. 
    
    ![Modificare le posizioni comparsa pagina](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    r. l'interruttore in **Seleziona tutto** nella cassetta postale nella parte superiore della pagina comparsa è selezionata, che indica che vengono eseguita la ricerca di tutte le cassette postali. Per limitare l'ambito della ricerca, fare clic su Attiva o disattiva per annullare la selezione, quindi fare clic su **Scegli utenti, gruppi o team** e scegliere cassette postali specifiche per la ricerca.
    
    b. l'interruttore in **Seleziona tutto** nell'area siti al centro della pagina comparsa è selezionata, che indica che tutti i siti vengono eseguita la ricerca. Per restringere la ricerca per siti selezionati, si potrebbe deselezionare l'opzione attiva o disattiva e quindi **Scegliere siti**. È necessario aggiungere ogni sito specifico che si desidera eseguire la ricerca, inclusi account OneDrive della persona.
    
    c. attiva o disattiva nella sezione delle cartelle pubbliche di Exchange è selezionata, vale a dire che tutte le cartelle pubbliche di Exchange vengono eseguita la ricerca. Si noti che è possibile cercare solo tutte le cartelle pubbliche di Exchange o nessuno di essi. Non è possibile scegliere quelle specifiche per la ricerca.
    
3. Se si modificano i percorsi contenuti della funzionalità di ricerca predefinita, fare clic su **salvare &amp; eseguire** iniziare nuovamente la ricerca. 
  
## <a name="more-information-about-using-the-dsr-case-tool"></a>Ulteriori informazioni sull'utilizzo dello strumento di maiuscole DSR

Nelle sezioni seguenti contengono ulteriori informazioni sull'utilizzo dello strumento di maiuscole DSR per rispondere alle richieste di esportazione DSR.
  
[Esportazione di dati da MyAnalytics e il servizio di Roaming di Office](#exporting-data-from-myanalytics-and-the-office-roaming-service)

[Esportazione di elementi indicizzati parzialmente](#exporting-partially-indexed-items)

[Ricerca e l'esportazione di dati da Microsoft Teams e gruppi di Office 365](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[Ricerca di cartelle pubbliche di Exchange](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-myanalytics-and-the-office-roaming-service"></a>Esportazione di dati da MyAnalytics e il servizio di Roaming di Office

È possibile utilizzare lo strumento maiuscole DSR per cercare ed esportare i dati di utilizzo viene generati da MyAnalytics e il servizio di Roaming di Office. Ecco una descrizione delle operazioni eseguite tali servizi:
  
- **MyAnalytics** - fornisce agli utenti informazioni su come utilizzano il tempo dedicato in base ai dati di posta elettronica e calendario nella cassetta postale. Tutte le informazioni MyAnalytics derivano dalle intestazioni di posta elettronica e riunione nella cassetta postale dell'utente. Gli utenti che sono assegnati a una licenza MyAnalytics possono accedere a Office 365 e passare al dashboard MyAnalytics per visualizzare informazioni su come utilizzano il tempo dedicato. (Gli utenti possono schermate di queste informazioni in risposta alla richiesta di accesso DSR). Ricerca incorporate in caso DSR esportano i dati che viene utilizzati per generare MyAnalytics informativa. 
    
- **Servizio di Roaming di office** - Roaming è un servizio che sono archiviate le impostazioni relative a Office, ad esempio tema di Office, dizionario personalizzato, le impostazioni della lingua, modalità di sviluppo e correzione automatica. 
    
I dati da MyAnalytics e il servizio Office Roaming viene archiviati nella cassetta postale dell'oggetto dati contenuti nelle cartelle nascoste presente in una messaggio non interpersonali () sottostruttura di cassette postali di Exchange Online. In questo modo che i dati viene nascosta dalla visualizzazione dell'utente quando si utilizzano Outlook o altri client di posta elettronica per accedere alla cassetta postale. Per ulteriori informazioni sulle cartelle nascoste, vedere [Cartelle nascoste MAPI](https://go.microsoft.com/fwlink/?linkid=872758).
  
È possibile creare una ricerca di contenuto separata (e associarlo a un caso DSR) che restituisce il MyAnalytics e i dati di utilizzo del servizio di Roaming Office nella cassetta postale di oggetti dei dati. Questi dati non sono incluso nelle statistiche di ricerca e non sono disponibile per l'anteprima. Ma è possibile esportare il certificato e quindi assegnare l'oggetto dati in risposta alla richiesta di esportazione DSR.
  
Quando si esportano dati da MyAnalytics e il servizio di Roaming di Office, vengono salvati i dati in una cartella separata per ogni applicazione che si trova nella cartella **ApplicationDataRoot** , ovvero in una cartella in cui è nome e indirizzo di posta elettronica della persona. Questi dati viene esportati come file JSON, ovvero i file di testo leggibile simili al file XML o TXT, che vengono associati ai messaggi di posta elettronica. Attualmente, queste cartelle sono denominate con un identificatore univoco globale (GUID) assegnato al MyAnalytics e il servizio Office Roaming sono elencati nella tabella seguente. Nelle versioni future dello strumento maiuscole DSR, il GUID verrà sostituito con il nome dell'applicazione effettivo. 
  
|**Applicazione**|**Nome GUID/cartella**|
|:-----|:-----|
|MyAnalytics  <br/> |3c896ded-22c5-450F-91f6-3d1ef0848f6e  <br/> |
|Servizio roaming di Office  <br/> |1caee58f-eb14-4a6b-9339-1fe2ddf6692b  <br/> |
   
 **Per cercare ed esportare dati MyAnalytics e servizio di Roaming di Office:**
  
1. In sicurezza &amp; centro conformità, fare clic sulla **riservatezza dei dati** \> **dati soggetto richieste**e quindi fare clic su **Apri** accanto al caso DSR che la persona che si desidera esportare i dati di utilizzo per. 
    
2. Fare clic sulla scheda **ricerca** nella parte superiore della pagina e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) **guidato ricerca**.
    
3. Fare clic su **Annulla** nella pagina **nome della ricerca** . 
    
4. In **query di ricerca**, selezionare le caselle di controllo accanto a **Servizio Roaming di Office**e **MyAnalytics** nella condizione di **tipo** . 
    
    ![Selezionare le caselle di controllo MyAnalytics e servizio di Roaming di Office per esportare i dati di utilizzo](media/3dacbc7a-c314-492c-828c-6757fda84963.png)
  
    Si noti che la condizione di **tipo** , che sono classi messaggio di posta elettronica, deve essere l'unico elemento nella query di ricerca. È possibile eliminare casella **parole chiave** o lasciare vuoto. 
    
5. In **percorsi**, verificare che sia selezionata **percorsi specifici** e quindi fare clic su **Modifica**.
    
6. Nella parte superiore della pagina **Modifica posizioni** di comparsa (sezione delle cassette postali), fare clic su **Scegli utenti, gruppi o team**.
    
7. Nella pagina **Modifica percorsi** fare clic su **Scegli utenti, gruppi o team**, fare clic sulla cassetta postale dell'oggetto dati e quindi salvare la selezione. 
    
8. Fare clic su **salvare &amp; eseguire**, quindi denominare la ricerca e salvarlo.
    
    La ricerca viene avviata.
    
 **Per esportare dati MyAnalytics e servizio di Roaming di Office:**
  
1. Una volta completata la ricerca creata nel passaggio precedente, fare clic sulla scheda **ricerca** nella parte superiore della pagina e quindi fare clic sulla casella accanto a Cerca. Potrebbe essere necessario fare clic su ![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Aggiorna** per visualizzare i criteri di ricerca. 
    
2. Nella pagina ricerca tendina fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **ulteriori**e quindi seleziona **esportare i risultati** dall'elenco a discesa. 
    
3. Nella pagina **esportazione dei risultati** selezionare le opzioni per esportare i dati di utilizzo consigliate. 
    
    ![Opzioni di esportazione per l'esportazione dei dati di utilizzo MyAnalytics e servizio di Roaming di Office](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    r. in **Opzioni di Output**, selezionare l'opzione prima ( **tutti gli elementi, ad eccezione di quelli che sono quelle che dispongono di un formato non riconosciuto, vengono crittografate o non indicizzate per altri motivi**) per esportare solo gli elementi indicizzati.
    
    b. in **contenuto di Exchange esportare**, selezionare la seconda opzione, **i file di un file PST contenente tutti i messaggi**.
    
    c. lasciare deselezionate le opzioni di esportazione restanti.
    
4. Dopo aver scelto le impostazioni di esportazione, fare clic su **Esporta**.
    
    I risultati della ricerca sono pronti per il download, il che significa che viene caricati all'area di archiviazione Azure per l'organizzazione nel cloud Microsoft. I passaggi successivi mostrano come scaricare questi dati al computer locale.
    
5. Fare clic sulla scheda **Esporta** per visualizzare il processo di esportazione che appena creata. Si noti che i processi di esportazione avere lo stesso nome corrispondente esegue una ricerca con **Export** aggiunto alla fine del nome di ricerca. 
    
6. Fare clic sul processo di esportazione appena creata per visualizzare la pagina di comparsa di esportazione. 
    
7. In **Esporta chiave**, fare clic su **Copia negli Appunti**. Utilizzare questa chiave nel passaggio 10 per scaricare i risultati della ricerca.
    
8. Fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **scaricare i risultati** nella parte superiore della pagina esportazione comparsa. 
    
9. Nella finestra popup nella parte inferiore della pagina, fare clic su **Apri** per aprire **Microsoft Office 365 eDiscovery dello strumento di esportazione**. Verrà installato la prima volta che si scarica i risultati della ricerca **eDiscovery dello strumento di esportazione** . 
    
10. Nello **strumento di esportazione di eDiscovery** incollare nella casella appropriata la chiave di esportazione copiata nel passaggio 7.
    
11. Fare clic su **Sfoglia** per specificare il percorso in cui si desidera scaricare i file dei risultati della ricerca. 
    
    > [!NOTE]
    > A causa della quantità elevata di attività del disco (letture e scritture), è necessario scaricare i risultati della ricerca in un'unità disco locale, non scaricare tali un'unità di rete o altro percorso di rete. 
  
12. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer. 
    
    **EDiscovery dello strumento di esportazione** viene visualizzato il processo di esportazione, con una stima del numero e dimensione degli altri download di informazioni sullo stato. Una volta completato il processo di esportazione, è possibile aprire il file PST di Exchange in Outlook e quindi passare alla cartella **ApplicationDataRoot** per accedere alle sottocartelle al servizio MyAnalytics e di Roaming. 
    
    Come indicato in precedenza, i file JSON che contiene i dati di utilizzo sono allegati ai messaggi. Per visualizzare un file JSON, fare clic su un messaggio e quindi aprire il file allegato JSON. 
  
### <a name="exporting-partially-indexed-items"></a>Esportazione di elementi indicizzati parzialmente

È consigliabile non esportare elementi indicizzati parzialmente (denominati anche gli elementi non indicizzati) dalla ricerca incorporata che viene creata quando si crea un nuovo caso DSR. Ciò avviene perché la ricerca risultati più probabile che includerà parzialmente indicizzato elementi per altri utenti all'interno dell'organizzazione e non solo parzialmente indicizzato elementi per l'oggetto dati). In realtà, è consigliabile creare una ricerca di contenuto separata associato il caso DSR progettato in modo da esportare solo gli elementi indicizzati parzialmente correlati all'argomento dati. 
  
Di seguito è un processo di alto livello per esportare elementi parzialmente indicizzati. Dopo aver è export, è possibile rivedere per determinare se un elementi risponde a un accesso DSR o richiesta di esportazione.
  
1. Aprire il caso DSR e creare una nuova ricerca nella pagina di **ricerca** . 
    
2. Utilizzare i criteri seguenti per configurare la query di ricerca e i percorsi di contenuti per la ricerca:
    
    - Utilizzare una query con parole chiave vuota/vuoto. Questo restituisce tutti gli elementi in percorsi contenuti vengono eseguita la ricerca.
    
    - Ricerca solo tale persona Exchange Online delle cassette postali e il proprio account OneDrive.
    
3. Dopo l'esecuzione della ricerca e completarlo, è possibile esportare e scaricare i risultati della ricerca (come descritto nel [passaggio 4](#step-4-export-the-data)). Utilizzare le impostazioni seguenti per esportare elementi parzialmente indicizzati. 
    
    - In **Opzioni di Output**, selezionare la terza opzione ( **solo gli elementi di un formato non riconosciuto, vengono crittografate o non indicizzate per altri motivi**) per esportare solo elementi parzialmente indicizzati.
    
    - In **Exchange esportare contenuto**, è possibile selezionare qualsiasi opzione in base alle proprie preferenze. 
    
    - Selezionare l'opzione **Includi versioni per i documenti di SharePoint** esporterà versioni dei documenti se una versione parzialmente è indicizzata. 
    
Per ulteriori informazioni sugli elementi indicizzati parzialmente, vedere: 
  
- [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

- [Esportazione di elementi indicizzati parzialmente](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a>Ricerca e l'esportazione di dati da Microsoft Teams e gruppi di Office 365

Le conversazioni che fanno parte dell'elenco di Chat di Microsoft Teams (denominato chat Team o chat dirette) sono archiviate nella cassetta postale di Exchange Online degli utenti che partecipano la chat. Inoltre, sono archiviati i file che condivide una persona in una chat dirette account OneDrive dell'utente che condivide il file. Perché la ricerca incorporata ricerche in tutte le cassette postali e gli account OneDrive nell'organizzazione, documenti condivisi in una sessione di chat (ovvero l'oggetto di dati creati o caricati) e team chat verranno restituiti dalla ricerca predefinita in un caso DSR.
  
In alternativa, le conversazioni che fanno parte di un canale team (denominato anche i messaggi di canale) sono archiviate nella cassetta postale associata a un team. Questi tipi di conversazioni che ha partecipato l'oggetto dati vengono restituiti dalla ricerca incorporato anche perché tutte le cassette postali associate a Microsoft Teams vengono eseguita la ricerca. Inoltre, vengono archiviate le sezioni potrebbe condivisione di un oggetto dati in un canale team nel sito di SharePoint del team. I file creati o uploadedby verrà restituito l'oggetto dati dalla ricerca predefinita in un caso DSR perché siti associati a Microsoft Teams vengono incluse nella ricerca.
  
Analogamente, le cassette postali e i siti di SharePoint che corrispondono a un gruppo di Office 365 sono inclusi anche della funzionalità di ricerca predefinita. Ciò significa che messaggi di posta elettronica che dove inviati o ricevuti in base all'oggetto dati e i file creati o caricati in base all'oggetto dati verranno restituiti. 
  
Per ulteriori informazioni sull'utilizzo di ricerca del contenuto per la ricerca di elementi in Microsoft Teams e Office 365 gruppi o per informazioni su come ottenere un elenco di membri, vedere la sezione "Ricerca di Microsoft Team e Office 365 gruppi" in [Ricerca contenuto in Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups). 
  
### <a name="searching-exchange-public-folders"></a>Ricerca di cartelle pubbliche di Exchange

Ricerca incorporate in caso DSR verrà messaggi di posta elettronica di restituire solo che l'oggetto dati inviati a una cartella pubblica abilitata alla posta elettronica o messaggi qualcun altro inviati a una cartella pubblica e copiati anche l'oggetto di dati. Non restituirà messaggio in cui l'oggetto dati potrebbe essere pubblicate in una cartella pubblica. Per cercare gli elementi che l'oggetto dati pubblicato in una cartella pubblica, è possibile creare un oggetto separato eseguire una ricerca di contenuto distinti che esegue la ricerca per gli oggetti pubblicati in una cartella pubblica in base all'oggetto dati.
  
Di seguito è un processo di alto livello per cercare gli elementi che potrebbe essere pubblicate l'oggetto dati in una cartella pubblica. 
  
1. Aprire il caso DSR e creare una nuova ricerca nella pagina di **ricerca** . 
    
2. Utilizzare i criteri seguenti per configurare la query di ricerca e i percorsi di contenuti per la ricerca:
    
  - Nella casella **parole chiave** , utilizzare la query di ricerca seguenti: 
    
    ```
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - Ricerca tutte le cartelle pubbliche di Exchange
    
  - Dopo l'esecuzione della ricerca e completarlo, è possibile esportare e scaricare i risultati della ricerca (come descritto nel [passaggio 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)). Utilizzare le impostazioni seguenti per esportare elementi parzialmente indicizzati. 
