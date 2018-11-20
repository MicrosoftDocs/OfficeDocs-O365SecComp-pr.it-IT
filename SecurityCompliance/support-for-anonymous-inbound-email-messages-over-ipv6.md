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
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6

Exchange Online Protection (EOP) ed Exchange Online supporta la ricezione di messaggi di posta elettronica in ingresso anonimi su IPv6 comunicazioni provenienti da mittenti non inviino messaggi su Transport Layer Security (TLS). È possibile consenso esplicito componente per la ricezione di messaggi su IPv6 richiedendo questa funzionalità di supporto Microsoft, aprire l'interfaccia di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), facendo clic sul **supporto**e quindi fare clic su **nuova richiesta di assistenza**). Se non consenso esplicito componente IPv6 si continueranno a ricevere i messaggi su IPv4.
  
I mittenti che trasmettono messaggi al servizio su IPv6 devono rispettare i seguenti due requisiti:
  
1. L'indirizzo IPv6 di invio deve avere un record PTR valido ([record DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) dell'indirizzo IPv6 di invio). 
    
2. Il mittente deve superare la verifica SPF (definita in [RFC 7208](https://tools.ietf.org/html/rfc7208)) oppure la [verifica DKIM](http://dkim.org/) (definita in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Il rispetto di tali requisiti è obbligatorio e non dipende dalla configurazione utilizzata prima di scegliere IPv6. Se entrambi i requisiti sono soddisfatti, il messaggio passerà attraverso il normale filtro dei messaggi di posta elettronica fornito dal servizio. Se uno dei due requisiti non è soddisfatto, il messaggio sarà rifiutato con una delle seguenti risposte 450:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Se non si è scelto di ricevere messaggi su IPv6 e il mittente tenta di forzare un messaggio su IPv6 collegandosi manualmente al server di posta, il messaggio sarà rifiutato con una risposta 550 simile alla seguente:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Supporto per la convalida di messaggi firmati con DKIM](support-for-validation-of-dkim-signed-messages.md)
  

