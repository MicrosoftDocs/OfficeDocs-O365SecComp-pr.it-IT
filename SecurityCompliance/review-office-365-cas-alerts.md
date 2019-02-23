---
title: Esaminare gli avvisi per intervenire in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Utilizzare la pagina avvisi in Office 365 cloud app Security per visualizzare potenziali problemi e intervenire. È possibile eliminare o risolvere gli avvisi e, se necessario, sospendere un account utente.
ms.openlocfilehash: 6c2f9788cb238e86abc347a3a118eb08fa84e971
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213166"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="81b61-104">Esaminare gli avvisi per intervenire in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="81b61-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="81b61-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="81b61-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="81b61-106">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="81b61-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="81b61-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="81b61-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="81b61-108">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="81b61-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="81b61-109">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="81b61-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="81b61-110">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="81b61-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="81b61-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="81b61-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="81b61-112">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="81b61-112">You are here!</span></span>  <br/> [<span data-ttu-id="81b61-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="81b61-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="81b61-114">È possibile utilizzare la pagina avvisi in Office 365 cloud app Security per visualizzare potenziali problemi e, se necessario, intervenire.</span><span class="sxs-lookup"><span data-stu-id="81b61-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81b61-p102">Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o un amministratore della sicurezza. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81b61-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="81b61-117">Come accedere alla pagina avvisi</span><span class="sxs-lookup"><span data-stu-id="81b61-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="81b61-118">Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.</span><span class="sxs-lookup"><span data-stu-id="81b61-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="81b61-119">Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.</span><span class="sxs-lookup"><span data-stu-id="81b61-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="81b61-120">![Nella pagina avvisi, è possibile visualizzare gli avvisi che sono stati attivati e tutte le azioni intraprese.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="81b61-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="81b61-121">Esaminare e gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="81b61-121">Review and handle alerts</span></span>

<span data-ttu-id="81b61-p103">Gli avvisi consentono di identificare le attività nell'ambiente cloud di Office 365 che potrebbe essere necessario esaminare ulteriormente. È inoltre possibile decidere di creare nuovi criteri o di modificare i criteri esistenti in base agli avvisi visualizzati. Ad esempio, se viene visualizzato un amministratore che accede da una posizione sconosciuta, è possibile decidere di impostare un criterio che impedisca agli amministratori di accedere a Office 365 da determinate posizioni.</span><span class="sxs-lookup"><span data-stu-id="81b61-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="81b61-125">È possibile filtrare gli avvisi per **categoria** o per **gravità** , in modo da poter gestire prima quelli più importanti.</span><span class="sxs-lookup"><span data-stu-id="81b61-125">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="81b61-p104">Per ogni avviso, esaminare cosa lo ha causato in modo da poter decidere quale azione eseguire. Per ulteriori informazioni su un avviso e per eseguire operazioni, ad esempio la risoluzione dell'avviso o la sospensione di un account utente, scegliere l'avviso per aprire una pagina dei dettagli. Nella pagina dei dettagli, è possibile esaminare il registro attività, gli account e gli utenti correlati all'avviso e intraprendere azioni come le seguenti:</span><span class="sxs-lookup"><span data-stu-id="81b61-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="81b61-p105">**Ignora** Se l'avviso è un falso positivo, respingerlo. Facoltativamente, è possibile aggiungere un commento per spiegare il motivo per cui è stato respinto.</span><span class="sxs-lookup"><span data-stu-id="81b61-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="81b61-p106">**Risoluzione degli avvisi** Se l'avviso è stato attivato da un'attività che si conosce non è una minaccia, risolverla. Facoltativamente, è possibile aggiungere un commento per spiegare perché è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="81b61-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="81b61-133">**Sospensione** Se si sospetta che gli accessi non autorizzati su un account, ad esempio un utente che effettua l'accesso da un altro paese quando si è a conoscenza che la persona è fisicamente presente in un ufficio locale, è possibile [sospendere l'account](suspend-or-restore-an-account-in-ocas.md) mentre si indaga su cosa succede.</span><span class="sxs-lookup"><span data-stu-id="81b61-133">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="81b61-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="81b61-134">Next steps</span></span>

- [<span data-ttu-id="81b61-135">Esaminare un'attività</span><span class="sxs-lookup"><span data-stu-id="81b61-135">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="81b61-136">Sospendere o ripristinare un account utente</span><span class="sxs-lookup"><span data-stu-id="81b61-136">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="81b61-137">Visualizzare un elenco di [log del traffico Web e origini dati](web-traffic-logs-and-data-sources-for-ocas.md) supportate</span><span class="sxs-lookup"><span data-stu-id="81b61-137">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="81b61-138">Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="81b61-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

