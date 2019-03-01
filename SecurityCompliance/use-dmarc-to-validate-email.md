---
title: Utilizzare DMARC per convalidare la posta elettronica in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: TN2DMC
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare l'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità (DMARC) per convalidare i messaggi inviati dall'organizzazione di Office 365.
ms.openlocfilehash: d224acaf6b1d53cdf9ababca87c5880a5499c613
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341577"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>Utilizzare DMARC per convalidare la posta elettronica in Office 365

L'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità ([DMARC](https://dmarc.org)) è compatibile con il servizio Sender Policy Framework (SPF) e la posta DomainKeys identificata (DKIM) per autenticare i mittenti di posta elettronica e garantire che i sistemi di posta elettronica di destinazione consideri attendibili il dominio. L'implementazione di DMARC con SPF e DKIM garantisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC aiuta la ricezione dei sistemi di posta elettronica a determinare cosa fare con i messaggi inviati dal dominio che non superano i controlli SPF o DKIM.
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>In che modo SPF e DMARC collaborano per proteggere la posta elettronica in Office 365?
<a name="SPFandDMARC"> </a>

 Un messaggio di posta elettronica potrebbe contenere più originatori o mittenti, indirizzi. Questi indirizzi sono utilizzati per scopi differenti. Ad esempio, si consideri quanto segue: 
  
- **Indirizzo "posta da"**: identifica il mittente e specifica dove inviare gli avvisi di reso se si verificano problemi con il recapito del messaggio, ad esempio le notifiche di mancato recapito. Viene visualizzato nella parte busta di un messaggio di posta elettronica e di solito non viene visualizzato dall'applicazione di posta elettronica. A volte viene chiamato l'indirizzo 5321. MailFrom o l'indirizzo del percorso inverso.
    
- **Indirizzo "da"**: l'indirizzo visualizzato come indirizzo da dall'applicazione di posta elettronica. Questo indirizzo identifica l'autore del messaggio di posta elettronica. Ovvero, la cassetta postale della persona o del sistema responsabile della scrittura del messaggio. A volte viene chiamato indirizzo 5322. from.
    
SPF Usa un record TXT DNS per fornire un elenco di indirizzi IP di invio autorizzati per un determinato dominio. Normalmente, i controlli SPF vengono eseguiti solo in base all'indirizzo 5321.MailFrom. Ciò significa che l'indirizzo 5322.From non è autenticato quando si usa SPF. Ciò consente uno scenario in cui un utente può ricevere un messaggio che supera un controllo SPF, ma presenta un indirizzo mittente 5322.From falsificato. Si consideri, ad esempio, la seguente trascrizione SMTP:
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

In questa trascrizione, gli indirizzi mittente sono i seguenti:
  
- Indirizzo Mail from (5321.MailFrom): phish@phishing.contoso.com
    
- Indirizzo From (5322.From): security@woodgrovebank.com
    
Se è stato configurato SPF, il server di ricezione esegue un controllo sull'indirizzo Mail from phish@phishing.contoso.com. Se il messaggio proviene da un'origine valida per il dominio phishing.contoso.com, allora supera il controllo SPF. Poiché il client di posta elettronica mostra solo l'indirizzo From, l'utente visualizza che il messaggio proviene da security@woodgrovebank.com. Solo con SPF, la validità di woodgrovebank.com non era mai stata autenticata.
  
Quando si utilizza DMARC, anche il server di ricezione esegue un controllo sull'indirizzo From. Nell'esempio precedente, se esiste un record TXT DMARC per woodgrovebank.com, allora il controllo sull'indirizzo From avrà esito negativo.
  
## <a name="what-is-a-dmarc-txt-record"></a>Che cos'è un record TXT DMARC?
<a name="WhatisDMARC"> </a>

Come i record DNS per SPF, il record per DMARC è un record di testo DNS che consente di prevenire spoofing e phishing. Viene pubblicato i record TXT DMARC in DNS. I record TXT DMARC consentono di convalidare l'origine dei messaggi di posta elettronica verificando l'indirizzo IP dell'autore della posta elettronica in base al proprietario del dominio del mittente. I record TXT DMARC identificano i server di posta elettronica in uscita autorizzati. I sistemi di posta elettronica di destinazione possono quindi verificare che l'origine dei messaggi ricevuti sia un server di posta elettronica in uscita autorizzato.
  
Il record TXT DMARC di Microsoft è simile al seguente:
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

