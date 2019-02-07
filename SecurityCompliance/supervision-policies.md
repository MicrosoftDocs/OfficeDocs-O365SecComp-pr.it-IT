---
title: Criteri di supervisione in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Informazioni sui criteri di supervisione in Office 365
ms.openlocfilehash: c66ded719791c4a5ecaaa459f81d0a0d4a3db924
ms.sourcegitcommit: e4d56cab6bbb77404457d506d17f6a7577f302be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "29760078"
---
# <a name="supervision-policies-in-office-365"></a>Criteri di supervisione in Office 365

Criteri di supervisione in Office 365 consentono di acquisire communications dipendente per un esame dai revisori designati. È possibile definire criteri specifici che acquisiscono posta elettronica interno ed esterno, Microsoft Teams o communications 3rd parti all'interno dell'organizzazione. I revisori possono quindi esaminare i messaggi per assicurarsi che siano conformi agli standard di messaggi della propria organizzazione e risolverli con tipo di classificazione. Questi criteri consentono inoltre di superare numerosi ostacoli conformità moderno, tra cui l'aumento tipi di canali di comunicazione, aumentando il volume di dati dei messaggi e applicazione della normativa & il rischio di multe di monitoraggio.

In alcune organizzazioni può essere una separazione dei compiti tra il gruppo di gestione della conformità e supporto IT. Office 365 supporta la separazione tra la configurazione tenant con funzionalità di supporto dei criteri di supervisione e la configurazione dei criteri e che agiscono per acquisite communications. Ad esempio, il gruppo IT di un'organizzazione può essere responsabile per impostare le autorizzazioni per i ruoli e gruppi per il supporto di criteri di supervisione configurati e gestiti dal team di conformità dell'organizzazione.

## <a name="scenarios-for-supervision-policies"></a>Scenari per i criteri di supervisione

Criteri di supervisione possono essere utili communications monitoraggio all'interno dell'organizzazione in diverse aree:

- **Criteri aziendali**

    I dipendenti devono rispettare utilizzo accettabile, standard etici e altri criteri aziendali in tutte le loro comunicazioni aziendali. Criteri di supervisione consente di rilevare violazioni dei criteri e consentono di eseguire azioni correttive per attenuare questo tipo di problemi. Ad esempio, è possibile monitorare dell'organizzazione per le risorse umane possibili violazioni, ad esempio molestie o l'utilizzo della lingua appropriata o offensivo nelle comunicazioni di dipendenti.

- **Gestione dei rischi**

    Le organizzazioni sono responsabili per tutte le comunicazioni distribuite in tutto l'infrastruttura e dei sistemi di rete aziendale. Utilizzo dei criteri di supervisione per individuare e gestire i rischi e potenziale legali consente di ridurre i rischi prima che possono danneggiare operazioni aziendali. Ad esempio, è possibile monitorare dell'organizzazione per le comunicazioni non autorizzate per i progetti riservati, ad esempio acquisizioni future, fusioni, l'utente utili, riorganizzazioni o modifiche team leader.

- **Conformità alle normative**

    La maggior parte delle organizzazioni devono rispettare alcuni tipi di standard di conformità alle normative durante le normali procedure operative. Tali normative spesso richiedono alle organizzazioni di implementare un tipo di controllo o responsabile della supervisione processo per la messaggistica che è appropriata per il settore. La regola finanziari settore normativi autorità (FINRA) 3110 è un ottimo esempio un requisito per le organizzazioni alle procedure di controllo sul posto di monitorare le attività dei dipendenti e i tipi di aziende in cui svolge. Un altro esempio potrebbe essere necessario monitorare broker-dealers all'interno dell'organizzazione per evitare riciclaggio potenziale, persona interna commerciali, collusione o attività corruzione. Criteri di supervisione consentono alle organizzazioni di soddisfare questi requisiti, fornendo un processo a monitor e report sulle comunicazioni aziendali.

## <a name="feature-components"></a>Componenti principali

### <a name="supervision-policy"></a>Criteri di supervisione

