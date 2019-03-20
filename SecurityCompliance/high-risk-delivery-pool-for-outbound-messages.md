---
title: Pool di recapito ad alto rischio per i messaggi in uscita
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Se il sistema di posta elettronica di un cliente è stato compromesso da malware o da un attacco di posta indesiderata e Invia la posta indesiderata in uscita tramite il servizio di filtraggio ospitato, questo può comportare l'elenco degli indirizzi IP dei server di Data Center di Office 365 che sono elencati nel blocco di terze parti elenchi.
ms.openlocfilehash: b3c0aecd45dd01d407712af2e3945e1cff521710
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692085"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="e9fdb-103">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="e9fdb-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="e9fdb-104">Se il sistema di posta elettronica di un cliente è stato compromesso da malware o da un attacco di posta indesiderata e Invia la posta indesiderata in uscita tramite il servizio di filtraggio ospitato, questo può comportare l'elenco degli indirizzi IP dei server di Data Center di Office 365 che sono elencati nel blocco di terze parti elenchi.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-104">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists.</span></span> <span data-ttu-id="e9fdb-105">Server di destinazione che non utilizzano il servizio di filtraggio ospitato, ma utilizzano questi elenchi di blocco, rifiutare tutti i messaggi di posta elettronica inviati da tutti gli indirizzi IP del filtro host che sono stati aggiunti a tali elenchi.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-105">Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists.</span></span> <span data-ttu-id="e9fdb-106">Per evitare questo, tutti i messaggi in uscita che superano la soglia di posta indesiderata vengono inviati tramite un pool di recapito ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-106">To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span></span> <span data-ttu-id="e9fdb-107">Questo pool di posta elettronica in uscita secondario viene utilizzato solo per inviare messaggi che potrebbero essere di bassa qualità.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-107">This secondary outbound email pool is only used to send messages that may be of low quality.</span></span> <span data-ttu-id="e9fdb-108">In questo modo, è possibile proteggere il resto della rete dall'invio di messaggi che hanno maggiori probabilità di provocare il blocco dell'indirizzo IP di invio.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-108">This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="e9fdb-109">L'utilizzo di un pool di recapito ad alto rischio dedicato contribuisce a garantire che il pool in uscita normale invii solo messaggi noti come di qualità elevata.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-109">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality.</span></span> <span data-ttu-id="e9fdb-110">L'utilizzo di questo pool IP secondario consente di ridurre la probabilità che il pool IP esterno normale venga aggiunto a un elenco bloccato.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-110">Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list.</span></span> <span data-ttu-id="e9fdb-111">La possibilità che il pool di recapito ad alto rischio venga posizionato su un elenco bloccato resta un rischio.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-111">The possibility of the high-risk delivery pool being placed on a blocked list remains a risk.</span></span> <span data-ttu-id="e9fdb-112">Questo è il funzionamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-112">This is by design.</span></span>
  
<span data-ttu-id="e9fdb-113">Messaggi in cui il dominio di invio non ha un record di indirizzo (un record), che fornisce l'indirizzo IP del dominio, e nessun record MX, che consente di indirizzare la posta ai server che devono ricevere la posta per un determinato dominio nel DNS, vengono sempre instradati attraverso il pool di recapito ad alto rischio a prescindere dalla disposizione di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="e9fdb-114">Informazioni sui messaggi di notifica sullo stato del reCapito (DSN)</span><span class="sxs-lookup"><span data-stu-id="e9fdb-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="e9fdb-115">Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i messaggi "rimbalzati" o "non riusciti" (DSN).</span><span class="sxs-lookup"><span data-stu-id="e9fdb-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="e9fdb-116">Le cause possibili di un eccessivo numero di messaggi DSN sono:</span><span class="sxs-lookup"><span data-stu-id="e9fdb-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="e9fdb-117">Una campagna di spoofing su uno dei clienti che utilizzano il servizio</span><span class="sxs-lookup"><span data-stu-id="e9fdb-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="e9fdb-118">Un attacco directory harvest</span><span class="sxs-lookup"><span data-stu-id="e9fdb-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="e9fdb-119">Un attacco di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e9fdb-119">A spam attack</span></span>
    
- <span data-ttu-id="e9fdb-120">Un server SMTP non autorizzato</span><span class="sxs-lookup"><span data-stu-id="e9fdb-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="e9fdb-121">Tutti questi problemi possono determinare un improvviso aumento del numero di messaggi DSN elaborati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-121">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service.</span></span> <span data-ttu-id="e9fdb-122">Molte volte, questi messaggi DSN sembrano essere posta indesiderata ad altri server e servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e9fdb-122">Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="e9fdb-123">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e9fdb-123">For more information</span></span>

[<span data-ttu-id="e9fdb-124">Configurare i criteri della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="e9fdb-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="e9fdb-125">DOMANDE frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="e9fdb-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

