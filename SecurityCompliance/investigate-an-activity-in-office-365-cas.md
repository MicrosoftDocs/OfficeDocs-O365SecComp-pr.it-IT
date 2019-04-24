---
title: Analizzare un'attività in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: "Con Office 365 cloud app Security, è possibile vedere cosa succede nell'ambiente di Office 365 analizzando e analizzando le attività e gli account. "
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254836"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="d1e48-103">Analizzare un'attività in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d1e48-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d1e48-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d1e48-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="d1e48-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d1e48-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="d1e48-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="d1e48-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="d1e48-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d1e48-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d1e48-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="d1e48-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d1e48-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="d1e48-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d1e48-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d1e48-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d1e48-111">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="d1e48-111">You are here!</span></span>  <br/> [<span data-ttu-id="d1e48-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d1e48-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="d1e48-113">Office 365 cloud app Security è compatibile con il [Registro di controllo di office 365](detailed-properties-in-the-office-365-audit-log.md).</span><span class="sxs-lookup"><span data-stu-id="d1e48-113">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span> <span data-ttu-id="d1e48-114">Con Office 365 cloud app Security, in qualità di amministratore globale o amministratore della sicurezza, è possibile utilizzare la pagina del registro attività per visualizzare i potenziali problemi relativi all'utilizzo di Office 365 da parte dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1e48-114">With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="d1e48-115">Come accedere alla pagina del registro attività</span><span class="sxs-lookup"><span data-stu-id="d1e48-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="d1e48-116">Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.</span><span class="sxs-lookup"><span data-stu-id="d1e48-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="d1e48-117">Nella barra di spostamento nella parte superiore dello schermo scegliere **indaga** \> **Registro attività**.</span><span class="sxs-lookup"><span data-stu-id="d1e48-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="d1e48-118">![Nel portale O365 CAS, scegliere indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="d1e48-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="d1e48-119">Esaminare ed esaminare le attività</span><span class="sxs-lookup"><span data-stu-id="d1e48-119">Review and investigate activities</span></span>

<span data-ttu-id="d1e48-120">Nella pagina Registro attività, è possibile visualizzare un elenco di varie attività che si svolgono all'interno dell'organizzazione utilizzando Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1e48-120">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365.</span></span> <span data-ttu-id="d1e48-121">È possibile utilizzare filtri nella parte superiore dello schermo per concentrarsi su un tipo specifico di attività o su un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="d1e48-121">You can use filters across the top of the screen to focus on a specific type of activity or a specific user.</span></span> <span data-ttu-id="d1e48-122">Ad esempio, nell'immagine seguente vengono visualizzate le informazioni sulla modifica della password dell'account di amministratore di Office 365 dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="d1e48-122">For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![In Office 365 cloud app Security fare clic su \> indaga registro attività.](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="d1e48-124">Quando si esamina ogni elemento del registro attività, è possibile fare clic sui puntini di lavoro per individuare altre attività correlate.</span><span class="sxs-lookup"><span data-stu-id="d1e48-124">As you look at each item in the Activity log, you can click the ellipses to find other related activities.</span></span> <span data-ttu-id="d1e48-125">Ad esempio, è possibile visualizzare altre attività dello stesso tipo, dallo stesso indirizzo IP o dallo stesso paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="d1e48-125">For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="d1e48-126">È anche possibile visualizzare informazioni su molti altri tipi di attività.</span><span class="sxs-lookup"><span data-stu-id="d1e48-126">You can view information about many other kinds of activities, too.</span></span> <span data-ttu-id="d1e48-127">Ad esempio, di seguito sono riportate alcune delle attività che è possibile visualizzare nel registro attività:</span><span class="sxs-lookup"><span data-stu-id="d1e48-127">For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="d1e48-128">Membri aggiunti o rimossi da gruppi</span><span class="sxs-lookup"><span data-stu-id="d1e48-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="d1e48-129">Modifiche apPortate alle licenze utente</span><span class="sxs-lookup"><span data-stu-id="d1e48-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="d1e48-130">File o cartelle condivisi internamente o esternamente</span><span class="sxs-lookup"><span data-stu-id="d1e48-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="d1e48-131">Siti creati o eliminati o raccolte siti</span><span class="sxs-lookup"><span data-stu-id="d1e48-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="d1e48-132">Regole di inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d1e48-132">Email forwarding rules</span></span>
    
<span data-ttu-id="d1e48-133">Utilizzare la pagina del registro attività per conoscere in che modo gli utenti dell'organizzazione utilizzano Office 365 e quali problemi potrebbero avere lungo la strada.</span><span class="sxs-lookup"><span data-stu-id="d1e48-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d1e48-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d1e48-134">Next steps</span></span>

- [<span data-ttu-id="d1e48-135">Esaminare gli avvisi per intervenire in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d1e48-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="d1e48-136">Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d1e48-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

