---
title: Esaminare gli avvisi per intervenire in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Utilizzare la pagina avvisi di protezione di applicazioni di Office 365 Cloud per visualizzare i potenziali problemi ed eseguire azioni. È possibile ignorare o risolvere gli avvisi e se necessario, sospendere un account utente.
ms.openlocfilehash: 2665f4ebc9c5c24b95da64954a606dfc0df99082
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014828"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="b6536-104">Esaminare gli avvisi per intervenire in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b6536-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="b6536-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b6536-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b6536-106">Pianificazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b6536-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b6536-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b6536-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b6536-108">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b6536-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b6536-109">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="b6536-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b6536-110">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="b6536-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="b6536-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="b6536-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="b6536-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="b6536-112">You are here!</span></span>  <br/> [<span data-ttu-id="b6536-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b6536-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="b6536-114">È possibile utilizzare la pagina avvisi di protezione di Office 365 Cloud App per visualizzare problemi potenziali e, se necessario, eseguire l'azione necessaria.</span><span class="sxs-lookup"><span data-stu-id="b6536-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6536-p102">È necessario essere un amministratore globale o sicurezza per eseguire le attività in questo articolo. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b6536-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="b6536-117">Come ottenere la pagina avvisi</span><span class="sxs-lookup"><span data-stu-id="b6536-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="b6536-118">Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="b6536-118">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="b6536-119">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="b6536-119">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="b6536-120">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="b6536-120">Choose **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="b6536-121">![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="b6536-121">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span>
  
4. <span data-ttu-id="b6536-122">Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.</span><span class="sxs-lookup"><span data-stu-id="b6536-122">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="b6536-123">![Nella pagina avvisi, è possibile visualizzare gli avvisi sono state attivate e le azioni eseguite.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="b6536-123">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="b6536-124">Revisione e gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="b6536-124">Review and handle alerts</span></span>

<span data-ttu-id="b6536-p103">Gli avvisi consentono di identificare le attività nell'ambiente Office 365 cloud che è possibile eseguire un'analisi approfondita. È inoltre possibile decidere di creare nuovi criteri o modificare criteri esistenti in base ad avvisi che viene visualizzato. Ad esempio, se è disponibile un amministratore l'accesso da una posizione strana, può decidere impostare un criterio che impedisce agli amministratori di accedere a Office 365 da determinate posizioni.</span><span class="sxs-lookup"><span data-stu-id="b6536-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="b6536-128">È possibile filtrare gli avvisi per **categoria** o per **gravità** in modo che è possibile gestire innanzitutto i più importanti.</span><span class="sxs-lookup"><span data-stu-id="b6536-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="b6536-p104">Per ciascun avviso, esaminare la causa per stabilire l'azione da intraprendere. Per visualizzare ulteriori dettagli su un avviso e per eseguire l'azione, ad esempio la risoluzione dell'avviso o sospendere un account di utenti, fare clic sull'avviso per aprire una pagina dei dettagli. Nella pagina dettagli è possibile esaminare il registro attività, gli account e gli utenti che sono correlati all'avviso ed eseguire azioni, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b6536-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="b6536-p105">**Eliminare** Se l'avviso è falso positivo, chiuderla. È facoltativamente possibile aggiungere un commento che spiega perché chiusa.</span><span class="sxs-lookup"><span data-stu-id="b6536-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="b6536-p106">**Risolvere avviso** Se è stato generato l'avviso per un'attività che si conosce non sia una minaccia, risolvere il problema. È facoltativamente possibile aggiungere un commento che spiega perché si risolti.</span><span class="sxs-lookup"><span data-stu-id="b6536-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="b6536-136">**Sospendere** Se si sospetta accesso non autorizzato aggiuntivi su un account, ad esempio, un utente l'accesso da un altro paese quando si conosce tale persona si trova fisicamente presso un ufficio locale, mentre è possibile [sospendere l'account](suspend-or-restore-an-account-in-ocas.md) analizzare ciò che avviene.</span><span class="sxs-lookup"><span data-stu-id="b6536-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="b6536-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b6536-137">Next steps</span></span>

- [<span data-ttu-id="b6536-138">Provare a utilizzare un'attività</span><span class="sxs-lookup"><span data-stu-id="b6536-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="b6536-139">Sospendere o il ripristino di un account utente</span><span class="sxs-lookup"><span data-stu-id="b6536-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="b6536-140">Visualizzare un elenco di [origini dati e registri di traffico Web](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b6536-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="b6536-141">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="b6536-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

