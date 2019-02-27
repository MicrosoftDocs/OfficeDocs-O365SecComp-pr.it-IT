---
title: Gestire gli elenchi di mittenti attendibili per messaggi inviati in massa
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: "Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio rispetta i mittenti e i domini attendibili esaminando l'indirizzo RFC 5321. MailFrom e l'indirizzo RFC 5322. from, mentre Outlook aggiunge l'indirizzo RFC 5322. from all'elenco dei mittenti attendibili di un utente. Nota: il servizio controlla sia l'indirizzo 5321. MailFrom sia l'indirizzo 5322. from per i mittenti e i domini bloccati."
ms.openlocfilehash: 27d635ec93dd04df8ebf22d5d3d8f8ead4b7bcf8
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276136"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="8498b-105">Gestire gli elenchi di mittenti attendibili per messaggi inviati in massa</span><span class="sxs-lookup"><span data-stu-id="8498b-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="8498b-p102">Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio rispetta i mittenti e i domini attendibili esaminando l'indirizzo RFC 5321. MailFrom e l'indirizzo RFC 5322. from, mentre Outlook aggiunge l'indirizzo RFC 5322. from all'elenco dei mittenti attendibili di un utente. Nota: il servizio controlla sia l'indirizzo 5321. MailFrom sia l'indirizzo 5322. from per i mittenti e i domini bloccati.</span><span class="sxs-lookup"><span data-stu-id="8498b-p102">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently. The service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list. (Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="8498b-p103">L'indirizzo di posta elettronica SMTP, altrimenti noto come indirizzo RFC 5321. MailFrom, è l'indirizzo di posta elettronica utilizzato per eseguire i controlli SPF e, se non è possibile recapitare la posta, il percorso in cui viene recapitato il messaggio. Si tratta di questo indirizzo di posta elettronica che viene inserito nel percorso di ritorno nelle intestazioni del messaggio per impostazione predefinita, sebbene sia possibile che il mittente designi un indirizzo diverso per il percorso restituito.</span><span class="sxs-lookup"><span data-stu-id="8498b-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="8498b-111">L'indirizzo da: nelle intestazioni del messaggio, altrimenti noto come indirizzo RFC 5322. from, è l'indirizzo di posta elettronica visualizzato nel client di posta elettronica, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="8498b-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="8498b-p104">La maggior parte delle volte, gli indirizzi 5321. MailFrom e 5322. from sono gli stessi. Questa è la caratteristica tipica della comunicazione da persona a persona. Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi sono spesso diversi. Questo accade solitamente più spesso per i messaggi di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="8498b-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="8498b-p105">Si supponga, ad esempio, che la compagnia aerea Blue laggiù abbia stipulato un contratto con Margie ' s Travel per inviare la propria pubblicità tramite posta elettronica. È quindi possibile ottenere un messaggio nella posta in arrivo dal mittente blueyonder@news.blueyonderairlines.com. In questo caso, l'indirizzo 5321. MailFrom è blueyonder.airlines@margiestravel.com e blueyonder@news.blueyonderairlines.com è l'indirizzo 5322. from che è quello visualizzato in Outlook. Poiché il servizio rispetta l'indirizzo RFC 5322. from, per evitare che questo messaggio venga filtrato, è sufficiente aggiungere l'indirizzo RFC 5322. from come mittente sicuro in Outlook.</span><span class="sxs-lookup"><span data-stu-id="8498b-p105">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising. You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com. In this case, the 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one you see in Outlook. Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can simply add the RFC 5322.From address as a safe sender in Outlook.</span></span>
  

