---
title: Gestione autorizzazioni gruppo di ruoli di amministratore in EOP
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 35f248bce26d28c8ab7465ff983629eb01db407b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150158"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="651ac-104">Gestire autorizzazioni gruppo di ruoli di amministratore in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="651ac-104">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="651ac-p102">In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="651ac-p102">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="651ac-107">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="651ac-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="651ac-108">Tempo stimato per il completamento: 5-10 minuti</span><span class="sxs-lookup"><span data-stu-id="651ac-108">Estimated time to complete: 5-10 minutes</span></span>
    
- <span data-ttu-id="651ac-p103">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Utenti, contatti e gruppi di ruoli" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="651ac-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="651ac-p104">Alcune autorizzazione in Office 365 eseguono il mapping delle autorizzazioni dei gruppi di ruoli di amministratore di EOP. Per ulteriori informazioni, vedere la colonna "Ruolo in Exchange Online" nella sezione "Quali servizi sono disponibili per le mie autorizzazioni di Office 365?" in [Assegnazione di ruoli di amministratore](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span><span class="sxs-lookup"><span data-stu-id="651ac-p104">Certain permissions in Office 365 map to EOP admin role group permissions. For more information, see the "Role in Exchange Online" column in the "Which services do my Office 365 permissions extend to?" section in [Assigning Admin Roles](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span></span>
    
- <span data-ttu-id="651ac-114">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="651ac-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="651ac-p105">Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="651ac-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="651ac-118">Operazione desiderata</span><span class="sxs-lookup"><span data-stu-id="651ac-118">What do you want to do?</span></span>

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="651ac-119">Aggiunta dei membri a gruppi di ruoli tramite EAC</span><span class="sxs-lookup"><span data-stu-id="651ac-119">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="651ac-120">Nell'interfaccia di amministrazione di Exchange, accedere a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli a cui si desidera aggiungere l'utente o gli utenti](../media/ITPro-EAC-EditIcon.gif), quindi fare clic su **modifica** ![icona modifica.</span><span class="sxs-lookup"><span data-stu-id="651ac-120">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="651ac-p106">In Membri, fare clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif). Viene visualizzata la finestra Seleziona membri.</span><span class="sxs-lookup"><span data-stu-id="651ac-p106">Under Members, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif). The Select Members window will appear.</span></span>
    
3. <span data-ttu-id="651ac-123">Cercare l'utente o gli utenti da aggiungere o selezionarli dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="651ac-123">Search for the user or users that you wish to add, or select them from the list.</span></span>
    
4. <span data-ttu-id="651ac-p107">Una volta selezionati gli utenti che si desidera aggiungere, fare clic su **Aggiungi**, quindi fare clic su **OK**. La finestra Seleziona membri si chiude.</span><span class="sxs-lookup"><span data-stu-id="651ac-p107">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>
    
5. <span data-ttu-id="651ac-p108">L'utente sarà stato aggiunto al riquadro **Membri**. Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="651ac-p108">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="651ac-128">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="651ac-128">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="651ac-129">Rimozione di membri da un gruppo di ruoli di amministratore tramite EAC</span><span class="sxs-lookup"><span data-stu-id="651ac-129">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="651ac-130">Nell'interfaccia di amministrazione di Exchange, accedere a **ruoli di amministratore** **delle autorizzazioni** \> , fare clic sul gruppo di ruoli da cui si desidera rimuovere un utente o utenti e](../media/ITPro-EAC-EditIcon.gif)quindi fare clic su **modifica** ![icona modifica.</span><span class="sxs-lookup"><span data-stu-id="651ac-130">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="651ac-131">In Membri, selezionare l'utente o gli utenti che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="651ac-131">Under Members, select the user or users that you want to remove and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="651ac-p109">Fare clic su **Salva** per salvare la modifica al gruppo di ruoli e tornare alla pagina **Ruoli amministratore**. Per verificare di aver rimosso correttamente l'utente dal gruppo di ruoli amministratore, assicurarsi che il membro non venga più visualizzato in Membri nel riquadro dei dettagli del gruppo di ruoli selezionato.</span><span class="sxs-lookup"><span data-stu-id="651ac-p109">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="651ac-134">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="651ac-134">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="651ac-135">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="651ac-135">For more information</span></span>

[<span data-ttu-id="651ac-136">Autorizzazioni di funzionalità in EOP</span><span class="sxs-lookup"><span data-stu-id="651ac-136">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
  

