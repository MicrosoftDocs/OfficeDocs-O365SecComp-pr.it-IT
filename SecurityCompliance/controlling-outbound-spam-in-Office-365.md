---
title: Controllo della posta indesiderata in uscita in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 09/18/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Se l'organizzazione invia una gran quantità di posta in blocco contrassegnata come posta indesiderata, potrebbe essere bloccata dall'invio di messaggi di posta elettronica con Office 365. Leggere questo articolo per ulteriori informazioni sul motivo per cui questo accade e su cosa è possibile fare.
ms.openlocfilehash: 476e1ddff73493881708e050fb7834e6bd6b272a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217336"
---
# <a name="controlling-outbound-spam-in-office-365"></a>Controllo della posta indesiderata in uscita in Office 365

Noi prendiamo sul serio la gestione della posta indesiderata in uscita perché la nostra è un servizio condiviso.  Esistono molti clienti che si trovano dietro un pool di risorse condiviso, in cui se un cliente invia la posta indesiderata in uscita, può peggiorare la reputazione IP in uscita del servizio e influisce sulla corretta recapito della posta elettronica per gli altri clienti. È ingiusto per il cliente a se il cliente B spam e varie terze parti elenchi dei blocchi IP elencare l'indirizzo IP che utilizza.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Operazioni che possono essere eseguite dagli amministratori per controllare la posta indesiderata in uscita

- **Abilitare le notifiche quando un account invia messaggi di posta indesiderata o arrestati**. Gli amministratori possono ottenere Ccn ogni volta che un messaggio è contrassegnato come posta indesiderata in uscita e inviato tramite il pool ad alto rischio. Monitorando questa cassetta postale, un amministratore può rilevare se dispone di un account compromesso nella propria rete o se il filtro di posta indesiderata contrassegna per un messaggio di posta elettronica come posta indesiderata.  Ulteriori informazioni sulla configurazione del criterio di posta indesiderata in uscita possono essere trovate [qui](configure-the-outbound-spam-policy.md).
 
