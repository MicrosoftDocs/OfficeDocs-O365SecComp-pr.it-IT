---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
description: I messaggi backscatter sono i messaggi di rimbalzo automatizzato che vengono inviati dai server di posta elettronica, in genere a causa di posta indesiderata in ingresso. DNSBLHTTP:// Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non è un elenco di un mittente e non è tenta di rimuovere il server dalla DNSBLHTTP:// Backscatterer.
ms.openlocfilehash: 2ab5c6a3bec347446452acd3bdfd8c5d309994a9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002685"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="0bd20-105">Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP</span><span class="sxs-lookup"><span data-stu-id="0bd20-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="0bd20-p102">I messaggi backscatter sono i messaggi di rimbalzo automatizzato che vengono inviati dai server di posta elettronica, in genere a causa di posta indesiderata in ingresso. Perché Exchange Online Protection (EOP) è una servizio di filtraggio della posta indesiderata, messaggi di posta elettronica inviati a destinatari che non esistenti e ad altre destinazioni potenzialmente dannoso vengono respinto dal nostro servizio. In questo caso, EOP genererà un messaggio di rapporto di mancato recapito (NDR) e offre al "mittente". Poiché i mittenti di posta indesiderata utilizzano frequentemente un indirizzo contraffatto o non valido "In" nei loro messaggi, l'indirizzo del mittente in cui viene inviato il rapporto di mancato recapito può comportare un messaggio backscatter. In questo caso, server in uscita associati alla rete EOP possono essere elencati in Backscatterer DNS blocco elenco (DNSBLHTTP://). DNSBLHTTP:// Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non è un elenco di un mittente e non è tenta di rimuovere il server dalla DNSBLHTTP:// Backscatterer.</span><span class="sxs-lookup"><span data-stu-id="0bd20-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0bd20-p103">In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage).</span><span class="sxs-lookup"><span data-stu-id="0bd20-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="0bd20-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0bd20-116">For more information</span></span>

[<span data-ttu-id="0bd20-117">Elenco IP Backscatterer.org</span><span class="sxs-lookup"><span data-stu-id="0bd20-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="0bd20-118">Vedere la voce "Backscatter rapporto di mancato recapito" in [Opzioni di filtro posta indesiderata](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="0bd20-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

