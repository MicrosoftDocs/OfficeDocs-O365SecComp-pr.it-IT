---
title: Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 17e5955195c4e38299712fb9161822984b2a643a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026223"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="3deff-103">Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP</span><span class="sxs-lookup"><span data-stu-id="3deff-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="3deff-104">In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3deff-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="3deff-105">**D. Perché i messaggi vengono accodati?**</span><span class="sxs-lookup"><span data-stu-id="3deff-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="3deff-p101">R. I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="3deff-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="3deff-109">**D. Come viene differito un messaggio?**</span><span class="sxs-lookup"><span data-stu-id="3deff-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="3deff-p102">R. I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.</span><span class="sxs-lookup"><span data-stu-id="3deff-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="3deff-113">**D. Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?**</span><span class="sxs-lookup"><span data-stu-id="3deff-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="3deff-p103">R. I messaggi il cui recapito è ritardato rimangono nelle code per 2 giorni. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. In media, l'intervallo tra i tentativi di invio è di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="3deff-p103">A. Messages in deferral will remain in our queues for 2 days. Message retry attempts are based on the error we get back from the recipient's mail system. On average, messages are retried every 5 minutes.</span></span>
  
 <span data-ttu-id="3deff-118">**D. Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?**</span><span class="sxs-lookup"><span data-stu-id="3deff-118">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="3deff-p104">R. Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="3deff-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