- **Esaminare manualmente i problemi di posta indesiderata dai provider di posta elettronica 3rd party**. Molti servizi di posta elettronica di terze parti come Outlook.com, Yahoo e AOL forniscono un ciclo di commenti e suggerimenti in cui se un utente del servizio contrassegna un messaggio di posta elettronica dal servizio come posta indesiderata, viene inserito e inviato nuovamente a noi per la revisione. Per ulteriori informazioni sul supporto dei mittenti per Outlook.com, fare clic [qui](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Cosa fa EOP per controllare la posta indesiderata in uscita 

1. **Segregazione del traffico in uscita in pool distinti di indirizzi IP**. Tutti i messaggi inviati dai clienti in uscita tramite il servizio vengono analizzati per la posta indesiderata. Se il messaggio è posta indesiderata, viene instradato attraverso il pool di reCapito ad alto rischio. Questo pool IP contiene notifiche di stato non recapitabili e posta indesiderata. Il reCapito al destinatario previsto non è garantito poiché molte terze parti non accetteranno la posta elettronica poiché la qualità del messaggio di posta elettronica emesso.<br/><br/>Suddividendo il traffico in questo modo si garantisce che la posta elettronica di qualità inferiore (indesiderata, NDR backscatter) non trascini la reputazione dei pool di posta elettronica in uscita normali. Il pool ad alto rischio ha generalmente una bassa reputazione in molti ricevitori su Internet, anche se questo non è universale. 

2. **Monitoraggio della reputazione IP**. Office 365 esegue una query su diversi elenchi dei blocchi IP di terze parti e genera avvisi se sono elencati su di essi. In questo modo è possibile reagire rapidamente quando la posta indesiderata ha provocato un peggioramento della reputazione. Quando viene generato un avviso, è presente una documentazione interna che indica i passaggi da eseguire per ottenere la lista. 

3. **Disabilitare gli account offensivi quando inviano troppa posta elettronica contrassegnata come posta**indesiderata. Anche se noi segregiamo la posta indesiderata e non la posta indesiderata in due pool IP separati in uscita, gli account di posta elettronica non possono inviare messaggi di posta indesiderata. Monitoriamo gli account che inviano messaggi di posta indesiderata e se superano un limite nascosto, l'account è bloccato dall'invio di posta indesiderata.<br/><br/>Un singolo messaggio contrassegnato come posta indesiderata potrebbe essere una classificazione errata da parte del motore di posta indesiderata e noto anche come falso positivo. Lo inviamo attraverso il pool ad alto rischio per dargli la possibilità di uscire; Tuttavia, un numero elevato di messaggi in un intervallo di tempo breve è indicativo di un problema e, quando ciò accade, blocca l'account dall'invio di qualsiasi altro messaggio di posta elettronica. Esistono diverse soglie per gli account di posta elettronica individuali così come in aggregato per l'intero tenant.

4. **Disabilitare gli account offensivi quando si inviano troppi messaggi di posta elettronica in un intervallo di tempo troppo breve**. Oltre ai limiti di cui sopra che cercano una proporzione di messaggi contrassegnati come posta indesiderata, esistono anche limiti che bloccano gli account al raggiungimento di un limite generale, indipendentemente dal fatto che i messaggi siano o meno contrassegnati come posta indesiderata. Il motivo per cui questo limite esiste è perché un account compromesso potrebbe inviare messaggi di posta indesiderata zero-day che sono stati persi dal filtro di posta indesiderata. Poiché è difficile, se non impossibile, a volte distinguere tra una campagna di mailing di massa legittima e una massiccia campagna di posta indesiderata, questi limiti vengono attivati per limitare eventuali danni.

> [!NOTE]
> Per #3 e #4, non vengono pubblicizzati i limiti esatti.  In questo modo si evita che gli spammer possano giocare il sistema e per garantire che sia possibile modificare i limiti quando necessario. I limiti sono abbastanza alti in modo che un utente medio dell'azienda non li colpisca mai e sia sufficientemente basso da contenere la maggior parte dei danni che uno spammer può eseguire. 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Soluzioni consigliate per i clienti che desiderano inviare messaggi di posta elettronica in uscita tramite EOP

È difficile trovare un equilibrio tra i clienti che desiderano inviare un volume elevato di posta elettronica rispetto alla protezione del servizio da account compromessi e messaggi di posta elettronica in blocco con procedure di acquisizione di elenchi di scarse dimensioni. Anche in questo caso, il costo di un atterraggio IP in uscita su un blocco di terze parti è superiore al blocco di un cliente dall'invio della posta elettronica in uscita. Come descritto nella [Descrizione del servizio Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), l'utilizzo di EOP per inviare messaggi di posta elettronica in blocco non è un utilizzo supportato del servizio e può essere consentito solo in base a "Best-Effort". Per i clienti che desiderano inviare messaggi di posta elettronica in blocco, è consigliabile eseguire le operazioni seguenti:

1. **Inviare il messaggio di posta elettronica in blocco tramite i propri server di posta locali**. Questo significa che il cliente dovrà mantenere la propria infrastruttura di posta elettronica per questo tipo di messaggio di posta elettronica.

2. **Utilizzare un messaggio di posta elettronica in blocco di terze parti per inviare la comunicazione di massa**. Sono disponibili diversi messaggi di posta elettronica di terze parti, la cui unica attività è inviare messaggi di posta elettronica in blocco. Possono collaborare con i clienti per assicurarsi che dispongano di una buona prassi di posta elettronica e che dispongano di risorse dedicate per l'applicazione. 

Il gruppo di lavoro per la messaggistica, la telefonia mobile, antiAbuso di malware (MAAWG) pubblica il roster di appartenenza [qui](http://www.maawg.org/about/roster). Numerosi provider di posta elettronica in blocco sono presenti nell'elenco e sono noti come cittadini Internet responsabili. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Protezione anti-spoofing in Office 365](anti-spoofing-protection.md)

[Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md)