È necessario creare criteri di supervisione in & la sicurezza centro conformità. Questi criteri definire quali comunicazioni e gli utenti sono soggetti a revisione all'interno dell'organizzazione, impostare condizioni personalizzate che devono soddisfare le comunicazioni e specifica che deve eseguire le revisioni. Gli utenti inclusi nel revisione controllo gruppo di ruoli è possibile impostare i criteri e chiunque disponga di questo ruolo assegnato possono accedere alla pagina di supervisione in dati di Governance di & la protezione di Office 365 centro conformità.

### <a name="supervised-users"></a>Utenti sorvegliati

Prima di iniziare a utilizzare supervisione, sarà necessario determinare chi avrà le comunicazioni riviste. Nel criterio, si utilizzerà gli indirizzi di posta elettronica utente per identificare i singoli utenti o gruppi di utenti a controllare. Alcuni esempi di questi gruppi sono Office 365 gruppi, liste di distribuzione basato su Exchange e canali Teams Microsoft. È inoltre possibile escludere utenti o gruppi specifici da supervisione inclusi all'interno di un gruppo sorvegliato o un elenco di gruppi.

> [!IMPORTANT]
> Tutti gli utenti monitorati da criteri di supervisione devono disporre di una licenza di Office 365 Enterprise E3 con il componente aggiuntivo avanzate conformità o da includere in una sottoscrizione a Office 365 Enterprise E5. Se non sono un piano di E5 Enterprise esistente e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Reviewers

Quando si crea un criterio di supervisione, se ne determinerà l'utente che eseguirà le valutazioni dei messaggi di utenti controllati. Nel criterio, si utilizzerà gli indirizzi di posta elettronica utente per identificare i singoli utenti o gruppi di utenti di controllare le comunicazioni controllate.

### <a name="groups-for-supervised-users-and-reviewers"></a>Gruppi controllati gli utenti e i revisori

Per semplificare l'installazione, creare gruppi per gli utenti che dovranno le comunicazioni esaminata e per gli utenti che verranno controllare le comunicazioni. Se si sta utilizzando gruppi, potrebbe essere necessario diverse. Ad esempio, se si desidera monitorare le comunicazioni tra i due gruppi distinti di persone o se si desidera specificare un gruppo a cui non è continui a essere controllati.

### <a name="supported-communication-types"></a>Tipi di comunicazione supportate

Con i criteri di supervisione, è possibile scegliere di controllare i messaggi in uno o più delle seguenti piattaforme di comunicazione:

- **Messaggio di posta elettronica di exchange:** Le cassette postali ospitate in Exchange Online come parte della sottoscrizione a Office 365 sono tutte le possibilità di supervisione messaggio. Messaggi di posta elettronica e allegati corrispondenti alle condizioni di criteri di supervisione sono immediatamente disponibili per il monitoraggio e nei report di supervisione. Tipi di allegati supportati per la supervisione sono gli stessi [tipi di file supportati per i controlli contenuti regola Exchange mail flow](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).
- **Team Microsoft:** Comunicazioni di chat e gli allegati associati in canali Teams Microsoft pubblici e privati e singole chat possono essere controllati. Chat team corrispondenti alle condizioni di criteri di supervisione vengono elaborate ogni 24 ore e quindi sono disponibili per il monitoraggio e nei report di supervisione.
- **Terze parti:** Se hai importato i dati nelle cassette postali di Office 365 nella propria organizzazione, è possibile controllare le comunicazioni da terze parti (come da Facebook o raccolta). [Informazioni su come importare i dati 3rd parti in Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data).

### <a name="policy-settings"></a>Impostazioni dei criteri

#### <a name="direction"></a>Direction

Per impostazione predefinita, la condizione **è direzione** viene visualizzata e non possono essere rimosse. È possibile scegliere le impostazioni di comunicazione direzione in un criterio singolarmente o insieme:

- **In ingresso** - è possibile scegliere di **ingresso** per controllare le comunicazioni che vengono inviate **a** utenti che si è scelto di supervisione delle attività **da** utenti non inclusi nel criterio.
- **In uscita** - è possibile scegliere **in uscita** se si desidera esaminare communications inviati **da** utenti che si è scelto di supervisione delle attività **a** utenti non inclusi nel criterio.
- **Internal** - è possibile scegliere **Internal** per esaminare inviate le comunicazioni **tra** persone identificato nel criterio.

#### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

È possibile includere i tipi di informazioni riservate come parte dei criteri di supervisione. Tipi di informazioni riservate sono entrambi tipi di dati predefinite o personalizzate che consentono di identificare e proteggere i numeri di carta di credito, numeri conto bancario, numeri di passaporto e altro ancora. Come parte di Office 365 [prevenzione della perdita di dati (DLP)](data-loss-prevention-policies.md), la configurazione di informazioni riservate può sfruttare modelli, prossimità caratteri, livelli di probabilità e i tipi di dati personalizzati per individuare e contrassegnare il contenuto che può essere riservato. I tipi di informazioni riservate predefiniti sono:

- Finanziari
- Medici e integrità
- Privacy
- Tipo di informazioni personalizzate

Per ulteriori informazioni sui dettagli delle informazioni riservate e i modelli inclusi i tipi di predefiniti, vedere [cercare i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).

#### <a name="custom-keyword-dictionaries"></a>Dizionari personalizzati parola chiave

Configurare i dizionari personalizzati parola chiave (o dizionari) può fornire gestione semplificata delle parole chiave specifiche per la propria organizzazione o del settore e può supportare fino a 100.000 termini al dizionario. Se necessario, è possibile applicare più dizionari personalizzati parola chiave per un singolo criterio o dispone di un dizionario singola parola chiave per ogni criterio. Questi dizionari vengono assegnati nei criteri di supervisione e possono essere originati da un file (ad esempio, un elenco con estensione csv o file con estensione txt) o da un elenco è possibile [inserire direttamente in un cmdlet di PowerShell](create-a-keyword-dictionary.md).

#### <a name="conditional-settings"></a>Impostazioni condizionali

Le condizioni che scelto per il criterio verranno applicata alle comunicazioni provenienti da origini di posta elettronica sia 3rd parti all'interno dell'organizzazione (come da Facebook o raccolta).

Nella tabella seguente vengono illustrati più relativi ogni condizione.
  
