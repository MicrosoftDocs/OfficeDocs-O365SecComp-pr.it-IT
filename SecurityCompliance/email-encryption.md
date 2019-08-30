---
title: Crittografia della posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: Confrontare le opzioni di crittografia in Office 365, tra cui la crittografia dei messaggi di Office (OME), S/MIME, Information Rights Management (IRM) e introduce Transport Layer Security (TLS).
ms.openlocfilehash: 79a7ddd13e437255fa671e949236c879b235c2ba
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649951"
---
# <a name="email-encryption-in-office-365"></a>Crittografia della posta elettronica in Office 365

Questo articolo confronta le opzioni di crittografia in Office 365, tra cui la crittografia dei messaggi di Office (OME), S/MIME, Information Rights Management (IRM) e introduce Transport Layer Security (TLS).
  
Office 365 offre numerose opzioni di crittografia per soddisfare le esigenze aziendali sulla protezione della posta elettronica. Questo articolo presenta tre modi in cui crittografare la posta elettronica in Office 365. Per altre informazioni su tutte le caratteristiche di sicurezza di Office 365, visitare il [Centro protezione di Office 365](http://go.microsoft.com/fwlink/p/?LinkID=282470). In questo articolo vengono illustrati i tre tipi di crittografia disponibili per gli amministratori di Office 365 per proteggere la posta elettronica in Office 365:
  
- Crittografia messaggi di Office (OME).

- S/MIME (Secure/Multipurpose Internet Mail Extensions).

- Information Rights Management (IRM).

## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>Che cos'è la crittografia della posta elettronica e come viene utilizzata da Office 365?

La crittografia è il processo con cui le informazioni vengono codificate in modo che solo un destinatario autorizzato sia in grado di decodificarle e utilizzarle. Office 365 usa la crittografia in due modi: nel servizio e come controllo cliente. Nel servizio, la crittografia viene usata per impostazione predefinita in Office 365. Non è necessario configurare alcunché. Ad esempio, Office 365 utilizza Transport Layer Security (TLS) per crittografare la connessione o la sessione tra due server. 
  
Ecco come funziona in genere la crittografia della posta elettronica:
  
- Un messaggio viene crittografato o trasformato da testo normale a testo crittografato illeggibile, sul computer del mittente o da un server centrale, mentre il messaggio è in transito.

- Mentre è in transito, per impedire la lettura nel caso in cui venga intercettato, il messaggio rimane in testo crittografato.

- Dopo la ricezione da parte del destinatario, il messaggio viene trasformato nuovamente in testo normale leggibile in uno dei due modi indicati di seguito:

  - il computer del destinatario utilizza una chiave per decrittografare il messaggio, o

  - un server centrale decrittografa il messaggio per conto del destinatario, dopo averne convalidato l'identità.

Per ulteriori informazioni su come Office 365 protegge la comunicazione tra server, ad esempio tra le organizzazioni in Office 365 o tra Office 365 e un partner commerciale attendibile all'esterno di Office 365, vedere l’articolo su [come Exchange Online usa TLS per proteggere le connessioni in Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Questo video offre un'introduzione alla [crittografia in Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Confronto tra le opzioni di crittografia dei messaggi di posta elettronica disponibili in Office 365

||![Immagine concettuale che descrive OME](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Immagine concettuale che descrive IRM](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Immagine concettuale che descrive SMIME](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|Di cosa si tratta?|Crittografia messaggi di Office 365 (OME) è un servizio basato su Azure Rights Management (Azure RMS) che consente di inviare posta elettronica crittografata a destinatari interni o esterni all'organizzazione, indipendentemente dall'indirizzo di posta elettronica di destinazione (Gmail, Yahoo! Mail, Outlook.com e così via). <br/> Come amministratore, è possibile impostare le regole di trasporto che definiscono le condizioni per la crittografia. Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente. <br/> Per visualizzare messaggi crittografati, i destinatari possono ottenere un passcode monouso, accedere con un account Microsoft oppure accedere con un account aziendale o dell'istituto di istruzione associato a Office 365. I destinatari possono anche inviare risposte crittografate. Non è necessario un abbonamento a Office 365 per visualizzare i messaggi crittografati o inviare risposte crittografate.|IRM è una soluzione di crittografia che applica anche limitazioni di utilizzo ai messaggi di posta elettronica. Consente di impedire che informazioni riservate vengano stampate, inoltrate o copiate da persone non autorizzate. <br/> Le funzionalità IRM in Office 365 utilizzano Azure Rights Management (Azure RMS).|S/MIME è una soluzione di crittografia basata su certificato che permette di crittografare e firmare digitalmente un messaggio. La crittografia del messaggio fa sì che solo il destinatario desiderato possa aprire e leggere il messaggio. Una firma digitale permette al destinatario di convalidare l'identità del mittente. <br/> Le firme digitali e la crittografia dei messaggi vengono entrambe rese possibili tramite l'uso di certificati digitali univoci che contengono le chiavi per la verifica delle firme digitali e per la crittografia o la decrittografia dei messaggi. <br/> Per usare S/MIME, è necessario avere chiavi pubbliche su file per ogni destinatario. I destinatari devono conservare le proprie chiavi private, che devono rimanere protette. Se le chiavi private di un destinatario vengono danneggiate, il destinatario deve ottenere una nuova chiave privata e distribuire nuovamente le chiavi pubbliche a tutti i potenziali mittenti.|
|Quali operazioni consente di eseguire la soluzione?|OME: <br/> Consente di crittografare i messaggi inviati a destinatari interni o esterni. <br/>  Consente agli utenti di inviare messaggi crittografati a qualsiasi indirizzo di posta elettronica, tra cui Outlook.com, Yahoo! Mail e Gmail. <br/>  Consente all'amministratore di personalizzare il portale di visualizzazione della posta elettronica per riflettere il marchio dell'organizzazione. <br/> Microsoft gestisce e archivia in modo sicuro le chiavi per conto dell'utente. <br/> Se il messaggio crittografato (inviato come allegato HTML) può essere aperto in un browser, non è necessario alcun software specifico dal lato client.|IRM: <br/> Usa la crittografia e le restrizioni di utilizzo per fornire protezione online e offline per i messaggi e gli allegati di posta elettronica. <br/> Fornisce all'amministratore la possibilità di configurare le regole di trasporto o le regole di protezione di Outlook per applicare automaticamente la protezione IRM per selezionare i messaggi. <br/> Consente agli utenti di applicare manualmente i modelli di Outlook o Outlook sul web (in precedenza noto come Outlook Web App).|Autenticazione del mittente di indirizzi S/MIME con le firme digitali e riservatezza dei messaggi con la crittografia.|
|Quali sono le operazioni che la soluzione non consente?|OME non consente l'applicazione di limitazioni di utilizzo ai messaggi. Ad esempio, non è possibile utilizzare la soluzione per impedire a un destinatario di inoltrare o stampare un messaggio crittografato.|Alcune applicazioni potrebbero non supportare i messaggi di posta elettronica IRM su tutti i dispositivi. Per altre informazioni su questi e altri prodotti per il supporto della posta elettronica IRM, vedere [Funzionalità del dispositivo client](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|S/MIME non consente l'analisi dei messaggi crittografati per verificare la presenza di malware, posta indesiderata o dei criteri.|
|Consigli e scenari di esempio|È consigliabile utilizzare OME quando si desidera inviare informazioni aziendali riservate a persone esterne all'organizzazione, ovvero utenti o altre aziende. Ad esempio:  <br/>  Un dipendente di banca invia comunicazioni sulla carta di credito ai clienti  <br/>  Un medico che invia cartelle cliniche a un paziente  <br/>  Un avvocato invia informazioni legali riservate a un altro avvocato|Si consiglia di utilizzare IRM per applicare limitazioni di utilizzo e la crittografia. Esempio:  <br/>  Un responsabile che invia informazioni riservate al team su un nuovo prodotto applicando l'opzione "Non inoltrare".  <br/>  Un dirigente che deve condividere una proposta di offerta con un'altra società, che include un allegato inviato da un partner che utilizza Office 365 e richiede che la posta elettronica e l'allegato siano entrambi protetti.|Si consiglia di utilizzare S/MIME quando la propria organizzazione o quella del destinatario richiede una reale crittografia peer-to-peer.  <br/>  S/MIME viene utilizzato più comunemente nei seguenti scenari:  <br/>  Comunicazione tra enti pubblici e altri enti governativi  <br/>  Comunicazioni tra un'azienda e un ente governativo|
||

## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>Quali sono le opzioni di crittografia disponibili per il mio abbonamento a Office 365?

Per informazioni sulle opzioni di crittografia disponibili per l'abbonamento a Office 365, vedere la [descrizione del servizio Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx). Qui è possibile trovare informazioni sulle seguenti funzionalità di crittografia:
  
- Azure RMS, OME e le funzionalità IRM

- S/MIME

- TLS

- Crittografia dei dati statici (tramite BitLocker)

Con Office 365 è anche possibile usare strumenti di crittografia di terze parti, ad esempio PGP (Pretty Good Privacy). Office 365 non supporta PGP/MIME ed è possibile usare solo PGP/Inline per inviare e ricevere messaggi di posta elettronica crittografati con PGP.

## <a name="what-about-encryption-for-data-at-rest"></a>Informazioni sulla crittografia dei dati inattivi

L'espressione "dati statici" fa riferimento ai dati non attivamente in transito. In Office 365, i dati statici della posta elettronica vengono crittografati utilizzando Crittografia unità BitLocker. BitLocker consente di crittografare i dischi rigidi nei data center di Office 365 per fornire protezione avanzata da accessi non autorizzati. Per altre informazioni, vedere [Panoramica di BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Ulteriori informazioni sulle opzioni di crittografia dei messaggi di posta elettronica in Office 365

Per altre informazioni sulle opzioni di crittografia della posta elettronica descritte in questo articolo e su TLS, vedere questi articoli:
  
**OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
**IRM**
  
[Information Rights Management in Exchange Online](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Informazioni su Azure Rights Management](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[S/MIME per la crittografia e firma dei messaggi](https://technet.microsoft.com/library/dn626158)
  
[Informazioni su S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Informazioni sulla crittografia a chiave pubblica](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[Configurare il flusso di posta tramite connettori in Office 365](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
