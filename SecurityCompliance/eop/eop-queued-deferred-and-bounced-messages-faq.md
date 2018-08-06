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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP

In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).
  
 **D. Perché i messaggi vengono accodati?**
  
R. I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.
  
 **D. Come viene differito un messaggio?**
  
R. I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.
  
 **D. Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?**
  
R. I messaggi il cui recapito è ritardato rimangono nelle code per 2 giorni. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. In media, l'intervallo tra i tentativi di invio è di 5 minuti.
  
 **D. Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?**
  
R. Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile. 
  

