---
title: Panoramica relativa ai criteri di prevenzione della perdita di dati
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/29/2019
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Con un criterio di prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365, è possibile identificare, monitorare e proteggere automaticamente le informazioni riservaTe in Office 365.
ms.openlocfilehash: 4117a99afc804fd397deb45087c5058077f9ff60
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000019"
---
# <a name="overview-of-data-loss-prevention-policies"></a>Panoramica relativa ai criteri di prevenzione della perdita di dati

Per ottenere la conformità agli standard aziendali e alle normative di settore, le organizzazioni devono proteggere le informazioni riservate e impedirne la divulgazione accidentale. Le informazioni riservate che si desidera proteggere dalla divulgazione all'esterno dell'organizzazione possono essere, ad esempio, dati finanziari o informazioni di identificazione personale (PII) come numeri di carta di credito, numeri di previdenza sociale o cartelle cliniche. Con un criterio di prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365, è possibile identificare, monitorare e proteggere automaticamente le informazioni riservaTe in Office 365.
  
Utilizzando un criterio DLP, è possibile:
  
- **Identificare informazioni riservate in numerosi percorsi, ad esempio Exchange Online, SharePoint Online, OneDrive for business e Microsoft teams.**
    
    Ad esempio, è possibile identificare qualsiasi documento contenente un numero di carta di credito memorizzato in qualsiasi sito di OneDrive for business oppure è possibile monitorare solo i siti di OneDrive di persone specifiche.
    
- **Impedire la condivisione accidentale di informazioni riservate**. 
    
    Ad esempio, è possibile identificare qualsiasi documento o messaggio di posta elettronica contenente un record di integrità condiviso con persone esterne all'organizzazione e quindi bloccare automaticamente l'accesso a tale documento o bloccare l'invio della posta elettronica.
    
- **Monitorare e proteggere le informazioni riservate nelle versioni desktop di Excel, PowerPoint e Word.**
    
    Proprio come in Exchange Online, SharePoint Online e OneDrive for business, questi programmi desktop di Office includono le stesse funzionalità per identificare le informazioni riservate e applicare i criteri DLP. DLP fornisce un monitoraggio continuo quando le persone condividono contenuto in queste applicazioni di Office.
    
- **Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro.**
    
    È possibile fornire agli utenti informazioni sui criteri DLP e aiutarli a garantire la conformità senza interrompere il lavoro. Ad esempio, se un utente tenta di condividere un documento che include informazioni riservate, il criterio DLP invia una notifica tramite posta elettronica e mostra un suggerimento per i criteri nell'ambito della raccolta documenti che consente all'utente di ignorare il criterio per motivi aziendali. Gli stessi suggerimenti per i criteri vengono visualizzati anche in Outlook sul Web, Outlook, Excel, PowerPoint e Word.
    
- **Visualizzare i report DLP che mostrano il contenuto che corrisponde ai criteri DLP dell'organizzazione.**
    
    Per valutare il livello di conformità di un'organizzazione al criterio DLP, è possibile visualizzare il numero relativo alle corrispondenze di criteri e regole nel tempo. Se un criterio DLP consente agli utenti di ignorare un suggerimento per i criteri e di segnalare un falso positivo, è anche possibile visualizzare gli utenti segnalati.
    
È possibile creare e gestire i criteri DLP nella pagina prevenzione della perdita di dati nel centro &amp; sicurezza e conformità di Office 365.
  
