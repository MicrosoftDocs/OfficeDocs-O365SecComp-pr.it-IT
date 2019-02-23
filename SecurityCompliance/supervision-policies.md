---
title: Criteri di superVisione in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Informazioni sui criteri di supervisione in Office 365
ms.openlocfilehash: 7a173809f37262f73671fe6ee96485cda97c1eb3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214116"
---
# <a name="supervision-policies-in-office-365"></a>Criteri di superVisione in Office 365

I criteri di superVisione in Office 365 consentono di acquisire le comunicazioni dei dipendenti per l'esame da revisori designati. È possibile definire criteri specifici che consentono di acquisire messaggi di posta elettronica interni ed esterni, Microsoft teams o comunicazioni di terze parti nell'organizzazione. I revisori possono quindi esaminare i messaggi per assicurarsi che siano conformi agli standard dei messaggi dell'organizzazione e risolverli con il tipo di classificazione. Questi criteri possono anche aiutare a superare molte sfide di conformità moderne, tra cui il monitoraggio dei tipi di canali di comunicazione, l'aumento del volume dei dati del messaggio e l'applicazione della normativa & il rischio di multe.

In alcune organizzazioni può verificarsi una separazione dei compiti tra il supporto IT e il gruppo di gestione della conformità. Office 365 supporta la separazione tra la configurazione del tenant e le funzionalità di supporto dei criteri di supervisione e la configurazione di criteri e l'azione su comunicazioni acquisite. Ad esempio, il gruppo IT di un'organizzazione potrebbe essere responsabile dell'impostazione delle autorizzazioni e dei gruppi di ruoli per supportare i criteri di supervisione configurati e gestiti dal team di conformità dell'organizzazione.

## <a name="scenarios-for-supervision-policies"></a>Scenari per i criteri di supervisione

I criteri di superVisione possono assistere il monitoraggio delle comunicazioni nell'organizzazione in diverse aree:

- **Criteri aziendali**

    I dipendenti devono essere conformi all'uso accettabile, agli standard etici e ad altri criteri aziendali in tutte le comunicazioni relative alle aziende. I criteri di superVisione sono in grado di rilevare violazioni dei criteri e di eseguire azioni correttive che consentono di attenuare questi tipi di incidenti. Ad esempio, è possibile monitorare la propria organizzazione per individuare potenziali violazioni delle risorse umane, quali molestie o utilizzo di linguaggio inappropriato o offensivo nelle comunicazioni dei dipendenti.

- **Gestione dei rischi**

    Le organizzazioni sono responsabili di tutte le comunicazioni distribuite nell'infrastruttura e nei sistemi di rete aziendale. L'utilizzo dei criteri di supervisione per identificare e gestire potenziali esposizione e rischi legali può contribuire a ridurre al minimo i rischi prima che possano danneggiare le operazioni aziendali. Ad esempio, è possibile monitorare la propria organizzazione per le comunicazioni non autorizzate per progetti riservati, ad esempio acquisizioni imminenti, fusioni, divulgazioni di guadagni, riorganizzazioni o modifiche del team di leadership.

- **Conformità alle normative**

    La maggior parte delle organizzazioni deve soddisfare alcuni tipi di standard di conformità normativi nell'ambito delle normali procedure operative. Queste normative richiedono spesso che le organizzazioni implementino un qualche tipo di processo di supervisione o sorveglianza per la messaggistica appropriata per il proprio settore. La regola FINRA (Financial Industry Regulatory Authority) 3110 è un buon esempio di un requisito per le organizzazioni di disporre di procedure di supervisione per monitorare le attività dei suoi dipendenti e i tipi di imprese in cui si impegna. Un altro esempio potrebbe essere la necessità di monitorare broker-dealer nell'organizzazione per salvaguardarsi da possibili operazioni di riciclaggio, insider trading, collusioni o tangenti. I criteri di superVisione consentono all'organizzazione di soddisfare questi requisiti fornendo una procedura per monitorare e segnalare le comunicazioni aziendali.

