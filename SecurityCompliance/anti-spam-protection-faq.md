---
title: DOMANDE frequenti sulla protezione da posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: In questo argomento vengono riportate le domande frequenti e le risposte sulla protezione dalla posta indesiderata. Le risposte sono valide per i clienti di Microsoft Exchange Online e Exchange Online Protection (EOP).
ms.openlocfilehash: 47ab5202e4f20bbb8cdcf1d83987b0c0c20e8f29
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341677"
---
# <a name="anti-spam-protection-faq"></a>DOMANDE frequenti sulla protezione da posta indesiderata

In questo argomento vengono riportate le domande frequenti e le risposte sulla protezione dalla posta indesiderata. Le risposte sono valide per i clienti di Microsoft Exchange Online e Exchange Online Protection (EOP). 
  
> [!TIP]
> Per domande e risposte sugli elenchi di mittenti attendibili e bloccati, vedere [elenchi di mittenti attendibili e mittenti bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). Per domande e risposte sulla quarantena, vedere domande [frequenti](quarantine-faq.md)sulla quarantena. 
  
 **D. Per impostazione predefinita, cosa accade a un messaggio identificato come posta indesiderata?**
  
R. **Per i messaggi in ingresso:** La maggior parte della posta indesiderata viene eliminata tramite il filtro delle connessioni, che si basa sull'indirizzo IP del mittente. Il servizio quindi analizza il contenuto del messaggio. Per impostazione predefinita, la posta indesiderata sottoposta a filtro contenuto viene inviata alla cartella Posta indesiderata del destinatario. Questa azione può essere modificata. Ad esempio, è possibile scegliere di inviare i messaggi di posta indesiderata alla quarantena configurando il criterio di filtro contenuto. 
  
