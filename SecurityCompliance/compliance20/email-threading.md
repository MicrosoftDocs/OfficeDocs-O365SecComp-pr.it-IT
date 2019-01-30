---
title: Messaggio di posta elettronica threading
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2340128f508a3be389afce86596f7e6395a0bb7e
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607923"
---
# <a name="email-threading"></a><span data-ttu-id="24de2-102">Messaggio di posta elettronica threading</span><span class="sxs-lookup"><span data-stu-id="24de2-102">Email threading</span></span>
<span data-ttu-id="24de2-p101">È consigliabile una conversazione di posta elettronica succedendo per un po' di tempo. Nella maggior parte dei casi, il messaggio di posta elettronica ultimo sul thread includerà il contenuto di tutti i precedenti messaggi di posta elettronica; Per ottenere un contesto completo della conversazione che si sono verificati il thread, esaminare l'ultimo messaggio di posta elettronica. Messaggio di posta elettronica threading identifica tali messaggi di posta elettronica in modo che i revisori possono esaminare una frazione di raccolte documenti senza perdere alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="24de2-p101">Consider an email conversation that has been going on for a while. In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread. Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="24de2-106">Che cosa threading posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="24de2-106">What does email threading do?</span></span>
<span data-ttu-id="24de2-p102">Messaggio di posta elettronica threading analizza ogni messaggio di posta elettronica e desconstructs per singoli messaggi. ogni messaggio di posta elettronica è una serie di singoli messaggi. Quindi, analizza tutti i messaggi di posta elettronica nel working set per determinare se un messaggio di posta elettronica con contenuto univoco o se la catena interamente contenuta in un messaggio di posta elettronica diverso. Alla fine messaggi di posta elettronica sono suddivise in quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="24de2-p102">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages. Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email. In the end emails are divided into four categories:</span></span>
- <span data-ttu-id="24de2-110">Inclusives: dell'ultimo messaggio nella posta elettronica include contenuto univoco e il messaggio di posta elettronica con tutti gli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è completamente contenuto in questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="24de2-110">Inclusives: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="24de2-111">Inclusi meno: dell'ultimo messaggio nella posta elettronica con contenuto univoco, ma il messaggio di posta elettronica non contiene alcuni degli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è completamente contenuto in questo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="24de2-111">Inclusive minus: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="24de2-112">Copia inclusivo: una copia esatta di un inclusi/inclusi meno posta elettronica</span><span class="sxs-lookup"><span data-stu-id="24de2-112">Inclusive copy: an exact copy of an inclusive/inclusive minus email</span></span>
- <span data-ttu-id="24de2-113">None: Il contenuto di questo messaggio di posta elettronica interamente contenuto in almeno un messaggio di posta elettronica è contrassegnato come sottrazione inclusi/inclusi.</span><span class="sxs-lookup"><span data-stu-id="24de2-113">None: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="24de2-114">Qual è la differenza dalle conversazioni di Outlook?</span><span class="sxs-lookup"><span data-stu-id="24de2-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="24de2-p103">In breve, questo suoni molto simile a raggruppamenti di conversazione in Outlook. Esistono tuttavia alcune differenze importanti. Prendere in considerazione una conversazione di posta elettronica che ha ricevuto inoltrata a due conversazione; ad esempio, un utente ha risposto a un messaggio di posta elettronica che non è più recente della conversazione in modo che le ultime due messaggi di posta elettronica nella conversazione entrambi con contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="24de2-p103">At a glance, this sounds very similar to conversation groupings in Outlook. However, there are some important distinctions. Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="24de2-p104">Outlook ancora per raggruppare i messaggi di posta elettronica in una singola conversazione; leggere l'ultima email implica manca il contesto della posta elettronica al penultimo, che contiene anche contenuto univoco. Poiché posta threading analizza ogni messaggio di posta elettronica in singoli componenti e li confronta, posta elettronica threading contrassegna entrambe le ultime due messaggi di posta elettronica come inclusives, assicurarsi che non perdere alcun contesto come leggere contrassegnato come inclusi tutti i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="24de2-p104">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content. Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>