Microsoft invia i suoi report DMARC a [Agari](https://agari.com), una terza parte. Agari raccoglie e analizza i report DMARC.
  
## <a name="implement-dmarc-for-inbound-mail"></a>Implementare DMARC per la posta in ingresso
<a name="implementDMARCinbound"> </a>

Non serve fare nulla per configurare DMARC per la posta ricevuta in Office 365. Microsoft si occupa di tutto. Per sapere cosa succede alla posta che non supera i controlli DMARC, vedere [Modalità di gestione della posta elettronica in ingresso che non supera DMARC da parte di Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail).
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>Implementare DMARC per la posta in uscita da Office 365
<a name="implementDMARCoutbound"> </a>

Se si usa Office 365, ma non si utilizza un dominio personalizzato, vale a dire, si usa onmicrosoft.com, non è necessario eseguire altre operazioni per configurare o implementare DMARC per l'organizzazione. SPF è già configurato e Office 365 genera automaticamente una firma DKIM per la posta in uscita. Per ulteriori informazioni sulla firma, vedere [Comportamento predefinito per DKIM e Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
 Se si dispone di un dominio personalizzato o si utilizzano i server Exchange locali oltre a Office 365, è necessario implementare manualmente DMAR per la posta in uscita. L'implementazione DMARC per il dominio personalizzato include questa procedura: 
  
- [Passaggio 1: identificare le origini valide della posta del dominio](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [Passaggio 2: configurare SPF per il dominio in Office 365](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [Passaggio 3: configurare DKIM per il dominio personalizzato in Office 365](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [Passaggio 4: formare il record TXT DMARC del dominio in Office 365](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Passaggio 1: identificare le origini valide della posta del dominio
<a name="IdentifyValidSources"> </a>

Se SPF è già stato configurato, allora questo esercizio è già stato completato. Tuttavia, per DMARC, occorre fare altre considerazioni. Quando si identificano origini di posta per il dominio, occorre rispondere a due domande:
  
- Quali indirizzi IP inviano messaggi da qualsiasi dominio?
    
- Per i messaggi inviati da terze parti per conto dell'utente, i domini 5321.MailFrom e 5322.From corrisponderanno?
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>Passaggio 2: configurare SPF per il dominio in Office 365
<a name="ConfigSPF"> </a>

Ora che si dispone di un elenco di mittenti validi, è possibile seguire la procedura per [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  
Ad esempio, presupponendo che contoso.com invia un messaggio da Exchange Online, un server Exchange locale il cui indirizzo IP è 192.168.0.1 e un'applicazione Web il cui indirizzo IP è 192.168.100.100, il record TXT SPFsarà simile alla seguente:
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Come procedura consigliata, assicurarsi che il record TXT SPF tenga in considerazione mittenti di terze parti.
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>Passaggio 3: configurare DKIM per il dominio personalizzato in Office 365
<a name="ConfigDKIM"> </a>

Dopo aver configurato SPF, è necessario configurare DKIM. DKIM consente di aggiungere una firma digitale ai messaggi di posta elettronica nell'intestazione del messaggio. Se non si configura DKIM e si consente invece a Office 365 di usare la configurazione DKIM predefinita per il dominio, DMARC potrebbe non riuscire. Questo perché la configurazione DKIM predefinita utilizza il dominio onmicrosoft.com iniziale come indirizzo 5322.From, non il dominio personalizzato. Ciò forza una mancata corrispondenza tra gli indirizzi 5321.MailFrom e 5322.From in tutta la posta elettronica inviata dal dominio.
  
Se si dispone di mittenti di terze parti che inviano posta per conto dell'utente e la posta inviata presenta indirizzi 5321.MailFrom e 5322.From non corrispondenti, DMARC non riuscirà per tale posta elettronica. Per evitare il problema, è necessario configurare DKIM per il dominio in modo specifico con tale mittente di terze parti. In questo modo Office 365 potrà autenticare la posta elettronica dal servizio di terze parti. Tuttavia, inoltre consente ad altri, ad esempio, Yahoo, Gmail e Comcast, di verificare la posta elettronica inviata a loro da terze parti come se la posta elettronica fosse stata inviata dall'utente. Ciò è utile perché consente ai clienti di creare fiducia nel dominio indipendentemente da dove si trova la loro cassetta postale e, contemporaneamente, Office 365 non contrassegnerà un messaggio come posta indesiderata a causa dello spoofing perché supera i controlli di autenticazione del dominio.
  
Per istruzioni sulla configurazione di DKIM del dominio e su come configurare DKIM per mittenti di terze parti affinché possano effettuare lo spoofing del dominio, vedere [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>Passaggio 4: formare il record TXT DMARC del dominio in Office 365
<a name="CreateDMARCRecord"> </a>

Anche se sono disponibili altre opzioni di sintassi non menzionate qui, queste sono le opzioni più comunemente utilizzate per Office 365. Formare il record TXT DMARC per il dominio nel formato:
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

dove:
  
- *Domain* è il dominio che si desidera proteggere. Per impostazione predefinita, il record protegge la posta dal dominio e da tutti i sottodomini. Ad esempio, se si specifica \_DMARC.contoso.com, DMARC proteggerà la posta dal dominio e da tutti i sottodomini, come housewares.contoso.com o plumbing.contoso.com. 
    
- Il valore *TTL* deve essere sempre uguale a un'ora. L'unità utilizzata per TTL, ovvero le ore (1 ora), i minuti (60 minuti) o i secondi (3600 secondi) variano a seconda del registrar per il dominio. 
    
- *PCT = 100* indica che questa regola deve essere utilizzata per il 100% del messaggio di posta elettronica.
    
- *criterio* specifica quali criteri si desidera che il server di ricezione segua se DMARC ha esito negativo. È possibile impostare il criterio su None, Quarantine o Reject. 
    
Per informazioni sulle opzioni da usare, acquisire familiarità con i concetti illustrati in [Procedure consigliate per l'implementazione di DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).
  
Esempi:
  
- Criterio impostato su none
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Criterio impostato su quarantine
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Criterio impostato su reject
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Dopo aver creato il record, è necessario aggiornare il record nel registrar del dominio. Per istruzioni sull'aggiunta del record TXT DMARC ai record DNS di Office 365, vedere [Creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>Procedure consigliate per l'implementazione di DMARC in Office 365
<a name="DMARCbestpractices"> </a>

È possibile implementare DMARC gradualmente senza influire sul resto del flusso di posta. Creare e implementare un piano di implementazione che segue questi passaggi. Eseguire ognuna di queste operazioni prima con un sottodominio, poi con gli altri sottodomini e infine con il dominio di primo livello nell'organizzazione prima di passare al passaggio successivo.
  
1. Monitorare l'effetto dell'implementazione DMARC
    
    Iniziare con un semplice record in modalità monitoraggio per un sottodominio o dominio che richiede che i destinatari DMARC inviino statistiche sui messaggi visualizzati utilizzando tale dominio. Un record in modalità monitoraggio è un record TXT DMARC con i criteri impostati su none (p=none). Molte aziende pubblicano un record TXT DMARC con p=nessuno perché non sono sicuri su quanta posta elettronica potrebbero perdere pubblicando un criterio DMARC più restrittivo. 
    
    È possibile farlo anche prima di aver implementato SPF o DKIM nell'infrastruttura di messaggistica. Tuttavia, non sarà possibile mettere in quarantena o rifiutare in modo efficace la posta tramite DMARCA finché non verranno implementati anche SPF e DKIM. Introducendo SPF e DKIM, i report generati tramite DMARC forniranno i numeri e le origini dei messaggi che superano i controlli e quelli che non li superano. È possibile individuare facilmente la quantità di traffico legittimo coperto o non coperto da questi e risolvere eventuali problemi. Si inizierà anche visualizzare il numero di messaggi fraudolenti inviati e da dove.
    
2. Richiedere che i sistemi di posta esterni mettano in quarantena la posta che non supera DMARC
    
    Quando si pensa che tutto o la maggior parte del traffico legittimo sia protetto da SPF e DKIM e si comprende l'impatto dell'implementazione DMARC, è possibile implementare un criterio di quarantena. Un criterio di quarantena è un record TXT DMARC il cui criterio è impostato su quarantine (p=quarantine). In questo modo viene, si chiede ai destinatari DMARC di mettere i messaggi dal dominio che non superano DMARC nell'equivalente locale di una cartella di posta indesiderata invece che nella Posta in arrivo dei clienti.
    
3. Richiedere che i sistemi di posta esterni non accettino messaggi che non superano DMARC
    
    Il passaggio finale consiste nell'implementare un criterio reject. Un criterio reject è un record TXT DMARC il cui criterio è impostato su reject (p=reject). Quando si esegue questa operazione, si chiede ai destinatari DMARC di non accettare messaggi che non superano i controlli DMARC. 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Modalità di gestione della posta elettronica in uscita che non supera DMARC da parte di Office 365
<a name="outbounddmarcfail"> </a>

Se un messaggio è in uscita da Office 365 e ha esito negativo DMARC e il criterio è impostato su p = Quarantine o p = Reject, il messaggio viene instradato attraverso il [pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md). Non è disponibile alcuna sostituzione per la posta elettronica in uscita.
  
Se si pubblica un criterio reject DMARC (p=reject), nessun altro cliente in Office 365 può eseguire lo spoofing del dominio perché i messaggi non potranno superare SPF o DKIM per il dominio quando si affidano a un messaggio in uscita attraverso il servizio. Tuttavia, se si pubblica un criterio reject di DMAR, ma non tutta la posta elettronica viene autenticata attraverso Office 365, una parte di questa potrebbe essere contrassegnata come posta indesiderata per la posta elettronica in ingresso (come descritto sopra) oppure sarà rifiutata se non si pubblica SPF e si prova ad inoltrarla in uscita attraverso il servizio. Ciò accade, ad esempio, se si dimentica di includere alcuni degli indirizzi IP per server e app che inviano posta per conto del dominio quando si crea il record TXT DMARC.
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Modalità di gestione della posta elettronica in ingresso che non supera DMARC da parte di Office 365
<a name="inbounddmarcfail"> </a>

Se il criterio DMARC del server di invio è p=reject, EOP contrassegna il messaggio come posta indesiderata invece di rifiutarlo. In altre parole, per la posta elettronica in ingresso, Office 365 considera p=reject e p=quarantine allo stesso modo.
  
Office 365 è configurato in questo modo perché una parte di posta elettronica legittima potrebbe non superare DMARC. Ad esempio, un messaggio potrebbe non superare DMARC se viene inviato a una lista di distribuzione che poi inoltre il messaggio a tutti i partecipanti della lista. Se Office 365 ha rifiutato questi messaggi, le persone potrebbero perdere posta elettronica legittima e non ci sarà modo di recuperarla. Al contrario, questi messaggi continueranno a non superare DMARC ma verranno contrassegnati come posta indesiderata e non rifiutati. Se si desidera, gli utenti possono comunque ricevere questi messaggi nella propria posta in arrivo attraverso i seguenti metodi:
  
- Gli utenti aggiungono mittenti sicuri singolarmente mediante il loro client di posta elettronica
    
- Gli amministratori creano una regola del flusso di posta di Exchange (nota anche come regola di trasporto) per tutti gli utenti che consentono i messaggi per i mittenti specifici. 
    
## <a name="troubleshooting-your-dmarc-implementation"></a>Risoluzione dei problemi relativi all'implementazione di DMARC
<a name="dmarctroubleshoot"> </a>

Se sono stati configurati i record MX del dominio in cui EOP non è la prima voce, gli errori DMARC non verranno applicati nel dominio. 
  
Se si è clienti di Office 365 e il proprio record MX principale del dominio non si riferisce a Exchange Online Protection, non si trarranno vantaggi da DMARC. Ad esempio, DMARC non funzionerà se si punta il record MX al server di posta locale e si indirizza quindi la posta elettronica a EOP utilizzando un connettore. In questo scenario, il dominio di destinazione è uno dei domini accettati ma EOP non è il principale MX. Ad esempio, si supponga che contoso.com punti il relativo MX a se stesso e utilizzi EOP come un record MX secondario, il record MX di contoso.com avrà il seguente aspetto:
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Tutto, o la maggior parte, la posta elettronica viene instradata per prima a mail.contoso.com poiché è l'MX principale e quindi la posta viene instradata a EOP. In alcuni casi, non è possibile neppure elencare EOP come record MX e semplicemente collegare i connettori per instradare la posta elettronica. EOP non deve essere la prima voce per la convalida di DMARC da eseguire. Garantisce solo la convalida, poiché non è possibile essere certi che tutti i server locali/non O365 eseguiranno controlli DMARC.  DMARC è idoneo per essere applicato per il dominio di un cliente (non per il server) quando si configura il record TXT DMARC, ma spetta al server di ricezione effettivamente eseguire l'applicazione.  Se si configura EOP come server di ricezione, EOP esegue l'applicazione di DMARC.
  
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection8"> </a>

Per ulteriori informazioni su DMARC le risorse che seguono possono essere di aiuto.
  
- [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include i campi di intestazione e di sintassi usati da Office 365 per i controlli DMARC. 
    
- Seguire la [serie di formazione su DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) da M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).
    
- Utilizzare l'elenco di controllo in [dmarcian](https://space.dmarcian.com/deployment/).
    
- Passare direttamente all'origine in [DMARC.org](https://dmarc.org).
    
## <a name="see-also"></a>See also
<a name="sectionSection8"> </a>

[Utilizzo di Sender Policy Framework (SPF) in Office 365 per impedire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[Configurazione di SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)

