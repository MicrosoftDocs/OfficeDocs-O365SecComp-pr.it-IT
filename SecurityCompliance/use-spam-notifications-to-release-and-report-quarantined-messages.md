---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/14/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Se l'amministratore abilita le notifiche per gli utenti, riceverà un messaggio di notifica che elenca i messaggi inviati alla cassetta postale che sono stati identificati come posta indesiderata, in blocco o in messaggi di phishing. È possibile rilasciare o segnalare i messaggi dopo la notifica.
ms.openlocfilehash: de67987b0028102bdf61889ce54ca4215182e279
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638973"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="bb574-104">Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365</span><span class="sxs-lookup"><span data-stu-id="bb574-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="bb574-105">Se l'amministratore abilita le notifiche di posta indesiderata per gli utenti, riceverà un messaggio di notifica che elenca i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata e in quarantena</span><span class="sxs-lookup"><span data-stu-id="bb574-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="bb574-106">Se si è un amministratore e si desidera abilitare questa funzionalità, è possibile scegliere l'opzione quando si [modifica un criterio di](https://go.microsoft.com/fwlink/?LinkId=800313)protezione da posta indesiderata predefinito.</span><span class="sxs-lookup"><span data-stu-id="bb574-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="bb574-107">Il messaggio ricevuto include il numero di messaggi di posta indesiderata in quarantena e la data e l'ora (in formato UTC (Universal Coordinated Time) dell'ultimo messaggio nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bb574-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="bb574-108">L'elenco include quanto segue per ogni messaggio:</span><span class="sxs-lookup"><span data-stu-id="bb574-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="bb574-109">**Mittente** Il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="bb574-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="bb574-110">**Oggetto** Oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="bb574-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="bb574-111">**Data** Data e ora (in formato UTC) del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="bb574-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="bb574-112">**Dimensioni** Le dimensioni del messaggio, in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="bb574-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="bb574-113">Di seguito sono riportate le azioni che è possibile eseguire con un messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="bb574-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="bb574-114">**Visualizzare in anteprima** il messaggio se si desidera visualizzare in anteprima il contenuto o l'intestazione prima di eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="bb574-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="bb574-115">**Scaricare** il messaggio se si desidera esaminare il messaggio e gli allegati (se presenti) del dispositivo prima di eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="bb574-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="bb574-116">**Rilascia** se il messaggio non è posta indesiderata e si desidera che Office 365 invii il messaggio alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="bb574-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="bb574-117">**Release _AMP_ Allow sender** se il messaggio non è posta indesiderata e si desidera che Office 365 aggiunga il mittente all'elenco Mittenti attendibili e destinatari per i messaggi di posta elettronica futuri.</span><span class="sxs-lookup"><span data-stu-id="bb574-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="bb574-118">Tenere presente che l'amministratore può disporre di altre configurazioni Consenti/blocca a livello di organizzazione che sostituiscono l'elenco dei mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="bb574-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="bb574-119">**Rilasciare il report di &**, se il messaggio non è spam e si desidera inviare il messaggio alla cassetta postale e segnalarlo a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bb574-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="bb574-120">**Blocca** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="bb574-120">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="bb574-121">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bb574-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="bb574-122">I messaggi in quarantena perché hanno trovato una regola del flusso di posta non sono inclusi nei messaggi in quarantena dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bb574-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="bb574-123">Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena.</span><span class="sxs-lookup"><span data-stu-id="bb574-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="bb574-124">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="bb574-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

