---
title: Sospendere o ripristinare un account utente in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 Cloud App protezione, è possibile eseguire le operazioni di governance sono di sospendere o riprendere un account utente. '
ms.openlocfilehash: 09d6ae870aa1a6b0a619ccf20f8cc19b392e23a8
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014848"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="2efd0-103">Sospendere o ripristinare un account utente in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2efd0-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="2efd0-104">Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2efd0-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="2efd0-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2efd0-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="2efd0-106">Pianificazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2efd0-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="2efd0-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="2efd0-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="2efd0-108">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2efd0-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="2efd0-109">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="2efd0-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="2efd0-110">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="2efd0-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="2efd0-111">Avviare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="2efd0-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="2efd0-112">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="2efd0-112">You are here!</span></span>  <br/> [<span data-ttu-id="2efd0-113">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2efd0-113">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="2efd0-p101">Si supponga che si riceve un avviso che uno degli account utente dell'organizzazione per Office 365 è stato danneggiato. In alternativa, si supponga che è stato ricevuto un avviso indicante che si verificano problemi con un account utente. Con Office 365 Cloud App protezione, è possibile sospendere un account utente e ripristinarla successivamente dopo che sono state analizzate avvisi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="2efd0-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2efd0-p102">Protezione di Office 365 Cloud App è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, protezione di Office 365 Cloud App può essere acquistata come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="2efd0-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="2efd0-120">Per sospendere un account utente in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2efd0-120">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="2efd0-p103">Quando si sospende un account utente, si impedisce all'utente di effettuare nuovamente l'accesso. È identico modifica l'account utente direttamente in Office 365 per impostare lo stato di accesso di **accesso bloccato**.</span><span class="sxs-lookup"><span data-stu-id="2efd0-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2efd0-p104">Se si blocca un utente di accedere a Office 365, sospendendo li o si modifica lo stato di accesso, tenere presente che può richiedere un'ora o richiesto per rendere effettive in tutti i dispositivi e client ([modificare o cambiare un utente in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) dell'utente. Se l'utente ha eseguito l'accesso a Office 365, il blocco avrà effetto ogni volta che Office 365 richiede l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2efd0-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="2efd0-p105">Come [amministratore globale o amministratore di protezione](permissions-in-the-security-and-compliance-center.md), passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. (Si passa alla sicurezza &amp; centro conformità.)</span><span class="sxs-lookup"><span data-stu-id="2efd0-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="2efd0-127">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="2efd0-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="2efd0-128">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="2efd0-128">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="2efd0-129">![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="2efd0-129">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="2efd0-130">Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.</span><span class="sxs-lookup"><span data-stu-id="2efd0-130">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="2efd0-131">Nella colonna **avviso** fare doppio clic su un avviso che fa riferimento a un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="2efd0-131">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="2efd0-132">Nella casella **account**, nella colonna **stato** , scegliere impostazioni ![icona impostazioni](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **utente Suspend**.</span><span class="sxs-lookup"><span data-stu-id="2efd0-132">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="2efd0-133">Per ripristinare un account utente</span><span class="sxs-lookup"><span data-stu-id="2efd0-133">To restore a user account</span></span>

<span data-ttu-id="2efd0-134">Vedere [ripristino di un utente in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="2efd0-134">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="2efd0-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2efd0-135">Next steps</span></span>

- [<span data-ttu-id="2efd0-136">Esaminare gli avvisi per intervenire in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2efd0-136">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="2efd0-137">Gestire le app di OAuth con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2efd0-137">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="2efd0-138">Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="2efd0-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

