---
title: Panoramica su Exchange Online Protection
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) è un servizio di filtro della posta elettronica che aiuta l'organizzazione a proteggersi da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica.
ms.openlocfilehash: 16f2f423b6e517cf204e4b4f6a2949baebfd6223
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686365"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

Microsoft Exchange Online Protection (EOP) è un servizio di filtraggio della posta elettronica basato sul cloud che contribuisce a proteggere l'organizzazione da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica. EOP è in grado di semplificare la gestione dell'ambiente di messaggistica e ridurre molti dei problemi legati alla gestione dei componenti hardware e software locali.
  
Di seguito sono riportati i modi principali in cui è possibile utilizzare EOP per la protezione dei messaggi:
  
- **In uno scenario autonomo** EOP offre protezione della posta elettronica basata sul cloud per l'ambiente di Microsoft Exchange Server 2013 locale, versioni di Exchange Server legacy o per qualsiasi altro locale soluzione di posta elettronica SMTP. 
    
- **Come parte di Microsoft Exchange Online** Per impostazioni predefinita, EOP protegge le cassette postali di Microsoft Exchange Online ospitate nel cloud. 
    
- **In una distribuzione ibrida** EOP può essere configurato per proteggere l'ambiente di messaggistica e controllare l'instradamento della posta quando si dispone di un mix di cassette postali locali e cloud. 
    
## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:
  
![Elaborazione di posta elettronica di EOP](../media/EOP-email-processing.png)
  
Un messaggio in arrivo inizialmente attraversa il filtro connessioni, che controlla reputazione del mittente e controlla se il messaggio di malware. La maggior parte delle posta indesiderata è stata arrestata a questo punto da EOP. I messaggi proseguono per il filtraggio dei criteri, dove i messaggi vengono valutati rispetto alle regole di trasporto personalizzato che si crea o applicare un modello. Ad esempio, esiste una regola che invia una notifica a un manager quando si riceve posta elettronica da un mittente specifico. (Controlli di prevenzione della perdita di dati inoltre verificano a questo punto, se si dispone di funzionalità, per informazioni sulla disponibilità delle funzionalità, vedere [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Successivamente, messaggi superare il filtro contenuto, dove il contenuto viene verificato la terminologia e le proprietà comuni della posta indesiderata. Un messaggio identificato come posta indesiderata dal filtro contenuto può essere inviata alla cartella posta indesiderata dell'utente o per la quarantena, tra le altre opzioni, in base alle impostazioni. Dopo che un messaggio passa correttamente tutti i livelli di protezione, viene recapitato al destinatario.
  
### <a name="eop-datacenters"></a>Datacenter EOP

EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server in ogni centro dati accettano messaggi per conto dell'utente, offrendo un livello di separazione tra l'organizzazione e Internet, riducendo in questo modo il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo. 
  
EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:
  
    
- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.
    
- In Asia Pacifico (centro dati), tutte le cassette postali di Exchange Online si trovano in datacenter APAC, ma messaggi attualmente vengono instradati tramite datacenter APAC per il filtraggio EOP.
=======
- In America, tutte le cassette postali di Exchange Online si trovano in datacenter negli Stati Uniti, ad eccezione in cui vengono utilizzati i Data Center in Brasile e Cile Sud America e in Canada in cui vengono utilizzati i Data Center in Canada. Tutti i messaggi di posta elettronica, inclusi i messaggi per i clienti Sud America e in Canada, vengono instradati tramite datacenter locale per il filtraggio EOP; visualizzare la posta viene memorizzata nel datacenter del tenant in cui si trova.
    
- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.
    
- In Asia Pacifico (centro dati), tutte le cassette postali di Exchange Online si trovano in datacenter APAC e messaggi attualmente vengono instradati tramite datacenter APAC per il filtraggio EOP.
    
- Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.
    
## <a name="eop-plans-and-features"></a>Piani e funzionalità di EOP

I piani di sottoscrizione EOP disponibili sono:
  
- **EOP autonomo** EOP protegge le cassette di posta locali. 
    
- **Funzionalità di EOP in Exchange Online** EOP protegge le cassette postali di Exchange Online ospitate nel cloud. 
    
- **CAL di Exchange Enterprise con Services** Protegge le cassette postali locali, come EOP autonomo, e include le funzionalità di prevenzione della perdita di dati (DLP) e di segnalazione tramite servizi Web. 
    
Per ulteriori informazioni sui requisiti, i limiti importanti e le funzionalità disponibili in tutti i piani di sottoscrizione EOP; vedere [Descrizione del servizio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619).
  
## <a name="setting-up-eop"></a>Configurare EOP

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.
  
Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Caratteristiche di EOP](eop-features.md)
  
[Video per iniziare con EOP](videos-for-getting-started-with-eop.md)
  
[Domande frequenti su EOP](eop-general-faq.md)
  
[Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)
  
[Domande frequenti sull'amministrazione delegata](delegated-administration-faq.md)
  
[Spostare i domini e le impostazioni da un'organizzazione di EOP a un'altra organizzazione di EOP](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

