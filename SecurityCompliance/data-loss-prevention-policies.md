---
title: Panoramica relativa ai criteri di prevenzione della perdita di dati
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: Con un criterio di criterio DLP perdita di dati in Office 365 Security &amp; centro conformità, è possibile identificare, monitorare e proteggere automaticamente le informazioni contenute in Office 365.
ms.openlocfilehash: e9d033bc54aae6bc1c8089793dbc618f11bef273
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013740"
---
# <a name="overview-of-data-loss-prevention-policies"></a>Panoramica relativa ai criteri di prevenzione della perdita di dati

Per rispettare normative del settore e standard aziendale, le organizzazioni hanno bisogno proteggere le informazioni riservate e il relativo divulgazione accidentale. Dati finanziari o informazioni personali (PII), ad esempio numeri di carta di credito, previdenza sociale o record integrità sono esempi di informazioni riservate che è possibile evitare che vengano perdute all'esterno dell'organizzazione. Con un criterio di criterio DLP perdita di dati in Office 365 Security &amp; centro conformità, è possibile identificare, monitorare e proteggere automaticamente le informazioni contenute in Office 365.
  
Utilizzando un criterio DLP, è possibile:
  
- **Identificare le informazioni riservate tra diversi luoghi, quali Exchange Online, SharePoint Online e OneDrive for Business.**
    
    Ad esempio, è possibile identificare un documento contenente un numero di carta di credito che viene archiviato in qualsiasi OneDrive per sito aziendale oppure è possibile monitorare solo i siti di OneDrive di utenti specifici.
    
- **Impedire la condivisione accidentale di informazioni riservate**. 
    
    Ad esempio, è possibile identificare qualsiasi documento o un messaggio di posta elettronica contenente un record di integrità è condivise con utenti esterni all'organizzazione, e quindi bloccare automaticamente l'accesso a tale documento o bloccare il messaggio di posta elettronica non verrà inviato.
    
- **Monitorare e proteggere le informazioni riservate nelle versioni desktop di Excel 2016, PowerPoint 2016 e Word 2016.**
    
    Proprio come in Exchange Online, SharePoint Online e OneDrive for Business, le applicazioni desktop di Office 2016 includono le stesse funzionalità per identificare le informazioni riservate e applicare i criteri DLP. DLP consente il monitoraggio continuo quando persone condividono contenuti in questi programmi Office 2016.
    
- **Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro.**
    
    È possibile formare gli utenti sui criteri DLP e migliorare la rimanere Compatible senza il loro lavoro. Ad esempio, se un utente tenta di condividere un documento che contiene informazioni riservate, un criterio DLP può inviare loro una notifica tramite posta elettronica e mostrare loro un suggerimento criterio nel contesto della raccolta documenti che consente di ignorare il criterio, se dispongono di un'azienda giustificazione. I suggerimenti criteri vengono visualizzati anche in Outlook sul web, Outlook 2013 e versioni successive, 2016 Excel, PowerPoint 2016 e 2016 Word.
    
- **DLP consente di visualizzare report che illustra il contenuto che genera una corrispondenza per i criteri DLP dell'organizzazione.**
    
    Per valutare la modalità di conformità di organizzazione con un criterio DLP, è possibile visualizzare il numero corrisponde a ogni criterio e regola ha nel tempo. Se un criterio DLP consente agli utenti di eseguire l'override di un suggerimento sul criterio e un falso positivo, è inoltre possibile visualizzare quali utenti hanno segnalato.
    
Creare e gestire i criteri DLP per la pagina di prevenzione della perdita di dati in Office 365 Security &amp; centro conformità.
  
