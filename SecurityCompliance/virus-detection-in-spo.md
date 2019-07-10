---
title: Rilevamento virus in SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online. I file vengono analizzati per i virus dopo che sono stati caricati. Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.
ms.openlocfilehash: 8b15ac8e82082c2c6d940986d2018fa559835146
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598342"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="7397c-105">Rilevamento virus in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7397c-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="7397c-106">Office 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7397c-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="7397c-107">I file vengono analizzati per i virus dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="7397c-107">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="7397c-108">Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="7397c-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7397c-109">Queste funzionalità antivirus in SharePoint Online sono un modo per contenere virus.</span><span class="sxs-lookup"><span data-stu-id="7397c-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="7397c-110">Non sono intese come un singolo punto di difesa contro il malware per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7397c-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="7397c-111">Si consiglia a tutti i clienti di valutare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="7397c-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="7397c-112">Per ulteriori informazioni sulle strategie e le procedure consigliate, vedere procedure consigliate [per la sicurezza per Office 365](security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="7397c-112">For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="7397c-113">Cosa succede quando un file infetto viene caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="7397c-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="7397c-114">Office 365 utilizza un motore di rilevamento virus comune.</span><span class="sxs-lookup"><span data-stu-id="7397c-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="7397c-115">Il motore viene eseguito in modo asincrono all'interno di SharePoint Online e analizza i file dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="7397c-115">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="7397c-116">Quando un file viene trovato per contenere un virus, viene contrassegnato in modo che non possa essere scaricato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="7397c-116">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="7397c-117">Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.</span><span class="sxs-lookup"><span data-stu-id="7397c-117">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="7397c-118">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="7397c-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="7397c-119">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7397c-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="7397c-120">Il motore di rilevamento dei virus analizza il file.</span><span class="sxs-lookup"><span data-stu-id="7397c-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="7397c-121">Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.</span><span class="sxs-lookup"><span data-stu-id="7397c-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="7397c-122">Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?</span><span class="sxs-lookup"><span data-stu-id="7397c-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="7397c-123">Se un file è infetto da un virus, gli utenti non possono scaricare il file da SharePoint Online utilizzando il browser.</span><span class="sxs-lookup"><span data-stu-id="7397c-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="7397c-124">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="7397c-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="7397c-125">Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7397c-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="7397c-126">All'utente viene fornito un avviso che è stato rilevato un virus.</span><span class="sxs-lookup"><span data-stu-id="7397c-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="7397c-127">All'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il proprio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="7397c-127">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="7397c-128">È possibile utilizzare il cmdlet Set-SPOTenant con il parametro **DisallowInfectedFileDownload** per non consentire agli utenti di scaricare un file rilevato, anche nella finestra di avviso antivirus.</span><span class="sxs-lookup"><span data-stu-id="7397c-128">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="7397c-129">Vedere [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="7397c-129">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="7397c-130">Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?</span><span class="sxs-lookup"><span data-stu-id="7397c-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="7397c-131">Se gli utenti sincronizzano i file con il nuovo client di sincronizzazione di OneDrive (OneDrive. exe) o il client di sincronizzazione di OneDrive for business precedente (Groove. exe), se un file contiene un virus, il client di sincronizzazione non lo scaricherà.</span><span class="sxs-lookup"><span data-stu-id="7397c-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="7397c-132">Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="7397c-132">The sync client will display a notification that the file can't be synced.</span></span>
  

