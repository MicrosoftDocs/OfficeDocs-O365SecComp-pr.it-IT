---
title: Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: Informazioni su dove è possibile per visualizzare informazioni sui file dannosi rilevato in SharePoint, OneDrive o team e come eseguire l'azione necessaria tali file.
ms.openlocfilehash: e9a68c1cee1f2f3fb7fba148365449f0136fe637
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530783"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="ba418-103">Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba418-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="ba418-p101">[Degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) consente di proteggere l'organizzazione da file dannosi nelle raccolte documenti e siti del team. Quando un file dannoso viene rilevato, tale file è bloccato in modo che non possono aprire, copiare, spostare o condividerlo fino a quando non vengono intraprese azioni ulteriormente dal team di protezione dell'organizzazione. In questo articolo per informazioni su come visualizzare informazioni sui file rilevati e le azioni da intraprendere.</span><span class="sxs-lookup"><span data-stu-id="ba418-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ba418-107">Per eseguire le attività descritte in questo articolo, è necessario disporre di volte necessario [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba418-107">In order to perform the tasks described in this article, you must have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="ba418-108">Visualizzare i report con informazioni sul file rilevati</span><span class="sxs-lookup"><span data-stu-id="ba418-108">View reports with information about detected files</span></span>

<span data-ttu-id="ba418-109">Per visualizzare lo stato e informazioni dettagliate sui file che sono stati rilevati da strumenti di analisi di Office 365, è possibile utilizzare la relazione sullo stato di protezione rischio.</span><span class="sxs-lookup"><span data-stu-id="ba418-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat protection status report.</span></span>
  
1. <span data-ttu-id="ba418-110">In Office 365 Security &amp; centro conformità, selezionare **rapporti** \> **Dashboard** \> **lo stato di protezione di rischio**.</span><span class="sxs-lookup"><span data-stu-id="ba418-110">In the Office 365 Security &amp; Compliance Center, choose **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
    
2. <span data-ttu-id="ba418-111">Nell'angolo superiore destro del report, scegliere **Visualizza dettagli tabella**.</span><span class="sxs-lookup"><span data-stu-id="ba418-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="ba418-112">Visualizzare l'elenco dei file che sono stati rilevati nel report.</span><span class="sxs-lookup"><span data-stu-id="ba418-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="ba418-113">Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluse le azioni intraprese, il nome del file, il percorso del file e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="ba418-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="ba418-114">Fare clic sulla scheda **Analisi avanzate** per visualizzare informazioni, ad esempio osservato comportamento e analisi dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="ba418-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
    
> [!TIP]
> <span data-ttu-id="ba418-115">Per ulteriori informazioni sui rapporti disponibili, vedere [visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ba418-115">To learn more about available reports, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="ba418-116">Visualizza ed esegue azioni sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="ba418-116">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="ba418-117">In Office 365 Security &amp; centro conformità, scegliere **gestione rischio** \> **revisione** \> **quarantena**.</span><span class="sxs-lookup"><span data-stu-id="ba418-117">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="ba418-118">Nell'angolo superiore sinistro, modificare il filtro di **posta elettronica** al **contenuto**.</span><span class="sxs-lookup"><span data-stu-id="ba418-118">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="ba418-119">Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluso l'URL del file.</span><span class="sxs-lookup"><span data-stu-id="ba418-119">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="ba418-120">Scegliere un'azione disponibile.</span><span class="sxs-lookup"><span data-stu-id="ba418-120">Choose an available action.</span></span>
    
  - <span data-ttu-id="ba418-121">Scegliere **versione &amp; report** per sbloccare il file.</span><span class="sxs-lookup"><span data-stu-id="ba418-121">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="ba418-122">Selezionare **Invia segnalazione a Microsoft** per segnalare il file come falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba418-122">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="ba418-123">Scegliere **Download file** per analizzare ulteriormente il file.</span><span class="sxs-lookup"><span data-stu-id="ba418-123">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="ba418-p102">Scegliere **Elimina** per rimuovere il file dall'elenco di elementi in quarantena. Se si sceglie questa opzione, è necessario eliminare anche il file dalla libreria rispettivo in SharePoint Online, OneDrive per Business o Microsoft Teams. Questa opzione non sbloccare un file vengano aperti o condivisa.</span><span class="sxs-lookup"><span data-stu-id="ba418-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="ba418-127">Scegliere **Chiudi** per chiudere i dettagli per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="ba418-127">Choose **Close** to close the details for a selected item.</span></span> 
    
> [!TIP]
> <span data-ttu-id="ba418-128">Per ulteriori informazioni sulla gestione dei file in quarantena, vedere [Manage quarantined messaggi e file con privilegi di amministratore in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ba418-128">To learn more about managing quarantined files, see [Manage quarantined messages and files as an administrator in Office 365](manage-quarantined-messages-and-files.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="ba418-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ba418-129">Related topics</span></span>

[<span data-ttu-id="ba418-130">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ba418-130">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="ba418-131">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="ba418-131">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="ba418-132">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="ba418-132">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

