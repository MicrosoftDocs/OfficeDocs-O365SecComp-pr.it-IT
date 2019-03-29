---
title: Sospendere o ripristinare un account utente in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 cloud app Security, le azioni di governance che è possibile intraprendere sono la sospensione o la sospensione di un account utente. '
ms.openlocfilehash: 10da1385f850fadf077b4e3f9e3a00e9e4629fdd
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862448"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="f0c39-103">Sospendere o ripristinare un account utente in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f0c39-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="f0c39-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f0c39-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="f0c39-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f0c39-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="f0c39-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="f0c39-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="f0c39-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="f0c39-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="f0c39-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="f0c39-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="f0c39-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="f0c39-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="f0c39-110">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="f0c39-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="f0c39-111">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="f0c39-111">You are here!</span></span>  <br/> [<span data-ttu-id="f0c39-112">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f0c39-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="f0c39-113">Si supponga di ricevere un avviso per il quale uno degli account utente dell'organizzazione per Office 365 è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="f0c39-113">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised.</span></span> <span data-ttu-id="f0c39-114">In alternativa, si supponga di aver ricevuto un avviso che indica che è presente un errore in un account utente.</span><span class="sxs-lookup"><span data-stu-id="f0c39-114">Or, suppose that you've received an alert that indicates something is wrong with a user account.</span></span> <span data-ttu-id="f0c39-115">Con Office 365 cloud app Security, è possibile sospendere un account utente e successivamente ripristinarlo dopo aver esaminato gli avvisi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="f0c39-115">With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0c39-116">Office 365 cloud app Security è disponibile in Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="f0c39-116">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="f0c39-117">Se l'organizzazione utilizza un altro abbonamento a Office 365 Enterprise, Office 365 cloud app Security può essere acquistato come componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f0c39-117">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="f0c39-118">(come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **aggiungi abbonamenti**). Per ulteriori informazioni, vedere [office 365 Platform Service Description: office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="f0c39-118">(As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="f0c39-119">Per sospendere un account utente in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="f0c39-119">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="f0c39-120">Quando si sospende un account utente, si impedisce all'utente di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f0c39-120">When you suspend a user account, you prevent the user from signing in again.</span></span> <span data-ttu-id="f0c39-121">Lo stesso vale per la modifica dell'account utente direttamente in Office 365 per impostare lo stato di accesso per l' **accesso bloccato**.</span><span class="sxs-lookup"><span data-stu-id="f0c39-121">It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0c39-122">Se si blocca un utente dall'accesso a Office 365, sospendendo o modificando lo stato di accesso, tenere presente che può richiedere un'ora o più per avere effetto su tutti i dispositivi e i client dell'utente ([modificare o modificare un utente in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span><span class="sxs-lookup"><span data-stu-id="f0c39-122">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)).</span></span> <span data-ttu-id="f0c39-123">Se l'utente ha eseguito l'accesso a Office 365, il blocco avrà effetto ogni volta che Office 365 richiede la possibilità di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f0c39-123">If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="f0c39-124">In qualità di amministratore [globale o amministratore della sicurezza](permissions-in-the-security-and-compliance-center.md), [https://protection.office.com](https://protection.office.com) passare a e accedere con l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="f0c39-124">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> <span data-ttu-id="f0c39-125">Questo porta al centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="f0c39-125">(This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="f0c39-126">Nel centro sicurezza &amp; e conformità, scegliere **avvisi** \> **Gestione avvisi avanzati**.</span><span class="sxs-lookup"><span data-stu-id="f0c39-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="f0c39-127">Scegliere **Vai a Office 365 cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="f0c39-127">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="f0c39-128">![Nel centro sicurezza &amp; e conformità, scegliere Gestisci avvisi avanzati per accedere a Office 365 cloud app Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="f0c39-128">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="f0c39-129">Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.</span><span class="sxs-lookup"><span data-stu-id="f0c39-129">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="f0c39-130">Nella colonna **avviso** fare doppio clic su un avviso relativo a un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="f0c39-130">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="f0c39-131">In **account**, nella colonna **stato** scegliere ![l'icona](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> impostazioni impostazioni **Sospendi utente**.</span><span class="sxs-lookup"><span data-stu-id="f0c39-131">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="f0c39-132">Per ripristinare un account utente</span><span class="sxs-lookup"><span data-stu-id="f0c39-132">To restore a user account</span></span>

<span data-ttu-id="f0c39-133">Vedere [ripristinare un utente in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="f0c39-133">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="f0c39-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f0c39-134">Next steps</span></span>

- [<span data-ttu-id="f0c39-135">Esaminare gli avvisi per intervenire in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f0c39-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="f0c39-136">Gestire le app di OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f0c39-136">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="f0c39-137">Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="f0c39-137">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

