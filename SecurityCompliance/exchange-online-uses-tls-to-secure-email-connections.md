---
title: Come viene utilizzato TLS in Exchange Online per proteggere il traffico della posta elettronica in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
description: Informazioni su come Exchange Online e Office 365 utilizzare Transport Layer Security (TLS) e Forward Secrecy (ADFS) per proteggere le comunicazioni di posta elettronica. Informazioni sul certificato emesso da Microsoft per Exchange Online.
ms.openlocfilehash: 079a6f574838f5710dbbbcb53726799abfae1d3a
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520145"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Come viene utilizzato TLS in Exchange Online per proteggere il traffico della posta elettronica in Office 365

Informazioni su come Exchange Online e Office 365 utilizzare Transport Layer Security (TLS) e Forward Secrecy (ADFS) per proteggere le comunicazioni di posta elettronica. Fornisce informazioni sul certificato emesso da Microsoft per Exchange Online.
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Introduzione a TLS per Office 365 ed Exchange Online

Transport Layer Security (TLS) e SSL create prima di TLS, vengono crittografati protocolli di proteggere le comunicazioni su una rete tramite i certificati di protezione per crittografare una connessione tra i computer. TLS sostituisce Secure Sockets Layer (SSL) e viene spesso SSL 3.1. Per Exchange Online, si utilizza TLS per crittografare le connessioni tra i server Exchange e le connessioni tra i server Exchange e altri server, ad esempio i server di Exchange in locale o server di posta elettronica ai destinatari. Dopo la connessione è crittografata, tutti i dati inviati tramite tale connessione inviati attraverso il canale di crittografia. Se, tuttavia si inoltra un messaggio in cui è stato inviato tramite una connessione crittografata TLS, il messaggio non è necessariamente crittografato. Ciò avviene perché in altre parole, TLS non crittografare il messaggio, solo la connessione.
  
Se si desidera crittografare il messaggio, è necessario utilizzare una tecnologia di crittografia che consenta di crittografare i contenuti dei messaggi come, ad esempio, Crittografia messaggi di Office. Per informazioni sulle opzioni di crittografia dei messaggi in Office 365, vedere [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md). 
  
È consigliabile utilizzare TLS nei casi in cui si desidera impostare un canale protetto di corrispondenza tra Office 365 e l'organizzazione locale o un'altra organizzazione, ad esempio un partner. Exchange Online sempre tenta prima di utilizzare TLS per proteggere la posta elettronica, ma non è sempre effettuare questa operazione se l'altra parte scapito della sicurezza TLS. Continuare a leggere per scoprire come è possibile proteggere tutta la posta al server locali o importanti partner utilizzando *i connettori*questo. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Come viene utilizzato TLS in Exchange Online tra clienti di Exchange Online

I server di Exchange Online consentono di crittografare sempre le connessioni ad altri server di Exchange Online nei nostri datacenter con TLS 1.2. Quando si invia la posta a un destinatario all'interno dell'organizzazione di Office 365, la posta elettronica viene inviata automaticamente tramite una connessione crittografata utilizzando TLS. Inoltre, tutta la posta elettronica inviata agli altri clienti di Office 365 viene inviata tramite connessioni che vengono crittografate con TLS e protette utilizzando Forward Secrecy.
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Utilizzo di TLS tra Office 365 e partner esterni, attendibili Office 365

