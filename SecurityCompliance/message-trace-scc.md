---
title: Traccia dei messaggi in & la sicurezza centro conformità
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Gli amministratori possono usare traccia dei messaggi in & la sicurezza centro conformità per scoprire Dov'ai messaggi.
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685507"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Traccia dei messaggi in & la sicurezza centro conformità

Traccia dei messaggi in & la sicurezza centro conformità segue messaggi di posta elettronica quando passano attraverso l'organizzazione Exchange Online. È possibile determinare se un messaggio è stato ricevuto, rifiutato, rinviato o distribuito tramite il servizio. Viene inoltre le azioni eseguite nel messaggio prima che raggiunto il relativo stato finale.

Traccia dei messaggi in & la sicurezza centro conformità migliora traccia dei messaggi che è stato disponibile nell'interfaccia di amministrazione di Exchange (EAC). È possibile utilizzare le informazioni di traccia dei messaggi per rispondere alle domande utente sulle modifiche apportate alle loro messaggi funzionalità, risoluzione dei problemi del flusso di posta elettronica e convalidare le modifiche ai criteri in modo efficiente.

## <a name="open-message-trace"></a>Traccia messaggio aperto

1. [Accedere a Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con il proprio account aziendale o dell'istituto di istruzione.

2. Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) nell'angolo in alto a sinistra e scegliere **Amministratore**.

3. Nel riquadro di spostamento, in basso a sinistra espandere **Admin Center** e selezionare **& Security Compliance**.

4. Nella pagina **sicurezza & conformità** visualizzata, espandere **il flusso della posta**e selezionare **traccia dei messaggi**.

## <a name="message-trace-page"></a>Pagina di traccia messaggio

Da qui è possibile avviare una nuova traccia predefinito facendo clic sul pulsante **Start una traccia** . In questo cercherà per tutti i messaggi per tutti i mittenti e destinatari ultimi due giorni. Oppure è possibile utilizzare una delle query archiviate dalle categorie di query disponibili e uno eseguirli come-è o utilizzarli come punto di partenza per le query:

- **Predefinito delle query**: query predefinita fornita da Office 365.

- **Le query personalizzate**: query salvate dagli amministratori dell'organizzazione per un utilizzo futuro.

- **Query salvata automaticamente**: più di recente dieci ultimi eseguono di query. In questo elenco rende più semplice sollevare di cui è stata interrotta.

In questa pagina è inoltre una sezione di **report Downloadable** per le richieste inviate, nonché i report stessi quando sono disponibili per il download.

## <a name="options-for-a-new-message-trace"></a>Opzioni per la nuova traccia dei messaggi

### <a name="filter-by-senders-and-recipients"></a>Filtra per i mittenti e destinatari

I valori predefiniti sono **tutti i mittenti** e **tutti i destinatari**, ma è possibile utilizzare i campi seguenti per filtrare i risultati:

- **Da questi utenti**: fare clic su campo da selezionare uno o più mittenti dall'organizzazione. È inoltre possibile iniziare a digitare un nome e gli elementi nell'elenco verranno filtrati da quanto è stato digitato, molto simile comportamento di una pagina di ricerca.

- **Per queste persone**: fare clic su campo da selezionare uno o più destinatari nell'organizzazione.

È inoltre possibile digitare gli indirizzi di posta elettronica di destinatari e mittenti esterni. I caratteri jolly sono supportate (`*@contoso.com` o `scot?@contoso.com`), ma non è possibile utilizzare più voci con caratteri jolly nello stesso campo contemporaneamente.

### <a name="time-range"></a>Intervallo di tempo

Il valore predefinito è **2 giorni**, ma è possibile specificare intervalli di data/ora di un massimo di 90 giorni. Quando si utilizzano gli intervalli di data/ora, prendere in considerazione questi problemi:

