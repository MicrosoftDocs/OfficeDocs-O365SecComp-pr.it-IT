---
title: Conflitti posta indesiderata inviata a Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
description: Guida di orientamento alla sicurezza posta elettronica di Microsoft prevede un approccio più prodotti non corrispondente. Si applica filtro tecnologia di Exchange Online Protection (EOP) protezione da posta indesiderata e anti-phishing piattaforme di posta elettronica di Microsoft per fornire agli utenti l'ultimo gli strumenti di protezione da posta indesiderati e anti-phishing e innovazioni nell'intera rete. L'obiettivo per EOP è offrire un servizio di posta elettronica completo e utilizzabile che consente di rilevare e proteggere gli utenti da posta indesiderata, posta elettronica falsi minacce (anti-phishing) e malware.
ms.openlocfilehash: dafcb827a323461936eadcd00c37fabd43005a80
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026353"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Conflitti posta indesiderata inviata a Office 365

Guida di orientamento alla sicurezza posta elettronica di Microsoft prevede un approccio più prodotti non corrispondente. Si applica filtro tecnologia di Exchange Online Protection (EOP) protezione da posta indesiderata e anti-phishing piattaforme di posta elettronica di Microsoft per fornire agli utenti l'ultimo gli strumenti di protezione da posta indesiderati e anti-phishing e innovazioni nell'intera rete. L'obiettivo per EOP è offrire un servizio di posta elettronica completo e utilizzabile che consente di rilevare e proteggere gli utenti da posta indesiderata, posta elettronica falsi minacce (anti-phishing) e malware.
  
## <a name="the-challenge"></a>Problema

Messaggio di posta elettronica è diventato uno strumento di comunicazione importante non solo per gli utenti, ma anche per gli operatori di marketing, il personale del supporto, organizzazioni di vendita e aziende di tutte le dimensioni. Come si è espanso utilizzo di posta elettronica, in modo ha parte di un messaggio di posta elettronica. Posta indesiderata non monitorato può bloccare posta in arrivo e reti, soddisfazione impatto e interferire con l'efficacia delle comunicazioni di posta elettronica legittimi. Per tale motivo Microsoft continua a investire in tecnologie di protezione da posta indesiderate. In altre parole, innanzitutto contenente e filtro posta indesiderata. 
  
## <a name="our-efforts"></a>Il prodotto

EOP offre una serie di operazioni per ridurre al minimo l'impatto negativo posta indesiderata è sull'esperienza di posta elettronica degli utenti.
  
### <a name="exchange-online-protection-technology"></a>Tecnologia di Exchange Online Protection

Per contribuire alla riduzione posta indesiderata, EOP include una protezione posta indesiderata utilizzando EOP proprietarie tecnologie di filtraggio posta elettronica dello schermo per identificare e separare posta indesiderata di posta elettronica legittimi. Il filtro contenuto EOP apprendimento da nota posta indesiderata e phishing minacce e commenti degli utenti da piattaforma i consumer, Outlook.com. Questi tipi di dati la formazione tecnologie EOP in grado di riconoscere posta indesiderata e posta elettronica legittimi e sono chiave input in reputazione del mittente. Corso commenti degli utenti EOP al programma di posta indesiderata classificazione assicura che le tecnologie di EOP continuamente addestrate e migliorate.
  
#### <a name="how-does-eop-work"></a>Come funziona EOP?

Quando un utente esterno riceve un messaggio di posta elettronica a un utente di EOP, tecnologie di filtraggio EOP valutare il contenuto del messaggio e assegna una classificazione per il messaggio basato sul probabilità che il messaggio di posta indesiderata. Questa restrizione viene archiviata come proprietà di un messaggio viene chiamata un livello di probabilità della posta indesiderata (SCL) nei messaggi. La posta indesiderata rimane con il messaggio viene trasmesso ad altri livelli di protezione da posta indesiderata in EOP. 
  
Per gestire i messaggi di posta elettronica con diversi livelli SCL vengono impostate le regole in EOP. Dispone di un messaggio di posta indesiderata superiore a una determinata soglia, si ritiene posta indesiderata. Il messaggio viene messo in quarantena o recapitato nella cartella posta indesiderata dell'utente a seconda di come l'amministratore di sistema consente di configurare l'opzione di recapito della posta indesiderata.
  
#### <a name="eop-filters"></a>Filtri EOP