|**Condizione**|**Come utilizzare la condizione**|
|:-----|:-----|
|Messaggio ricevuto da uno di questi domini  <br><br> Messaggio non viene ricevuto da uno di questi domini | Per applicare i criteri per domini specifici vengono incluse o escluse in un messaggio ricevuto, immettere ogni dominio e separare più domini con una virgola. Ogni dominio immesso verrà applicata separatamente (solo uno di questi domini è necessario applicare per i criteri da applicare al messaggio). |
|Messaggio viene inviato a uno di questi domini  <br><br> Messaggio non verrà inviata a uno di questi domini | Per applicare i criteri per domini specifici vengono incluse o escluse in un messaggio inviato, immettere ogni dominio e separare più domini con una virgola. Ogni dominio immesso verrà applicata separatamente (solo uno di questi domini è necessario applicare per i criteri da applicare al messaggio). |
|Messaggio è classificato con una qualsiasi delle etichette di questo tipo  <br><br> Messaggio non è classificato con una qualsiasi delle etichette di questo tipo | Per applicare il criterio quando alcune etichette di conservazione vengono incluse o escluse in un messaggio. Etichette di conservazione devono essere configurate separatamente e possono essere impostate su etichette configurate come parte di questa condizione. Ogni etichetta è scegliere verrà applicata separatamente (solo uno di questi etichette necessario applicare per i criteri da applicare al messaggio). Per ulteriori informazioni sulla configurazione di etichette di conservazione, vedere [Overview of etichette di conservazione](https://docs.microsoft.com/office365/securitycompliance/labels).|
|Messaggio contiene una di queste parole  <br><br> Messaggio non include alcuna di queste parole | Per applicare il criterio quando alcune parole o frasi vengono incluse o escluse in un messaggio, immettere ogni parola o frase su una riga distinta. Verrà applicata separatamente ogni riga di parole si immette (solo uno di questi righe necessario applicare per i criteri da applicare al messaggio). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva [minuscole parole e frasi di messaggi di posta elettronica o gli allegati](supervision-policies.md#Matchwords).|
|Allegato include una di queste parole  <br><br> Allegato non include alcuna di queste parole | Per applicare il criterio quando alcune parole o frasi vengono incluse o escluse in un allegato del messaggio (ad esempio, un documento di Word), immettere ogni parola o frase su una riga distinta. Verrà applicata separatamente ogni riga di parole si immette (necessario applicare una sola riga per il criterio da applicare all'allegato). Per ulteriori informazioni sull'immissione di parole o frasi, vedere la sezione successiva [minuscole parole e frasi di messaggi di posta elettronica o gli allegati](supervision-policies.md#Matchwords).|
|Allegato corrisponde a uno qualsiasi di questi tipi di file  <br><br> Gli allegati sono Nessuno di questi tipi di file | Per controllare le comunicazioni che includono o escludono tipi specifici di allegati, immettere le estensioni di file (ad esempio .exe o PDF). Se si desidera includere o escludere più estensioni di file, immettere queste informazioni su righe separate. Estensione solo un allegato deve corrispondere per il criterio da applicare.|
|La dimensione del messaggio è maggiore di  <br><br> Dimensione del messaggio non è più grande | Per esaminare i messaggi di base in una determinata dimensione, utilizzare le condizioni per specificare la dimensione massima o minima che può essere un messaggio prima che sia soggetto a revisione. Ad esempio, se si specifica **dimensione dei messaggi è superiori a quelle** \> **MB 1.0**, tutti i messaggi che sono MB 1.01 e che verranno più soggette a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte questa condizione.|
|Allegato è più grande  <br><br> Non è più grande allegato | Per esaminare i messaggi in base alla dimensione degli allegati, specificare la dimensione massima o minima allegato può essere prima del messaggio e relativi allegati sono soggetti a revisione. Ad esempio, se si specifica **l'allegato è più grande** \> **2.0 MB**, tutti i messaggi con allegati MB 2.01 e failover saranno soggette a revisione. È possibile scegliere byte, kilobyte, megabyte o gigabyte questa condizione.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Corrispondenza di parole e frasi a messaggi di posta elettronica o allegati
<a name="Matchwords"> </a>

Verrà applicata separatamente ogni riga di parole si immette (una sola riga necessario applicare per la condizione dei criteri da applicare alla posta elettronica o allegato). Ad esempio, utilizziamo la condizione, **che messaggio contiene una di queste parole**, con il tipo"parole chiave" e "persona interna negoziazione" su righe separate. Il criterio verrà applicato a tutti i messaggi che includono il parola "un particolare tipo" o la frase "utente interno negoziazione". Solo una di queste parole o frasi deve essere eseguito per questa condizione dei criteri da applicare. Parole nel messaggio o allegato devono corrispondere esattamente quello inserito.
  
##### <a name="entering-multiple-conditions"></a>Immissione di più condizioni

Se si immettono più condizioni, Office 365 utilizza contemporaneamente tutte le condizioni per determinare quando applicare i criteri per gli elementi di comunicazione. Quando si imposta più condizioni, è necessario che vengano soddisfatti tutti per il criterio da applicare, a meno che non si immette un'eccezione. Si supponga, ad esempio, che è necessario creare un criterio che si applicano se un messaggio contiene la parola "commerciali" e maggiore di 2MB. Tuttavia, se anche il messaggio contiene le parole "Approvato da parte di Contoso finanziaria", il criterio non applicare. In questo modo, in questo caso, le tre condizioni sarebbero come indicato di seguito:
  
- **Messaggio contiene una di queste parole**, con le parole chiave "commerciali"

- **Dimensione del messaggio è superiori a quelle**con il valore di 2 MB

- Il **messaggio non include alcuna di queste parole**, con le parole chiave "Approvato dal team finanziari Contoso".

#### <a name="review-percentage"></a>Percentuale di revisione

È possibile specificare una percentuale di tutte le comunicazioni applicato un criterio di supervisione se si desidera ridurre la quantità di contenuto per la revisione. La percentuale di totale corrispondenti alle condizioni che scelto è in modo casuale verrà selezionare tale quantità di contenuto. Se si desidera che i revisori per esaminare tutti gli elementi, è possibile immettere **100%** nei criteri di supervisione.

## <a name="monitoring--managing"></a>Monitoraggio & gestione

I risultati dei criteri di supervisione del monitoraggio e l'applicazione di un tag di soluzione è facile e conveniente. È possibile visualizzare rapidamente lo stato di elementi revisionati, gli utenti e gruppi sotto controllo e gli utenti e gruppi designati come revisori.

### <a name="supervision-policy-dashboard"></a>Dashboard di criteri di supervisione

Il modo più semplice per gestire i rapporti Criteri di supervisione e risolvere gli elementi in sospeso consiste nell'utilizzare il dashboard di criteri di supervisione. Questo dashboard consente ai revisori di determinare rapidamente gli elementi che devono essere esaminato, esegue azioni su un elemento e controllare i risultati del precedentemente revisione e risoluzione degli elementi per ogni criterio di supervisione. È possibile accedere il dashboard di criteri di supervisione in & la protezione di Office 365 centro conformità a **supervisione** > *Del criterio personalizzato* > **aperto**.

#### <a name="dashboard-home"></a>Home page di dashboard

La pagina del dashboard **principale** ha diverse sezioni che consentono di eseguire rapidamente l'azione in Criteri di supervisione. È possibile:

- Esaminare rapidamente argomenti di rilievo risolti e in sospeso per la settimana
- Visualizzare un elenco di utenti sorvegliati e ai gruppi sorvegliati per il criterio selezionato
- Visualizzare un elenco dei revisori ed esaminare i team per il criterio selezionato
- Vedere quali piattaforme di comunicazione con contenuto sotto controllo per il criterio.

#### <a name="supervise-tab"></a>Scheda della supervisione delle attività

La scheda **Supervise** viene identificata dove revisori possono eseguire l'azione necessaria e risolvere gli elementi per il criterio selezionato. È possibile:

- Filtrare elementi in sospeso, compatibile con, non è conforme e ambigui
- Contrassegnare un singolo elemento come compatibile con, non è conforme o ambigui. È inoltre possibile registrare un commento con l'elemento per aiutare a chiarire il tag azione eseguita.
- Blocco contrassegnare più elementi come compatibile con, non è conforme o ambigui. È inoltre possibile registrare un commento con più elementi per aiutare a chiarire il tag azione eseguita.
- Visualizzare la cronologia di tagging di un singolo elemento, tra cui persona che ha risolto l'elemento, la data e ora dell'azione, il tag di soluzione e gli eventuali commenti inclusi.
- Riclassificare elementi precedentemente revisionati come compatibile con, non è conforme o ambigui. È inoltre possibile registrare un commento con uno o più elementi per aiutare a chiarire l'azione riclassificazione eseguita.

#### <a name="resolved-items-tab"></a>Risolto scheda elementi

Nella scheda **Elementi risolto** è dove i revisori possono visualizzare tutti gli elementi precedentemente risolti per il criterio selezionato. È possibile:

- Visualizzare e ordinare l'oggetto, mittente e data degli elementi risolti rapidamente.
- Visualizzare la cronologia di classificazione e i commenti di un qualsiasi elemento selezionato

### <a name="other-ways-to-review-items"></a>Altri modi per controllare gli elementi

Se i revisori preferisce non utilizzare il dashboard di supervisione in Office 365, sono inoltre disponibili altre opzioni per esaminare e gestire elementi raccolti da criteri di supervisione.

#### <a name="outlook-on-the-web"></a>Outlook sul web

Gli utenti designati come i revisori nei criteri di supervisione possono utilizzare Outlook sul web per esaminare e risolvere gli elementi di supervisione. Il componente aggiuntivo per la supervisione viene installato automaticamente in Outlook sul web per tutti i revisori specificato nel criterio. È necessaria alcuna configurazione aggiuntiva dall'organizzazione per le cartelle condivise criteri supervisione sia disponibile per i revisori configurati.

Utilizzo di Outlook sul web, i revisori possono:

- Visualizzare gli elementi filtrati in base allo stato compatibile con, non Compatible, ambigui e risolto
- Contrassegnare un singolo elemento come compatibile con, non Compatible, ambigui o risolto. È inoltre possibile registrare un commento con l'elemento per aiutare a chiarire il tag azione eseguita.
- Visualizzare la cronologia di tagging di un singolo elemento, tra cui persona che ha risolto l'elemento, la data e ora dell'azione, il tag di soluzione e gli eventuali commenti inclusi.
- Riclassificare elementi precedentemente revisionati come compatibile con, non è conforme o ambigui. È inoltre possibile registrare un commento con singoli elementi per aiutare a chiarire l'azione riclassificazione eseguita.

#### <a name="microsoft-outlook"></a>Microsoft Outlook

Per esaminare communications identificato da un criterio di supervisione, i revisori inoltre possono utilizzare il componente aggiuntivo per la supervisione per Microsoft Outlook. Tuttavia, i revisori devono eseguire alcuni passaggi per installare la versione desktop di Outlook. Per informazioni dettagliate sull'installazione di supervisione componente aggiuntivo per Outlook, vedere [configurare i criteri di supervisione](configure-supervision-policies.md).

Utilizzo di Outlook, i revisori possono:

- Visualizzare gli elementi filtrati in base allo stato compatibile con, non Compatible, ambigui e risolto
- Contrassegnare un singolo elemento come compatibile con, non Compatible, ambigui o risolto. È inoltre possibile registrare un commento con l'elemento per aiutare a chiarire il tag azione eseguita.
- Visualizzare la cronologia di tagging di un singolo elemento, tra cui persona che ha risolto l'elemento, la data e ora dell'azione, il tag di soluzione e gli eventuali commenti inclusi.
- Riclassificare elementi precedentemente revisionati come compatibile con, non è conforme o ambigui. È inoltre possibile registrare un commento con singoli elementi per aiutare a chiarire l'azione riclassificazione eseguita.

## <a name="reporting"></a>Creazione di rapporti

Utilizzare i rapporti di supervisione esaminare l'attività di verifica a livello di criteri e revisore. Per ogni criterio, è inoltre possibile visualizzare le statistiche live sullo stato corrente dell'attività di verifica. È possibile utilizzare i rapporti di supervisione:
  
- Verificare che i criteri funzionino come previsto.
- Vengono identificate Scopri tutto quanti communications per la revisione.
- Scoprire esaminare il numero non sono compatibile con le comunicazioni e quelli che stanno passando. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.

### <a name="view-the-supervision-report"></a>Visualizzare il report di supervisione

1. Accedere a [protezione & centro conformità](https://protection.office.com/) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365 con le autorizzazioni per visualizzare i report di supervisione.
2. Accedere a uno di **report** \> **Dashboard** o **supervisione**. Verrà visualizzato un supervisione reporting widget con un riepilogo delle attività di criteri di supervisione corrente.
3. Selezionare widget **supervisione** per aprire la pagina report dettagliato.

> [!NOTE]
> Se non si è in grado di accedere alla pagina di **report** , verificare che l'utente sia un membro del gruppo di ruoli revisione supervisione come illustrato in [rendere supervisione disponibili nell'organizzazione](configure-supervision-policies.md). L'inclusione nel consente di gruppo ruolo creare e gestire supervisione criteri ed eseguire il report.
  
### <a name="how-to-use-the-report"></a>Come utilizzare i report

Quando un criterio di supervisione identifica un messaggio di comunicazione per la revisione, il messaggio di posta elettronica viene recapitato nella cartella di supervisione del revisore in Outlook e Outlook web app. In questo report sono elencati il nome di ogni criterio e il numero delle comunicazioni in ogni fase del processo di revisione.
  
Utilizzare il report per:
  
- Visualizzare i dati per tutti i criteri specifici o.
- Visualizzare i dati raggruppati per tipo di tag (ad esempio conforme, Questionable e così via), revisore o tipo di messaggio.
- Esportare i dati in un file CSV sulla base data dell'attività, criteri e attività revisore.
- Filtrare i dati in base a data dell'attività, tipo di tag, revisore e tipo di messaggio.

Di seguito vengono illustrati i valori che potrebbe essere presente nella colonna **tipo di Tag** .
  
|**Tipo di tag**|**Significato**|
|:-----|:-----|
| Non è stato rivisto | Il numero di messaggi di posta elettronica non ancora riviste. Questi messaggi di posta elettronica sono in attesa di revisione in Office 365 supervisione dashboard o nella cartella di supervisione del revisore di Outlook/Outlook Web App.|
| Compatible | Il numero di messaggi di posta elettronica esaminato e contrassegnato come compatibile. Questi messaggi è ancora necessario risolvere. |
| Ambigui | Il numero di messaggi di posta elettronica esaminato e contrassegnati ambigui. Questo funge da un contrassegno; altri revisori consentono di controllare se un messaggio di posta elettronica deve indagini per motivi di conformità. Questi messaggi è ancora necessario risolvere. |
| Non conforme (attivo) | Il numero di messaggi di posta elettronica non conforme che sono attualmente analisi dei revisori. |
| Non è compatibile (risolti) | Il numero di messaggi di posta elettronica non compatibili con i revisori esaminate e risolti. |
| Frequenza di accessi al criterio | (Ogni giorno) il numero totale di messaggi da Exchange, team e le origini dati di terze parti corrispondenti a uno o più condizioni definite nei criteri di supervisione |
| In rientra nell' | (Ogni giorno) il numero totale di messaggi da Exchange, team e le origini dati di terze parti analizzate dai criteri di supervisione |
| Risolto | Il numero totale di messaggi da Exchange, team e le origini dati di terze parti che sono state classificate come **risolto**|

> [!NOTE]
> Criteri di supervisione devono innanzitutto effettuare il provisioning prima che verranno visualizzate nel report. Inoltre, se vengono eliminati i criteri, i dati cronologici comunque visualizzati. Tuttavia, viene indicati come "criterio inesistente" e la funzione di **esportazione** non è disponibile.

## <a name="auditing"></a>Controllo

In alcuni casi, è necessario fornire informazioni alla normativa o i revisori di conformità per dimostrare supervisione delle comunicazioni e delle attività dei dipendenti. Può trattarsi di un riepilogo di tutte le attività di supervisione associati a un criterio definito o in qualsiasi momento è stato modificato o aggiornato un criterio di supervisione. Criteri di supervisione sono incorporate audit trail per la preparazione completata per revisioni interne o esterne. È possibile dimostrare dimostrazione delle procedure di supervisione con una cronologia controllo dettagliata di ogni azione monitorati da criteri di supervisione.

Le seguenti attività di criteri di supervisione vengono controllate e possono essere visualizzate utilizzando i registri di controllo di Office 365 unified:

|**Attività**|**Comandi associati**|
|:-----|:-----|
| Creazione di un criterio | Nuovo SupervisoryReviewPolicy <br> Nuovo SupervisoryReviewRule |
| Modifica di un criterio | Set-SupervisoryReviewPolicy <br> Set-SupervisoryReviewRule |
| Eliminazione di un criterio| Remove-SupervisoryReviewPolicy |

Audit possono essere recuperati utilizzando la funzione di ricerca del Registro di controllo unificato oppure utilizzando il cmdlet di PowerShell [UnifiedAuditLog di ricerca](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) .

Ad esempio, nell'esempio seguente restituisce le attività per la tutte le autorità di controllo verifica attività (criteri e regole) e vengono elencate le informazioni dettagliate per ogni:

```
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"} | fl CreationDate,Operations,UserIds,AuditData 
```

Oltre alle informazioni fornite nel supervisione rapporti e registri, è possibile anche utilizzare il cmdlet di PowerShell [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewactivity?view=exchange-ps) per restituire un elenco dettagliato completo di supervisione tutte le attività del criterio.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Per avviare la configurazione di criteri di supervisione per l'organizzazione, vedere [configurare i criteri di supervisione](configure-supervision-policies.md).