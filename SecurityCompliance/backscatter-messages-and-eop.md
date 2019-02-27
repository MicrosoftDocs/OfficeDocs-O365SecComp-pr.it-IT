---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. La DNSBL Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non si tratta di un elenco di spammer e non si tenta di rimuovere i server dal DNSBL di Backscatterer.
ms.openlocfilehash: 73f8631c50bcfb8a023b2b6007b7ccf48038e16e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275296"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="b0ec0-105">Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP</span><span class="sxs-lookup"><span data-stu-id="b0ec0-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="b0ec0-p102">I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. Poiché Exchange Online Protection (EOP) è un servizio di filtro della posta indesiderata, i messaggi di posta elettronica inviati a destinatari inesistenti e ad altre destinazioni sospette vengono rifiutati dal servizio. In questo caso, EOP genererà un messaggio di rapporto di mancato recapito (NDR) e lo riconsegnerà al "mittente". Poiché gli spammer utilizzano frequentemente un indirizzo contraffatto o non valido nei propri messaggi, l'indirizzo del mittente a cui viene inviato il rapporto di MANCAto reCAPITO può comportare un messaggio a dispersione. In questo caso, i server in uscita associati alla rete EOP possono essere elencati nell'elenco DNS bloccati di Backscatterer (DNSBL). La DNSBL Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non si tratta di un elenco di spammer e non si tenta di rimuovere i server dal DNSBL di Backscatterer.</span><span class="sxs-lookup"><span data-stu-id="b0ec0-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="b0ec0-p103">In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage).</span><span class="sxs-lookup"><span data-stu-id="b0ec0-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="b0ec0-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b0ec0-116">For more information</span></span>

[<span data-ttu-id="b0ec0-117">Elenco IP Backscatterer.org</span><span class="sxs-lookup"><span data-stu-id="b0ec0-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="b0ec0-118">Vedere la voce "backscattering di rapporto di MANCAto reCAPITO" in [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="b0ec0-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

