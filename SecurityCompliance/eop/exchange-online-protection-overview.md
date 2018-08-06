---
title: Panoramica su Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) è un servizio di filtro della posta elettronica che aiuta l'organizzazione a proteggersi da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica.
ms.openlocfilehash: 89852c7ba211ccb266c8b231b00d3d83987a5f20
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026693"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="29e3f-103">Panoramica su Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="29e3f-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="29e3f-p101">Microsoft Exchange Online Protection (EOP) è un servizio di filtraggio della posta elettronica basato sul cloud che contribuisce a proteggere l'organizzazione da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica. EOP è in grado di semplificare la gestione dell'ambiente di messaggistica e ridurre molti dei problemi legati alla gestione dei componenti hardware e software locali.</span><span class="sxs-lookup"><span data-stu-id="29e3f-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="29e3f-106">Di seguito sono riportati i modi principali in cui è possibile utilizzare EOP per la protezione dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="29e3f-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="29e3f-107">**In uno scenario autonomo** EOP offre protezione della posta elettronica basata sul cloud per l'ambiente di Microsoft Exchange Server 2013 locale, versioni di Exchange Server legacy o per qualsiasi altro locale soluzione di posta elettronica SMTP.</span><span class="sxs-lookup"><span data-stu-id="29e3f-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="29e3f-108">**Come parte di Microsoft Exchange Online** Per impostazioni predefinita, EOP protegge le cassette postali di Microsoft Exchange Online ospitate nel cloud.</span><span class="sxs-lookup"><span data-stu-id="29e3f-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="29e3f-109">**In una distribuzione ibrida** EOP può essere configurato per proteggere l'ambiente di messaggistica e controllare l'instradamento della posta quando si dispone di un mix di cassette postali locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="29e3f-109">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="29e3f-110">Come funziona EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-110">How EOP works</span></span>

<span data-ttu-id="29e3f-111">Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:</span><span class="sxs-lookup"><span data-stu-id="29e3f-111">To understand how EOP works, it helps to see how it processes incoming email:</span></span>
  
![Elaborazione di posta elettronica di EOP](../media/EOP-email-processing.png)
  
<span data-ttu-id="29e3f-p102">Un messaggio in arrivo inizialmente attraversa il filtro connessioni, che controlla reputazione del mittente e controlla se il messaggio di malware. La maggior parte delle posta indesiderata è stata arrestata a questo punto da EOP. I messaggi proseguono per il filtraggio dei criteri, dove i messaggi vengono valutati rispetto alle regole di trasporto personalizzato che si crea o applicare un modello. Ad esempio, esiste una regola che invia una notifica a un manager quando si riceve posta elettronica da un mittente specifico. (Controlli di prevenzione della perdita di dati inoltre verificano a questo punto, se si dispone di funzionalità, per informazioni sulla disponibilità delle funzionalità, vedere [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Successivamente, messaggi superare il filtro contenuto, dove il contenuto viene verificato la terminologia e le proprietà comuni della posta indesiderata. Un messaggio identificato come posta indesiderata dal filtro contenuto può essere inviata alla cartella posta indesiderata dell'utente o per la quarantena, tra le altre opzioni, in base alle impostazioni. Dopo che un messaggio passa correttamente tutti i livelli di protezione, viene recapitato al destinatario.</span><span class="sxs-lookup"><span data-stu-id="29e3f-p102">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware. The majority of spam is stopped at this point and deleted by EOP. Messages continue through policy filtering, where messages are evaluated against custom transport rules that you create or enforce from a template. For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender. (Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam. A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings. After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="29e3f-120">Datacenter EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-120">EOP datacenters</span></span>

<span data-ttu-id="29e3f-p103">EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server in ogni centro dati accettano messaggi per conto dell'utente, offrendo un livello di separazione tra l'organizzazione e Internet, riducendo in questo modo il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo.</span><span class="sxs-lookup"><span data-stu-id="29e3f-p103">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="29e3f-p104">EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:</span><span class="sxs-lookup"><span data-stu-id="29e3f-p104">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
- <span data-ttu-id="29e3f-p105">America del, Online Exchange tutte le cassette postali si trovano in datacenter negli Stati Uniti, ad eccezione dei Sud America in cui vengono utilizzati datacenter in Brasile e Cile e in Canada in cui vengono utilizzati i Data Center in Canada. Tutti i messaggi di posta elettronica, inclusi i messaggi per i clienti Sud America e in Canada, vengono instradati tramite Data Center statunitense per il filtraggio EOP; Tuttavia la posta visualizzare viene memorizzata nel centro dati in cui si trova il tenant..</span><span class="sxs-lookup"><span data-stu-id="29e3f-p105">In the America's, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used. All email messages, including messages for customers in South America and Canada, are routed through U.S. datacenters for EOP filtering; however quaratined email is stored in the datacenter where the tenant is located..</span></span>
    
- <span data-ttu-id="29e3f-130">In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="29e3f-130">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="29e3f-p106">In Asia Pacifico (APAC), tutte le cassette postali di Exchange Online si trovano in datacenter in APAC, ma i messaggi vengono attualmente instradati tramite datacenter in EMEA per il filtraggio EOP. Questo sistema cambierà nel quarto trimestre del 2014, quando i messaggi saranno instradati tramite datacenter in APAC per il filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="29e3f-p106">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, but messages are currently routed through EMEA datacenters for EOP filtering. This is targeted to be changing in the fourth quarter of 2014, when messages will be routed through APAC datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="29e3f-133">Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="29e3f-133">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="29e3f-134">Piani e funzionalità di EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-134">EOP plans and features</span></span>

<span data-ttu-id="29e3f-135">I piani di sottoscrizione EOP disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="29e3f-135">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="29e3f-136">**EOP autonomo** EOP protegge le cassette di posta locali.</span><span class="sxs-lookup"><span data-stu-id="29e3f-136">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="29e3f-137">**Funzionalità di EOP in Exchange Online** EOP protegge le cassette postali di Exchange Online ospitate nel cloud.</span><span class="sxs-lookup"><span data-stu-id="29e3f-137">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="29e3f-138">**CAL di Exchange Enterprise con Services** Protegge le cassette postali locali, come EOP autonomo, e include le funzionalità di prevenzione della perdita di dati (DLP) e di segnalazione tramite servizi Web.</span><span class="sxs-lookup"><span data-stu-id="29e3f-138">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="29e3f-139">Per ulteriori informazioni sui requisiti, i limiti importanti e le funzionalità disponibili in tutti i piani di sottoscrizione EOP; vedere [Descrizione del servizio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span><span class="sxs-lookup"><span data-stu-id="29e3f-139">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="29e3f-140">Configurare EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-140">Setting up EOP</span></span>

<span data-ttu-id="29e3f-p107">La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.</span><span class="sxs-lookup"><span data-stu-id="29e3f-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="29e3f-143">Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="29e3f-143">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="29e3f-144">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="29e3f-144">For more information</span></span>

[<span data-ttu-id="29e3f-145">Caratteristiche di EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-145">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="29e3f-146">Video per iniziare con EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-146">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="29e3f-147">Domande frequenti su EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-147">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="29e3f-148">Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-148">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="29e3f-149">Domande frequenti sull'amministrazione delegata</span><span class="sxs-lookup"><span data-stu-id="29e3f-149">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="29e3f-150">Spostare i domini e le impostazioni da un'organizzazione di EOP a un'altra organizzazione di EOP</span><span class="sxs-lookup"><span data-stu-id="29e3f-150">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

