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
ms.openlocfilehash: 4b2c902adacd6e72e587aadaceecd22dd0084d85
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686426"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP

In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).
  
 **D. Perché i messaggi vengono accodati?**
  
R. I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.
  
 **D. Come viene differito un messaggio?**
  
R. I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.
  
 **D. Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?**
  
R. messaggi accodati resteranno nel nostro code per 2 giorni. Messaggio di tentativi sono basati su errore che è possibile ottenere dal sistema di posta elettronica del destinatario. Il dilazioni alcuni prima sono 15 minuti o minore di successivi tentativi di connessione (tramite il successiva decine metà o meno) aumentare l'intervallo su più tentativi per un massimo di 60 minuti. L'espansione di durata intervallo è dinamico, tenendo in considerazione più variabili come dimensioni coda e la priorità del messaggio interno. In base, è 15 minuti (o minore di) per avviare, quindi l'espansione da quest'ultimo su alcune ore successiva al massimo di 60 minuti.
  
 **D. Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?**
  
R. Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile. 
  

