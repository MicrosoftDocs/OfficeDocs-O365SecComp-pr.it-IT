---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/12/2018
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
ms.openlocfilehash: 7f68b70298fca7d8ed5f5e5b8dc9c727c3a6a6c1
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492725"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="d1d0f-104">Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365</span><span class="sxs-lookup"><span data-stu-id="d1d0f-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="d1d0f-105">Se l'amministratore abilita le notifiche di posta indesiderata per gli utenti, riceverà un messaggio di notifica che elenca i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata e in quarantena</span><span class="sxs-lookup"><span data-stu-id="d1d0f-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="d1d0f-106">Se si è un amministratore e si desidera abilitare questa funzionalità, è possibile scegliere l'opzione quando si [modifica un criterio di](https://go.microsoft.com/fwlink/?LinkId=800313)protezione da posta indesiderata predefinito.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="d1d0f-107">Il messaggio ricevuto include il numero di messaggi di posta indesiderata in quarantena e la data e l'ora (in formato UTC (Universal Coordinated Time) dell'ultimo messaggio nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="d1d0f-108">L'elenco include quanto segue per ogni messaggio:</span><span class="sxs-lookup"><span data-stu-id="d1d0f-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="d1d0f-109">**Mittente** Il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="d1d0f-110">**Oggetto** Oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="d1d0f-111">**Data** Data e ora (in formato UTC) del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="d1d0f-112">**Dimensioni** Le dimensioni del messaggio, in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="d1d0f-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="d1d0f-113">Al momento, esistono due azioni che è possibile eseguire con un messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="d1d0f-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="d1d0f-114">**Rilascia in posta in arrivo** Scegliere questa casella per inviare il messaggio alla posta in arrivo, in cui è possibile visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="d1d0f-115">**Segnala come non** indesiderato Scegliere questa pagina per inviare una copia del messaggio a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-115">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="d1d0f-116">Il team di analisi di posta indesiderata, valuta e analizza il messaggio e a seconda dei risultati dell'analisi, regola il filtro di protezione da posta indesiderata per consentire l'inoltro del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-116">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="d1d0f-117">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d1d0f-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="d1d0f-118">I messaggi in quarantena perché hanno trovato una regola del flusso di posta non sono inclusi nei messaggi in quarantena dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-118">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="d1d0f-119">Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-119">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="d1d0f-120">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="d1d0f-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