- Per impostazione predefinita, si seleziona l'intervallo di tempo nella visualizzazione, **il dispositivo di scorrimento** utilizzando una linea di tempo. È possibile solo selezionare il giorno o ora di impostazioni che vengono visualizzate. Tentativo di selezionare un valore intermedi verrà bloccata bolla iniziale e finale per più vicino visualizzato impostazione.

   ![Un intervallo di tempo il dispositivo di scorrimento in una nuova traccia dei messaggi in & la sicurezza centro conformità](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   Tuttavia, è inoltre possibile passare alla visualizzazione di **personalizzato** dove è possibile specificare i valori di **Data di inizio** e **Data fine** (inclusi volte) ed è inoltre possibile selezionare il **fuso orario** per l'intervallo di data/ora. Si noti che l'impostazione del **fuso orario** si applica a entrambi gli input di query e risultati della query.

   ![Un intervallo di tempo personalizzato in un nuovo traccia dei messaggi in & la sicurezza centro conformità](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   Per 10 giorni o meno i risultati sono disponibili immediatamente sotto forma di un rapporto di **Riepilogo** . Se si specifica un intervallo di tempo è leggermente maggiore di 10 giorni, i risultati verranno ritardi perché sono disponibili solo come file CSV scaricabile (report di **Riepilogo avanzata** o **estesa** ).

   Per ulteriori informazioni sui tipi di report diverso, vedere la sezione [scegliere il tipo di report](#choose-report-type) in questo argomento.

   **Nota**: report di riepilogo ed estese avanzata vengono preparati utilizzando dati di traccia dei messaggi archiviati e potrebbe richiedere diverse ore prima che il report è disponibile per il download. In base al numero gli altri amministratori inoltre abbiano inviato le richieste di relazioni intorno alla stessa ora, è possibile notare un ritardo prima dell'avvio di elaborazione per le richieste in coda.

- Salvataggio di una query nella visualizzazione **dispositivo di scorrimento** viene salvato l'intervallo di tempo relativo (ad esempio 3 giorni dalla data odierna). Salvataggio di una query nella visualizzazione **personalizzata** viene salvato l'intervallo di data/ora assoluto (ad esempio 2018-05-06 13:00 per 2018-05-08 18:00).

### <a name="more-search-options"></a>Altre opzioni di ricerca

#### <a name="delivery-status"></a>Stato di recapito

È possibile lasciare il valore predefinito **tutti** selezionata oppure è possibile selezionare uno dei seguenti valori per filtrare i risultati:

- **Recapitati**: il messaggio è stato correttamente recapitato alla destinazione prevista.

- **In sospeso**: recapito del messaggio è in corso tentativi o nuovi tentativi.

- **Expanded**: un destinatario di gruppo di distribuzione è stata espansa prima del recapito per i singoli membri del gruppo.

- **Errore**: Impossibile recapitare il messaggio.

- **In quarantena**: il messaggio è stato messo in quarantena (come posta indesiderata, posta inviata in blocco o phishing). Per ulteriori informazioni, vedere [i messaggi di posta elettronica quarantena in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).

- **Filtrato come posta indesiderata**: il messaggio è stato identificato posta indesiderata ed è stato rifiutato o bloccati (non in quarantena).

- **Recupero dello stato:** Il messaggio è stato ricevuto recentemente da Office 365, ma non gli altri dati sullo stato sono ancora disponibili. Controllare nuovamente in pochi minuti.

**Nota**: I valori **in sospeso,** **in quarantena**e **Filtro posta indesiderata** sono disponibili solo per le ricerche di meno di 10 giorni. Inoltre, potrebbero verificarsi un ritardo da 5 a 10 minuti tra lo stato di recapito effettivo e segnalate.

#### <a name="message-id"></a>ID messaggio

Questo è l'ID messaggio internet (detto anche ID Client) trovato nel **ID messaggio:** campo di intestazione nell'intestazione del messaggio. Gli utenti possono assegnare questo valore per analizzare i messaggi specifici.

Questo valore è costante per la durata del messaggio. Per i messaggi creati in Office 365 o Exchange, il valore è nel formato `<GUID@ServerFQDN>`, incluse le parentesi angolari (\< \>). Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Altri sistemi di messaggistica è possono utilizzare una sintassi diversa o valori. Questo valore deve per essere univoco, ma non tutti i sistemi di posta elettronica strettamente seguono questo requisito. Se il **ID messaggio:** campo di intestazione non esiste o è vuoto per i messaggi in arrivo provenienti da origini esterne, viene assegnato un valore arbitrario.

Quando si utilizza **L'ID messaggio** per filtrare i risultati, assicurarsi di includere l'intera stringa, incluse le parentesi.

#### <a name="direction"></a>Direction

È possibile lasciare il valore predefinito **tutti** selezionata oppure è possibile selezionare **in ingresso** (i messaggi inviati a destinatari nell'organizzazione) o **in uscita** (i messaggi inviati dagli utenti all'interno dell'organizzazione) per filtrare i risultati.

#### <a name="original-client-ip-address"></a>Indirizzo IP del client originale

È possibile filtro i risultati dall'indirizzo IP del client per analizzare i computer violato l'invio di grandi quantità di posta indesiderata o malware. Anche se i messaggi potrebbero sembrare provenienti da mittenti multipli, è probabile che lo stesso computer sia la generazione di tutti i messaggi.

**Nota**: le informazioni sull'indirizzo IP client è disponibile solo per 10 giorni ed è disponibile solo nei rapporti di **Riepilogo avanzata** o **estesa** (con estensione CSV scaricabile).

### <a name="choose-report-type"></a>Scelta del tipo di rapporto

I tipi di report disponibili sono:

- **Riepilogo**: disponibile se l'intervallo di tempo è inferiore a 10 giorni e non richiede alcun ulteriori opzioni di filtro. I risultati sono disponibili quasi immediatamente dopo che si fa clic su **Cerca**.

- **Riepilogo avanzata** o **estesa**: questi rapporti sono disponibili solo come file CSV scaricabili e richiedere una o più delle opzioni di filtro seguenti indipendentemente dall'intervallo di tempo: **da tali utenti**, **a queste persone**o ** ID messaggio**. È possibile utilizzare i caratteri jolly per i mittenti o destinatari (ad esempio \*@contoso.com).

**Note**:

- Rapporti di riepilogo ed estese avanzate vengono preparati utilizzando dati di traccia dei messaggi archiviati e potrebbe richiedere diverse ore prima che sia disponibile per il download del report. In base al numero gli altri amministratori inoltre abbiano inviato le richieste di relazioni intorno alla stessa ora, è possibile notare un ritardo prima dell'avvio da elaborare le richieste in coda.

- Mentre è possibile selezionare un rapporto di riepilogo o estese avanzata per qualsiasi intervallo di data/ora, comunemente ultimi quattro ore dei dati archiviati non ancora disponibile per questi due tipi di report.

Quando si fa clic su **Avanti**, viene visualizzata una pagina di riepilogo in cui sono elencate le opzioni di filtro che è stato selezionato, un titolo univoco (modificabile) per il report e l'indirizzo di posta elettronica che riceve la notifica al termine della traccia dei messaggi (anche modificabile, e deve essere in uno dei domini accettati dell'organizzazione). Fare clic su **report di preparazione** per inviare la traccia dei messaggi. Nell'oggetto principale della pagina **traccia dei messaggi** è possibile visualizzare lo stato del report nella sezione **report Downloadable** .

Per ulteriori informazioni sulle informazioni restituite nei diversi tipi di report, vedere la sezione successiva.

## <a name="message-trace-results"></a>Risultati di traccia dei messaggi

I diversi tipi di report restituiscano diversi livelli di informazioni. Le informazioni disponibili in diversi report sono descritto nelle sezioni seguenti.

### <a name="summary-report-output"></a>Output del report di riepilogo

Dopo aver eseguito la traccia dei messaggi, verranno elencati i risultati vengono ordinati decrescente data/ora (primo più recente).

![Risultati dei report di riepilogo per traccia dei messaggi in & la sicurezza centro conformità](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Un rapporto di riepilogo contiene le informazioni seguenti:

- **Data**: data e ora in cui il messaggio è stato ricevuto dal servizio, utilizzando il fuso orario UTC configurato.

- **Mittente**: l'indirizzo di posta elettronica del mittente (*alias*@*dominio*).

- **Destinatario**: l'indirizzo di posta elettronica del destinatario o destinatari. Per un messaggio inviato a più destinatari, non esiste una riga per ogni destinatario. Se il destinatario è un gruppo di distribuzione, gruppo di distribuzione dinamico o gruppo di protezione abilitati alla posta elettronica, il gruppo è il primo destinatario e quindi ogni membro del gruppo è su una riga separata.

- **Oggetto**: I primi 256 caratteri del messaggio **soggetto:** campo.

- **Stato**: questi valori sono descritti nella sezione [stato di recapito](#delivery-status) .

Per impostazione predefinita, i primi 250 risultati vengono caricati e immediatamente disponibili. Quando scorrere verso il basso, non esiste una pausa leggera in quanto il batch successivo di risultati vengono caricati. Invece di scorrimento, è possibile scegliere di **caricare tutti** per caricare tutti i risultati fino a un massimo di 10.000.

È possibile fare clic sulle intestazioni di colonna per ordinare i risultati in base ai valori di colonna in ordine crescente o decrescente.

È possibile fare clic su **risultati filtrati** per filtrare i risultati in base a uno o più colonne.

È possibile esportare i risultati dopo che sono state selezionate una o più righe facendo clic su **Esporta risultati** e quindi selezionare **Esporta tutti i risultati**, **esportazione caricato i risultati**o **esportazione selezionata**.

#### <a name="find-related-records-for-this-message"></a>Trovare i record correlati per questo messaggio

Record di messaggi correlati sono record che condivisi lo stesso ID di messaggio. Si tenga presente che anche un singolo messaggio inviato tra due persone può essere generati più record. Aumenta il numero di record quando il messaggio viene influenzato da espansione dei gruppi di distribuzione, inoltro, regole del flusso di posta elettronica (noto anche come regole di trasporto) e così via.

Dopo aver selezionato la casella di controllo della riga, è possibile trovare i record correlati per il messaggio fare clic sul pulsante **Trova correlati** che viene visualizzata o selezionando **altre opzioni** ![più](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **trovare i record correlati per questo messaggio**).

Per ulteriori informazioni sull'ID del messaggio, vedere la sezione ID messaggio più indietro in questo argomento.

#### <a name="message-trace-details"></a>Dettagli traccia messaggio

Nell'output del rapporto di riepilogo, è possibile visualizzare informazioni dettagliate su un messaggio utilizzando uno dei metodi seguenti:

- Selezionare la riga (fare clic in qualsiasi punto nella riga ad eccezione della casella di controllo).

- Selezionare la casella di controllo della riga e fare clic su **altre opzioni** ![più](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Visualizza dettagli messaggio**.

   ![Dettagli dopo fare doppio clic su una riga nei risultati della traccia dei messaggi rapporto riepilogativo in & la sicurezza centro conformità](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

I dettagli della traccia messaggio contengono le seguenti informazioni aggiuntive che non sono presente in un rapporto di riepilogo:

- **Gli eventi di messaggio**: in questa sezione contiene le classificazioni che consentono di classificare le azioni eseguite sui messaggi al servizio. Alcuni degli eventi di più interessanti che possono verificarsi sono:

   - **Ricezione**: il messaggio è stato ricevuto dal servizio.

   - **Inviare**: il messaggio è stato inviato dal servizio.

   - **Errore**: il messaggio non è stato possibile recapitare.

   - **Fornire**: il messaggio è stato recapitato a una cassetta postale.

   - **Espandi**: il messaggio è stato inviato a un gruppo di distribuzione che è stato esteso.

   - **Trasferire**: destinatari sono stati spostati su un messaggio moltiplicato in seguito la conversione del contenuto, limitazioni dei destinatari del messaggio o ad agenti.

   - **Defer**: il recapito del messaggio è stato rimandato e potrebbe essere effettuato un altro tentativo più avanti.

   - **Risolto**: il messaggio è stato reindirizzato a un nuovo indirizzo del destinatario basato su una ricerca Active Directory. In questo caso, l'indirizzo del destinatario originale è elencato in una riga separata nella traccia dei messaggi con lo stato di recapito finale per il messaggio.

   Si noti che anche un messaggio se viene recapitato con successo genererà più voci relative agli **eventi** di traccia dei messaggi.

- **Ulteriori informazioni**: in questa sezione sono i seguenti dettagli:

   - **ID messaggio**: questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo argomento. Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

   - **Dimensione messaggio**

   - **Da IP**: l'indirizzo IP del computer che ha inviato il messaggio. Per i messaggi in uscita inviati da Exchange Online, questo valore è vuoto.

   - **IP a**: indirizzo IP o gli indirizzi dove il tentativo del servizio di recapitare il messaggio. Se il messaggio ha più destinatari, queste vengono visualizzate. Per i messaggi in ingresso inviati a Exchange Online, questo valore è vuoto.

### <a name="enhanced-summary-reports"></a>Rapporti di riepilogo avanzate

Disponibili rapporti di riepilogo avanzata (completate) sono disponibili nella sezione **report Downloadable** alla traccia dei messaggi di inizio. Le informazioni seguenti sono disponibili nel rapporto:

- **origin_timestamp**<sup>*</sup>: data e ora quando il messaggio è stata inizialmente ricevuto dal servizio, utilizzando il fuso orario UTC configurato.

- **sender_address**: indirizzo di posta elettronica del mittente (*alias*@*dominio*).

- **Recipient_status**: lo stato di recapito del messaggio al destinatario. Se il messaggio è stato inviato a più destinatari, verranno visualizzati tutti i destinatari e allo stato corrispondente per ognuno, nel formato: \< *indirizzo di posta elettronica*\>##\<*stato*\>. Per esempio:

   - **##Receive, invia** indica che il messaggio è stato ricevuto dal servizio ed è stato inviato alla destinazione prevista.

   - **Esito negativo ##Receive,** indica che il messaggio è stato ricevuto dal servizio, ma recapito alla destinazione prevista non è riuscita.

   - **Fornire ##Receive,** indica che il messaggio è stato ricevuto dal servizio ed è stato recapitato alla cassetta postale del destinatario.

- **message_subject**: I primi 256 caratteri del campo **oggetto** del messaggio.

- **total_bytes**: le dimensioni del messaggio in byte, inclusi gli allegati.

- **message_id**: questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo argomento. Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: un valore di ID univoci messaggi che vengono mantenute in tutte le copie dei messaggi che possono essere create a causa di espansione dei gruppi di distribuzione o la moltiplicazione. È un valore di esempio `1341ac7b13fb42ab4d4408cf7f55890f`.

- **original_client_ip**: l'indirizzo IP del client del mittente.

- **Direzionalità**: indica che il messaggio è stato inviato all'interno (1) dell'organizzazione o se è stato inviato in uscita (2) dalla propria organizzazione.

- **connector_id**: il nome del connettore di origine o destinazione. Per ulteriori informazioni sui connettori in Exchange Online, vedere [configurare il flusso di posta utilizzando i connettori in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority**<sup>*</sup>: se è stato inviato il messaggio con priorità **alta**, **Low**o **Normal** .

<sup>*</sup>Queste proprietà sono disponibili solo nei rapporti di riepilogo avanzata.

### <a name="extended-reports"></a>Report estesa

Report estesa (completate) disponibili sono disponibili nella sezione **report Downloadable** all'inizio della traccia dei messaggi. Quasi tutte le informazioni da un rapporto di riepilogo avanzata è disponibile in un report estesa (ad eccezione dei **origin_timestamp** e **delivery_priority**). Sono disponibile in un report Extended solo le informazioni seguenti:

- **client_ip**: l'indirizzo IP del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.

- **client_hostname**: il nome host o il nome di dominio completo del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.

- **server_ip**: l'indirizzo IP del server di origine o destinazione.

- **server_hostname**: il nome host o il nome di dominio completo del server di destinazione.

- **source_context**: informazioni Extra associate al campo **origine** . Per esempio:

   - `Protocol Filter Agent`

   - `3489061114359050000`

- **origine**: componente di Exchange Online è responsabile dell'evento. Per esempio:

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- **event_id**: questi corrispondono ai valori illustrati nella sezione [individuare i record correlati per questo messaggio di](#find-related-records-for-this-message) **evento messaggio** .

- **internal_message_id**: un identificatore di messaggio che viene assegnato dal server di Exchange Online che sta elaborando il messaggio.

- **recipient_address**: gli indirizzi di posta elettronica dei destinatari del messaggio. Più indirizzi di posta elettronica sono separati da virgola (;).

- **recipient_count**: il numero totale di destinatari del messaggio.

- **related_recipient_address**: utilizzare in combinazione con `EXPAND`, `REDIRECT`, e `RESOLVE` indirizzi associati a del messaggio di posta elettronica degli eventi per visualizzare altri destinatari.

- **Guida di riferimento**: questo campo contiene informazioni aggiuntive per specifici tipi di eventi. Per esempio:

   - **DSN**: contiene il collegamento al report, ovvero il valore **message_id** della notifica stato recapito associato (noto anche come un nome DSN, rapporto di mancato recapito, rapporti di mancato recapito o messaggio di rimbalzo) se un nome DSN viene generato dopo l'evento. Se si tratta di un messaggio DSN, questo campo contiene il valore **message_id** del messaggio originale è stato generato il DSN per.

   - **ESPANDI**: contiene il valore **related_recipient_address** di messaggi correlati.

   - **Ricezione**: può contenere il valore **message_id** del messaggio correlato se il messaggio è stato generato da altri processi (ad esempio le regole posta in arrivo).

   - **Inviare**: contiene il valore **internal_message_id** dei messaggi DSN.

   - **Trasferire**: contiene il valore **internal_message_id** del messaggio viene viene instradato (ad esempio, per la conversione del contenuto, limitazioni dei destinatari del messaggio o ad agenti).

   - **MAILBOXRULE**: contiene il valore **internal_message_id** del messaggio in ingresso che ha causato la regola di posta in arrivo generare il messaggio in uscita.

   Per tutti gli altri tipi di evento, questo campo in genere è vuoto.

- **return_path**: l'indirizzo di posta elettronica mittente specificato dal comando **MAIL FROM** che ha inviato il messaggio. Sebbene questo campo non è vuoto, il valore dell'indirizzo mittente null rappresentato come può contenere `<>`.

- **message_info**: informazioni aggiuntive relative al messaggio. Per esempio:

   - Il messaggio origine data / ora in formato UTC per `DELIVER` e `SEND` eventi. Data-ora di origine è l'ora in cui il messaggio immessa innanzitutto l'organizzazione Exchange Online. La data e ora UTC è rappresentata nel formato di data / ora ISO8601: `yyyy-mm-ddThh:mm:ss.fffZ`, dove `yyyy` = anno, `mm` = mese, `dd` = giorno, `T` indica l'inizio del componente ora `hh` = ore, `mm` = minuti, `ss` = secondo, `fff` = frazioni di secondo, e `Z` indica `Zulu`, ovvero un altro modo per indicare l'ora UTC.

   - Errori di autenticazione. Ad esempio, potrebbe essere visualizzato il valore `11a` e il tipo di autenticazione utilizzato quando si è verificato l'errore di autenticazione.

- **tenant_id**: un valore GUID che rappresenta l'organizzazione Exchange Online (ad esempio `39238e87-b5ab-4ef6-a559-af54c6b07b42`).

- **original_server_ip**: l'indirizzo IP del server originale.

- **custom_data**: contiene i dati relativi ai tipi di evento specifico. Per ulteriori informazioni, vedere le sezioni seguenti.

#### <a name="customdata-values"></a>valori custom_data

Il campo **custom_data** per un `AGENTINFO` evento viene utilizzato da un'ampia gamma di agenti di Exchange Online per registrare i dati di elaborazione dei messaggi. Nelle sezioni seguenti vengono descritte alcune degli agenti più interessanti.

#### <a name="spam-filter-agent"></a>Agente filtro da posta indesiderata

Un valore **custom_data** che inizia con `S:SFA` è dall'agente filtro posta indesiderata. Nella tabella seguente sono descritti i dettagli principali:

|**Valore**|**Descrizione**|
|:-----|:-----|
|`SFV=NSPM`|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|`SFV=SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.|
|`SFV=BLK`|Le regole del filtro sono state ignorate e il messaggio è stato bloccato perché è stato originato da un mittente bloccato.|
|`SFV=SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.|
|`SCL=<number>`|Per ulteriori informazioni sui valori SCL differenti e sul loro aspetto, vedere [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).|
|`PCL=<number>`|Il valore di livello di probabilità di Phishing (PCL) del messaggio. Questi possono essere interpretati esattamente come il valore SCL valori documentati nei [livelli di probabilità di posta indesiderata](https://technet.microsoft.com/library/jj200686.aspx).|
|`DI=SB`|Il mittente del messaggio è stato bloccato.|
|`DI=SQ`|Il messaggio è stato messo in quarantena.|
|`DI=SD`|Il messaggio è stato eliminato.|
|`DI=SJ`|Il messaggio è stato inviato nella cartella posta indesiderata del destinatario.|
|`DI=SN`|Il messaggio è stato instradato tramite il pool recapito ad alto rischio. Per ulteriori informazioni, vedere [pool di recapito ad alto rischio per i messaggi in uscita](https://technet.microsoft.com/library/jj200746.aspx).|
|`DI=SO`|Il messaggio è stato instradato tramite un pool di recapito ad alto rischio.|
|' SFS = [un]|SFS = [b]'|Indica una corrispondenza tra le regole relative alla posta indesiderata.|
|`IPV=CAL`|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|`H=<EHLOstring>`|La stringa HELO o EHLO del server in connessione posta elettronica.|
|`PTR=<ReverseDNS>`|Il record PTR dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.|

Un valore **custom_data** di esempio per un messaggio viene filtrato per posta indesiderata simile alla seguente:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente di filtro malware

Un valore **custom_data** che inizia con `S:AMA` è dall'agente filtro malware. Nella tabella seguente sono descritti i dettagli principali:

|**Valore**|**Descrizione**|
|:-----|:-----|
|' AMA = SOMMA|v = 1|` or `AMA = EV|v = 1'|Il messaggio è stato determinato come contenente malware. `SUM` indica malware è stato rilevato da un numero qualsiasi di moduli. `EV` indica il malware rilevato da un determinato modulo. Quando viene rilevato malware da un motore che si generano le azioni successive.|
|`Action=r`|Il messaggio è stato sostituito.|
|`Action=p`|Il messaggio è stato ignorato.|
|`Action=d`|Il messaggio è stato rinviato.|
|`Action=s`|Il messaggio è stato eliminato.|
|`Action=st`|Il messaggio è stato ignorato.|
|`Action=sy`|Il messaggio è stato ignorato.|
|`Action=ni`|Il messaggio è stato rifiutato.|
|`Action=ne`|Il messaggio è stato rifiutato.|
|`Action=b`|Il messaggio è stato bloccato.|
|`Name=<malware>`|Il nome del malware rilevato.|
|`File=<filename>`|Il nome del file che contiene malware.|

Un valore **custom_data** di esempio per un messaggio che contiene malware simile al seguente:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente della regola di trasporto

Un valore **custom_data** che inizia con`S:TRA` è dall'agente regole di trasporto per le regole del flusso di posta elettronica (noto anche come regole di trasporto). Nella tabella seguente sono descritti i dettagli principali:

|**Valore**|**Descrizione**|
|:-----|:-----|
|' ETR|ruleId =<guid>`|L'ID regola corrispondente.|
|`St=<datetime>`|Data e ora in formato UTC quando si è verificata la corrispondenza della regola.|
|`Action=<ActionDefinition>`|L'azione che sono stato applicato. Per un elenco delle azioni disponibili, vedere [Mail flow azioni delle regole di Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).|
|`Mode=<Mode>`|La modalità della regola. I valori validi sono:<br/>• **Applica**: tutte le azioni della regola verranno applicate. <br/>• **Test con suggerimenti criteri:**: le azioni del suggerimento criteri qualsiasi verranno inviate, ma non verranno applicate altre azioni su. <br/>• **Verifica senza i suggerimenti criteri**: le azioni verranno elencate in un file di registro, ma i mittenti non riceveranno alcuna notifica e azioni non verranno applicate in.|

Un valore **custom_data** di esempio per un messaggi che soddisfa le condizioni di una regola del flusso di posta elettronica è simile al seguente:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
