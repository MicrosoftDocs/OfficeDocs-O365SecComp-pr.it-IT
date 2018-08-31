---
title: Office 365 ATP per SharePoint, OneDrive e Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: Estendere la protezione di Office 365 avanzate minaccia per i file in SharePoint Online, OneDrive for Business e Teams Microsoft per consentire la collaborazione più sicura per l'organizzazione.
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531223"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6fcd3-103">Office 365 ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fcd3-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6fcd3-p101">Utenti con regolarità condividere file e collaborare con SharePoint, OneDrive e Teams Microsoft. Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può collaborare in modo più sicuro. Degli strumenti di analisi consente di rilevare e bloccare i file che vengono identificati come dannose in siti del team e raccolte documenti. Leggere questo articolo per ottenere una panoramica degli strumenti di analisi di SharePoint Online, OneDrive for Business e Teams Microsoft e quindi eseguire i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p101">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries. Read this article to get an overview of ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams, and then take your next steps.</span></span> 
  
> [!TIP]
> <span data-ttu-id="6fcd3-p102">Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale di Office 365 o un amministratore di sicurezza. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p102">In order to perform the tasks described in this article, you must be an Office 365 global administrator or a security administrator. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-it-works"></a><span data-ttu-id="6fcd3-110">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="6fcd3-110">How it works</span></span>

<span data-ttu-id="6fcd3-p103">Quando un file in SharePoint Online, OneDrive for Business e Microsoft Teams è stato identificato come dannose, degli strumenti di analisi si integra direttamente con gli archivi di file per bloccare il file. Nell'immagine seguente viene illustrato un esempio di un file dannoso rilevato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p103">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="6fcd3-113">[![Cattura di schermata del file in OneDrive for Business con uno rilevato come dannosi](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="6fcd3-113">[![Screenshot of files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="6fcd3-p104">Anche se il file bloccato sia ancora elencato nella raccolta documenti e applicazioni web di, portatile o desktop, file bloccati non può essere aperti, copiato, spostato o condivisi. Persone, comunque possibile eliminare un file bloccati. Ecco un esempio di quali che aspetto nel dispositivo mobile dell'utente:</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p104">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="6fcd3-117">[![Cattura di schermata dell'eliminazione di un file bloccati di OneDrive for Business da app per dispositivi mobili OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="6fcd3-117">[![Screenshot of deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="6fcd3-p105">A seconda della configurazione di Office 365, gli utenti possono o potrebbero non avere la possibilità di scaricare un file bloccato. Di seguito viene scaricato un file bloccato aspetto sul dispositivo mobile dell'utente:</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p105">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file. Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="6fcd3-120">[![Cattura di schermata di scaricare un file bloccato in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="6fcd3-120">[![Screenshot of downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="6fcd3-121">Per ulteriori informazioni, vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team di Microsoft](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-121">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
### <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="6fcd3-122">Tenere presente quanto segue</span><span class="sxs-lookup"><span data-stu-id="6fcd3-122">Keep the following points in mind</span></span>

- <span data-ttu-id="6fcd3-p106">Degli strumenti di analisi non verrà verificata ogni singolo file in SharePoint Online, OneDrive per Business o Microsoft Teams. Questo è per impostazione predefinita. I file vengono analizzati in modo asincrono, un processo che utilizza gli eventi di attività di condivisione e guest insieme euristica smart e segnali minaccia per identificare i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p106">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>
    
- <span data-ttu-id="6fcd3-126">File che vengono identificati come dannoso in SharePoint Online, OneDrive for Business o Microsoft Teams verrà visualizzate nei [rapporti di protezione di Office 365 avanzate rischio](view-reports-for-atp.md) e rischio Esplora (parte di [Business Intelligence di Office 365 rischio](office-365-ti.md)).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-126">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in Threat Explorer (part of [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>
    
- <span data-ttu-id="6fcd3-p107">Degli strumenti di analisi fa parte della strategia dell'organizzazione complessiva threat protection, che include la protezione da posta indesiderata e protezione anti-malware, nonché collegamenti sicuri e gli allegati sicuri. Per ulteriori informazioni, vedere [protezione contro le minacce in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p107">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="6fcd3-p108">Un amministratore di SharePoint Online è possibile determinare se si desidera consentire agli utenti di scaricare file che vengono rilevati come dannose. In tal caso, l'esecuzione del cmdlet Set-SPOTenant PowerShell utilizzando il parametro DisallowInfectedFileDownload (vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team Microsoft che](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p108">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="6fcd3-131">(Nuovo)! Quarantena in strumenti di analisi di SharePoint Online, OneDrive for Business e team di Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fcd3-131">(New!) Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="6fcd3-132">* * A partire da ritardo maggio 2018, funzionalità di [quarantena](quarantine-email-messages.md) in sicurezza &amp; centro conformità vengono estese a strumenti di analisi di SharePoint Online, OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-132">**Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> **
  
<span data-ttu-id="6fcd3-p109">Quando un file in SharePoint Online, OneDrive for Business o Microsoft Teams viene identificato come dannose, oltre a strumenti di analisi blocco dei file l'apertura o condivise, tale file è incluso in un elenco di elementi in quarantena. (Nella protezione &amp; centro conformità, passare a **gestione delle minacce** \> **revisione** \> **quarantena** e applicare un filtro contenuto.)</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p109">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items. (In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for Content.)</span></span> 
  
<span data-ttu-id="6fcd3-135">Parte del team di protezione di Office 365 dell'organizzazione che hanno la necessità [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md), è possibile scaricare, versione, report ed eliminare i file che vengono rilevati come dannose da strumenti di analisi dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-135">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="6fcd3-p110">**Rilascio e report di** un file consente di rimuovere il blocco degli strumenti di analisi del file il team rispettivi siti o una raccolta documenti di SharePoint, OneDrive o Teams Microsoft. Gli utenti sono in grado di aprire, condividere e scaricare il file. E, quando è selezionata l'opzione **Invia rapporto a Microsoft** , il file viene indicato come falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p110">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="6fcd3-p111">**Eliminazione di un file** consente di rimuovere il file dalla quarantena; Tuttavia, il file è ancora impedito viene aperto o condivisa. Il file deve eliminato nelle rispettive raccolta o un team di sito con documenti (SharePoint Online, OneDrive for Business o Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="6fcd3-p111">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="6fcd3-141">**Download di un file** consente di scaricare e analizzare il file per eventuali falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="6fcd3-141">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="6fcd3-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6fcd3-142">Next steps</span></span>

- [<span data-ttu-id="6fcd3-143">Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi</span><span class="sxs-lookup"><span data-stu-id="6fcd3-143">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
- [<span data-ttu-id="6fcd3-144">Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fcd3-144">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a><span data-ttu-id="6fcd3-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6fcd3-145">Related topics</span></span>

[<span data-ttu-id="6fcd3-146">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6fcd3-146">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="6fcd3-147">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="6fcd3-147">View the reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="6fcd3-148">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="6fcd3-148">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