![Pagina di prevenzione della perdita di dati nel centro &amp; sicurezza e conformità di Office 365](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>Contenuto di un criterio DLP

In un criterio DLP sono disponibili alcuni elementi di base:
  
- Dove proteggere il contenuto, ad **** esempio i siti di Exchange Online, SharePoint Online e OneDrive for business, nonché le chat e i canali di Microsoft teams. 
    
- Quando e in che modo proteggere il contenuto, applicando **regole** composte da: 
    
  - **Condizioni** il contenuto deve corrispondere prima che la regola venga applicata, ad esempio solo per il contenuto contenente i numeri di previdenza sociale condivisi con utenti esterni all'organizzazione. 
    
  - **Azioni** che la regola deve effettuare automaticamente quando vengono rilevati contenuti corrispondenti alle condizioni: ad esempio, è possibile bloccare l'accesso al documento e inviare una notifica tramite posta elettronica sia all'utente che al responsabile della conformità. 
    
È possibile utilizzare una regola per rispondere a uno specifico requisito di conformità, per poi utilizzare un criterio DLP per raggruppare i requisiti di sicurezza più comuni, ad esempio, tutte le regole necessarie per ottenere la conformità a una normativa specifica.
  
È possibile che si disponga di un criterio DLP che consente di rilevare la presenza di informazioni soggette ai moduli di conformità Health Insurance Portability and Accountability Act (HIPAA). Questo criterio DLP potrebbe contribuire alla protezione dei dati HIPAA (cosa) in tutti i siti di SharePoint Online e in tutti i siti di OneDrive for business (dove), individuando qualsiasi documento contenente queste informazioni riservate condivise con persone esterne all'organizzazione (la condizioni) e quindi il blocco dell'accesso al documento e l'invio di una notifica (le azioni). I requisiti vengono archiviati come regole individuali e raggruppati come criterio DLP per semplificare la gestione e la creazione di report.
  
![Diagramma che mostra il criterio DLP contenente posizioni e regole](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>Percorsi

Un criterio DLP è in grado di individuare e proteggere le informazioni riservate in Office 365, se tali informazioni sono disponibili in Exchange Online, SharePoint Online, OneDrive for business o Microsoft teams. È possibile scegliere di proteggere il contenuto in messaggi di posta elettronica di Exchange, chat e canali di Microsoft teams e tutte le raccolte di SharePoint o OneDrive oppure selezionare percorsi specifici per un criterio.
  
![Opzioni per la posizione in cui è possibile applicare un criterio DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
Si noti che se si sceglie di includere o escludere specifici siti di SharePoint o account di OneDrive, un criterio DLP può contenere non più di 100 tali inclusioni ed esclusioni. Anche se questo limite esiste, è importante comprendere che è possibile superare questo limite applicando un criterio a livello di organizzazione o un criterio che si applica a intere posizioni.
  
### <a name="rules"></a>Regole

Le regole sono ciò che impone i requisiti aziendali per il contenuto dell'organizzazione. Un criterio include una o più regole e ciascuna di queste è composta da condizioni e azioni. Per ogni regola, le azioni vengono eseguite automaticamente, non appena vengono soddisfatte le condizioni. Le regole vengono eseguite sequenzialmente, a partire dalla regola con priorità più alta in ogni criterio.
  
Una regola fornisce anche opzioni per informare gli utenti (con suggerimenti per i criteri e le notifiche tramite posta elettronica) e gli amministratori (con i rapporti sugli incidenti di posta elettronica) che il contenuto ha confrontato la regola.
  
Ecco i componenti di una regola, ognuno illustrato di seguito.
  
![Sezioni dell'editor delle regole DLP](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condizioni

Le condizioni sono importanti perché determinano i tipi di informazioni che si stanno cercando e quando intraprendere un'azione. Ad esempio, è possibile scegliere di ignorare il contenuto contenente numeri di passaporto, a meno che il contenuto non contenga più di dieci numeri e sia condiviso con persone esterne all'organizzazione.
  
Le condizioni si concentrano sul **contenuto**, ad esempio sui tipi di informazioni riservate che si sta cercando e sul **contesto**, ad esempio il documento con cui è condiviso. È possibile utilizzare le condizioni per assegnare azioni diverse a livelli di rischio diversi; ad esempio, i contenuti riservati condivisi all'interno dell'organizzazione potrebbero essere caratterizzati da un rischio inferiore rispetto ai contenuti riservati condivisi con utenti esterni all'organizzazione. 
  
![Elenco che mostra le condizioni DLP disponibili](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
Le condizioni disponibili a questo punto consentono di determinare se:
  
- Content contiene un tipo di informazioni riservate.
    
- Il contenuto contiene un'etichetta. Per ulteriori informazioni, vedere la sezione riportata [di seguito utilizzando un'etichetta come condizione in un criterio DLP](#using-a-label-as-a-condition-in-a-dlp-policy).
    
- Il contenuto viene condiviso con utenti esterni o interni alla propria organizzazione.
    
#### <a name="types-of-sensitive-information"></a>Tipi di informazioni riservate

Un criterio DLP consente di proteggere le informazioni riservate, definite come **tipo di informazioni riservate**. Office 365 include definizioni per molti tipi di informazioni riservate comuni in molte aree geografiche diverse pronte per l'uso, ad esempio un numero di carta di credito, numeri di conto corrente bancario, numeri di ID nazionali e numeri di passaporto. 
  
![Elenco dei tipi di informazioni riservate disponibili](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Quando un criterio DLP Cerca un tipo di informazioni riservate, ad esempio un numero di carta di credito, non cerca semplicemente un numero di 16 cifre. Ogni tipo di informazioni riservate viene definito e rilevato utilizzando una combinazione dei seguenti elementi:
  
- Parole chiave
    
- Funzioni interne relative a checksum di convalida o alla composizione
    
- Valutazione delle espressioni ricorrenti al fine di individuare corrispondenze del motivo
    
- Valutazione di altri contenuti
    
In questo modo, il rilevamento DLP raggiunge un livello elevato di precisione riducendo il numero di falsi positivi che possono interrompere il lavoro delle persone.
  
#### <a name="actions"></a>Azioni

Quando il contenuto corrisponde a una condizione in una regola, è possibile applicare azioni per proteggere automaticamente il contenuto.
  
![Elenco di azioni DLP disponibili](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Con le azioni ora disponibili, è possibile:
  
- **Limitare l'accesso al contenuto** Per il contenuto del sito, ciò significa che le autorizzazioni per il documento sono limitate per tutti, tranne l'amministratore principale della raccolta siti, il proprietario del documento e la persona che ha modificato il documento. Questi utenti possono rimuovere le informazioni riservate dal documento o intraprendere altre azioni di correzione. Quando il documento è conforme, vengono automaticamente ripristinate le autorizzazioni originali. Quando l'accesso a un documento è bloccato, il documento viene visualizzato con un'icona particolare di suggerimento per i criteri nella raccolta sul sito. 
    
    ![Suggerimento per i criteri con accesso al documento bloccato](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    Per il contenuto della posta elettronica, questa azione blocca il messaggio da inviare. A seconda del modo in cui la regola DLP è configurata, il mittente Visualizza un rapporto di MANCAto reCAPITO o (se la regola utilizza una notifica) un suggerimento per i criteri e/o la notifica tramite posta elettronica.
    
    ![Avviso che i destinatari non autorizzati devono essere rimossi dal messaggio](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notifiche degli utenti e sostituzioni degli utenti

È possibile utilizzare le notifiche e le sostituzioni per istruire gli utenti sui criteri DLP e aiutarli a rimanere conformi senza bloccarne il lavoro. Ad esempio, se un utente tenta di condividere un documento che include informazioni riservate, il criterio DLP invia una notifica tramite posta elettronica e mostra un suggerimento per i criteri nell'ambito della raccolta documenti che consente all'utente di ignorare il criterio per motivi aziendali.
  
![Notifiche utente e override delle sezioni dell'editor delle regole DLP](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
Il messaggio di posta elettronica può informare la persona che ha inviato, condiviso o modificato l'ultimo contenuto e, per il contenuto del sito, l'amministratore principale della raccolta siti e il proprietario del documento. Inoltre, è possibile aggiungere o rimuovere chiunque scegliere dalla notifica di posta elettronica.
  
Oltre a inviare una notifica tramite posta elettronica, una notifica utente visualizza un suggerimento per i criteri:
  
- In Outlook e Outlook sul Web.
    
- Per il documento in un sito di SharePoint Online o di OneDrive for business.
    
- In Excel, PowerPoint e Word, quando il documento viene archiviato in un sito incluso in un criterio DLP.
    
La notifica di posta elettronica e il suggerimento per i criteri spiegano perché i conflitti di contenuto con un criterio DLP. Se desiderato, la notifica di posta elettronica e il suggerimento per i criteri possono consentire agli utenti di ignorare una regola segnalando un falso positivo o fornendo una motivazione aziendale. In questo modo, è possibile illustrare agli utenti le caratteristiche dei criteri DLP e la loro modalità di applicazione senza impedire alle persone di eseguire le proprie attività. Le informazioni sulle sostituzioni e sui falsi positivi sono abilitate anche per la creazione di report (vedere le informazioni sui report DLP riportate in basso) e incluse nei rapporti sulle operazioni non consentite (sezione seguente), in modo che il responsabile della conformità possa consultarle regolarmente.
  
Di seguito è riportato l'aspetto di un suggerimento per i criteri in un account di OneDrive for business.
  
![Suggerimento per i criteri per un documento in un account di OneDrive](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>Rapporti operazioni non consentite

Quando viene confrontata una regola, è possibile inviare un rapporto eventi imprevisti al responsabile della conformità (o a qualsiasi persona scelta) con i dettagli dell'evento. Questo report include informazioni sull'elemento corrispondente, sul contenuto effettivo corrispondente alla regola e sul nome della persona che ha modificato il contenuto. Per i messaggi di posta elettronica, il report include anche come allegato il messaggio originale che corrisponde a un criterio DLP.
  
![Pagina per la configurazione di rapporti operazioni non consentite](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>Raggruppamento e operatori logici

Il criterio DLP è spesso un requisito semplice, ad esempio per identificare tutto il contenuto che contiene un numero di preVidenza sociale degli Stati Uniti. Tuttavia, in altri scenari, il criterio DLP potrebbe dover identificare dati definiti in modo più definito.
  
Ad esempio, per identificare il contenuto soggetto all'US Health Insurance Act (HIPAA), è necessario cercare:
  
- Contenuto che contiene tipi specifici di informazioni riservate, ad esempio un numero di preVidenza sociale statunitense o un numero di Drug Enforcement Agency (DEA).
    
    E
    
- Contenuto più difficile da identificare, ad esempio le comunicazioni relative alla cura o alle descrizioni dei servizi medici forniti. Se si identifica questo contenuto, è necessario che le parole chiave corrispondano a liste di parola chiavi molto estese, ad esempio la classificazione internazionale delle malattie (ICD-9-CM o ICD-10-CM).
    
È possibile identificare facilmente tali dati definiti in modo definito utilizzando il raggruppamento e gli operatori logici (e, o). Quando si crea un criterio DLP, è possibile:
  
- Tipi di informazioni riservate del gruppo.
    
- Scegliere l'operatore logico tra i tipi di informazioni riservate all'interno di un gruppo e tra i gruppi stessi.
    
### <a name="choosing-the-operator-within-a-group"></a>Scelta dell'operatore all'interno di un gruppo

All'interno di un gruppo, è possibile scegliere se una o tutte le condizioni del gruppo devono essere soddisfatte per il contenuto in modo che corrisponda alla regola.
  
![Gruppo che Mostra gli operatori all'interno del gruppo](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Aggiunta di un gruppo

È possibile aggiungere rapidamente un gruppo, che può avere le proprie condizioni e l'operatore all'interno del gruppo.
  
![Pulsante Aggiungi gruppo](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Scelta dell'operatore tra gruppi

Tra i gruppi, è possibile scegliere se le condizioni di un solo gruppo o di tutti i gruppi devono essere soddisfatte per il contenuto in modo che corrisponda alla regola.
  
Ad esempio, il criterio **HIPAA americano** incorporato ha una regola che utilizza un operatore **and** tra i gruppi in modo che identifichi il contenuto che contiene: 
  
- dagli identificatori di informazioni **personali** del gruppo (almeno un numero SSN **o** un numero dea) 
    
    **E**
    
- dal gruppo **termini medici** (almeno una parola chiave ICD-9-cm **o** la parola chiave ICD-10-cm) 
    
![Gruppi che mostrano l'operatore tra gruppi](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>Priorità in base alla quale vengono elaborate le regole

Quando si creano regole in un criterio, a ogni regola viene assegnata una priorità nell'ordine in cui è stata creata, ovvero la regola creata per primo ha priorità assoluta, la regola creata secondo ha una seconda priorità e così via. Dopo aver creato una regola, non è possibile modificare la priorità, tranne eliminando e ricrearla.
  
![Regole in ordine di priorità](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
Quando il contenuto viene valutato in base alle regole, le regole vengono elaborate in ordine di priorità. Se il contenuto corrisponde a più regole, le regole vengono elaborate in ordine di priorità e l'azione più restrittiva viene applicata. Ad esempio, se il contenuto corrisponde a tutte le regole seguenti, la regola 3 viene applicata perché è la regola più alta, la più restrittiva:
  
- Regola 1: notifica solo agli utenti
    
- Regola 2: notifica agli utenti, limita l'accesso e consente le sostituzioni degli utenti
    
- Regola 3: notifica agli utenti, limita l'accesso e non consente le sostituzioni degli utenti
    
- Regola 4: notifica solo agli utenti
    
- Regola 5: limita l'accesso
    
- Regola 6: notifica agli utenti, limita l'accesso e non consente le sostituzioni degli utenti
    
In questo esempio, si noti che le corrispondenze per tutte le regole vengono registrate nei registri di controllo e visualizzate nei rapporti DLP, anche se viene applicata solo la regola più restrittiva.
  
In relazione ai suggerimenti per i criteri, tenere presente che:
  
- Verrà visualizzato solo il suggerimento per i criteri dalla priorità più alta e la regola restrittiva. Ad esempio, un suggerimento per i criteri di una regola che impedisce l'accesso al contenuto viene sovrapposto a un suggerimento per i criteri di una regola che invia semplicemente una notifica. Ciò impedisce che l'utente visualizzi una cascata di suggerimenti per i criteri.
    
- Se i suggerimenti per i criteri nella regola più restrittiva consentono all'utente di ignorare la regola, in questo modo vengono ignorate anche le altre regole per le quali è stata rilevata una corrispondenza del contenuto.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Regole di ottimizzazione per rendere più facile o più difficile la corrispondenza

Dopo che la gente ha creato e attivato i propri criteri DLP, a volte si ricorre a questi problemi:
  
- Un numero eccessivo di contenuti che **non sono** informazioni riservate corrisponde alle regole, ovvero troppi falsi positivi. 
    
- Troppo poco contenuto con **** informazioni riservate corrisponde alle regole-in altre parole, le azioni protettive non vengono applicate alle informazioni riservate. 
    
Per risolvere questi problemi, è possibile ottimizzare le regole regolando il numero di istanze e la precisione della corrispondenza per rendere più difficile o più facile per il contenuto soddisfare le regole. Ogni tipo di informazioni riservate utilizzato in una regola dispone sia di un conteggio delle istanze che di una corrispondenza accurata.
  
### <a name="instance-count"></a>Numero di istanze

Il numero di istanze indica semplicemente il numero di occorrenze di un tipo specifico di informazioni riservate che devono essere presenti per il contenuto in modo che corrisponda alla regola. Ad esempio, il contenuto corrisponderà alla regola indicata di seguito se tra 1 e 9 unici Stati Uniti o Regno Unito sono identificati i numeri di passaporto.
  
Si noti che il numero di istanze **** include solo corrispondenze univoche per tipi di informazioni riservate e parole chiave. Ad esempio, se un messaggio di posta elettronica contiene 10 occorrenze dello stesso numero di carta di credito, queste 10 occorrenze contano come una singola istanza di un numero di carta di credito. 
  
Per utilizzare il numero di istanze per ottimizzare le regole, le linee guida sono semplici:
  
- Per semplificare la corrispondenza della regola, ridurre il numero **minimo** e/o aumentare il numero **massimo** . È inoltre possibile impostare **Max** su **any** eliminando il valore numerico. 
    
- Per rendere la regola più difficile da eguagliare, aumentare il numero **minimo** . 
    
In genere, le azioni meno restrittive, ad esempio l'invio delle notifiche degli utenti, vengono utilizzate in una regola con un numero di istanze inferiore (come 1-9). E si utilizzano azioni più restrittive, ad esempio la limitazione dell'accesso al contenuto senza consentire le sostituzioni degli utenti, in una regola con un numero di istanze più alto (come 10-any).
  
![Conteggi delle istanze nell'editor delle regole](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisione della corrispondenza

Come descritto in questo esempio, viene definito e rilevato un tipo di informazioni riservate utilizzando una combinazione di diversi tipi di evidenza. In genere, un tipo di informazioni riservate è definito da più combinazioni tali, denominate modelli. Un modello che richiede meno evidenza ha un'accuratezza della corrispondenza inferiore (o un livello di confidenza), mentre un modello che richiede una maggiore evidenza ha un'accuratezza della corrispondenza superiore (o un livello di confidenza). Per ulteriori informazioni sui modelli effettivi e i livelli di sicurezza utilizzati da ogni tipo di informazione riservata, vedere [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
Ad esempio, il tipo di informazioni riservate denominato numero di carta di credito è definito da due modelli:
  
- Un modello con una confidenza del 65% che richiede:
    
  - Numero nel formato di un numero di carta di credito.
    
  - Numero che passa il checksum.
    
- Un modello con una confidenza del 85% che richiede:
    
  - Numero nel formato di un numero di carta di credito.
    
  - Numero che passa il checksum.
    
  - Una parola chiave o una data di scadenza nel formato corretto.
    
È possibile utilizzare questi livelli di confidenza (o la corrispondenza accuratezza) nelle regole. In genere, si utilizzano azioni meno restrittive, ad esempio l'invio di notifiche degli utenti, in una regola con una precisione di corrispondenza inferiore. E si utilizzano azioni più restrittive, ad esempio la limitazione dell'accesso al contenuto senza consentire le sostituzioni degli utenti, in una regola con una maggiore precisione della corrispondenza.
  
È importante comprendere che quando un tipo specifico di informazioni riservate, ad esempio un numero di carta di credito, viene identificato nel contenuto, viene restituito un solo livello di confidenza:
  
- Se tutte le corrispondenze sono per un singolo modello, viene restituito il livello di probabilità per il modello.
    
- Se sono presenti corrispondenze per più di un modello (ad esempio, vi sono corrispondenze con due livelli di confidenza diversi), viene restituito un livello di confidenza superiore a quello dei singoli modelli solo. Questa è la parte più difficile. Ad esempio, per una carta di credito, se vengono confrontati entrambi i modelli di 65% e 85%, il livello di probabilità restituito per il tipo di informazioni riservate è superiore al 90% perché più prove significano maggiore sicurezza.
    
Pertanto, se si desidera creare due regole mutualmente esclusive per le carte di credito, una per l'accuratezza della corrispondenza del 65% e una per l'accuratezza della corrispondenza del 85%, gli intervalli per la precisione delle corrispondenze sono simili al seguente. La prima regola preleva solo le corrispondenze del modello 65%. La seconda regola preleva le corrispondenze con almeno **una** corrispondenza del 85% e **potenzialmente può avere** altre corrispondenze con confidenza inferiore. 
  
![Due regole con intervalli diversi per l'accuratezza delle corrispondenze](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Per questi motivi, le linee guida per la creazione di regole con precisione di corrispondenza diverse sono le seguenti:
  
- Il livello di confidenza più basso utilizza in genere lo stesso valore per **min** e **Max** (non un intervallo). 
    
- Il livello di confidenza più elevato è in genere un intervallo da appena sopra il livello di confidenza inferiore a 100.
    
- Qualsiasi livello di confidenza tra i livelli di riservatezza in genere si trova appena al di sotto del livello di confidenza più alto.
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Utilizzo di un'etichetta come condizione in un criterio DLP

È possibile creare un'etichetta e quindi:
  
- **Pubblicarlo** , in modo che gli utenti finali possano visualizzare e applicare manualmente l'etichetta al contenuto. 
    
- **ApplicaRlo automaticamente** ai contenuti che soddisfano le condizioni scelte. 
    
Per ulteriori informazioni sulle etichette, vedere [Overview of](labels.md)retention labels.
  
Dopo aver creato un'etichetta, è possibile utilizzare tale etichetta come condizione nei criteri DLP. Ad esempio, potrebbe essere necessario eseguire questa operazione perché:
  
- È stata pubblicata un'etichetta denominata **Confidential**, in modo che gli utenti dell'organizzazione possano applicare manualmente l'etichetta a documenti e posta elettronica riservati. Se si utilizza questa etichetta come condizione nei criteri DLP, è possibile limitare i contenuti etichettati come **riservati** alla condivisione con utenti esterni all'organizzazione. 
    
- È stata creata un'etichetta denominata **Alpine House** per un progetto di quel nome e quindi l'etichetta viene applicata automaticamente al contenuto contenente le parole chiave "Alpine House". Se si utilizza questa etichetta come condizione nei criteri DLP, è possibile visualizzare un suggerimento per i criteri per gli utenti finali quando si sta per condividere il contenuto con un utente esterno all'organizzazione. 
    
- È stata pubblicata un'etichetta denominata **record di imposta**, in modo che il responsabile dei record possa applicare manualmente l'etichetta al contenuto che deve essere classificato come record. Se si utilizza questa etichetta come condizione nei criteri DLP, è possibile cercare il contenuto con questa etichetta insieme ad altri tipi di informazioni riservate, come ITINs o SNSS; applicare le azioni di protezione al **record di imposta sul**contenuto etichettato; e ottenere relazioni dettagliate sulle attività relative ai criteri DLP dei dati del log di controllo e dei rapporti DLP. 
    
- È stata pubblicata un'etichetta denominata **Executive Leadership Team-sensitive** per le cassette postAli di Exchange e gli account di OneDrive di un gruppo di dirigenti. Se si utilizza questa etichetta come condizione nei criteri DLP, è possibile applicare sia le azioni di conservazione che quelle di protezione sullo stesso sottoinsieme di contenuto e utenti. 
    
Utilizzando le etichette come condizione nelle regole DLP, è possibile applicare in modo selettivo azioni di protezione su un insieme specifico di contenuto, percorsi o utenti.
  
![Etichette come condizione](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a>Il supporto per le etichette di riservatezza è in arrivo

Si noti che attualmente è possibile utilizzare solo un'etichetta di conservazione come condizione, non un' [etichetta](sensitivity-labels.md)di riservatezza. In questa condizione è attualmente in uso il supporto per l'utilizzo di un'etichetta di riservatezza.
  
### <a name="how-this-feature-relates-to-other-features"></a>Come questa funzionalità si riferisce ad altre caratteristiche

È possibile applicare diverse funzionalità ai contenuti che contengono informazioni riservate:
  
- Un' [etichetta di conservazione](labels.md#applying-a-retention-label-automatically-based-on-conditions) e un [criterio di conservazione](retention-policies.md) possono entrambe applicare le azioni di **conservazione** su questo contenuto. 
    
- Un criterio DLP può applicare azioni di **protezione** su questo contenuto. E prima di applicare queste azioni, un criterio DLP può richiedere che vengano soddisfatte altre condizioni oltre al contenuto contenente un'etichetta. 
    
![Diagramma delle caratteristiche che possono essere applicate alle informazioni riservate](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Si noti che un criterio DLP ha una funzionalità di rilevamento più avanzata rispetto a un'etichetta o a un criterio di conservazione applicati a informazioni riservate. Un criterio DLP può applicare azioni protettive sul contenuto che contiene informazioni riservate e, se le informazioni riservate vengono rimosse dal contenuto, le azioni di protezione vengono annullate al successivo analisi del contenuto. Tuttavia, se un criterio di conservazione o un'etichetta viene applicata al contenuto contenente informazioni riservate, si tratta di un'azione una tantum che non verrà annullata anche se le informazioni riservate sono state rimosse.
  
Se si utilizza un'etichetta come condizione in un criterio DLP, è possibile applicare sia le azioni di conservazione che quelle di protezione sul contenuto con quell'etichetta. È possibile pensare ai contenuti che contengono un'etichetta esattamente come il contenuto che contiene informazioni riservate, sia un'etichetta che un tipo di informazioni riservate sono proprietà utilizzate per classificare il contenuto, in modo da poter applicare le azioni su tale contenuto.
  
![Diagramma dei criteri DLP utilizzando l'etichetta come condizione](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Impostazioni semplici rispetto alle impostazioni avanzate

Quando si crea un criterio DLP, è possibile scegliere tra impostazioni semplici o avanzate:
  
- **Le impostazioni semplici** semplificano la creazione del tipo più comune di criteri DLP senza utilizzare l'Editor regole per creare o modificare le regole. 
    
- **Impostazioni avanzate** utilizzare l'editor delle regole per fornire il controllo completo su tutte le impostazioni per il criterio DLP. 
    
Non si preoccupi, sotto le coperture, le impostazioni semplici e le impostazioni avanzate funzionano esattamente lo stesso, applicando le regole costituite da condizioni e azioni, solo con impostazioni semplici, non viene visualizzato l'editor delle regole. Si tratta di un modo rapido per creare un criterio DLP.
  
### <a name="simple-settings"></a>Impostazioni semplici

Di gran lunga, lo scenario DLP più comune è la creazione di un criterio per proteggere il contenuto che contiene informazioni riservate di essere condiviso con persone esterne all'organizzazione e l'esecuzione di un'azione correttiva automatica, ad esempio la limitazione degli utenti che possono accedere al contenuto. invio di notifiche all'utente finale o di amministratore e controllo dell'evento per indagini successive. Gli utenti utilizzano DLP per impedire la divulgazione involontaria di informazioni riservate.
  
Per semplificare la realizzazione di questo obiettivo, quando si crea un criterio DLP, è possibile scegliere **Usa impostazioni semplici**. Queste impostazioni forniscono tutto ciò che è necessario per implementare i più comuni criteri DLP, senza dover accedere all'editor delle regole.
  
![Opzioni DLP per le impostazioni semplici e avanzate](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Impostazioni avanzate

Se è necessario creare criteri DLP personalizzati, è possibile scegliere **Usa impostazioni avanzate**.
  
Le impostazioni avanzate presentano l'editor delle regole, in cui si dispone del controllo completo su ogni possibile opzione, tra cui il numero di istanze e l'accuratezza della corrispondenza (livello di probabilità) per ogni regola.
  
Per passare rapidamente a una sezione, fare clic su un elemento nella barra di spostamento superiore dell'editor delle regole per passare alla sezione seguente.
  
![Menu di spostamento superiore dell'editor delle regole DLP](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Modelli dei criteri di prevenzione della perdita dei dati

Il primo passaggio per la creazione di un criterio DLP è la scelta delle informazioni da proteggere. A partire da un modello DLP, è possibile salvare il lavoro di creazione di un nuovo set di regole da zero e capire quali tipi di informazioni devono essere incluse per impostazione predefinita. È quindi possibile aggiungere o modificare questi requisiti per ottimizzare la regola per soddisfare i requisiti specifici dell'organizzazione.
  
Un modello di criteri DLP preconfigurato può essere utile per individuare tipi specifici di informazioni riservate, ad esempio i dati HIPAA, i dati PCI-DSS, Gramm-Leach-Bliley Act o persino informazioni di identificazione personale specifiche delle impostazioni locali (P.I.). Per agevolare l'individuazione e la protezione dei tipi comuni di informazioni riservate, i modelli di criteri inclusi in Office 365 già contengono i tipi di informazioni riservate più comuni.
  
![Elenco dei modelli di criteri di prevenzione della perdita dei dati con lo stato attivo sul modello degli Stati Uniti Patriot Act](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
L'organizzazione può anche avere i propri requisiti specifici, nel qual caso è possibile creare un criterio DLP da zero scegliendo l'opzione **criteri personalizzati** . Un criterio personalizzato è vuoto e non contiene regole prefabbricate. 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>Distribuzione graduale dei criteri DLP attraverso la modalità test

Quando si creano i criteri DLP, è necessario distribuirli gradualmente per valutarne l'impatto e l'efficacia, prima di applicarli completamente. Ad esempio, non si desidera che un nuovo criterio DLP involontariamente blocca l'accesso a migliaia di documenti di cui gli utenti hanno bisogno di accedere per poter svolgere il proprio lavoro.
  
Se si stanno creando criteri DLP con un impatto potenziale elevato, è consigliabile seguire questa sequenza:
  
1. **Avviare la modalità di test senza suggerimenti** per i criteri e quindi utilizzare i report DLP e gli eventuali rapporti sugli incidenti per valutare l'impatto. È possibile utilizzare i report DLP per visualizzare il numero, il percorso, il tipo e la gravità di corrispondenza del criterio. A seconda dei risultati, è possibile ottimizzare le regole in modo adeguato. In modalità test, i criteri DLP non avranno effetto sulla produttività degli utenti dell'organizzazione. 
    
2. **Passare alla modalità test con notifiche e suggerimenti per i criteri** in modo da istruire gli utenti in merito ai criteri di conformità e prepararli all'applicazione delle regole. In questa fase, è inoltre possibile chiedere agli utenti di segnalare i falsi positivi per definire ulteriormente le regole. 
    
3. **Avviare l'applicazione completa nei criteri** in modo che le azioni nelle regole vengano applicate e il contenuto sia protetto. Continuare a eseguire il monitoraggio dei report DLP e di eventuali eventi imprevisti oppure delle notifiche per essere certi di ottenere i risultati desiderati. 
    
![Opzioni per l'utilizzo della modalità di test e dell'attivazione dei criteri](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
È possibile disattivare un criterio DLP in qualsiasi momento, disabilitando anche tutte le regole nel criterio. Tuttavia, ogni regola può anche essere disattivata singolarmente commutando lo stato nell'editor delle regole.
  
![Opzioni per disattivare una regola in un criterio](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a>Rapporti DLP

Dopo aver creato e attivato i criteri DLP, è necessario verificare che funzionino come previsto e che vi aiutino a rimanere conformi. Grazie ai report DLP, è possibile visualizzare rapidamente il numero relativo alle corrispondenze del criterio DLP e delle regole e il numero di falsi positivi e sostituzioni. Per ciascun report, è possibile filtrare tali corrispondenze in base al percorso o a un intervallo di tempo e circoscriverle in base a un criterio, una regola o un'azione specifici.
  
Grazie ai report DLP, è possibile ottenere approfondimenti aziendali e:
  
- Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
- Individuare i processi aziendali che violano i criteri di conformità dell'organizzazione.
    
- Comprendere l'eventuale impatto aziendale dei criteri DLP.
    
Inoltre, è possibile utilizzare i report DLP per ottimizzare i criteri DLP, quando vengono eseguiti.
  
![Dashboard report nel centro sicurezza e conformità](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Funzionamento dei criteri DLP

DLP permette di rilevare le informazioni riservate tramite un'analisi approfondita dei contenuti (non solo una semplice analisi del testo). Questa analisi approfondita utilizza corrispondenze delle parole chiave, del dizionario, la valutazione di espressioni regolari, funzioni interne e di altri metodi al fine di rilevare i contenuti corrispondenti ai criteri DLP. Viene considerata riservata potenzialmente solo una piccola percentuale dei dati. Un criterio DLP consente di identificare, monitorare e proteggere automaticamente solo tali dati, senza influire in alcun modo sul lavoro degli utenti con il resto del contenuto.
  
### <a name="policies-are-synced"></a>I criteri sono sincronizzati

Dopo aver creato un criterio DLP nel centro sicurezza &amp; e conformità, quest'ultimo viene archiviato in un archivio dei criteri centrale e quindi sincronizzato con le diverse origini di contenuto, tra cui:
  
- Exchange Online e da qui a Outlook sul Web e Outlook
    
- Siti OneDrive for Business
    
- Siti SharePoint Online
    
- Programmi desktop di Office (Excel, PowerPoint e Word)

- Canali e chat di Microsoft Teams
    
Dopo che i criteri sono stati sincronizzati con i percorsi giusti, viene avviata la valutazione del contenuto e l'applicazione delle azioni.
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Valutazione dei criteri nei siti OneDrive for Business e SharePoint Online

In tutti i siti di SharePoint Online e OneDrive for business, i documenti cambiano continuamente, vengono continuamente creati, modificati, condivisi e così via. Ciò significa che, in qualsiasi momento, i documenti possono violare oppure essere conformi a un criterio DLP. Ad esempio, un utente può caricare un documento privo di informazioni riservate sul sito del proprio team ma, in un secondo momento, un utente diverso può modificare lo stesso documento e aggiungervi informazioni riservate.
  
Per questo motivo, i criteri DLP consentono di verificare la corrispondenza dei documenti ai criteri in background frequentemente. Tale operazione può essere considerata come una valutazione asincrona del criterio.
  
#### <a name="how-it-works"></a>Funzionamento
 
Quando gli utenti aggiungono o cambiano documenti nei propri siti, il motore di ricerca analizza il contenuto in modo che sia possibile cercarlo in un secondo momento. Anche se questo accade, il contenuto viene analizzato per informazioni riservate e per verificare se è condiviso. Tutte le informazioni riservate trovate vengono archiviate in modo sicuro nell'indice di ricerca, affinché solo il team di conformità possa accedervi, ma non gli utenti tipici. Ogni criterio DLP attivato viene eseguito in background (in modo asincrono), controllando la ricerca di frequente per qualsiasi contenuto che corrisponda a un criterio e applicando le azioni per proteggerlo dalle perdite accidentali.
  
![Diagramma che mostra il modo in cui i criteri DLP valutano il contenuto in modo asincrono](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
Infine, i documenti possono essere in conflitto con un criterio DLP ma possono anche diventare conformi a tale criterio. Ad esempio, se una persona aggiunge numeri di carta di credito a un documento, è possibile che un criterio DLP blocchi l'accesso a tale documento automaticamente. Tuttavia, se in un secondo momento l'utente elimina le informazioni riservate, l'azione (in questo caso, di blocco) viene automaticamente annullata durante la successiva valutazione del documento rispetto al criterio.
  
La prevenzione della perdita dei dati (DLP) consente di valutare qualsiasi contenuto che è possibile indicizzare. Per ulteriori informazioni sui tipi di file sottoposti a ricerca per indicizzazione per impostazione predefinita, vedere default indicizzazione del [nome di file e tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Valutazione dei criteri in Exchange Online, Outlook e Outlook sul Web

Quando si crea un criterio DLP che include Exchange Online come percorso, il criterio è sincronizzato dal centro sicurezza &amp; e conformità di Office 365 a Exchange Online e quindi da Exchange Online a Outlook sul Web e Outlook.
  
Quando un messaggio viene composto in Outlook, l'utente può visualizzare i suggerimenti per i criteri quando il contenuto da creare viene valutato in base ai criteri DLP. Dopo aver inviato un messaggio, viene valutato in base ai criteri DLP come parte normale del flusso di posta, insieme alle regole del flusso di posta di Exchange (note anche come regole di trasporto) e ai criteri DLP creati nell'interfaccia di amministrazione di Exchange. I criteri DLP analizzano sia il messaggio che gli allegati.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Valutazione dei criteri nei programmi desktop di Office

Excel, PowerPoint e Word includono la stessa funzionalità per identificare le informazioni riservate e applicare i criteri DLP come SharePoint Online e OneDrive for business. Queste applicazioni di Office sincronizzano i criteri DLP direttamente dall'archivio dei criteri centrali e quindi valutano continuamente il contenuto in base ai criteri DLP quando le persone lavorano con documenti aperti da un sito incluso in un criterio DLP.
  
La valutazione del criterio DLP in Office è progettata per non influire sulle prestazioni dei programmi o sulla produttività degli utenti che lavorano al contenuto. Se si lavora su un documento di grandi dimensioni o se il computer dell'utente è occupato, potrebbero essere necessari alcuni secondi affinché venga visualizzato un suggerimento per i criteri.

### <a name="policy-evaluation-in-microsoft-teams"></a>Valutazione del criterio in Microsoft Teams
 
Quando si crea un criterio DLP che include Microsoft teams come percorso, i criteri vengono sincronizzati dal centro sicurezza &amp; e conformità di Office 365 agli account utente e ai canali e alle chat di Microsoft teams. A seconda del modo in cui vengono configurati i criteri DLP, quando un utente tenta di condividere informazioni riservate in una chat o un canale di Microsoft teams, il messaggio può essere bloccato o revocato. Inoltre, i documenti che contengono informazioni riservate e che sono condivisi con gli ospiti (utenti esterni) non verranno aperti per tali utenti.

Si supponga, ad esempio, che un utente tenti di condividere le informazioni riservate in una chat o un canale di team con utenti esterni. Si supponga che sia stato definito un criterio DLP per evitare questo problema. Con la protezione sul posto, vengono eliminati i messaggi che contengono informazioni riservate agli utenti esterni. Questo accade in pochi secondi e avviene automaticamente, in base al modo in cui viene configurato il criterio DLP.

Suggerimenti per i criteri notifica ai mittenti il motivo per cui i messaggi sono stati bloccati o revocati. Ad esempio, a un mittente potrebbe essere detto che il messaggio contiene informazioni personali che non sono consentite per la condivisione con nessuno o che un documento contenente PII non può essere condiviso con persone esterne all'organizzazione. Il mittente può quindi modificare il messaggio in modo che sia conforme ai criteri DLP.
 
## <a name="permissions"></a>Autorizzazioni

I membri del team di conformità che creeranno criteri DLP devono disporre delle autorizzazioni &amp; per il Centro sicurezza e conformità. Per impostazione predefinita, l'amministratore del tenant avrà accesso a questo percorso e potrà fornire ai responsabili della conformità e agli altri utenti &amp; l'accesso al centro sicurezza e conformità, senza fornire loro tutte le autorizzazioni di un amministratore tenant. A tale scopo, è consigliabile eseguire le operazioni seguenti:
  
1. Creare un gruppo in Office 365 e aggiungervi i responsabili della conformità.
    
2. Creare un gruppo di ruoli nella pagina **autorizzazioni** del Centro sicurezza &amp; e conformità. 
    
3. Aggiungere il gruppo di Office 365 al gruppo di ruoli creato.
    
Per ulteriori informazioni, vedere [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie solo per la creazione e l'applicazione di un criterio DLP. L'applicazione di un criterio non richiede l'accesso ai contenuti.
  
## <a name="find-the-dlp-cmdlets"></a>Individuare i cmdlet DLP

Per utilizzare la maggior parte dei cmdlet per il centro &amp; sicurezza e conformità, è necessario:
  
1. [Connettersi al Centro sicurezza e conformità Office 365 utilizzando sessione remota di PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
    
2. Utilizzare uno di questi [cmdlet di policy-and-Compliance-DLP](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)
    
Tuttavia, i report DLP devono estrarre dati dall'intera sede di Office 365, incluso Exchange Online. Per questo motivo, **i cmdlet per i report DLP sono disponibili in PowerShell di Exchange Online, non in PowerShell per &amp; il Centro sicurezza e conformità**. Pertanto, per utilizzare i cmdlet per i report DLP, è necessario eseguire le operazioni seguenti:
  
1. [Connettersi a Exchange Online usando una sessione remota di PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. Utilizzare uno di questi cmdlet per i report DLP:
    
  - [Get-DlpDetectionsReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [Get-DlpDetailReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a>Ulteriori informazioni

- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Creare un criterio di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md)
    
- [Cosa individuano le funzioni di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md)
    
- [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md)
    

