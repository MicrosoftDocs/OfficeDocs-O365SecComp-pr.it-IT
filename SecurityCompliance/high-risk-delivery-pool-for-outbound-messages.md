---
title: Pool di recapito ad alto rischio per i messaggi in uscita
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: Quando il sistema di posta elettronica del destinatario è stato danneggiato tramite un attacco dannoso posta indesiderata o malware e di invio di posta indesiderata in uscita tramite il servizio di filtraggio ospitato, con conseguenti gli indirizzi IP dei server di centro dati di Office 365 viene elencato nel blocco di terze parti elenchi.
ms.openlocfilehash: 69548488f70944a319a449bfc4ac1cb1bffd7b1c
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003135"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="0aaba-103">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="0aaba-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="0aaba-p101">Quando il sistema di posta elettronica del destinatario è stato danneggiato tramite un attacco dannoso posta indesiderata o malware e di invio di posta indesiderata in uscita tramite il servizio di filtraggio ospitato, con conseguenti gli indirizzi IP dei server di centro dati di Office 365 viene elencato nel blocco di terze parti elenchi. Server di destinazione è non utilizzare il servizio di filtraggio ospitato, ma utilizzare questi elenchi di blocco, rifiutare tutta la posta elettronica inviata da qualsiasi indirizzo IP filtraggio ospitato che è stati aggiunti a tali elenchi. Per evitare questo problema, tutti i messaggi in uscita che superano la soglia della posta indesiderata vengono inviati a un pool di recapito ad alto rischio. In questo pool secondario posta elettronica in uscita viene utilizzato solo per inviare i messaggi che possono essere di bassa qualità. Ciò consente di proteggere il resto della rete di inviare messaggi creati da più potrebbe provocare nell'indirizzo IP del mittente bloccato.</span><span class="sxs-lookup"><span data-stu-id="0aaba-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="0aaba-p102">L'utilizzo di un pool di recapito ad alto rischio dedicati assicura che il pool in uscita normale solo invia messaggi conosciute di alta qualità. Utilizzo di questo pool IP secondario consente di ridurre la probabilità che il pool in uscita IP normale viene aggiunto a un elenco dei domini bloccati. La possibilità di essere messa in un elenco dei domini bloccati del pool di recapito ad alto rischio rimane un rischio. Questo è per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0aaba-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="0aaba-113">I messaggi in cui il dominio di invio presenta alcun record indirizzo (record), che permette di utilizzare l'indirizzo IP del dominio, e nessun record MX, che consente ai server che devono ricevere posta elettronica per un dominio specifico nel sistema DNS posta diretta, vengono sempre indirizzati tramite il pool di recapito ad alto rischio indipendentemente dal fatto l'eliminazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="0aaba-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="0aaba-114">Informazioni sui messaggi di notifica stato recapito (DSN)</span><span class="sxs-lookup"><span data-stu-id="0aaba-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="0aaba-115">Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i messaggi (DSN) "animati" o "non riusciti".</span><span class="sxs-lookup"><span data-stu-id="0aaba-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="0aaba-116">Le cause possibili di un eccessivo numero di messaggi DSN sono:</span><span class="sxs-lookup"><span data-stu-id="0aaba-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="0aaba-117">Una campagna di spoofing su uno dei clienti che utilizzano il servizio</span><span class="sxs-lookup"><span data-stu-id="0aaba-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="0aaba-118">Un attacco directory harvest</span><span class="sxs-lookup"><span data-stu-id="0aaba-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="0aaba-119">Un attacco di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="0aaba-119">A spam attack</span></span>
    
- <span data-ttu-id="0aaba-120">Un server SMTP non autorizzato</span><span class="sxs-lookup"><span data-stu-id="0aaba-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="0aaba-p103">Tutti questi problemi può comportare un aumento del numero di messaggi DSN elaborati dal servizio improvviso. In molti casi, questi messaggi DSN visualizzati come posta indesiderata per altri servizi e server di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0aaba-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="0aaba-123">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0aaba-123">For more information</span></span>

[<span data-ttu-id="0aaba-124">Configurazione del criterio delle posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="0aaba-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="0aaba-125">Domande frequenti sulla protezione anti-spam</span><span class="sxs-lookup"><span data-stu-id="0aaba-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

