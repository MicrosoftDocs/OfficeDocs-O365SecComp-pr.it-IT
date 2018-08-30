---
title: Risoluzione dei problemi della posta elettronica inviati a Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
description: In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che hanno riscontrato problemi durante il tentativo di invio della posta elettronica in arrivo in Office 365 e procedure consigliate per la posta in blocco per i clienti di Office 365.
ms.openlocfilehash: 3d8c0a05d096da87b9f686222055d76a6ae96ff2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003205"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>Risoluzione dei problemi della posta elettronica inviati a Office 365

In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che hanno riscontrato problemi durante il tentativo di invio della posta elettronica in arrivo in Office 365 e procedure consigliate per la posta in blocco per i clienti di Office 365.
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>Risoluzione dei problemi comuni di recapito della posta a Office 365

Scegliere uno di questi problemi comuni.
  
- [Invio di gestione dei IP e del dominio reputazione?](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [Sono posta invio da nuovi indirizzi IP?](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [Verificare che il DNS sia impostato correttamente](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [Verificare che si non annuncia se stessi come un indirizzo IP non instradabile](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [È stato ricevuto un rapporto di mancato recapito (NDR) per l'invio di posta elettronica a un utente in Office 365](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [Posta elettronica sbarcata nella cartella posta indesiderata del destinatario in EOP](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [Il traffico dall'indirizzo IP è limitato da EOP](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Invio di gestione dei IP e del dominio reputazione?
<a name="ManageRep"> </a>

Tecnologie di filtraggio EOP sono progettate per fornire protezioni di protezione da posta indesiderate per Microsoft Office 365, nonché altri prodotti di Microsoft Exchange Server, Microsoft Office Outlook e Windows Live Mail. È inoltre possibile sfruttare SPF, DKIM e DMARC; posta elettronica le tecnologie di autenticazione che consentono di risolvere il problema di phishing e spoofing verificare che il dominio di invio della posta elettronica è autorizzato a tale scopo. Filtraggio EOP è influenzato da diversi fattori legati all'indirizzo IP del mittente, dominio, autenticazione, correttezza dell'elenco, percentuali di reclamo, contenuto e altro ancora. Una delle entità fattori determinano verso il basso reputazione del mittente e le capacità di fornire il messaggio di posta elettronica è tariffa reclamo posta indesiderata. 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a>Sono posta invio da nuovi indirizzi IP?
<a name="NewIPs"> </a>

Indirizzi IP precedentemente non utilizzati per inviare posta elettronica in genere non dispongono di alcun reputazione costituita nel nostro sistemi. Di conseguenza, messaggi di posta elettronica dalla nuovo IP sono più probabile riscontrare problemi di recapito. Dopo che l'indirizzo IP è generato reputazione per non l'invio di posta indesiderata, EOP consente in genere per una migliore esperienza di recapito di posta elettronica.
  
Nuovo indirizzi IP che vengono aggiunte per i domini che vengono autenticati in record SPF esistenti in genere verificarsi il vantaggio di ereditarietà alcune della reputazione mittente del dominio. Se il dominio è una buona l'invio di reputazione IP nuovo potrebbe verificarsi un più rapido quanto tempo. Un nuovo PI prevedibili utilizzare il nome all'interno di un paio di settimane o prima a seconda di volume, correttezza dell'elenco e tariffe reclamo posta indesiderata.
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a>Verificare che il DNS sia impostato correttamente
<a name="ConfirmDNSsetup"> </a>

Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, è necessario contattare il provider di hosting DNS.
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Verificare che si non annuncia se stessi come un indirizzo IP non instradabile
<a name="NoReverseDNS"> </a>

È non può accettare la posta elettronica da mittenti che ha esito negativo di una ricerca DNS inverso. In alcuni casi, i mittenti legittimi annunciano erroneamente come un indirizzo IP instradabile internet non quando si tenta di aprire una connessione a EOP. Indirizzi IP riservati per le reti private (non instradabili) includono:
  
- 192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)
    
- 10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)
    
- 172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>È stato ricevuto un rapporto di mancato recapito (NDR) per l'invio di posta elettronica a un utente in Office 365
<a name="NDRInbound"> </a>

Alcuni problemi di recapito sono il risultato dell'indirizzo IP del mittente viene bloccato da Microsoft o dal momento che l'account utente viene identificato come mittente da escludere a causa di attività da posta indesiderata precedente. Se si ritiene che si è ricevuto il rapporto di mancato recapito in errore, eseguire le istruzioni nel messaggio di rapporto di mancato recapito per risolvere il problema. 
  
Per ulteriori informazioni sull'errore è stato ricevuto, vedere l'elenco completo dei codici di errore SMTP [DSN e NDR in Exchange 2013 locale e Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).
  
 Ad esempio, se viene visualizzato il rapporto di mancato recapito seguente, significa che l'indirizzo IP del mittente è stato bloccato da Microsoft. 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
Per richiedere la rimozione dall'elenco, è possibile [utilizzare il portale delist per eliminare il proprio nome nell'elenco Mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>Posta elettronica sbarcata nella cartella posta indesiderata del destinatario in EOP
<a name="JunkMailBox"> </a>

Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile utilizzare il destinatario a inviare questo messaggio falso positivo al Team di analisi della posta indesiderata Microsoft, che valutare e analizzare il messaggio. In base ai risultati dell'analisi, le regole di filtro dei contenuti da posta indesiderata a livello di servizio possono essere regolate per consentire il messaggio attraverso. Messaggio di posta elettronica consente di inviare messaggi a Microsoft che non devono essere classificate come posta indesiderata. In tal caso, assicurarsi di utilizzare i passaggi nella procedura seguente.
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>Utilizzare la posta elettronica per inviare messaggi falsi positivi al Team di analisi della posta indesiderata di Microsoft

1. Salvare il messaggio che si desidera inviare come posta non indesiderata.
    
2. Creare un nuovo messaggio vuoto e allegarvi il messaggio di posta non indesiderata.
    
    Se necessario, è possibile collegare più messaggi di posta non indesiderata.
    
3. Copiare e incollare la riga dell'oggetto del messaggio originale nella riga dell'oggetto del nuovo messaggio.
    
    > [!IMPORTANT]
    > Lasciare vuoto il corpo del nuovo messaggio. 
  
4. Inviare il nuovo messaggio a [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Il traffico dall'indirizzo IP è limitato da EOP
<a name="AllowEOPIPs"> </a>

Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP viene limitato da EOP, ad esempio:
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
È stato ricevuto il rapporto di mancato recapito perché sono stata rilevata attività sospette dall'indirizzo IP e sono state temporaneamente limitata durante un'ulteriore di valutazione. Se il sospetto è deselezionato attraverso la valutazione, questa limitazione verrà revocata a breve.
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a>Non è possibile ricevere posta elettronica da mittenti in Office 365
<a name="AllowEOPIPs"> </a>

 Per ricevere messaggi da utenti, verificare che la rete consente connessioni verso gli indirizzi IP utilizzato nel nostro datacenter EOP. Per ulteriori informazioni, vedere [gli indirizzi IP di Exchange Online Protection](eop/exchange-online-protection-ip-addresses.md). Per un record dell'indirizzo IP di tutti gli indirizzi che sono stati aggiunti, modificati o obsoleti lo scorso anno, vedere [Modifica delle notifiche per gli indirizzi IP di EOP](eop/change-notification-for-eop-ip-addresses.md).
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>Procedure consigliate per l'invio tramite posta elettronica in blocco per gli utenti di Office 365
<a name="BulkMailer"> </a>

Se si spesso condurre campagne di posta elettronica in blocco per gli utenti di Office 365 e per garantire che i messaggi di posta elettronica verranno aggiunti in modo sicuro e tempestivo, seguire i suggerimenti forniti in questa sezione.
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Verificare che il mittente: nome riflette il mittente del messaggio

L'oggetto deve essere un breve riepilogo delle quali il messaggio è dedicato e il corpo dei messaggi deve chiaramente e conciso indicano il ruolo l'offerta, servizi o prodotti su. Per esempio:
  
Correggere
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
Non corretto
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
Per i partecipanti a sapere chi è il più semplice apportate e meno difficoltà, le operazioni è necessario il recapito attraverso la maggior parte dei filtri posta indesiderata.
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Sempre includono un'opzione unsubscribe in messaggi di posta elettronica campagna

Messaggi di posta elettronica di marketing, soprattutto notiziari, deve sempre includere un modo per annullare la sottoscrizione da futuri messaggi di posta elettronica. Per esempio:
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
Alcuni mittenti includono questa opzione per richiedere i destinatari inviare un messaggio di posta elettronica a un determinato alias con "Unsubscribe" nell'oggetto. Questo non è preferibile utilizzare l'esempio di un solo clic. Se si sceglie di richiedono ai destinatari di inviare un messaggio di posta, assicurarsi che quando si fa clic sul collegamento, tutti i campi necessari siano prepopolati.
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Utilizzare l'opzione doppia consenso esplicito per la registrazione del messaggio di posta elettronica o newsletter di marketing

Se l'azienda richiede o incoraggia agli utenti di registrare le informazioni di contatto per accedere ai prodotti o servizi, è consigliabile questo best practice del settore. Alcune aziende rendono consigliata per accedere automaticamente agli utenti di marketing messaggi di posta elettronica o newsletter durante il processo di registrazione, ma si è considerato un'ambigui consigliata marketing nel mondo del filtro di posta elettronica.
  
Durante il processo di registrazione, se il "Sì, inviare me notiziario" o "Sì, inviare me offerte speciali" casella di controllo è selezionata per impostazione predefinita, gli utenti che non prestare particolare attenzione potrebbero inavvertitamente iscrizione a posta elettronica marketing o newsletter che non vengano Se si desidera ricevere.
  
 È consigliabile l'opzione doppio di consenso esplicito in realtà, il che significa che la casella di controllo per i messaggi di marketing o newsletter sia selezionata per impostazione predefinita. Inoltre, dopo che il modulo di registrazione è stato inviato, all'utente con un URL che consente di verificare la propria decisione di ricevere messaggi di marketing viene inviato un messaggio di posta elettronica di verifica. 
  
 In questo modo si garantisce che solo gli utenti che desiderano ricevere posta marketing effettuati la registrazione per i messaggi di posta elettronica, successivamente deselezionando la società invio di un messaggio di posta elettronica ambigui marketing consigliate. 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Verificare che il contenuto di messaggi di posta elettronica trasparente e riconducibili

Altrettanto importante come il contenuto che contengono il modo in cui che vengono inviati i messaggi di posta elettronica. Durante la creazione di contenuto di posta elettronica, utilizzare le procedure consigliate seguenti per verificare che i messaggi di posta elettronica non verrà essere contrassegnati da servizi di filtro della posta elettronica:
  
- Quando il messaggio di posta elettronica richiede che i destinatari di aggiungere il mittente alla Rubrica, è necessario indicare che tale azione non è una garanzia di recapito.
    
- Devono essere inclusi nel corpo del messaggio i reindirizzamenti simile e coerenti e non più e variabili. Un reindirizzamento in questo contesto è tutto ciò che punta dal messaggio, ad esempio documenti e collegamenti. Se si dispone di una quantità elevata di tali campagne o annullare collegamenti o aggiornare i collegamenti di profilo, sono tutti i devono puntare allo stesso dominio. Per esempio:
    
    Correggere
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    Non corretto
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- Evitare di contenuto con immagini di grandi dimensioni e gli allegati o messaggi composti unicamente di un'immagine.
    
- Impostazioni relative alla privacy pubblica o P3P devono indicare la presenza di verifica pixel (bug web o beacon).
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Rimuovere gli alias di posta elettronica non corretto dei database

Un alias di posta elettronica del database che consente di creare un rimbalzo-back è necessario e inserisce i messaggi di posta elettronica in uscita a rischio per un ulteriore esame da servizi di filtro della posta elettronica. Verificare che il database di posta elettronica aggiornato.
  

