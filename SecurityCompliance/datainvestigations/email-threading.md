---
title: Threading posta elettronica
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c2086c1667f4c5a612f0980c2492819168d92977
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150818"
---
# <a name="email-threading"></a><span data-ttu-id="071aa-102">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="071aa-102">Email threading</span></span>

<span data-ttu-id="071aa-103">Si consideri una conversazione di posta elettronica che si sta protrattando da un po' di tempo.</span><span class="sxs-lookup"><span data-stu-id="071aa-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="071aa-104">Nella maggior parte dei casi, l'ultimo messaggio di posta elettronica sul thread includerà il contenuto di tutti i messaggi di posta elettronica precedenti. la revisione dell'ultimo messaggio di posta elettronica fornirà un contesto completo della conversazione che è stata eseguita nel thread.</span><span class="sxs-lookup"><span data-stu-id="071aa-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="071aa-105">Il threading e-mail identifica tali messaggi di posta elettronica in modo che i revisori possano rivedere una frazione dei documenti raccolti senza perdere alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="071aa-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="071aa-106">Cosa fa il threading della posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="071aa-106">What does email threading do?</span></span>

<span data-ttu-id="071aa-107">Il threading della posta elettronica analizza ogni messaggio di posta elettronica e lo desconstructs ai singoli messaggi; ogni messaggio di posta elettronica è una catena di singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="071aa-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="071aa-108">Quindi, analizza tutti i messaggi di posta elettronica nel working set per determinare se un messaggio di posta elettronica ha contenuto univoco o se la catena è totalmente contenuta in un altro indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="071aa-108">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="071aa-109">Alla fine i messaggi di posta elettronica sono divisi in quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="071aa-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="071aa-110">**Inclusive**: l'ultimo messaggio nella posta elettronica ha contenuto univoco e l'indirizzo di posta elettronica include tutti gli allegati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questa e-mail.</span><span class="sxs-lookup"><span data-stu-id="071aa-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="071aa-111">**Inclusive minus**: l'ultimo messaggio nella posta elettronica ha contenuto univoco, ma la posta elettronica non contiene alcuni degli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è totalmente contenuto in questo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="071aa-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="071aa-112">**Copia inclusiva**: una copia esatta di un messaggio di posta elettronica incluso/incluso</span><span class="sxs-lookup"><span data-stu-id="071aa-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="071aa-113">**None**: il contenuto di questo messaggio di posta elettronica è totalmente contenuto in almeno un messaggio di posta elettronica contrassegnato come incluso/inclusivo meno.</span><span class="sxs-lookup"><span data-stu-id="071aa-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="071aa-114">In che modo è diversa dalle conversazioni in Outlook?</span><span class="sxs-lookup"><span data-stu-id="071aa-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="071aa-115">A colpo d'occhio, questo sembra molto simile ai gruppi di conversazione in Outlook.</span><span class="sxs-lookup"><span data-stu-id="071aa-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="071aa-116">Tuttavia, esistono alcune distinzioni importanti.</span><span class="sxs-lookup"><span data-stu-id="071aa-116">However, there are some important distinctions.</span></span> <span data-ttu-id="071aa-117">Si consideri una conversazione di posta elettronica che è stata biforcuta in due conversazioni; ad esempio, qualcuno ha risposto a un messaggio di posta elettronica che non è l'ultimo della conversazione in modo che gli ultimi due messaggi di posta elettronica nella conversazione abbiano entrambi contenuto univoco.</span><span class="sxs-lookup"><span data-stu-id="071aa-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="071aa-118">Outlook potrebbe comunque raggruppare i messaggi di posta elettronica in una singola conversazione; leggere solo l'ultimo messaggio di posta elettronica significherebbe mancare il contesto del penultimo messaggio di posta elettronica, che contiene anche contenuti univoci.</span><span class="sxs-lookup"><span data-stu-id="071aa-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="071aa-119">Poiché il threading della posta elettronica analizza tutti i messaggi di posta elettronica in singoli componenti e li confronta, il threading della posta elettronica contrassegna entrambi gli ultimi due messaggi di posta elettronica come inclusivi, assicurando che non mancherà alcun contesto purché vengano lette tutte le e-mail contrassegnate come inclusive.</span><span class="sxs-lookup"><span data-stu-id="071aa-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>