Per impostazione predefinita, Exchange Online utilizza sempre TLS opportunistico. Di conseguenza, Exchange Online sempre tenta di crittografare le connessioni con la versione più sicura di TLS prima, quindi verso il basso l'elenco delle cifre TLS può essere utilizzato fino a individuare quella in cui è possono accettare entrambi i partecipanti. A meno che non è stato configurato Exchange Online per garantire che i messaggi al destinatario vengono inviati solo tramite connessioni protette, quindi per impostazione predefinita il messaggio verrà inviato se l'organizzazione del destinatario non supporta la crittografia TLS. TLS opportunistico è sufficiente per la maggior parte delle aziende. Tuttavia, per le aziende che hanno requisiti di conformità, ad esempio medici, banca o organizzazioni governative, è possibile configurare Exchange Online in modo da richiedere o imporre, TLS. Per ulteriori informazioni, vedere [configurare il flusso di posta utilizzando i connettori in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Se si decide di configurare TLS tra l'organizzazione e un'organizzazione partner di fiducia, Exchange Online può utilizzare TLS forzato per creare i canali di comunicazione attendibili. TLS forzato richiede l'organizzazione partner di autenticarsi a Exchange Online con un certificato di protezione per inviare posta a un utente. Sarà necessario il partner di gestire i propri certificati per eseguire questa operazione. In Exchange Online, connettori viene utilizzato per proteggere i messaggi inviati dall'accesso non autorizzato prima di raggiungere il provider di posta elettronica del destinatario. Per informazioni sull'utilizzo di connettori per configurare il flusso di posta elettronica, vedere [configurare il flusso di posta utilizzando i connettori in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e distribuzioni ibride di Exchange Server

Se si sta gestendo una distribuzione ibrida di Exchange, le esigenze di server di Exchange locale per l'autenticazione con Office 365 utilizzando un certificato di protezione per inviare posta a destinatari le cui cassette postali sono solo in Office 365. Di conseguenza, è necessario gestire i propri certificati di sicurezza per i server Exchange locale. In modo sicuro, è necessario archiviare e gestire i certificati del server. Per ulteriori informazioni sulla gestione dei certificati nelle distribuzioni ibride, vedere [requisiti relativi ai certificati per le distribuzioni ibride](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Come configurare TLS forzato per Exchange Online in Office 365

Per i clienti di Exchange Online, in modo che TLS forzato per l'utilizzo per la protezione di tutta la posta elettronica inviata e ricevuta, è necessario impostare più di un connettore che è necessario TLS. È necessario un solo connettore per la posta elettronica inviato alle cassette postali utente e un altro connettore per la posta elettronica inviato dalle cassette postali degli utenti. Creare questi connettori nell'interfaccia di amministrazione di Exchange in Office 365. Per ulteriori informazioni, vedere [configurare il flusso di posta utilizzando i connettori in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informazioni sul certificato TLS per Exchange Online

Nella tabella seguente sono riportate informazioni il certificato utilizzate da Exchange Online. Se il partner commerciale configurazione TLS forzato sul proprio server di posta elettronica, è necessario fornire tali informazioni a loro. Tenere presente che per motivi di sicurezza, i certificati modificare nel tempo. È stata di implementazione un aggiornamento per il certificato entro i centri dati. Il nuovo certificato è valido da 3 settembre 2018.
  
 **Informazioni del certificato corrente valide da 3 settembre 2018**
  
|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |CA-R1 GlobalSign principale <br/> |
|Nome certificato  <br/> |Mail.Protection.Outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
 **Informazioni sui certificati deprecati valido fino a 3 settembre 2018**
  
Per garantire una transizione senza problemi, si continuerà a fornire le informazioni del certificato precedente per riferimento per un certo tempo, tuttavia, è necessario utilizzare le informazioni del certificato corrente da questo punto in poi.
  
****

|**Attributo**|**Valore**|
|:-----|:-----|
|Autorità di certificazione principale  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome certificato  <br/> |Mail.Protection.Outlook.com  <br/> |
|Organizzazione  <br/> |Microsoft Corporation  <br/> |
|Unità organizzativa  <br/> |Microsoft Corporation  <br/> |
|Forza della chiave del certificato  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparare il nuovo certificato di Exchange Online

Il nuovo certificato emesso da un'autorità di certificazione diversi (CA) dal precedente dei certificati utilizzati da Exchange Online. Di conseguenza, è necessario eseguire alcune operazioni prima di poterlo per utilizzare il nuovo certificato.

Il nuovo certificato è necessaria la connessione agli endpoint dell'autorità di certificazione nuovo come parte di convalida del certificato. In caso contrario può causare un flusso di posta negativamente venga modificato. Se è proteggere i server di posta elettronica con i firewall che consentono solo i server di posta connettersi con determinate destinazioni che è necessario verificare se il server è in grado di convalidare il nuovo certificato. Per verificare che il server può utilizzare il nuovo certificato, completare la procedura seguente:

1. Connettersi al Server Exchange locale tramite Windows PowerShell e quindi eseguire il comando seguente:  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. Nella finestra visualizzata scegliere **recuperare**.
3. Quando l'utilità viene completato il controllo viene restituito lo stato. Se lo stato viene visualizzato **OK**, il server di posta convalidare correttamente il nuovo certificato. In caso contrario, è necessario determinare la causa le connessioni ai esito negativo. È probabile che è necessario aggiornare le impostazioni di un firewall. Un elenco completo degli endpoint che devono accedere includono:
    - OCSP.GlobalSign.com
     - CRL.GlobalSign.com
     - Secure.GlobalSign.com   

In genere, si ricevere gli aggiornamenti per i certificati radice automaticamente tramite Windows Update. Tuttavia alcune distribuzioni disporre aggiuntive per la protezione che impedisce che si verifichino automaticamente gli aggiornamenti. Questi bloccato nelle distribuzioni in cui Windows Update non possono aggiornare automaticamente i certificati radice, è necessario assicurarsi che sia installato il certificato CA radice corretto completando la procedura seguente:
1.  Connettersi al Server Exchange locale tramite Windows PowerShell e quindi eseguire il comando seguente:  
  `certmgr.msc`
2. In **Certificati radice attendibili certificazione autorità /**, verificare che il nuovo certificato sia elencato.

## <a name="get-more-information-about-tls-and-office-365"></a>Ulteriori informazioni su TLS e Office 365

Per un elenco di pacchetto di crittografia supportato, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](technical-reference-details-about-encryption.md).
  
[Impostare i connettori per il flusso di posta sicura con un'organizzazione partner](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Connettori con protezione della posta elettronica avanzate](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Crittografia in Office 365](encryption.md)
  

