---
title: Supporto per la convalida di messaggi firmati con DKIM
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Informazioni sulla convalida dei messaggi firmati di DKIM in Exchange Online Protection ed Exchange Online
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643268"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="be3e2-103">Supporto per la convalida di messaggi firmati con DKIM</span><span class="sxs-lookup"><span data-stu-id="be3e2-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="be3e2-104">Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="be3e2-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="be3e2-105">DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri.</span><span class="sxs-lookup"><span data-stu-id="be3e2-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="be3e2-106">Collega una messaggio di posta elettronica all'organizzazione che lo ha inviato.</span><span class="sxs-lookup"><span data-stu-id="be3e2-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="be3e2-107">La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati tramite comunicazioni IPv6.</span><span class="sxs-lookup"><span data-stu-id="be3e2-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="be3e2-108">Office 365 supporta ora anche DKIM quando la posta viene inviata tramite IPv4.</span><span class="sxs-lookup"><span data-stu-id="be3e2-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="be3e2-109">Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).</span><span class="sxs-lookup"><span data-stu-id="be3e2-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="be3e2-p102">DKIM convalida un messaggio con firma digitale visualizzato nell'intestazione DKIM-Signature nelle intestazioni del messaggio. I risultati di una convalida DKIM-Signature vengono inseriti nell'intestazione Authentication-Results, che è conforme a RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):</span><span class="sxs-lookup"><span data-stu-id="be3e2-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="be3e2-113">Gli amministratori possono creare [regole del flusso di posta](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) di Exchange (note anche come regole di trasporto) sui risultati di una convalida DKIM per filtrare o instradare i messaggi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="be3e2-113">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

