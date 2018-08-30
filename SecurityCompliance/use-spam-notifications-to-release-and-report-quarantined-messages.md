---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: Se l'amministratore ha abilitato le notifiche per gli utenti, si riceverà un messaggio di notifica in cui sono elencati i messaggi inviati alla cassetta postale che sono stati identificati come posta indesiderata, blocco o messaggi di phishing. È possibile rilasciare o segnalazione dei messaggi dopo la notifica.
ms.openlocfilehash: e355a94af5ac295503a8e205b1a896afc1c54fb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530546"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="cbdb7-104">Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365</span><span class="sxs-lookup"><span data-stu-id="cbdb7-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="cbdb7-105">Se l'amministratore ha abilitato le notifiche di posta indesiderata per gli utenti, si riceverà un messaggio di notifica in cui sono elencati i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata e quarantena invece.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="cbdb7-106">Se si è un amministratore e si desidera attivare questa funzionalità, è possibile scegliere l'opzione quando si [Modifica un criterio di protezione da posta indesiderata predefinito](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="cbdb7-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="cbdb7-p102">Il messaggio che viene visualizzato il numero di messaggi in quarantena che si dispone, e la data e ora (in UTC o Coordinated Universal Time) dell'ultimo messaggio sono inclusi nell'elenco. L'elenco include quanto segue per ogni messaggio:</span><span class="sxs-lookup"><span data-stu-id="cbdb7-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="cbdb7-109">**Mittente** L'operazione di invio nome e indirizzo e-mail del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="cbdb7-110">**Oggetto** Oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="cbdb7-111">**Data** Data e ora (in formato UTC) del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="cbdb7-112">**Dimensioni** La dimensione del messaggio, in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="cbdb7-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="cbdb7-113">Attualmente, non vi sono due azioni da intraprendere con un messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="cbdb7-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="cbdb7-114">**Versione di posta in arrivo** Selezionare questa opzione per inviare il messaggio di posta in arrivo, dove è possibile visualizzare.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="cbdb7-p103">**Segnalare come posta non indesiderata** Selezionare questa opzione per inviare una copia del messaggio a Microsoft per l'analisi. Il team di posta indesiderata valuta e analizza il messaggio e, in base ai risultati dell'analisi, modifica le regole di filtro di protezione da posta indesiderata per consentire il messaggio attraverso.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="cbdb7-117">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cbdb7-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="cbdb7-p104">I messaggi vengono messi in quarantena perché sono corrispondenti a una regola di flusso di posta elettronica non vengono inclusi nei messaggi in quarantena utente. Vengono elencati solo i messaggi di quarantena della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="cbdb7-120">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="cbdb7-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

