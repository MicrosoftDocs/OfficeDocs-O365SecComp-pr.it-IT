---
title: Concedere agli utenti l'accesso a Office 365 Security &amp; centro conformità
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni in Office 365 Security &amp; centro conformità prima che gestiscono le relative funzionalità di conformità o sicurezza.
ms.openlocfilehash: 5055c64d914e15a6570c339ade48bb8f7e802ea7
ms.sourcegitcommit: a56fa2e184a2662fd8a7881ccea0891e9a26d497
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "27221067"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="64e02-103">Concedere agli utenti l'accesso a Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="64e02-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="64e02-p101">Gli utenti devono disporre delle autorizzazioni in Office 365 Security &amp; centro conformità prima che gestiscono le relative funzionalità di conformità o sicurezza. Un amministratore globale di Office 365 o membro del gruppo di ruoli OrganizationManagement nella protezione &amp; centro conformità, è possibile fornire tali autorizzazioni agli utenti. Solo gli utenti saranno in grado di gestire le funzionalità di conformità o sicurezza dispongano di accesso a.</span><span class="sxs-lookup"><span data-stu-id="64e02-p101">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features. As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users. Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="64e02-107">Per ulteriori informazioni sulle autorizzazioni diverse è possibile fornire agli utenti nella protezione &amp; centro conformità, check-out [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="64e02-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="64e02-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="64e02-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="64e02-109">È necessario essere un amministratore globale di Office 365 o un membro del gruppo di ruoli OrganizationManagement nella protezione &amp; centro conformità, per completare la procedura descritta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="64e02-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="64e02-110">Gruppi di ruoli per la sicurezza &amp; centro conformità potrebbe essere nomi simili per i gruppi di ruoli in Exchange Online, ma non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="64e02-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="64e02-111">Appartenenze ai gruppi di ruolo non sono condivise tra Exchange Online e la sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="64e02-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="64e02-112">Utilizzare l'interfaccia di amministrazione di Office 365 per assegnare un altro utente l'accesso alla protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="64e02-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="64e02-113">[Accedere a Office 365 e accedere all'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span><span class="sxs-lookup"><span data-stu-id="64e02-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="64e02-114">Nell'interfaccia di amministrazione di Office 365, aprire **Admin Center** e quindi fare clic su **protezione &amp; conformità**.</span><span class="sxs-lookup"><span data-stu-id="64e02-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="64e02-115">In sicurezza &amp; centro conformità, accedere alle **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="64e02-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="64e02-116">Nell'elenco scegliere il gruppo di ruoli che si desidera aggiungere l'utente e fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="64e02-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="64e02-117">Nella pagina delle proprietà del gruppo di ruoli in **membri**, fare clic su **Aggiungi**![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) e selezionare il nome dell'utente (o gli utenti) si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="64e02-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="64e02-118">Se sono state selezionate tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su \*\*aggiungere-\> \*\* e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="64e02-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="64e02-119">Fare clic su **Salva** per salvare le modifiche al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="64e02-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="64e02-120">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="64e02-120">How do you know this worked?</span></span>

1. <span data-ttu-id="64e02-121">In sicurezza &amp; centro conformità, accedere alle **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="64e02-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="64e02-122">Nell'elenco, selezionare il gruppo di ruoli per visualizzare i membri.</span><span class="sxs-lookup"><span data-stu-id="64e02-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="64e02-123">A destra e i dettagli di gruppo di ruolo, è possibile visualizzare i membri del gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="64e02-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="64e02-124">Utilizzare PowerShell per assegnare un altro utente l'accesso alla protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="64e02-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="64e02-125">[Connettersi a PowerShell centro conformità e sicurezza di Office 365](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="64e02-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="64e02-126">Usa il comando **Add-RoleGroupMember** per aggiungere un utente al ruolo Gestione organizzazione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64e02-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="64e02-127">**Parametri**</span><span class="sxs-lookup"><span data-stu-id="64e02-127">**Parameters**</span></span>
  
- <span data-ttu-id="64e02-128">_-Identity_ è il gruppo di ruoli al quale aggiungere un membro.</span><span class="sxs-lookup"><span data-stu-id="64e02-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- <span data-ttu-id="64e02-p102">_Membro_ è la cassetta postale, gruppo di protezione universale (USG) o computer da aggiungere al gruppo di ruoli. È possibile specificare un solo membro alla volta.</span><span class="sxs-lookup"><span data-stu-id="64e02-p102">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group. You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="64e02-131">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span><span class="sxs-lookup"><span data-stu-id="64e02-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="64e02-132">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="64e02-132">How do you know this worked?</span></span>

<span data-ttu-id="64e02-133">Per verificare che è stato assegnato agli utenti l'accesso per la protezione &amp; centro conformità, utilizzare il cmdlet **Get-RoleGroupMember** per visualizzare i membri nel gruppo di ruoli Gestione organizzazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64e02-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="64e02-134">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span><span class="sxs-lookup"><span data-stu-id="64e02-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