Oltre alle tecnologie di filtro di protezione da posta indesiderate, EOP inoltre consente l'amministratore di sistema per impostare i livelli di filtro per personalizzare ulteriormente il recapito di posta elettronica per gli account utente. Gli amministratori possono aggiungere facilmente un mittente o nome di dominio per i mittenti attendibili e l'elenco dei domini in modo che il messaggio di posta elettronica da tale mittente o dominio mai considerato come posta indesiderata indipendentemente dal contenuto del messaggio. Per informazioni, vedere [Mittenti attendibili e bloccati liste in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Protezione dal phishing

Il phishing (pronunciato "pesca") è una maschera furto d'identità e una delle minacce crescite su Internet. È spesso possibile identificare un messaggio di phishing quando richiede informazioni personali o finanziarie o include un collegamento a un sito Web che richiede tali informazioni. EOP offre protezione dal phishing come parte delle tecnologie di filtraggio EOP proprietarie. Tecnologie di filtraggio EOP analizzare il messaggio di posta elettronica per il rilevamento di collegamenti contraffatti o domini falsificati per proteggere gli utenti da questi tipi di phishing in linea.
  
#### <a name="how-does-phishing-protection-work"></a>Funzionamento protezione dal phishing

Frequenza con cui un messaggio di posta elettronica phishing verrà inviata contenente un collegamento, una volta selezionato il collegamento come reindirizzare gli utenti a un sito web contraffatto visualizzato valido (ad esempio la banca o servizio in linea). In questo sito di phishing in genere viene richiesto di immettere informazioni personali, come i nomi utente, password e di previdenza sociale. Tutte le informazioni che immesse nel sito di phishing consentono specificati sottrarre l'identità dell'utente. Utilizzando conosciuti marchi attendibili e logo, autori siano in grado di apparire autorizzato. Tecnologia di filtro anti-phishing offerta nei controlli di EOP per le caratteristiche di phishing potenziali di posta elettronica. Se viene trovato, il messaggio di posta elettronica viene spostato nella cartella posta indesiderata.
  
Microsoft è concentrato sforzi tecnologia anti-phishing in due risulterà: innanzitutto per impedire che i messaggi di posta elettronica di phishing sta per raggiungere gli utenti e in secondo luogo, contribuendo a eliminare la possibilità degli utenti da ingannato spoofing messaggi di posta elettronica e siti web. 
  
> [!TIP]
> Internet Explorer versioni 7 e di sopra verrà bloccare o avvisare gli utenti quando visita noti o potenziali phishing dei siti in modo che non sono indotto fornire informazioni personali. [Assicurarsi di avere l'ultima versione di Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Autenticazione

Lo spoofing del dominio è un modo di imitazione un indirizzo di posta elettronica legittimi per rendere falsi posta elettronica legittimi. Lo spoofing viene utilizzato da utenti non autorizzati o organizzazioni di tentativi di phishing a indurre persone di rivelare informazioni personali. Divulgazione di informazioni quali può causare per identificare il furto e altri tipi di truffe di false.
  
EOP utilizza mittente protezione Framework (SPF), DomainKeys identificato posta (DKIM) e Domain-based Message Authentication, report e conformità (DMARC) e altre autenticazioni implicite per verificare che i messaggi provengono dal dominio da che dichiarano di provengono . È consigliabile che tutti i mittenti utilizzano SPF e DKIM per proteggere i destinatari di posta indesiderate posta elettronica e tentativi di phishing. È consigliabile prendere in considerazione i mittenti DMARC per rifiutare o mettere in quarantena posta elettronica inviato da mittenti non autorizzati di pubblicazione.
  
- Per ulteriori informazioni su SPF, vedere [RFC 7208](https://tools.ietf.org/html/rfc7208) e [Sender Policy Framework](http://www.openspf.org/).
    
- Per ulteriori informazioni su DKIM, vedere [RFC 6376](https://tools.ietf.org/html/rfc6376) e [DKIM.org](http://dkim.org/).
    
- Per ulteriori informazioni su DMARC, vedere [DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Normativa

In Microsoft, si ritiene che lo sviluppo di tecnologie e nuove self-disposizioni richiede il supporto dei criteri effettivi government e giuridico. La proliferazione di posta indesiderata in tutto il mondo è migliorarne le numerose corpi legislativi per definire quali messaggi di posta commerciale. Molti paesi hanno ora leggi in materia di conflitti da posta indesiderata sul posto. Questo approccio complementare è come consentire di limitare la posta indesiderata consentendo legittimi commerce électronique a risultati economici degli Stati Uniti ha federal e sullo stato leggi in materia di governance di posta indesiderata. Atto CAN SPAM espande gli strumenti disponibili per i messaggi di posta elettronica falsi e ingannevoli curbing.
  