![Pagina di prevenzione della perdita di dati in Office 365 Security &amp; centro conformità](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>Contenuto di un criterio DLP

In un criterio DLP sono disponibili alcuni elementi di base:
  
- Posizione in cui proteggere il contenuto - **percorsi** quali Exchange Online, SharePoint Online e OneDrive per i siti. 
    
- Quando e in che modo proteggere il contenuto, applicando **regole** composte da: 
    
  - **Condizioni** contenuto deve corrispondere perché viene applicata la regola, ad esempio, essere solo per il contenuto che contiene numeri di previdenza sociale condiviso con utenti esterni all'organizzazione. 
    
  - **Azioni** che la regola deve effettuare automaticamente quando vengono rilevati contenuti corrispondenti alle condizioni: ad esempio, è possibile bloccare l'accesso al documento e inviare una notifica tramite posta elettronica sia all'utente che al responsabile della conformità. 
    
È possibile utilizzare una regola per soddisfare requisiti specifici di protezione specifici e quindi utilizzare un criterio DLP per raggruppare i requisiti di protezione comuni, ad esempio tutte le regole necessarie per rispettare una regolazione specifica.
  
Ad esempio, potrebbe essere un criterio DLP che consente di rilevare la presenza di informazioni sono soggette all'Health Insurance Portability and Accountability Act (HIPAA). Questo criterio DLP può migliorare la protezione dei dati HIPAA (what) in tutti i siti di SharePoint Online e OneDrive tutti i siti di Business (where) mediante la ricerca di un documento contenente queste informazioni riservate che sono condiviso con persone esterne all'organizzazione (il condizioni) e quindi bloccare l'accesso al documento e inviare alcuna notifica (azioni). Questi requisiti vengono memorizzati come singole regole e raggruppati come un criterio DLP per semplificare la gestione e creazione di report.
  
![Diagramma che mostra il criterio DLP contenente posizioni e regole](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>Percorsi

Un criterio DLP consente di trovare e proteggere le informazioni contenute in Office 365, se quest'ultimo si trova in Exchange Online, SharePoint Online o OneDrive for Business. È possibile scegliere di proteggere tutti i siti di SharePoint o gli account utilizzati per OneDrive appena specifici siti o gli account o tutte le cassette postali. Si noti che non è ancora possibile selezionare le cassette postali di utenti specifici.
  
![Opzioni per la posizione in cui è possibile applicare un criterio DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
Si noti che se si sceglie di includere o escludere specifici siti di SharePoint o gli account OneDrive, un criterio DLP può contenere non più di 100 tali inclusioni ed esclusioni. Sebbene questo limite è presente, informazioni che è possibile superare questo limite applicando un criterio a livello di organizzazione o un criterio che si applica ai percorsi intero.
  
### <a name="rules"></a>Regole

Le regole sono quali applicare i requisiti aziendali contenuti dell'organizzazione. Un criterio contiene una o più regole e ogni regola è costituita da condizioni e azioni. Per ogni regola, quando si verificano le condizioni, le operazioni vengono eseguite automaticamente. Le regole vengono eseguite in modo sequenziale, inizia con la regola di priorità più alta in ogni criterio.
  
Una regola sono inoltre disponibili opzioni per notificare agli utenti (con suggerimenti sui criteri e notifiche tramite posta elettronica) e gli amministratori (con i rapporti operazioni non consentite di posta elettronica) che contenuto con corrispondenza della regola.
  
Ecco i componenti di una regola, ognuno illustrati di seguito.
  
![Sezioni dell'editor di regole DLP](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condizioni

Condizioni sono importanti perché determinano quali tipi di informazioni da cercare e quando si desidera creare un'azione. Ad esempio, si può scegliere di ignorare contenuto contenenti numeri di passaporto solo se il contenuto contiene più di 10 questi numeri e condivise con utenti esterni all'organizzazione.
  
Condizioni concentrano sui **contenuti**, ad esempio i tipi di informazioni riservate si sta cercando, nonché al **contesto**, ad esempio il documento che è condiviso con. È possibile utilizzare le condizioni per assegnare azioni diverse a diversi livelli di rischio -, ad esempio contenuti sensibili condivisi internamente potrebbero essere basso rischio e richiedono meno azioni rispetto contenuti sensibili condivisi con utenti esterni all'organizzazione. 
  
![Elenco che mostra le condizioni DLP disponibili](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
Le condizioni disponibili a questo punto consentono di determinare se:
  
- Contenuto contiene un tipo di informazioni riservate.
    
- Contenuto include un'etichetta. Per ulteriori informazioni, vedere la sezione di seguito [utilizzando un'etichetta come condizione in un criterio DLP](data-loss-prevention-policies.md#label).
    
- Il contenuto viene condiviso con utenti esterni o interni alla propria organizzazione.
    
#### <a name="types-of-sensitive-information"></a>Tipi di informazioni riservate

Un criterio DLP consentono di proteggere le informazioni riservate, che viene definite come **tipo di informazioni sensibili**. Office 365 include le definizioni per molti tipi di informazioni riservate comuni in numerose aree geografiche diverse che si desidera utilizzare, ad esempio un numero di carta di credito, numeri conto bancario, numeri ID nazionali e numeri di passaporto. 
  
![Elenco dei tipi di informazioni riservate disponibili](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Quando un criterio DLP Cerca un tipo di informazioni riservate, ad esempio un numero di carta di credito, non semplicemente aspetto di un numero di 16 cifre. Ogni tipo di informazioni riservate viene definito e rilevato utilizzando una combinazione di:
  
- Parole chiave
    
- Funzioni interne relative a checksum di convalida o alla composizione
    
- Valutazione delle espressioni ricorrenti al fine di individuare corrispondenze del motivo
    
- Valutazione di altri contenuti
    
In questo modo il rilevamento DLP raggiungere un elevato grado di precisione riducendo il numero di falsi positivi che potrebbero interrompere l'ufficio di persone.
  
#### <a name="actions"></a>Azioni

Quando il contenuto soddisfa una condizione in una regola, è possibile applicare azioni per proteggere automaticamente il contenuto.
  
![Elenco di azioni DLP disponibili](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Con le azioni disponibili a questo punto, è possibile:
  
- **Limitare l'accesso al contenuto** Per il contenuto del sito, ciò significa che le autorizzazioni per il documento sono riservate per tutti gli utenti ad eccezione di amministratore della raccolta siti principale, proprietario del documento e persona che ha modificato il documento. Queste persone consente di rimuovere le informazioni riservate dal documento o di eseguire altre azioni correttive. Quando il documento è in conformità, verranno ripristinate automaticamente le autorizzazioni originale. Quando viene bloccato l'accesso a un documento, con un'icona di suggerimento criteri speciali nella raccolta nel sito del documento. 
    
    ![Suggerimento per i criteri con accesso al documento bloccato](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    Per il contenuto di posta elettronica, l'azione blocca il messaggio non verrà inviato. A seconda della configurazione di regole DLP, al mittente viene visualizzato un rapporto di mancato recapito o (se la regola utilizza una notifica) una notifica criteri suggerimento e/o di posta elettronica.
    
    ![Che è necessario rimuovere destinatari non autorizzati dal messaggio di avviso](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notifiche utente e l'override dell'utente

È possibile utilizzare le notifiche e ha la priorità per formare gli utenti sui criteri DLP e migliorare la rimanere Compatible senza il loro lavoro. Ad esempio, se un utente tenta di condividere un documento che contiene informazioni riservate, un criterio DLP può inviare loro una notifica tramite posta elettronica e mostrare loro un suggerimento criterio nel contesto della raccolta documenti che consente di ignorare il criterio, se dispongono di un'azienda giustificazione.
  
![Utente e le notifiche utente esegue l'override di sezioni dell'editor regole DLP](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
Messaggio di posta elettronica per notificare la persona che ha inviato, condivisi o dell'ultima modifica il contenuto e, per il contenuto del sito, l'amministratore della raccolta siti principale e dal proprietario del documento. Inoltre, è possibile aggiungere o rimuovere chiunque scegliere tra la notifica di posta elettronica.
  
Oltre a inviare una notifica tramite posta elettronica, una notifica all'utente verrà visualizzato un suggerimento criterio:
  
- In Outlook 2013 e versioni successive e Microsoft Outlook sul web.
    
- Per il documento in SharePoint Online o un nuovo OneDrive per sito aziendale.
    
- In Excel 2016, 2016 PowerPoint e Word 2016, quando il documento viene archiviato in un sito inclusi in un criterio DLP.
    
La notifica tramite posta elettronica e un suggerimento per il criterio viene illustrato il motivo per cui è contenuto in conflitto con un criterio DLP. Se si sceglie il suggerimento messaggio di posta elettronica di notifica e criteri di possibile consentire agli utenti di modificare una regola di reporting un falso positivo o fornendo motivazione aziendale. Ciò consente di informare gli utenti sui criteri DLP e applicarle senza impedire agli utenti di svolgere il lavoro. Informazioni sulle sostituzioni e falsi positivi anche registrate per i report (vedere di seguito relative ai rapporti DLP) e incluso l'evento imprevisto segnala (sezione successiva), in modo che il responsabile della conformità regolarmente possono esaminare queste informazioni.
  
Ecco un suggerimento criterio aspetto in un OneDrive per conto di Business.
  
![Suggerimento per il criterio per un documento di un account OneDrive](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>Rapporti operazioni non consentite

Quando viene soddisfatta una regola, è possibile inviare un rapporto operazioni non consentite per il responsabile della conformità (o le persone che si sceglie) con i dettagli dell'evento. In questo report include informazioni sull'elemento corrispondente, il contenuto effettivo che la regola e il nome della persona che ha modificato il contenuto corrispondente. Per i messaggi di posta elettronica, il report include anche come allegato il messaggio originale che corrisponde a un criterio DLP.
  
![Pagina per la configurazione di rapporti operazioni non consentite](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>Operatori logici e raggruppamento

Frequenza con cui il criterio DLP è un requisito semplice, ad esempio per identificare tutti i contenuti che includono un numero di previdenza sociale negli Stati Uniti. In altri scenari, tuttavia, il criterio DLP potrebbe essere necessario identificare dati definiti in modo più flessibile.
  
Ad esempio, per identificare contenuto soggetti a US Health Insurance Act (HIPAA), è necessario cercare:
  
- Contenuto con specifici tipi di informazioni riservate, ad esempio un numero di previdenza sociale negli Stati Uniti o un numero Drug imposizione Agency (DEA).
    
    E
    
- Il contenuto che è più difficile identificare, ad esempio communications su un paziente terapie o le descrizioni dei servizi medici resi disponibili. Che identifica questo contenuto, è necessario corrispondenti alle parole chiave da elenchi di grandi dimensioni parola chiave, ad esempio International classificazione di malattie (ICD-9-CM o ICD 10 CM).
    
È possibile identificare con facilità tali dati definizione debole tramite operatori logici e raggruppamento (AND, OR). Quando si crea un criterio DLP, è possibile:
  
- Raggruppare i tipi di informazioni riservate.
    
- Selezionare l'operatore logico tra i tipi di informazioni sensibili all'interno di un gruppo e i gruppi di se stessi.
    
### <a name="choosing-the-operator-within-a-group"></a>La scelta dell'operatore all'interno di un gruppo

All'interno di un gruppo, è possibile scegliere se alcune o tutte le condizioni di tale gruppo devono essere soddisfatti per il contenuto per la corrispondenza della regola.
  
![Gruppo che mostra gli operatori all'interno del gruppo](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Aggiunta di un gruppo

È possibile aggiungere rapidamente un gruppo, che può includere le condizioni e operatore all'interno di tale gruppo.
  
![Aggiungere il pulsante gruppo](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>La scelta dell'operatore tra i gruppi

Tra i gruppi, è possibile scegliere se devono essere soddisfatte le condizioni in un solo gruppo o tutti i gruppi per il contenuto per la corrispondenza della regola.
  
Ad esempio, criterio **Usa HIPAA** incorporato ha una regola che utilizza un operatore **AND** tra i gruppi in modo che identifichi contenuti che includono: 
  
- dal gruppo di **Identificatori PII** (numero SSN almeno un numero **o** DEA) 
    
    **E**
    
- dal gruppo di **Termini medici** (almeno un ICD-9-CM **o** ICD-10 CM parola chiave) 
    
![Gruppi di visualizzazione l'operatore tra i gruppi](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>La priorità da cui vengono elaborate le regole

Quando si creano regole in un criterio, ogni regola viene assegnata una priorità nell'ordine in cui viene creata, vale a dire, la regola creata prima ha la priorità più alta, la regola creata in secondo luogo ha priorità seconda e così via. Dopo aver creato una regola, non è possibile modificare la priorità ad eccezione di eliminazione e crearne uno nuovo.
  
![Regole in ordine di priorità](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
Quando il contenuto viene valutato rispetto alle regole, le regole vengono elaborate in ordine di priorità. Se il contenuto corrisponde a più regole, le regole vengono elaborate in ordine di priorità e viene applicata l'azione più restrittivo. Ad esempio, se corrisponde a quello contenuto di tutte le regole seguenti, regola 3 viene applicato in quanto è la priorità massima, più restrittivo regola:
  
- Regola 1: invia una notifica agli utenti
    
- Regola 2: invia una notifica agli utenti, limita l'accesso e consente l'override dell'utente
    
- Regola 3: invia una notifica agli utenti, limita l'accesso e non consente l'override dell'utente
    
- Regola 4: invia una notifica agli utenti
    
- Regola 5: consente di limitare l'accesso
    
- Regola 6: invia una notifica agli utenti, limita l'accesso e non consente l'override dell'utente
    
In questo esempio si noti che corrispondenze per tutte le regole vengono registrate nei registri di controllo e mostrate nei rapporti DLP, anche se viene applicata solo la regola più restrittiva.
  
Per quanto riguarda suggerimenti sui criteri, tenere presente che:
  
- Solo il suggerimento criteri dalla priorità più alta, verrà visualizzato regola più restrittiva. Ad esempio, un suggerimento per il criterio da una regola che blocca l'accesso al contenuto verrà visualizzato su un suggerimento sul criterio da una regola che si limita a inviare una notifica. In questo modo si impedisce persone da visualizzare in una serie di suggerimenti sui criteri.
    
- Se i suggerimenti per i criteri nella regola più restrittiva consentono all'utente di ignorare la regola, in questo modo vengono ignorate anche le altre regole per le quali è stata rilevata una corrispondenza del contenuto.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Ottimizzazione di regole per renderli più difficili da soddisfare o più semplice

Dopo persone creato e attivare i criteri DLP, sono a volte vengono eseguiti in questi problemi:
  
- Quantità eccessiva di informazioni riservate **non** corrispondano alle regole - in altre parole, un numero eccessivo di falsi positivi il contenuto. 
    
- Troppo piccola contenuto che **è** informazioni riservate corrispondano alle regole, in altre parole, le operazioni di protezione non vengono applicate nel informazioni riservate. 
    
Per risolvere questi problemi, è possibile ottimizzare le regole di modificando il conteggio delle istanze e accuratezza per rendere più difficile o più semplice per il contenuto da soddisfare le regole di corrispondenza. Ogni tipo di informazioni riservate utilizzato in una regola è un'istanza contare e corrispondere la precisione.
  
### <a name="instance-count"></a>Conteggio delle istanze

Conteggio delle istanze significa semplicemente il numero di occorrenze di un tipo specifico di informazioni riservate devono essere presente per il contenuto per la corrispondenza della regola. Ad esempio, il contenuto verrà corrisponde la regola illustrata di seguito se tra 1 e 9 univoci negli Stati Uniti o Regno Unito vengono identificati i numeri di passaporto.
  
Si noti che il conteggio delle istanze include solo **univoco** corrispondenze per le parole chiave e tipi di informazioni riservate. Ad esempio, se un messaggio di posta elettronica contiene 10 occorrenze dello stesso numero di carta di credito, le 10 occorrenze contano come una singola istanza di un numero di carta di credito. 
  
Per utilizzare conteggio delle istanze per ottimizzare le regole, le indicazioni sono semplice:
  
- Per facilitare la regola da soddisfare, diminuire il conteggio **min** e/o aumentare il numero **massimo** . È possibile anche impostare **max** a **qualsiasi** eliminando il valore numerico. 
    
- Per rendere più difficili da soddisfare la regola, aumentare il numero di **minuti** . 
    
In genere, si utilizzano azioni meno restrittive, ad esempio l'invio di notifiche per utente, in una regola con un numero inferiore di istanza (ad esempio, 1-9). È possibile utilizzare azioni più restrittive, ad esempio la limitazione dell'accesso al contenuto non sono consentite override dell'utente, in una regola con un conteggio delle istanze superiore (ad esempio, qualsiasi 10).
  
![Istanza conta nell'editor di regole](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisione di corrispondenza

Come descritto in precedenza, un tipo di informazioni riservate viene definito e rilevato mediante una combinazione di tipi diversi di prova. In genere, un tipo di informazioni riservate dipende dal più combinazioni simili, detti criteri. Un motivo che richiede meno prova con una precisione corrispondenza inferiore (o livello di probabilità), mentre un criterio che richiede che ulteriori prove con maggiore precisione di corrispondenza (o un livello di probabilità). Per ulteriori informazioni sui modelli effettivi e livelli di probabilità utilizzati da ogni tipo di informazioni riservate, vedere [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
Ad esempio, il tipo di informazioni riservate denominato numero di carta di credito viene definito da due motivi:
  
- Un criterio con confidenza 65% che è necessario:
    
  - Un numero in formato di un numero di carta di credito.
    
  - Numero che passa il valore di checksum.
    
- Un criterio con confidenza 85% che è necessario:
    
  - Un numero in formato di un numero di carta di credito.
    
  - Numero che passa il valore di checksum.
    
  - Una parola chiave o una data di scadenza nel formato corretto.
    
È possibile utilizzare tali probabilità livelli (o la precisione di corrispondenza) nelle regole. In genere, si utilizzano azioni meno restrittive, ad esempio l'invio di notifiche per utente, in una regola con una precisione di corrispondenza inferiore. È possibile utilizzare azioni più restrittive, ad esempio la limitazione dell'accesso al contenuto non sono consentite override dell'utente, in una regola con maggiore precisione di corrispondenza.
  
È importante tenere presente che, quando un tipo specifico di informazioni riservate, ad esempio un numero di carta di credito, viene identificato nel contenuto, viene restituito solo un livello di probabilità singolo:
  
- Se tutte le corrispondenze per un singolo modello, viene restituito il livello di confidenza per questo motivo.
    
- Se non esistono corrispondenze per uno o più motivo (ad esempio, esistono corrispondenze con due livelli diversi confidenza), viene restituito un livello di probabilità superiore a tutti i modelli singolo soli. Questo è difficile. Ad esempio, per la carta di credito, se il 65% e 85% pattern sono soddisfatte, il livello di probabilità restituito per che tipo di informazioni riservate è superiore al 90% perché ulteriori prove significa più probabilità.
    
Pertanto se si desidera creare due regole si escludono a vicenda per la carta di credito, uno per la precisione di corrispondenza 65% e uno per la precisione di corrispondenza 85%, gli intervalli di corrispondenza accuratezza avrà il formato. La prima regola riprende solo i risultati del motivo il 65%. La seconda regola preleva genera una corrispondenza con **almeno una** corrispondenza 85% e **può includere di** altri inferiore confidenza. 
  
![Due regole con intervalli diversi per la precisione di corrispondenza](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Per questi motivi, le indicazioni per la creazione di regole con corrispondenza diverso accuratezza sono la seguente:
  
- Il livello di probabilità di minimo in genere utilizza lo stesso valore per **le funzioni min** e **max** (non un intervallo). 
    
- In genere il più alto livello di probabilità è un intervallo da sopra il livello di probabilità di inferiore a 100.
    
- Tutti i livelli di probabilità intermedi in genere compreso tra sopra il livello di probabilità inferiore subito sotto il livello di probabilità di superiore.
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Utilizza un'etichetta come condizione in un criterio DLP

È possibile creare un'etichetta e quindi:
  
- **Pubblica** , in modo che gli utenti finali possono vedersi e applicare manualmente l'etichetta per il contenuto. 
    
- **Applicare automaticamente** il contenuto che soddisfa le condizioni che si sceglie. 
    
Per ulteriori informazioni sulle etichette, vedere [Overview of etichette](labels.md).
  
Dopo aver creato un'etichetta, quindi utilizzare tale etichetta come condizione nei criteri DLP. È possibile ad esempio, in quanto:
  
- È stato pubblicato un'etichetta nome **riservato**in modo che gli utenti dell'organizzazione applicare manualmente l'etichetta a documenti e posta elettronica riservato. Utilizzando l'etichetta come condizione nel criterio DLP, è possibile limitare contenuto etichettato **riservato** da condiviso con persone esterne all'organizzazione. 
    
- Creato un'etichetta di **Neve accesso a terze parti** per un progetto il cui nome e quindi applicato automaticamente tale etichetta per il contenuto che contiene le parole chiave "Neve persone". Utilizzando l'etichetta come condizione nel criterio DLP, è possibile visualizzare un suggerimento criterio agli utenti finali quando si utilizzano per condividere il contenuto con una persona esterna all'organizzazione. 
    
- È stato pubblicato un'etichetta denominata **record imposte**, in modo che il programma di gestione record applicare manualmente l'etichetta per il contenuto che deve essere classificato come record. Utilizzando l'etichetta come condizione nel criterio DLP, è possibile cercare del contenuto con etichetta in combinazione con altri tipi di informazioni riservate, ad esempio si o SSNs; applicare le azioni di protezione al contenuto etichettato **record imposte**. e ottenere rapporti dettagliati attività sul criterio DLP da rapporti DLP e i dati del Registro di controllo. 
    
- È stato pubblicato un'etichetta chiamata **Team leader Executive - riservati** per l'account di OneDrive di un gruppo di dirigenti e cassette postali di Exchange. Utilizzando l'etichetta come condizione nel criterio DLP, è possibile applicare azioni eseguite sia conservazione e protezione per lo stesso sottoinsieme del contenuto e gli utenti. 
    
In base alle etichette come condizione nelle regole DLP, può è in modo selettivo applicare azioni di protezione su un set specifico di contenuto, le posizioni o gli utenti.
  
![Etichette come condizione](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)
  
### <a name="how-this-feature-relates-to-other-features"></a>La relazione tra questa funzionalità e altre caratteristiche

Diverse funzionalità può essere applicata al contenuto che contiene informazioni riservate:
  
- Un' [applicazione un'etichetta automaticamente in base a condizioni](labels.md#applying-a-label-automatically-based-on-conditions) e un [criterio di conservazione](retention-policies.md) può applicare entrambi azioni di **conservazione** del contenuto. 
    
- Un criterio DLP può applicare azioni di **protezione** del contenuto. E prima applicate queste operazioni, un criterio DLP può richiedere altre condizioni per soddisfare oltre il contenuto che include un'etichetta. 
    
![Diagramma delle funzionalità che possono essere applicati a informazioni riservate](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Si noti che un criterio DLP è una funzionalità di rilevamento più completa di un criterio di etichetta o conservazione applicato alle informazioni riservate. Un criterio DLP può applicare un'azione correttiva al contenuto che contiene informazioni riservate e se le informazioni riservate viene rimosso dal contenuto, le azioni di protezione vengono annullate il successivo periodo di che analizzare il contenuto. Ma se un criterio di conservazione o un'etichetta è stata applicata al contenuto che contiene informazioni riservate, che corrisponde a un'azione occasionale che non verrà annullata anche se rimuovere le informazioni riservate.
  
Utilizzando un'etichetta come condizione in un criterio DLP, è possibile applicare azioni di conservazione sia protezione nel contenuto con tale etichetta. È possibile paragonare contenuto che include un'etichetta del contenuto che contiene informazioni riservate - sia un'etichetta di un tipo di informazioni riservate sono proprietà utilizzati per classificare il contenuto, in modo che sia possibile applicare azioni eseguite su tale contenuto.
  
![Diagramma del criterio DLP con etichetta come condizione](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Impostazioni Simple e le impostazioni avanzate

Quando si crea un criterio DLP, l'utente dovrà scegliere tra le impostazioni simple o avanzate:
  
- **Impostazioni Simple** rendono più semplice creare il tipo di criterio DLP più comune senza utilizzare l'editor delle regole per creare o modificare le regole. 
    
- **Impostazioni avanzate di** utilizzare l'editor regola per fornire il controllo completo su tutte le impostazioni per il criterio DLP. 
    
Non bisogna preoccuparsi, in modo non evidente, le impostazioni simple e le impostazioni avanzate funzionano esattamente, dall'applicazione di regole comprese le condizioni e azioni - solo con le impostazioni simple, non viene visualizzata l'editor regola. È un modo rapido per creare un criterio DLP.
  
### <a name="simple-settings"></a>Impostazioni Simple

Finora, lo scenario DLP più comune sta creando un criterio per proteggere il contenuto contenente le informazioni riservate dal condiviso con le persone all'esterno dell'organizzazione e intraprendere un'azione correttiva automatica, ad esempio se si restringe possono accedere al contenuto invio di notifiche amministratore o dell'utente finale e il controllo dell'evento per il controllo versioni successiva. Utenti utilizzare DLP per evitare involontaria divulgazione di informazioni riservate.
  
Per semplificare il raggiungimento di questo obiettivo, quando si crea un criterio DLP, è possibile scegliere **le impostazioni di semplice utilizzo**. Queste impostazioni consentono di tutte le informazioni che necessarie per implementare il criterio DLP più comune, senza dover ricorrere nell'editor di regole.
  
![Opzioni DLP per le impostazioni avanzate e semplici](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Impostazioni avanzate

Se è necessario creare più criteri DLP personalizzati, è possibile **utilizzare le impostazioni avanzate**.
  
Le impostazioni avanzate contiene l'editor regola, in cui si è controllo completo su tutte le possibili opzioni, tra cui il conteggio delle istanze e corrisponda accuratezza (livello di probabilità) per ogni regola.
  
Per passare rapidamente a una sezione, fare clic su un elemento nel riquadro di spostamento superiore dell'editor di regole per passare alla sezione riportata di seguito.
  
![Menu di spostamento superiore dell'editor regole DLP](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Modelli di criteri DLP

Il primo passaggio nella creazione di un criterio DLP è la scelta di informazioni per la protezione. Iniziando con un modello DLP si salva il lavoro di creazione di un nuovo set di regole da zero e capire quali tipi di informazioni devono essere inclusi per impostazione predefinita. È quindi possibile aggiungere o modificare questi requisiti per ottimizzare la regola per soddisfare esigenze specifiche dell'organizzazione.
  
Un modello di criterio DLP preconfigurato consente di rilevare specifiche tipologie di informazioni riservate, ad esempio dati HIPAA, dati PCI-DSS, dati Gramm-Leach-Bliley Act o informazioni personali anche specifiche delle impostazioni locali (P.I.). Per rendere più semplice per trovare e la protezione dei tipi comuni di informazioni riservate, i modelli di criteri inclusi in Office 365 già contengono i tipi di informazioni riservate più comuni necessari per iniziare a.
  
![Elenco dei modelli di criteri di prevenzione della perdita dei dati con lo stato attivo sul modello degli Stati Uniti Patriot Act](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
L'organizzazione può inoltre avere i proprio requisiti specifici, nel qual caso è possibile creare un criterio DLP da zero scegliendo l'opzione **criteri personalizzato** . Un criterio personalizzato è vuoto e non contiene predefinite regole. 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>Distribuzione graduale dei criteri DLP attraverso la modalità test

Quando si creano i criteri DLP, è consigliabile distribuire gradualmente per valutare l'impatto e testare l'efficacia prima di metterle. Ad esempio, non si desidera un nuovo criterio DLP inavvertitamente bloccare l'accesso a migliaia di documenti che gli utenti devono accedere per ottenere il loro lavoro.
  
Se si sta creando criteri DLP con un impatto potenziale di grandi dimensioni, è consigliabile sequenza indicata di seguito:
  
1. Rapporti di **avvio in modalità test senza suggerimenti sui criteri** e quindi utilizzare il DLP e qualsiasi incidente indicato per valutare l'impatto. È possibile utilizzare rapporti DLP per visualizzare il percorso, tipo di gravità del corrispondenze di criteri e il numero. In base ai risultati, è possibile ottimizzare le regole in base alle esigenze. In modalità di test, i criteri DLP non influirà la produttività delle persone che lavorano nell'organizzazione. 
    
2. **Passare alla modalità di Test con le notifiche e suggerimenti sui criteri** in modo da iniziare a fornire agli utenti di criteri di conformità e prepararli per le regole che verranno applicate. In questa fase, è inoltre possibile chiedere agli utenti di segnalare falsi positivi in modo che è possibile perfezionare le regole. 
    
3. **Avviare l'applicazione completa i criteri** in modo che le azioni nelle regole vengono applicate e il contenuto del protetto. Continuare a monitorare i report DLP e qualsiasi rapporti operazioni non consentite o le notifiche per assicurarsi che i risultati sono si prevede. 
    
![Opzioni per l'utilizzo della modalità di test e dell'attivazione dei criteri](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
È possibile disattivare un criterio DLP in qualsiasi momento, che influisce su tutte le regole del criterio. Tuttavia, ogni regola può anche essere disattivata singolarmente da attivare e disattivare il relativo stato nell'editor di regole.
  
![Opzioni per disattivare una regola in un criterio](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a>Rapporti DLP

Dopo aver creato e attivare i criteri DLP, è consigliabile verificare che si sta funzionino come previsto è e consentono di garantire la conformità. Rapporti DLP, è possibile visualizzare rapidamente il numero di criteri DLP e regola corrispondente nel tempo e il numero di falsi positivi e ha la precedenza. Per ogni report, è possibile filtrare le corrispondenze per ogni sede, l'intervallo di tempo e anche limitare la ricerca verso il basso per un criterio specifico, regola o azione.
  
Grazie ai report DLP, è possibile ottenere approfondimenti aziendali e:
  
- Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
- Individuare i processi aziendali che violano i criteri di conformità dell'organizzazione.
    
- Comprendere l'eventuale impatto aziendale dei criteri DLP.
    
Inoltre, è possibile utilizzare i report DLP per ottimizzare i criteri DLP, quando vengono eseguiti.
  
![Report Dashboard nel centro conformità e sicurezza](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Funzionamento dei criteri DLP

DLP permette di rilevare le informazioni riservate tramite un'analisi approfondita dei contenuti (non solo una semplice analisi del testo). Questa analisi approfondita utilizza corrispondenze delle parole chiave, del dizionario, la valutazione di espressioni regolari, funzioni interne e di altri metodi al fine di rilevare i contenuti corrispondenti ai criteri DLP. Viene considerata riservata potenzialmente solo una piccola percentuale dei dati. Un criterio DLP consente di identificare, monitorare e proteggere automaticamente solo tali dati, senza influire in alcun modo sul lavoro degli utenti con il resto del contenuto.
  
### <a name="policies-are-synced"></a>I criteri sono sincronizzati

Dopo aver creato un criterio DLP per la protezione &amp; centro conformità, abbia archiviati in un archivio centrale dei criteri e quindi sincronizzati con le origini di contenuto diversi, tra cui:
  
- Exchange Online e da caso Outlook sul web e Outlook 2013 e versioni successive
    
- Siti OneDrive for Business
    
- Siti SharePoint Online
    
- Programmi desktop di Office 2016 (Excel 2016, PowerPoint 2016 e Word 2016)
    
Dopo che il criterio del sincronizzati alle posizioni corrette, viene avviata la valutazione di contenuto e applicare azioni.
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Valutazione dei criteri nei siti OneDrive for Business e SharePoint Online

In tutti i siti di SharePoint Online e OneDrive per i siti, documenti cambiano continuamente, ovvero vengono continuamente vengono creati, modificati, condivise e così via. Ciò significa documenti sono in conflitto o essere conformi ai criteri DLP in qualsiasi momento. Ad esempio, un utente può caricare un documento che non contiene informazioni riservate a loro sito del team, ma in seguito, un'altra persona può modificare lo stesso documento e aggiungervi informazioni riservate.
  
Per questo motivo, i criteri DLP consentono di verificare la corrispondenza dei documenti ai criteri in background frequentemente. Tale operazione può essere considerata come una valutazione asincrona del criterio.
  
Ecco come funziona. Come utenti aggiungere o modificare documenti nei siti, il motore di ricerca analizza il contenuto, in modo che è possibile cercare lo più avanti. In questo corso, il contenuto analizzate anche per le informazioni riservate e per controllare se è condivisa. Informazioni riservate che si trova viene archiviate in modo sicuro nell'indice di ricerca, in modo che può accedere solo al team di conformità, ma gli utenti non tipici. Ogni criterio DLP che è attivato l'esecuzione in background (modalità asincrona), verifica frequentemente per qualsiasi contenuto corrispondente a un criterio di ricerca e l'applicazione di azioni per proteggerlo dal perdite involontarie.
  
![Figura che mostra come criterio DLP valuta contenuto in modo asincrono](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
Infine, i documenti possono essere in conflitto con un criterio DLP ma possono anche diventare conformi a tale criterio. Ad esempio, se una persona aggiunge numeri di carta di credito a un documento, è possibile che un criterio DLP blocchi l'accesso a tale documento automaticamente. Tuttavia, se in un secondo momento l'utente elimina le informazioni riservate, l'azione (in questo caso, di blocco) viene automaticamente annullata durante la successiva valutazione del documento rispetto al criterio.
  
DLP restituisce qualsiasi contenuto che può essere indicizzato. Per ulteriori informazioni su quali tipi di file la ricerca per indicizzazione per impostazione predefinita, vedere [estensioni di file a ricerca per indicizzazione e tipi di file in SharePoint Server 2013 analizzati predefiniti](https://go.microsoft.com/fwlink/p/?LinkID=627430).
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a>Valutazione dei criteri in Exchange Online, Outlook 2013 e versioni successive e Microsoft Outlook sul web

Quando si crea un criterio DLP che include Exchange Online come un percorso, il criterio del sincronizzato da Office 365 Security &amp; centro conformità Exchange Online e quindi da Exchange Online per Outlook sul web e Outlook 2013 e versioni successive.
  
Quando viene viene composto un messaggio di Outlook, l'utente può vedere Suggerimenti sui criteri come il contenuto che si sta creando viene valutato criteri DLP. E dopo l'invio di un messaggio viene valutata criteri DLP come una normale parte del flusso di posta, insieme ai criteri DLP creati nell'interfaccia di amministrazione di Exchange e le regole di trasporto di Exchange (vedere la sezione successiva per ulteriori informazioni sulla). Analisi dei criteri DLP messaggio e degli allegati.
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a>Valutazione dei criteri nei programmi desktop di Office 2016

Excel 2016, 2016 PowerPoint e Word 2016 includono le stesse funzionalità per identificare le informazioni riservate e applicare i criteri DLP come SharePoint Online e OneDrive for Business. Questi programmi Office 2016 sincronizzare i criteri DLP direttamente dall'archivio centrale dei criteri e quindi valutano continuamente il contenuto in base a criteri DLP quando gli utenti utilizzano i documenti aperti da un sito in cui è incluso in un criterio DLP.
  
La valutazione dei criteri DLP nel 2016 Office non è progettata per influire sulle prestazioni dei programmi o la produttività delle persone che lavorano sul contenuto. Se si sta lavorando su documenti di grandi dimensioni o nel computer dell'utente è occupato, potrebbe richiedere qualche secondo per un suggerimento criterio venga visualizzata.
  
## <a name="permissions"></a>Autorizzazioni

Membri del team di conformità che verranno creati criteri DLP devono delle autorizzazioni per la protezione &amp; centro conformità. Per impostazione predefinita, l'amministratore tenant potranno accedere a questa posizione e possono assegnare responsabili della conformità e altri utenti l'accesso alla protezione &amp; centro conformità, senza fornire tutte le autorizzazioni di un amministratore tenant. A tale scopo, è consigliabile è:
  
1. Creare un gruppo in Office 365 e aggiungervi i responsabili della conformità.
    
2. Creare un gruppo di ruoli nella pagina **autorizzazioni** di sicurezza &amp; centro conformità. 
    
3. Aggiungere il gruppo di Office 365 al gruppo di ruoli creato.
    
Per ulteriori informazioni, vedere [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).
  
Queste autorizzazioni sono necessarie solo per la creazione e l'applicazione di un criterio DLP. L'applicazione di un criterio non richiede l'accesso ai contenuti.
  
## <a name="find-the-dlp-cmdlets"></a>Trovare i cmdlet DLP

Utilizzare la maggior parte dei cmdlet per la sicurezza &amp; centro conformità, è necessario:
  
1. [Connettersi a Office 365 Security &amp; centro conformità utilizzando PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Utilizzare una qualsiasi delle domande [protezione di Office 365 &amp; cmdlet centro conformità](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Tuttavia, rapporti DLP necessario estrarre dati da tra Office 365, inclusi Exchange Online. Per questo motivo, i cmdlet per i rapporti DLP sono disponibili in Exchange Online Powershell, non in sicurezza &amp; Powershell centro conformità. Pertanto, per utilizzare i cmdlet per i rapporti DLP, è necessario:
  
1. [Connessione a Exchange Online tramite remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Utilizzare uno di questi cmdlet per i rapporti DLP:
    
  - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a>Ulteriori informazioni

- [Creare un criterio DLP da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    
- [Cosa individuano le funzioni DLP ](what-the-dlp-functions-look-for.md)
    
- [Creare un tipo di informazione riservata personalizzato](create-a-custom-sensitive-information-type.md)
    

