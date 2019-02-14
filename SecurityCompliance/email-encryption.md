---
title: Crittografia della posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: Confrontare le opzioni di crittografia in Office 365, tra cui la crittografia messaggi Office (OME), S/MIME, Information Rights Management (IRM) e informazioni sulla sicurezza TLS (Transport Layer).
ms.openlocfilehash: a6db6c9cf6af180fe84e955613fb6b1175ee0747
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995357"
---
# <a name="email-encryption-in-office-365"></a>Crittografia della posta elettronica in Office 365

In questo articolo vengono messi a confronto le opzioni di crittografia in Office 365, tra cui la crittografia messaggi Office (OME), S/MIME, Information Rights Management (IRM) e sono state introdotte Transport Layer Security (TLS).
  
Office 365 offre più opzioni di crittografia che consentono di soddisfare le esigenze aziendali per la protezione della posta elettronica. In questo articolo vengono illustrate tre modi per crittografare la posta elettronica in Office 365. Per ulteriori informazioni su tutte le funzionalità di sicurezza in Office 365, visitare il [Centro protezione di Office 365](http://go.microsoft.com/fwlink/p/?LinkID=282470). In questo articolo vengono presentati i tre tipi di crittografia disponibile per gli amministratori di Office 365 proteggere la posta elettronica in Office 365:
  
- Crittografia messaggi di Office (OME).
    
- S/MIME (Secure/Multipurpose Internet Mail Extensions).
    
- Information Rights Management (IRM).
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>Che cos'è la crittografia della posta elettronica e come viene utilizzata da Office 365?

La crittografia è il processo di base alla quale le informazioni vengono codificate in modo che solo un destinatario autorizzato può decodificare e utilizzare le informazioni. Office 365 viene utilizzata la crittografia in due modi: nel servizio e come controllo cliente. Nel servizio, viene utilizzata la crittografia in Office 365 per impostazione predefinita. non è necessario configurare altre. Ad esempio Office 365 utilizza Transport Layer Security (TLS) per crittografare la connessione o sessione tra due server. 
  
Ecco come funziona in genere la crittografia di posta elettronica:
  
- Un messaggio viene crittografato o trasformato dal testo normale in testo crittografato illeggibile, nel computer del mittente o da un server centrale mentre il messaggio è in corso.
    
- Il messaggio rimane in testo crittografato mentre è in corso per proteggerlo dal letti nel caso in cui il messaggio viene intercettato.
    
- Dopo la ricezione da parte del destinatario, il messaggio viene trasformato nuovamente in testo normale leggibile in uno dei due modi indicati di seguito:
    
  - Computer del destinatario utilizza una chiave per decrittografare il messaggio o
    
  - Un server centrale consente di decrittografare il messaggio per conto del destinatario, dopo la convalida di identità del destinatario.
    
Per ulteriori informazioni sulla modalità di protezione delle comunicazioni tra i server Office 365, ad esempio tra organizzazioni all'interno di Office 365 o tra Office 365 e un partner commerciale attendibile all'esterno di Office 365, vedere [come Exchange Online utilizza TLS per proteggere la posta elettronica connessioni in Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Guardare questo video per avere un'introduzione alla [crittografia in Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Confronto tra le opzioni di crittografia dei messaggi di posta elettronica disponibili in Office 365

||        ![Immagine concettuale che descrive OME](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)                 |        ![Immagine concettuale che descrive IRM](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)                 |        ![Immagine concettuale che descrive SMIME](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)                |
|:-----|:-----|:-----|:-----|
|Di cosa si tratta?  <br/> |Crittografia messaggi di Office 365 (OME) è un servizio basato su Azure Rights Management (Azure RMS) che consente di inviare posta elettronica crittografata a destinatari interni o esterni all'organizzazione, indipendentemente dall'indirizzo di posta elettronica di destinazione (Gmail, Yahoo! Mail, Outlook.com e così via).  <br/> Come amministratore, è possibile impostare le regole di trasporto che definiscono le condizioni per la crittografia. Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente.  <br/> Per visualizzare i messaggi crittografati, i destinatari possono ottenere un passcode occasionale, accedere con un account Microsoft o accedere con un ufficio o scuola account associate a Office 365. I destinatari possono inoltre inviare le risposte crittografate. Non è necessaria una sottoscrizione a Office 365 per visualizzare i messaggi crittografati o inviare risposte crittografate.  <br/> |IRM è una soluzione di crittografia che applica anche limitazioni di utilizzo ai messaggi di posta elettronica. Consente di impedire che informazioni riservate vengano stampate, inoltrate o copiate da persone non autorizzate.  <br/> Le funzionalità IRM in Office 365 utilizzano Azure Rights Management (Azure RMS). 
  <br/> |S/MIME è una soluzione di crittografia basata su certificati che consente di crittografare sia firmare digitalmente un messaggio. La crittografia dei messaggi si assicura che solo il destinatario può aprire e leggere il messaggio. Una firma digitale consente al destinatario di convalidare l'identità del mittente.  <br/> Le firme digitali e la crittografia dei messaggi sono resi possibili tramite certificati digitali univoci contenenti le chiavi per la verifica delle firme digitali e per la crittografia oppure la decrittografia dei messaggi.  <br/> Per utilizzare S/MIME, è necessario disporre delle chiavi pubbliche nel file di ogni destinatario. Destinatari costretto a gestire i propri chiavi private, devono restare protette. Se sono state compromesse chiavi private del destinatario, il destinatario deve ottenere una nuova chiave privata e ridistribuire le chiavi pubbliche a tutti i mittenti possibili.  <br/> |
|Quali operazioni consente di eseguire la soluzione?  <br/> | OME:  <br/>  Consente di crittografare i messaggi inviati a destinatari interni o esterni.  <br/>  Consente agli utenti di inviare messaggi crittografati a qualsiasi indirizzo di posta elettronica, tra cui Outlook.com, Yahoo! Mail e Gmail.  <br/>  Consente di, come un amministratore per personalizzare il messaggio di posta elettronica visualizzazione del portale in modo da riflettere marchio dell'organizzazione.  <br/>  Microsoft gestisce in modo sicuro e archivia le chiavi, in modo che non è necessario.  <br/>  Se il messaggio crittografato (inviato come allegato HTML) può essere aperto in un browser, non è necessario alcun software specifico dal lato client.  <br/> | IRM:  <br/>  Utilizza la crittografia e le limitazioni di utilizzo per fornire protezione online e offline per messaggi di posta elettronica e allegati.  <br/>  Fornisce all'amministratore la possibilità di configurare le regole di trasporto o le regole di protezione di Outlook per applicare automaticamente la protezione IRM per selezionare i messaggi.  <br/>  Consente agli utenti di applicare manualmente i modelli di Outlook o Outlook Web App.  <br/> |Autenticazione del mittente di indirizzi S/MIME con le firme digitali e riservatezza dei messaggi con la crittografia.  <br/> |
|Quali sono le operazioni che la soluzione non consente?  <br/> |OME non è possibile applicare restrizioni di utilizzo per i messaggi. Ad esempio, è possibile utilizzare per interrompere un destinatario di inoltro o la stampa di un messaggio crittografato.  <br/> |Alcune applicazioni potrebbero non supportare messaggi di posta elettronica IRM in tutti i dispositivi. Per ulteriori informazioni su questi e altri prodotti che supportano la posta elettronica IRM, vedere [funzionalità dei dispositivi Client](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).<br/> |S/MIME non consentire i messaggi crittografati da analizzare per malware, posta indesiderata o dei criteri.  <br/> |
|Consigli e scenari di esempio  <br/> | È consigliabile utilizzare OME quando si desidera inviare informazioni aziendali riservate a utenti esterni all'organizzazione, sia che si acceda consumer o altre imprese. Per esempio:  <br/>  Un dipendente di banca invia comunicazioni sulla carta di credito ai clienti  <br/>  Office del medico invio cliniche al paziente  <br/>  Un avvocato invia informazioni legali riservate a un altro avvocato  <br/> | Si consiglia di utilizzare IRM per applicare limitazioni di utilizzo e la crittografia. Esempio:  <br/>  Un responsabile l'invio di informazioni riservate al proprio team su un nuovo prodotto applica l'opzione "Non inoltrare".  <br/>  Un dirigente che deve condividere una proposta di offerta con un'altra società, che include un allegato inviato da un partner che utilizza Office 365 e richiede che la posta elettronica e l'allegato siano entrambi protetti.  <br/> | È consigliabile utilizzare S/MIME quando l'organizzazione o l'organizzazione del destinatario richiede vera e propria crittografia peer-to-peer.  <br/>  S/MIME viene utilizzato più comunemente nei seguenti scenari:  <br/>  Comunicazione tra enti pubblici e altri enti governativi  <br/>  Comunicazioni tra un'azienda e un ente governativo  <br/> |
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>Quali sono le opzioni di crittografia disponibili per il mio abbonamento a Office 365?

Per informazioni sulle opzioni di crittografia di posta elettronica per la sottoscrizione a Office 365, vedere la [descrizione del servizio Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx). In questo caso, è possibile trovare informazioni sulle caratteristiche di crittografia seguenti:
  
- Azure RMS, tra cui funzionalità IRM e OME
    
- S/MIME
    
- TLS
    
- Crittografia dei dati statici (tramite BitLocker)
    
## <a name="what-about-encryption-for-data-at-rest"></a>Informazioni sulla crittografia dei dati statici

"Dati statici" si riferisce a dati in transito, non sono attiva. In Office 365, dati di posta elettronica statici viene crittografati tramite crittografia unità BitLocker. BitLocker consente di crittografare i dischi rigidi nei Data Center di Office 365 per fornire la protezione avanzata da accessi non autorizzati. Per ulteriori informazioni, vedere [BitLocker Overview](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>Ulteriori informazioni sulle opzioni di crittografia dei messaggi di posta elettronica in Office 365

Per ulteriori informazioni sulle opzioni di crittografia dei messaggi di posta elettronica in questo articolo, nonché TLS, vedere gli articoli:
  
 **OME**
  
[Office 365 Message Encryption (OME)](ome.md)
  
 **IRM**
  
[Information Rights Management in Exchange Online](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[Che cos'è Azure Rights Management?](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[S/MIME per la crittografia e firma dei messaggi](https://technet.microsoft.com/library/dn626158)
  
[Informazioni sui S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Crittografia a chiave pubblica](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[Configurare il flusso di posta personalizzati utilizzando i connettori in Office 365](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

