---
title: Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: Informazioni su come configurare il supporto per i messaggi anonimi da origini IPv6 per Exchange Online Protection ed Exchange Online.
ms.openlocfilehash: 0d324ce6e0ff0ff9104ef597176b09a5a319abc7
ms.sourcegitcommit: 75b985b2574f4be70cf352498ea300b3d99dd338
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2018
ms.locfileid: "26255811"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="1031c-103">Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6</span><span class="sxs-lookup"><span data-stu-id="1031c-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="1031c-p101">Exchange Online Protection (EOP) ed Exchange Online supporta la ricezione di messaggi di posta elettronica in ingresso anonimi su IPv6 comunicazioni provenienti da mittenti non inviino messaggi su Transport Layer Security (TLS). È possibile consenso esplicito componente per la ricezione di messaggi su IPv6 richiedendo questa funzionalità di supporto Microsoft, aprire l'interfaccia di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), facendo clic sul **supporto**e quindi fare clic su **nuova richiesta di assistenza**). Se non consenso esplicito componente IPv6 si continueranno a ricevere i messaggi su IPv4.</span><span class="sxs-lookup"><span data-stu-id="1031c-p101">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS). You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Office 365 admin center at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), clicking **Support**, and then clicking **New service request**). If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="1031c-107">I mittenti che trasmettono messaggi al servizio su IPv6 devono rispettare i seguenti due requisiti:</span><span class="sxs-lookup"><span data-stu-id="1031c-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="1031c-108">L'indirizzo IPv6 di invio deve avere un record PTR valido ([record DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) dell'indirizzo IPv6 di invio).</span><span class="sxs-lookup"><span data-stu-id="1031c-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="1031c-109">Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](http://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="1031c-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="1031c-p102">Il rispetto di tali requisiti è obbligatorio e non dipende dalla configurazione utilizzata prima di scegliere IPv6. Se entrambi i requisiti sono soddisfatti, il messaggio passerà attraverso il normale filtro dei messaggi di posta elettronica fornito dal servizio. Se uno dei due requisiti non è soddisfatto, il messaggio sarà rifiutato con una delle seguenti risposte 450:</span><span class="sxs-lookup"><span data-stu-id="1031c-p102">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="1031c-113">Se non si è scelto di ricevere messaggi su IPv6 e il mittente tenta di forzare un messaggio su IPv6 collegandosi manualmente al server di posta, il messaggio sarà rifiutato con una risposta 550 simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1031c-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="1031c-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1031c-114">For more information</span></span>

[<span data-ttu-id="1031c-115">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="1031c-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

