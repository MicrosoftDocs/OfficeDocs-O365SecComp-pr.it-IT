---
title: Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection: M365-security-compliance
description: Informazioni su come attivare degli strumenti di analisi di SharePoint, OneDrive e team, nonché su come impostare gli avvisi per file rilevati.
ms.openlocfilehash: 8c63110baf391fd727e296f34361047b4b67b0cb
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995337"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ee563-103">Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi</span><span class="sxs-lookup"><span data-stu-id="ee563-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ee563-p101">[Degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md) consente di proteggere l'organizzazione da inavvertitamente condivisione file dannosi. Quando un file dannoso viene rilevato, tale file è bloccato in modo che non possono aprire, copiare, spostare o condividerlo fino a quando non vengono intraprese azioni ulteriormente dal team di protezione dell'organizzazione. Leggere questo articolo per attivare degli strumenti di analisi di SharePoint, OneDrive e team, impostare gli avvisi per essere informati file rilevati e intraprendere le azioni successive.</span><span class="sxs-lookup"><span data-stu-id="ee563-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="ee563-107">Per definire o modificare i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="ee563-107">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="ee563-108">Ruolo</span><span class="sxs-lookup"><span data-stu-id="ee563-108">Role</span></span>  |<span data-ttu-id="ee563-109">Modalità assegnato</span><span class="sxs-lookup"><span data-stu-id="ee563-109">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="ee563-110">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="ee563-110">Office 365 Global Administrator</span></span> |<span data-ttu-id="ee563-p102">La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="ee563-p102">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="ee563-113">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee563-113">Security Administrator</span></span> |<span data-ttu-id="ee563-114">Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="ee563-114">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="ee563-115">Exchange Online Organization Management</span><span class="sxs-lookup"><span data-stu-id="ee563-115">Exchange Online Organization Management</span></span> |<span data-ttu-id="ee563-116">Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="ee563-116">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="ee563-117">oppure</span><span class="sxs-lookup"><span data-stu-id="ee563-117">or</span></span> <br>  <span data-ttu-id="ee563-118">Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="ee563-118">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ee563-119">Attivare ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee563-119">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ee563-p103">**Prima di iniziare questa procedura, verificare che la registrazione di controllo è stata abilitata per l'ambiente Office 365**. Questo viene in genere eseguito da un utente che disponga del ruolo registri di controllo assegnato in Exchange Online. Per ulteriori informazioni, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-p103">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="ee563-123">Accedere a [https://protection.office.com](https://protection.office.com)e accedere con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="ee563-123">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ee563-124">In Office 365 Security &amp; centro conformità, nel riquadro di spostamento a sinistra, in **gestione rischio**, scegliere **criterio** \> **Gli allegati sicuri**.</span><span class="sxs-lookup"><span data-stu-id="ee563-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="ee563-125">![In sicurezza &amp; centro conformità, scegliere gestione rischio \> criteri](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="ee563-125">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="ee563-126">Selezionare **attiva degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ee563-126">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="ee563-127">![Attivare la protezione avanzata minaccia per SharePoint Online, OneDrive for Business e team di Microsoft](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="ee563-127">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="ee563-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ee563-128">Click **Save**.</span></span>
    
5. <span data-ttu-id="ee563-129">Esaminare (e, nel modo appropriato, modifica) [criteri gli allegati sicuri](set-up-atp-safe-attachments-policies.md) e [collegamenti sicuri criteri](set-up-atp-safe-links-policies.md)dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee563-129">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="ee563-130">(Scelta consigliata) Come un amministratore globale o un amministratore di SharePoint Online, eseguire il cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true*.</span><span class="sxs-lookup"><span data-stu-id="ee563-130">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="ee563-p104">L'impostazione del parametro a blocchi *true* tutte le azioni (ad eccezione di Elimina) per rilevato file. Utenti non possono aprire, spostare, copiare o condividere file rilevati.</span><span class="sxs-lookup"><span data-stu-id="ee563-p104">Setting the parameter to *true* blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="ee563-p105">L'impostazione del parametro su *false* blocca tutte le azioni ad eccezione di eliminazione e Download. Persone possono scegliere di accettare il rischio e scaricare un file rilevato.</span><span class="sxs-lookup"><span data-stu-id="ee563-p105">Setting the parameter to *false* blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="ee563-135">Consentire fino a 30 minuti per le modifiche apportate da distribuire a tutti i centri dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee563-135">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="ee563-136">(Scelta consigliata) Procedere per impostare gli avvisi per file rilevati.</span><span class="sxs-lookup"><span data-stu-id="ee563-136">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="ee563-137">Per ulteriori informazioni sull'utilizzo di PowerShell con Office 365, vedere [gestire Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ee563-137">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="ee563-138">Per ulteriori informazioni sull'esperienza utente quando viene rilevato un file come dannose, vedere [cosa fare quando un file dannoso viene rilevato in SharePoint Online, OneDrive o team di Microsoft](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="ee563-138">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="ee563-139">Configurare gli avvisi per file rilevati</span><span class="sxs-lookup"><span data-stu-id="ee563-139">Set up alerts for detected files</span></span>

<span data-ttu-id="ee563-140">Per ricevere una notifica quando un file in SharePoint Online, OneDrive per Business o Microsoft Teams è stato identificato come moleste, è possibile impostare un avviso.</span><span class="sxs-lookup"><span data-stu-id="ee563-140">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="ee563-141">Nella [protezione di Office 365 &amp; centro conformità](https://protection.office.com), scegliere **avvisi** \> **Gestisci avvisi**.</span><span class="sxs-lookup"><span data-stu-id="ee563-141">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="ee563-142">Scegliere **nuovo criterio di avviso**.</span><span class="sxs-lookup"><span data-stu-id="ee563-142">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="ee563-p106">Specificare un nome per l'avviso. Ad esempio, è possibile digitare file dannosi nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="ee563-p106">Specify a name for the alert. For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="ee563-p107">Digitare una descrizione dell'avviso. Ad esempio, è possibile digitare notifica all'admins quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee563-p107">Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="ee563-147">Nella sezione **Invia avviso se...** , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee563-147">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="ee563-p108">r. nell'elenco **delle attività** scegliere **malware rilevate nel file**.</span><span class="sxs-lookup"><span data-stu-id="ee563-p108">a. In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="ee563-p109">b. lasciare vuoto il campo **gli utenti** .</span><span class="sxs-lookup"><span data-stu-id="ee563-p109">b. Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="ee563-152">Nella sezione **Invia avviso a...** selezionare uno o più gli amministratori globali, gli amministratori di protezione o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="ee563-152">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="ee563-153">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ee563-153">Click **Save**.</span></span>
    
<span data-ttu-id="ee563-154">Per ulteriori informazioni sugli avvisi, vedere [consente di creare avvisi attività in Office 365 Security &amp; centro conformità](create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-154">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ee563-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ee563-155">Next steps</span></span>

1. [<span data-ttu-id="ee563-156">Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee563-156">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="ee563-157">Gestire i messaggi in quarantena e i file in qualità di amministratore in Office 365</span><span class="sxs-lookup"><span data-stu-id="ee563-157">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  