## <a name="feature-components"></a>Componenti delle funzionalità

### <a name="supervision-policy"></a>Criteri di superVisione

Verranno creati i criteri di supervisione nel centro sicurezza & Compliance. Questi criteri definiscono le comunicazioni e gli utenti soggetti a revisione nell'organizzazione, definiscono le condizioni personalizzate che devono soddisfare le comunicazioni e specifica chi deve eseguire le revisioni. Gli utenti inclusi nel gruppo di ruoli revisione di superVisione possono impostare i criteri e tutti coloro a cui è assegnato questo ruolo possono accedere alla pagina di superVisione sotto la governance dei dati nel centro sicurezza & Compliance Office 365.

### <a name="supervised-users"></a>Utenti controllati

Prima di iniziare a utilizzare la supervisione, è necessario determinare gli utenti che avranno la revisione delle comunicazioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica degli utenti per identificare gli utenti o i gruppi di persone da controllare. Alcuni esempi di questi gruppi sono i gruppi di Office 365, le liste di distribuzione basate su Exchange e i canali Microsoft teams. È inoltre possibile escludere utenti o gruppi specifici da una vigilanza inclusa all'interno di un gruppo controllato o di un elenco di gruppi.

> [!IMPORTANT]
> Tutti gli utenti monitorati dai criteri di supervisione devono disporre di una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato o essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare a eseguire la supervisione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Revisori

Quando si crea un criterio di supervisione, si determinerà anche chi eseguirà le revisioni dei messaggi degli utenti controllati. Nei criteri si utilizzeranno gli indirizzi di posta elettronica degli utenti per identificare gli utenti o i gruppi di persone per esaminare le comunicazioni sorvegliate.

### <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi per gli utenti e i revisori controllati

Per semplificare la configurazione, creare gruppi per gli utenti che avranno la propria comunicazione e i gruppi di utenti che rivedranno tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi. Ad esempio, se si desidera monitorare le comunicazioni tra due gruppi distinti di persone o se si desidera specificare un gruppo che non verrà controllato.

### <a name="supported-communication-types"></a>Tipi di comunicazione supportati

Con i criteri di supervisione, è possibile scegliere di monitorare i messaggi in una o più delle piattaforme di comunicazione seguenti:

- **Posta elettronica di Exchange:** Le cassette postali ospitate in Exchange Online come parte dell'abbonamento a Office 365 sono tutte idonee per la supervisione dei messaggi. I messaggi di posta elettronica e gli allegati che corrispondono alle condizioni dei criteri di supervisione sono immediatamente disponibili per il monitoraggio e i report I tipi di allegati supportati per la supervisione sono gli stessi dei [tipi di file supportati per le ispezioni del contenuto delle regole del flusso di posta di Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).
- **Microsoft teams:** È possibile controllare le comunicazioni chat e gli allegati associati sia nei canali di Microsoft Public che in quelli privati e nelle chat individuali. Chat teams le condizioni dei criteri di supervisione vengono elaborate una volta ogni 24 ore e quindi sono disponibili per il monitoraggio e per i report di supervisione.
- **Origini di terze parti:** È possibile controllare le comunicazioni provenienti da origini di terze parti (come da Facebook o DropBox) se i dati sono stati importati nelle cassette postali di Office 365 nell'organizzazione. [Informazioni su come importare i dati di terze parti in Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).

### <a name="policy-settings"></a>Impostazioni dei criteri

#### <a name="direction"></a>Direction

Per impostazione predefinita, la **direzione è** la condizione viene visualizzata e non può essere rimossa. Le impostazioni delle direzioni di comunicazione in un criterio possono essere scelte singolarmente o contemporaneamente:

- In **ingresso** -è possibile scegliere in **ingresso** per esaminare le comunicazioni inviate **agli** utenti scelti per la supervisione **da** parte di utenti non inclusi nel criterio.
- In **uscita** : è possibile scegliere in **uscita** se si desidera esaminare le comunicazioni inviate **dalle** persone che si è scelto di controllare **per** gli utenti non inclusi nel criterio.
- **Internal** -è possibile scegliere **Internal** per esaminare le comunicazioni inviate **tra** le persone identificate nel criterio.

#### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

È possibile includere i tipi di informazioni riservate nell'ambito del criterio di supervisione. I tipi di informazioni riservate sono tipi di dati predefiniti o personalizzati che consentono di identificare e proteggere i numeri di carta di credito, i numeri di conto corrente bancario, i numeri di passaporto e altro ancora. Come parte di Office 365 [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md), la configurazione delle informazioni riservate può sfruttare i modelli, la prossimità dei caratteri, i livelli di sicurezza e persino i tipi di dati personalizzati per identificare e contrassegnare il contenuto che potrebbe essere sensibile. I tipi di informazioni riservate predefinite sono:

- Finanziari
- Medicale e sanitarie
- Privacy
- Tipo di informazioni personalizzato

Per ulteriori informazioni sui dettagli riservati e sui modelli inclusi nei tipi predefiniti, vedere [quali tipi di informazioni riservaTe devono essere cercate](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Dizionari per parole chiave personalizzate

La configurazione di dizionari per parole chiave personalizzate (o lessici) può fornire una gestione semplice delle parole chiave specifiche per l'organizzazione o l'industria e può supportare fino a 100.000 termini per dizionario. Se necessario, è possibile applicare più dizionari di parole chiave personalizzati a un singolo criterio oppure disporre di un solo dizionario di parole chiave per ogni criterio. Questi dizionari sono assegnati a un criterio di supervisione e possono essere provenienti da un file, ad esempio un elenco con estensione CSV o txt, oppure da un elenco che è possibile [immettere direttamente in un cmdlet di PowerShell](create-a-keyword-dictionary.md).

#### <a name="conditional-settings"></a>Impostazioni condizionali

Le condizioni che scegli per il criterio si applicano alle comunicazioni sia da fonti di posta elettronica che di terze parti nell'organizzazione (come da Facebook o DropBox).

Nella tabella seguente vengono illustrate altre informazioni su ogni condizione.
  
|**Condizione**|**Come utilizzare la condizione**|
|:-----|:-----|
|Il messaggio viene ricevuto da uno di questi domini  <br><br> Il messaggio non viene ricevuto da nessuno di questi domini | Per applicare il criterio quando alcuni domini sono inclusi o esclusi in un messaggio ricevuto, immettere ogni dominio e separare più domini con una virgola. Ogni dominio immesso verrà applicato separatamente (solo uno di questi domini deve richiedere il criterio da applicare al messaggio). |
|Il messaggio viene inviato a uno di questi domini  <br><br> Il messaggio non viene inviato a uno di questi domini | Per applicare il criterio quando alcuni domini sono inclusi o esclusi in un messaggio inviato, immettere ogni dominio e separare più domini con una virgola. Ogni dominio immesso verrà applicato separatamente (solo uno di questi domini deve richiedere il criterio da applicare al messaggio). |
|Il messaggio è classificato con una qualsiasi di queste etichette  <br><br> Il messaggio non è classificato con nessuna di queste etichette | Per applicare il criterio quando determinate etichette di conservazione sono incluse o escluse in un messaggio. Le etichette di conservazione devono essere configurate separatamente e le etichette configurate possono essere scelte come parte di questa condizione. Ogni etichetta scelta verrà applicata separatamente (solo una di queste etichette deve richiedere il criterio da applicare al messaggio). Per ulteriori informazioni sulla configurazione delle etichette di conservazione, vedere [Overview of](https://docs.microsoft.com/office365/securitycompliance/labels)retention labels.|
|Il messaggio contiene una o più delle seguenti parole  <br><br> Il messaggio contiene nessuna di queste parole | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un messaggio, immettere ogni parola o frase su una riga distinta. Ogni riga di parole immesse verrà applicata separatamente (solo una di queste righe deve richiedere il criterio da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](supervision-policies.md#Matchwords).|
|L'allegato contiene una o più delle seguenti parole  <br><br> L'allegato contiene nessuna di queste parole | Per applicare il criterio quando determinate parole o frasi sono incluse o escluse in un allegato del messaggio, ad esempio un documento di Word, immettere ogni parola o frase su una riga distinta. Ogni riga di parole immesse verrà applicata separatamente (è necessario applicare solo una riga per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva che [corrisponde a parole e frasi a messaggi di posta elettronica o allegati](supervision-policies.md#Matchwords).|
|Attachment è uno qualsiasi di questi tipi di file  <br><br> Attachment è nessuno di questi tipi di file | Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file, ad esempio. exe o. pdf. Se si desidera includere o escludere più estensioni di file, immetterle su righe separate. Per applicare il criterio, è necessario che sia presente una sola estensione per gli allegati.|
|La dimensione del messaggio è maggiore di  <br><br> La dimensione del messaggio non è maggiore di | Per esaminare i messaggi in base a una determinata dimensione, utilizzare queste condizioni per specificare le dimensioni massime o minime che un messaggio può avere prima che sia soggetto a revisione. ad esempio, se si specifica che **la dimensione del messaggio è maggiore di** \> **1,0 mb**, tutti i messaggi che sono 1,01 MB e maggiori saranno soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
|L'allegato è più grande di  <br><br> L'allegato non è più grande di | Per esaminare i messaggi in base alle dimensioni degli allegati, specificare le dimensioni massime o minime che un allegato può avere prima che il messaggio e i suoi allegati siano soggetti a revisione. ad esempio, se si specifica **attachment è maggiore di** \> **2,0 mb**, tutti i messaggi con allegati 2,01 MB e oltre saranno soggetti a revisione. Per questa condizione è possibile scegliere byte, kilobyte, megabyte o gigabyte.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Ogni riga di parole immesse verrà applicata separatamente (è necessario applicare solo una riga per la condizione di criteri da applicare al messaggio di posta elettronica o all'allegato). Ad esempio, usiamo la condizione, il **messaggio contiene una o più delle seguenti parole**, con le parole chiave "Banker" e "insider trading" su righe separate. Il criterio si applica a tutti i messaggi che includono la parola "Banker" o la frase "insider trading". Per applicare questa condizione di criteri, è necessario che si verifichi solo una di queste parole o frasi. Le parole del messaggio o dell'allegato devono corrispondere esattamente a quelle immesse.
  
##### <a name="entering-multiple-conditions"></a>Immissione di più condizioni

Se si immettono più condizioni, Office 365 utilizza tutte le condizioni insieme per determinare quando applicare il criterio agli elementi di comunicazione. Quando si configurano più condizioni, è necessario che siano soddisfatte per l'applicazione del criterio, a meno che non si immetta un'eccezione. Si supponga, ad esempio, che sia necessario creare un criterio che dovrebbe essere applicato se un messaggio contiene la parola "Trade" ed è maggiore di 2MB. Tuttavia, se il messaggio contiene anche le parole "apProvate da Contoso Financial", il criterio non dovrebbe essere applicato. Pertanto, in questo caso, le tre condizioni sarebbero le seguenti:
  
- Il **messaggio contiene una di queste parole**, con le parole chiave "Trade"

- La **dimensione del messaggio è maggiore di**, con il valore 2 MB

- Il **messaggio contiene nessuna di queste parole**, con le parole chiave "approvate da Contoso Financial team".

#### <a name="review-percentage"></a>Percentuale di Revisione

È possibile specificare una percentuale di tutte le comunicazioni disciplinate da un criterio di supervisione se si desidera ridurre la quantità di contenuto da rivedere. Selezioneremo casualmente la quantità di contenuto dalla percentuale totale corrispondente alle condizioni scelte. Se si desidera che i revisori rivedano tutti gli elementi, è possibile immettere **100%** in un criterio di supervisione.

## <a name="monitoring--managing"></a>Monitoraggio della gestione di &

Monitorare i risultati dei criteri di supervisione e applicare un tag di risoluzione è facile e conveniente. È possibile visualizzare rapidamente lo stato degli elementi recensiti, degli utenti e dei gruppi in supervisione, nonché gli utenti e i gruppi designati come revisori.

### <a name="supervision-policy-dashboard"></a>Dashboard criteri di superVisione

Il modo più semplice per gestire i risultati dei criteri di supervisione e risolvere gli elementi in sospeso consiste nell'utilizzare il dashboard dei criteri di supervisione. Questo dashboard consente ai revisori di visualizzare rapidamente gli elementi che devono essere esaminati, intervenire su un elemento ed esaminare i risultati degli elementi precedentemente esaminati e risolti per ogni criterio di supervisione. è possibile accedere al dashboard dei criteri di supervisione nel centro conformità di Office 365 **** > Security & per la supervisione*del criterio* > personalizzato**aperto**.

#### <a name="dashboard-home"></a>Home dashboard

La **Home** page del dashboard contiene diverse sezioni che consentono di intervenire rapidamente sui criteri di supervisione. Qui è possibile:

- Esaminare rapidamente le evidenziazioni in sospeso e risolte per la settimana
- Visualizzare un elenco degli utenti controllati e dei gruppi controllati per il criterio selezionato
- Visualizzare un elenco di revisori e team di revisione per il criterio selezionato
- Vedere quali piattaforme di comunicazione dispongono di contenuto sotto controllo per il criterio.

#### <a name="supervise-tab"></a>Scheda supervisiona

La scheda **supervisiona** è la posizione in cui i revisori possono intervenire e risolvere gli elementi identificati dal criterio selezionato. Qui è possibile:

- Filtrare in base agli elementi in sospeso, conformi, non conformi e discutibili
- Contrassegnare un singolo elemento come conforme, non conforme o discutibile. È inoltre possibile registrare un commento con l'elemento per chiarire l'azione di tagging eseguita.
- I tag di massa più elementi sono conformi, non conformi o discutibili. È inoltre possibile registrare un commento con più elementi per chiarire l'azione di tagging eseguita.
- Visualizzare la cronologia del tagging per un singolo elemento, compresi gli utenti che hanno risolto l'elemento, la data e l'ora dell'azione, il tag di risoluzione e tutti i commenti inclusi.
- Riclassificare gli elementi precedentemente recensiti come conformi, non conformi o discutibili. È inoltre possibile registrare un commento con elementi singoli o multipli per chiarire l'azione di riclassificazione eseguita.

#### <a name="resolved-items-tab"></a>Scheda elementi risolti

La scheda **elementi risolti** è la posizione in cui i revisori possono visualizzare tutti gli elementi precedentemente risolti per il criterio selezionato. Qui è possibile:

- Visualizzare e ordinare rapidamente l'oggetto, il mittente e la data degli elementi risolti.
- Visualizzare la classificazione e la cronologia dei commenti di qualsiasi elemento selezionato

### <a name="other-ways-to-review-items"></a>Altri modi per esaminare gli elementi

Se i revisori preferiscono non utilizzare il dashboard di supervisione in Office 365, dispongono anche di altre opzioni per la revisione e la gestione degli elementi raccolti dai criteri di supervisione.

#### <a name="outlook-on-the-web"></a>Outlook sul web

Gli utenti designati come revisori in un criterio di supervisione possono utilizzare Outlook sul Web per esaminare e risolvere gli elementi di supervisione. Il componente aggiuntivo di superVisione viene installato automaticamente in Outlook sul Web per tutti i revisori specificati nel criterio. Non è necessaria alcuna configurazione aggiuntiva da parte dell'organizzazione per le cartelle condivise dei criteri di supervisione per essere disponibili per i revisori configurati.

Tramite Outlook sul Web, i revisori possono:

- Visualizzare gli elementi filtrati in base allo stato conforme, non conforme, discutibile e risolto
- Contrassegnare un singolo elemento come conforme, non conforme, discutibile o risolto. È inoltre possibile registrare un commento con l'elemento per chiarire l'azione di tagging eseguita.
- Visualizzare la cronologia del tagging per un singolo elemento, compresi gli utenti che hanno risolto l'elemento, la data e l'ora dell'azione, il tag di risoluzione e tutti i commenti inclusi.
- Riclassificare gli elementi precedentemente recensiti come conformi, non conformi o discutibili. È inoltre possibile registrare un commento con elementi singoli per chiarire l'azione di riclassificazione eseguita.

#### <a name="microsoft-outlook"></a>Microsoft Outlook

Per esaminare le comunicazioni identificate da un criterio di supervisione, i revisori possono anche utilizzare il componente aggiuntivo di superVisione per Microsoft Outlook. Tuttavia, i revisori devono eseguire alcuni passaggi per installarlo nella versione desktop di Outlook. Per istruzioni dettagliate sull'installazione del componente aggiuntivo per la superVisione per Outlook, vedere [Configure Supervision Policies](configure-supervision-policies.md).

Utilizzando Outlook, i revisori possono:

- Visualizzare gli elementi filtrati in base allo stato conforme, non conforme, discutibile e risolto
- Contrassegnare un singolo elemento come conforme, non conforme, discutibile o risolto. È inoltre possibile registrare un commento con l'elemento per chiarire l'azione di tagging eseguita.
- Visualizzare la cronologia del tagging per un singolo elemento, compresi gli utenti che hanno risolto l'elemento, la data e l'ora dell'azione, il tag di risoluzione e tutti i commenti inclusi.
- Riclassificare gli elementi precedentemente recensiti come conformi, non conformi o discutibili. È inoltre possibile registrare un commento con elementi singoli per chiarire l'azione di riclassificazione eseguita.

## <a name="reporting"></a>Creazione di rapporti

Utilizzare i rapporti di supervisione per visualizzare l'attività di revisione a livello di criteri e revisori. Per ogni criterio, è anche possibile visualizzare le statistiche in tempo reale sullo stato corrente dell'attività di revisione. È possibile utilizzare i report di supervisione per:
  
- Verificare che i criteri funzionino come previsto.
- Informazioni su quante comunicazioni vengono identificate per la revisione.
- Informazioni su quante comunicazioni non sono conformi e quali passano la revisione. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.

### <a name="view-the-supervision-report"></a>Visualizzare il report di superVisione

1. Accedere al [Centro sicurezza e conformità di &](https://protection.office.com/) utilizzando le credenziali per un account di amministratore nell'organizzazione di Office 365 che disponga delle autorizzazioni per visualizzare i report di supervisione.
2. Andare al **Dashboard** o alla supervisione di **report** \> . **** Verrà visualizzato un widget di Reporting di supervisione con un riepilogo delle attività correnti dei criteri di supervisione.
3. Selezionare il **** widget di supervisione per aprire la pagina del rapporto dettagliato.

> [!NOTE]
> Se non si è in grado di accedere alla pagina **report** , verificare di essere membri del gruppo di ruolo revisione di supervisione, come descritto in rendere la [supervisione disponibile nell'organizzazione](configure-supervision-policies.md). L'inclusione in questo gruppo di ruoli consente di creare e gestire i criteri di supervisione ed eseguire il report.
  
### <a name="how-to-use-the-report"></a>Come utilizzare il report

Quando un criterio di supervisione identifica un messaggio di comunicazione per la revisione, la posta elettronica viene recapitata alla cartella di superVisione del revisore in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). Questo rapporto elenca il nome di ogni criterio e il numero di comunicazioni in ogni fase del processo di revisione.
  
Utilizzare il report per:
  
- Visualizzare i dati per tutti i criteri o specifici.
- Visualizzare i dati raggruppati in base al tipo di tag (ad esempio, conforme, discutibili, ecc.), revisore o tipo di messaggio.
- Esportare i dati in un file CSV in base alla data di attività, ai criteri e all'attività reviewer.
- Filtrare i dati in base a data attività, tipo di tag, revisore e tipo di messaggio.

Di seguito viene indicato un guasto dei valori che è possibile visualizzare nella colonna **tipo di tag** .
  
|**Tipo di tag**|**Cosa significa**|
|:-----|:-----|
| Non Recensito | Il numero di messaggi di posta elettronica che non sono stati ancora recensiti. Questi messaggi di posta elettronica attendono la revisione nel dashboard di supervisione di Office 365 o nella cartella di supervisione del revisore in Outlook/Outlook sul Web
| Conformi | Il numero di messaggi di posta elettronica esaminati e contrassegnati come conformi. Questi messaggi devono essere ancora risolti. |
| Ambigui | Il numero di messaggi di posta elettronica esaminati e contrassegnati come discutibili. Questo funge da contrassegno. altri revisori possono aiutare a controllare se un messaggio di posta elettronica deve essere controllato per la conformità. Questi messaggi devono essere ancora risolti. |
| Non conforme (attivo) | Il numero di messaggi di posta elettronica non conformi che i revisori stanno attualmente esaminando. |
| Non conforme (risolto) | Il numero di messaggi di posta elettronica non conformi che i revisori hanno esaminato e risolto. |
| Hit Policy | Numero totale (giornaliero) dei messaggi provenienti da origini dati di Exchange, teams e di terze parti che corrispondono a una o più condizioni definite in un criterio di supervisione |
| Competenza | Numero totale (giornaliero) dei messaggi provenienti da origini dati di Exchange, teams e di terze parti analizzati da un criterio di supervisione |
| Risolto | Il numero totale di messaggi provenienti da origini dati di Exchange, teams e di terze parti classificate come **risolte**|

> [!NOTE]
> Prima che vengano visualizzati in questo report, è necessario eseguire il provisioning di criteri di superVisione. Inoltre, se i criteri vengono eliminati, i dati cronologici vengono ancora visualizzati. Tuttavia, sono indicati come "criteri non esistenti" e la funzione di **esportazione** non è disponibile.

## <a name="auditing"></a>Controllo

In alcuni casi, è necessario fornire informazioni ai revisori dei conti normativi o di conformità per dimostrare la supervisione delle attività e delle comunicazioni degli impiegati. Può trattarsi di un riepilogo di tutte le attività di supervisione associate a un criterio definito o in qualsiasi momento in cui un criterio di supervisione è stato modificato o aggiornato. I criteri di superVisione sono basati su percorsi di controllo integrati per una completa preparazione per i controlli interni o esterni. La prova delle procedure di supervisione può essere dimostrata con una cronologia di controllo dettagliata di tutte le azioni monitorate dai criteri di supervisione.

Le attività dei criteri di supervisione seguenti sono controllate e possono essere visualizzate utilizzando i log di controllo di Office 365:

|**Attività**|**Comandi associati**|
|:-----|:-----|
| Creazione di un criterio | New-SupervisoryReviewPolicy <br> New-SupervisoryReviewRule |
| Modifica di un criterio | Set-SupervisoryReviewPolicy <br> Set-SupervisoryReviewRule |
| Eliminazione di un criterio| Remove-SupervisoryReviewPolicy |

I controlli possono essere recuperati utilizzando la funzione di ricerca del registro di controllo unificato o utilizzando il cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell.

Ad esempio, nell'esempio seguente vengono restituite le attività per tutte le attività di revisione di supervisione (criteri e regole) ed elenchi di informazioni dettagliate per ogni:

```
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"} | fl CreationDate,Operations,UserIds,AuditData 
```

Oltre alle informazioni fornite nei report e nei registri di supervisione, è anche possibile utilizzare il cmdlet [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewactivity?view=exchange-ps) di PowerShell per restituire un elenco dettagliato completo di tutte le attività dei criteri di supervisione.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per avviare la configurazione dei criteri di supervisione per l'organizzazione, vedere [configurare i criteri](configure-supervision-policies.md)di supervisione.