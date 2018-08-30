---
title: Rilevamento di virus in SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 può proteggere l'ambiente da malware per l'individuazione dei virus nei file che gli utenti caricano con SharePoint Online. File di ricerca di virus dopo che vengono caricati. Se un file viene trovato un virus, una proprietà viene impostata in modo che gli utenti non possono scaricare o sincronizzare il file.
ms.openlocfilehash: 22e983d35283ff96e1469fdf913e25b8d1d1c485
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531056"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="1abff-105">Rilevamento di virus in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1abff-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="1abff-p102">Office 365 può proteggere l'ambiente da malware per l'individuazione dei virus nei file che gli utenti caricano con SharePoint Online. File di ricerca di virus dopo che vengono caricati. Se un file viene trovato un virus, una proprietà viene impostata in modo che gli utenti non possono scaricare o sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="1abff-p102">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1abff-p103">Tali funzionalità antivirus in SharePoint Online rappresentano un modo per contenere virus. Non non sono previsti come un singolo punto di sistema di difesa contro malware per l'ambiente. Microsoft incoraggia tutti i clienti di valutare e implementare protezione antimalware a diversi livelli e applicarlo procedure consigliate per la protezione dell'infrastruttura di enterprise. Per ulteriori informazioni sulle strategie e procedure consigliate, vedere [le procedure consigliate per Office 365](security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="1abff-p103">These antivirus capabilities in SharePoint Online are a way to contain viruses. They aren't intended as a single point of defense against malware for your environment. We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure. For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="1abff-113">Cosa succede quando un file che contengono un virus caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="1abff-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="1abff-p104">Office 365 utilizza un motore di rilevamento dei virus più comuni. Il modulo di gestione viene eseguito in modo asincrono in SharePoint Online e analizza i file dopo essere state caricate. Quando viene rilevato un file di contengono un virus, viene contrassegnata in modo che non possono essere scaricato nuovamente. In aprile 2018, viene rimosso il limite massimo 25 MB per file analizzati.</span><span class="sxs-lookup"><span data-stu-id="1abff-p104">Office 365 uses a common virus detection engine. The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded. When a file is found to contain a virus, it's flagged so that it can't be downloaded again. In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="1abff-118">Ecco che cosa accade:</span><span class="sxs-lookup"><span data-stu-id="1abff-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="1abff-119">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1abff-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="1abff-120">Il motore di rilevamento virus analizza i file.</span><span class="sxs-lookup"><span data-stu-id="1abff-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="1abff-121">Se viene rilevato un virus, il motore di virus imposta una proprietà per il file che indica che contiene.</span><span class="sxs-lookup"><span data-stu-id="1abff-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="1abff-122">Cosa succede quando un utente tenta di scaricare un file che contengono un virus utilizzando il browser?</span><span class="sxs-lookup"><span data-stu-id="1abff-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="1abff-123">Se un file contiene un virus, gli utenti non possono scaricare il file da SharePoint Online mediante l'utilizzo del browser.</span><span class="sxs-lookup"><span data-stu-id="1abff-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="1abff-124">Ecco che cosa accade:</span><span class="sxs-lookup"><span data-stu-id="1abff-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="1abff-125">L'utente apre un web browser e tenta di scaricare un file che contengono un virus da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1abff-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="1abff-126">L'utente ha un avviso indicante che è stato rilevato un virus e ha la possibilità di scaricare il file e tenta la pulizia mediante un software antivirus.</span><span class="sxs-lookup"><span data-stu-id="1abff-126">The user is given a warning that a virus has been detected, and is given the option to download the file and attempt to clean it using their own virus software.</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="1abff-127">Cosa succede quando il client di sincronizzazione OneDrive tenta di sincronizzare un file che contengono un virus?</span><span class="sxs-lookup"><span data-stu-id="1abff-127">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="1abff-p105">Se gli utenti sincronizzare i file con il nuovo client di sincronizzazione OneDrive (OneDrive.exe) o il precedente OneDrive for Business client di sincronizzazione (Groove.exe), se un file contiene un virus, il client di sincronizzazione non scaricarlo. Il client di sincronizzazione verrà visualizzata una notifica che il file non può essere sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="1abff-p105">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  

