---
title: Rilevare un'attività in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: "Con Office 365 Cloud App protezione, è possibile visualizzare quanto avviene nell'ambiente Office 365 per informazioni istruttoria attività e gli account. "
ms.openlocfilehash: 03db572ebddbdf27371f8e6fd2f0cdd91c14a12f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530390"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="48e99-103">Rilevare un'attività in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48e99-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="48e99-104">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="48e99-104">****Evaluation** \>**</span></span>|<span data-ttu-id="48e99-105">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="48e99-105">****Planning** \>**</span></span>|<span data-ttu-id="48e99-106">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="48e99-106">****Deployment** \>**</span></span>|<span data-ttu-id="48e99-107">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="48e99-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="48e99-108">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="48e99-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="48e99-109">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="48e99-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="48e99-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="48e99-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="48e99-111">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="48e99-111">You are here!</span></span>  <br/> [<span data-ttu-id="48e99-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="48e99-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="48e99-p101">Office 365 Cloud App sicurezza e l'utilizzo del [Registro di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md). Con Office 365 Cloud App protezione, come un amministratore globale o sicurezza, è possibile utilizzare la pagina del Registro di attività per visualizzare i potenziali problemi in modo l'organizzazione utilizza Office 365.</span><span class="sxs-lookup"><span data-stu-id="48e99-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="48e99-115">Come ottenere la pagina di registro delle attività</span><span class="sxs-lookup"><span data-stu-id="48e99-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="48e99-p102">Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="48e99-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="48e99-118">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="48e99-118">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="48e99-119">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="48e99-119">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="48e99-121">Nella barra di spostamento nella parte superiore dello schermo, scegliere **indagare** \> **registro attività**.</span><span class="sxs-lookup"><span data-stu-id="48e99-121">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span>
    
    ![Nel portale di accesso client di Office 365, selezionare indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="48e99-123">Rivedere e analizzare le attività</span><span class="sxs-lookup"><span data-stu-id="48e99-123">Review and investigate activities</span></span>

<span data-ttu-id="48e99-p103">Nella pagina registro attività, è possibile visualizzare un elenco di varie attività che sono in corso all'interno dell'organizzazione con Office 365. È possibile utilizzare filtri nella parte superiore dello schermo per evidenziare un tipo specifico di attività o un utente specifico. Ad esempio, nell'immagine seguente vengono visualizzate informazioni sulla modifica della password dell'account di un'organizzazione Office 365 admin:</span><span class="sxs-lookup"><span data-stu-id="48e99-p103">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![In Office 365 Cloud App sicurezza scegliere indagare \> registro attività.](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="48e99-p104">Come si esamina ogni elemento nel registro attività, è possibile fare clic sui puntini di sospensione per trovare altre attività correlate. Ad esempio, è possibile visualizzare altre attività dello stesso tipo, dallo stesso indirizzo IP o dalla stesso paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="48e99-p104">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="48e99-p105">È possibile visualizzare informazioni su molti altri tipi di attività, troppo. Ad esempio, ecco alcune delle attività che è possibile visualizzare nel registro attività:</span><span class="sxs-lookup"><span data-stu-id="48e99-p105">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="48e99-132">Aggiungere o rimuovere dai gruppi di membri</span><span class="sxs-lookup"><span data-stu-id="48e99-132">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="48e99-133">Modifiche di licenze utente</span><span class="sxs-lookup"><span data-stu-id="48e99-133">Changes in user licenses</span></span>
    
- <span data-ttu-id="48e99-134">File o cartelle condivise internamente o esternamente</span><span class="sxs-lookup"><span data-stu-id="48e99-134">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="48e99-135">Siti creati o eliminati o raccolte siti</span><span class="sxs-lookup"><span data-stu-id="48e99-135">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="48e99-136">Le regole di inoltro di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="48e99-136">Email forwarding rules</span></span>
    
<span data-ttu-id="48e99-137">Utilizzare la pagina di attività del Registro di acquisire familiarità con modalità di utilizzo personale della tua organizzazione Office 365 e sugli aspetti dei problemi potrebbe dover durante il processo.</span><span class="sxs-lookup"><span data-stu-id="48e99-137">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="48e99-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="48e99-138">Next steps</span></span>

- [<span data-ttu-id="48e99-139">Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48e99-139">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="48e99-140">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="48e99-140">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