> [!IMPORTANT]
> Per i clienti autonomi di EOP: per verificare che l'azione **Sposta messaggio all'indesiderata cartella di posta elettronica** funzioni con le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server locali per rilevare intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere Verificare che la posta indesiderata [venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
 **Per i messaggi in uscita:** Il messaggio viene instradato tramite il pool di recapito ad alto rischio o restituito e non recapitato. Nel secondo caso il mittente riceve una messaggio di notifica dello stato del recapito indicante l'impossibilità di recapitare il messaggio. 
  
 **D. che cos'è una variante di posta indesiderata di zero-day e come viene gestita dal servizio?**
  
A. una variante di posta indesiderata di zero-day è una variante di posta indesiderata di prima generazione sconosciuta che non è mai stata acquisita o analizzata, quindi i filtri del contenuto della posta indesiderata non dispongono ancora di informazioni disponibili per il rilevamento. Dopo che un campione di posta indesiderata di zero giorni viene acquisito e analizzato dai nostri analisti di posta indesiderata, se soddisfa i criteri di classificazione della posta indesiderata, i filtri del contenuto di posta indesiderata vengono aggiornati per rilevarlo e non è più considerato "zero-day" ( **Nota:** se si riceve un messaggio che potrebbe essere una variante di posta indesiderata di zero giorni, per aiutarci a migliorare il servizio, inviare il messaggio a Microsoft utilizzando uno dei metodi descritti in [inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)
  
 **D. È necessario configurare il servizio per fornire la protezione dalla posta indesiderata?**
  
R. Dopo l'accesso al servizio e l'aggiunta del dominio, il filtro della posta indesiderata è abilitato automaticamente in tutta l'azienda tramite i criteri predefiniti di protezione dalla posta indesiderata. I criteri predefiniti sono ottimizzati in modo da fornire la protezione senza richiedere configurazione aggiuntiva (con la sola eccezione dei clienti EOP indipendenti). Come amministratore, è possibile modificare i criteri predefiniti di protezione della posta indesiderata in modo che siano adattati per soddisfare al meglio le esigenze della propria organizzazione. Per una maggiore granularità, è anche possibile creare criteri di filtro contenuto personalizzati e applicarli a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma è possibile modificarne il livello di priorità (l'ordine di esecuzione).
  
Per ulteriori informazioni sulla configurazione dei criteri di protezione dalla posta indesiderata, vedere i seguenti argomenti:
  
[Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md)
  
[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
 **D. Se viene modificato un criterio di posta indesiderata, quando tempo trascorre prima che modifiche vengano applicate?**
  
A. Fino a 1 ora.
  
 **D. Il filtro della posta elettronica in blocco è abilitato per impostazione predefinita?**
  
A. per impostazione predefinita, è abilitata l'opzione filtro **posta** indesiderata avanzata per i nuovi clienti. Per i clienti migrati, questa impostazione corrisponderà alla configurazione di FOPE. Per ulteriori informazioni sulla posta elettronica in blocco, vedere [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
 **D. Il servizio offre filtro URL?**
  
R. Sì, il servizio dispone di un filtro URL che verifica la presenza di URL all'interno dei messaggi. Se vengono rilevati contenuti indesiderati o sospetti associati all'URL, il messaggio viene contrassegnato come posta indesiderata.
  
 **D. In che modo gli utenti che utilizzano il servizio inviano falsi negativi (posta indesiderata) e falsi positivi (posta non indesiderata) a Microsoft?**
  
R. I messaggi di posta indesiderata e non possono essere inviati a Microsoft per l'analisi in diversi modi. Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **D. È possibile ricevere rapporti sulla posta indesiderata?**
  
A. Sì, ad esempio, è possibile ottenere un rapporto di rilevamento della posta indesiderata nell'interfaccia di amministrazione di Office 365. Questo report Visualizza il volume di posta indesiderata come numero di messaggi univoci. Per ulteriori informazioni sulla creazione di report, vedere i collegamenti seguenti:
  
Clienti di Exchange Online: [monitoraggio, creazione di rapporti e traccia dei messaggi in Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)
  
Clienti di Exchange Online Protection: [Reporting e traccia dei messaggi in Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)
  
 **D. Qualcuno mi ha inviato un messaggio ma non lo trovo. Sospetto che sia stato identificato come posta indesiderata. Esiste uno strumento per scoprirlo?**
  
R. Sì, lo strumento di traccia dei messaggi consente di seguire i messaggi di posta elettronica nel loro percorso attraverso il servizio e scoprire cosa è accaduto. Per ulteriori informazioni sull'utilizzo dello strumento di traccia dei messaggi per scoprire perché un messaggio è stato contrassegnato come posta indesiderata, vedere [Il messaggio era contrassegnato come posta indesiderata?](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam).
  
 **D: Il servizio limiterà la posta (limite di frequenza) se gli utenti inviano posta indesiderata in uscita?**
  
A. se più della metà della posta inviata da un utente tramite il servizio entro un determinato intervallo di tempo (ad esempio, per ora) è determinata come posta indesiderata da Office 365, l'utente verrà bloccato dall'invio dei messaggi. Nella maggior parte dei casi, se un messaggio in uscita è determinato come posta indesiderata, viene instradato attraverso il pool di recapito ad alto rischio, che riduce la probabilità che il pool di indirizzi IP in uscita normale venga aggiunto a un elenco di indirizzi bloccati.
  
È possibile inviare una notifica a un indirizzo di posta elettronica specificato quando un mittente è bloccato nell'invio di posta indesiderata in uscita. Per ulteriori informazioni su questa impostazione, vedere [Configure the outbound Spam Policy](configure-the-outbound-spam-policy.md).
  
 **D. È possibile utilizzare un provider antimalware e di protezione dalla posta indesiderata di terze parti insieme a Exchange Online?**
  
A. Sì, è possibile configurare un altro servizio antimalware e di protezione dalla posta indesiderata per proteggere le cassette postali di Exchange Online. Per eseguire questa attività per la posta in ingresso, è necessario reindirizzare i messaggi di posta elettronica al provider di terze parti modificando i record MX in modo che puntino a tale provider e quindi reindirizzare i messaggi a EOP per l'ulteriore elaborazione. Per eseguire questa attività per la posta in uscita, è necessario configurare la destinazione di recapito dei messaggi per il provider di terze parti (smart host), come indicato in [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).
  
 **D. Microsoft dispone di documentazione su come è possibile proteggersi da tentativi di phishing?**
  
R. Sì. Consultare i seguenti articoli:
  
[Articoli di Privacy e Sicurezza online su tentativi di phishing, truffe di false lotterie e altri tipi di frode](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[E-mail e phishing: guida per la protezione del computer](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 **D. I messaggi di posta indesiderata e malware vengono analizzati da coloro a cui sono indirizzati o vengono trasferiti a entità giudiziarie?**
  
R. Il servizio si concentra sul rilevamento e sulla rimozione di posta indesiderata e malware, tuttavia occasionalmente ci occupiamo di analizzare campagne di attacco o posta indesiderata specialmente pericolose e dannose e di perseguire gli autori. A tale scopo è possibile la collaborazione con le unità legali e di crimini digitali per eliminare botnet spammer, impedire agli spammer di utilizzare il servizio (se lo usano per inviare posta in uscita) e passare le informazioni agli enti giudiziari per il procedimento penale.
  
 **D. Quali sono le procedure ottimali per la posta i uscita che garantiscono che la posta venga recapitata?**
  
R. Le linee guida presentate di seguito rappresentano le procedure ottimali per l'invio di messaggi di posta elettronica.
  
1. **Il dominio di invio della posta elettronica deve risolversi in DNS.**
    
    Ad esempio, se il mittente è user@example.com, il dominio example.com viene risolto nell'indirizzo IP 192.0.43.10. Se un dominio di invio non dispone di un record A-record e no MX in DNS, il servizio instraderà il messaggio attraverso il pool di recapito ad alto rischio, indipendentemente dal fatto che il contenuto del messaggio sia o meno indesiderato. Per ulteriori informazioni sul pool di recapito a rischio elevato, vedere [pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md). 
    
2. **L'indirizzo IP di invio del server di posta in uscita deve avere una voce DNS (PTR) inversa.**
    
    Ad esempio, in caso di invio dall'indirizzo IP 192.0.43.10, la voce DNS inversa per tale IP è 43-10.any.icann.org. 
    
3. **I comandi HELO/EHLO e MAIL FROM devono essere coerenti e presenti in formato nome di dominio anziché di indirizzo IP.**
    
    Il comando HELO/EHLO deve essere configurato in modo da corrispondere al DNS inverso dell'indirizzo IP di invio in modo che il dominio resti lo stesso tra le diverse parti delle intestazioni dei messaggi.
    
4. **Accertarsi che in DNS siano impostati i record SPF corretti.**
    
    I record SPF consentono di verificare che la posta inviata da un dominio giunga veramente da tale dominio e non sia soggetta a spoofing. Per ulteriori informazioni sui record SPF, vedere i seguenti collegamenti:
    
    [Configurazione di SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [Create DNS records for Office 365](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. **Per accedere alla posta elettronica con DKIM, utilizzare la canonicalizzazione semplice.**
    
    Se un mittente desidera accedere ai propri messaggi utilizzando DKIM (Domain Keys Identified Mail) e desidera inviare la posta in uscita tramite il servizio, deve accedere utilizzando l'algoritmo di canonicalizzazione semplice delle intestazioni. L'accesso con una canonicalizzazione più complessa potrebbe invalidare la firma quando passa attraverso il servizio.
    
6. **I proprietari dei domini devono disporre di informazioni accurate nel database WHOIS.**
    
    Tale database identifica i proprietari del dominio e indica come contattarli immettendo la società padre stabile, il punto di contatto e i server dei nomi.
    
7. **Peri programmi di posta in blocco, il nome Da: deve riflettere il mittente del messaggio mentre la riga dell'oggetto del messaggio deve essere un breve riepilogo delle informazioni contenute nel messaggio.**
    
    Il corpo del messaggio deve contenere una chiara indicazione dell'offerta, servizio o prodotto. Ad esempio, se un mittente sta inviando posta in blocco per la società Contoso, i campi Da e Oggetto devono essere simili ai seguenti:
    
    Da: marketing@contoso.com
    
    Oggetto: Nuovo catalogo per Natale! 
    
    Di seguito viene riportato un esempio di cosa non fare, perché non è descrittivo:
    
    Da: utente@hotmail.com
    
    Oggetto: Cataloghi
    
8. **Se si invia posta in blocco a molti destinatari e il messaggio è in formato newsletter, nella parte finale del messaggio occorre fornire un modo per annullare la sottoscrizione.**
    
    L'opzione che consente di annullare la sottoscrizione sarà simile alla seguente:
    
    Questo messaggio è stato inviato a esempio@contoso.com da mittente@fabrikam.com. Aggiornamento profilo/indirizzo di posta elettronica | Rimozione istantanea con **SafeUnsubscribe** | Informativa sulla privacy
    
9. **Se si invia posta elettronica in blocco, l'acquisizione dell'elenco deve essere eseguita utilizzando double opt-in, uno standard del settore.**
    
    Double opt-in è una procedura che richiede che l'utente esegua due azioni per registrarsi per la posta di marketing.
    
1. La prima azione consiste nel selezionare una casella di controllo precedentemente non selezionata per indicare che desidera ricevere ulteriori offerte o messaggi di posta elettronica.
    
2. La seconda azione viene eseguita quando il commerciante invia un messaggi di posta elettronica di conferma all'indirizzo di posta elettronica fornito dall'utente chiedendogli di fare clic sul un collegamento sensibile al tempo per completare la conferma.
    
    L'utilizzo della doppia conferma contribuisce alla buona reputazione per i mittenti di posta elettronica in blocco.
    
10. **I mittenti in blocco devono creare contenuto trasparente per cui possono essere ritenuti responsabili:**
    
1. Le espressioni che richiedono ai destinatari di aggiungere il mittente alla rubrica devono indicare che tale azione non è una garanzia di recapito.
    
2. Quando si costruiscono i reindirizzamenti nel corpo del messaggio, utilizzare uno stile di collegamento coerente.
    
3. Non inviare immagini o allegati di grandi dimensioni o messaggi composti unicamente da un'immagine.
    
4. Nell'uso di pixel di verifica (bug Web o beacon), indicarne chiaramente la presenza delle impostazioni P3P o della privacy pubblica.
    
11. **Formattare le notifiche di stato di recapito in uscita.**
    
    Quando si generano messaggi di notifica dello stato di recapito, i mittenti devono seguire il formato di restituzione al mittente in [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).
    
12. **Rimuovere gli indirizzi di posta elettronica di restituzione per utenti inesistenti.**
    
    Se si riceve un rapporto di mancato recapito per un indirizzo di posta elettronica non più in uso, rimuovere l'alias di posta elettronica inesistente dall'elenco. Gli indirizzi di posta elettronica possono cambiare nel tempo.
    
13. **Utilizzare il programma SNDS (Smart Network Data Services) di Hotmail.**
    
    Hotmail utilizza un programma chiamato Smart Network Data Services che consente ai mittenti di verificare i reclami inviati dagli utenti finali. SNDS è il portale principale per la risoluzione dei problemi di recapito a Hotmail.
    
## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[Elenchi di mittenti attendibili e bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md)
  
[Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP](backscatter-messages-and-eop.md)
  

