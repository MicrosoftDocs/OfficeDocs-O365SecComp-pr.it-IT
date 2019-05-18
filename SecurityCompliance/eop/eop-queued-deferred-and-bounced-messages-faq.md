---
title: Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 7d584d8356cfca805427c5dd41dc3dee2ee57e85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150268"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="d8f61-103">Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d8f61-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="d8f61-104">In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d8f61-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="d8f61-105">**D. Perché i messaggi vengono accodati?**</span><span class="sxs-lookup"><span data-stu-id="d8f61-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="d8f61-p101">R. I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="d8f61-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="d8f61-109">**D. Come viene differito un messaggio?**</span><span class="sxs-lookup"><span data-stu-id="d8f61-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="d8f61-p102">R. I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.</span><span class="sxs-lookup"><span data-stu-id="d8f61-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="d8f61-113">**D. Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?**</span><span class="sxs-lookup"><span data-stu-id="d8f61-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="d8f61-114">R.</span><span class="sxs-lookup"><span data-stu-id="d8f61-114">A.</span></span> <span data-ttu-id="d8f61-115">I messaggi il cui recapito è ritardato rimangono nelle code per 2 giorni.</span><span class="sxs-lookup"><span data-stu-id="d8f61-115">Messages in deferral will remain in our queues for 2 days.</span></span> <span data-ttu-id="d8f61-116">I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="d8f61-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="d8f61-117">I primi deferimenti sono di 15 minuti o meno, con i successivi tentativi (nelle prossime mezze dozzine) che aumentano l'intervallo su più tentativi fino a un massimo di 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="d8f61-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="d8f61-118">L'espansione della durata dell'intervallo è dinamica, tenendo in considerazione più variabili come le dimensioni delle code e la priorità dei messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="d8f61-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="d8f61-119">In Basic, è 15 minuti (o meno) per iniziare, quindi espandersi da lì nelle prossime ore fino a 60 mins max.</span><span class="sxs-lookup"><span data-stu-id="d8f61-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="d8f61-120">**D. Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?**</span><span class="sxs-lookup"><span data-stu-id="d8f61-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="d8f61-p104">R. Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.  </span><span class="sxs-lookup"><span data-stu-id="d8f61-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

