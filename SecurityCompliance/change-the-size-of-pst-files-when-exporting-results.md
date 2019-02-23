---
title: Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST scaricati nel computer quando si esportano i risultati della ricerca di eDiscovery.
ms.openlocfilehash: 8a956091f29ec1b564d3194c7e3ca2680fdeb564
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214626"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="82657-103">Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="82657-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="82657-p101">Quando si utilizza lo strumento di esportazione di eDiscovery di Office 365 per esportare i risultati di una ricerca di eDiscovery dai diversi strumenti di eDiscovery di Microsoft, le dimensioni predefinite di un file PST che può essere esportato sono 10 GB. Se si desidera modificare queste dimensioni predefinite, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Un motivo per farlo è un file PST che può essere adattato ai supporti rimovibili, ad esempio un DVD, un disco compatto o un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="82657-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="82657-107">Lo strumento di esportazione di Office 365 eDiscovery viene utilizzato per esportare i risultati della ricerca quando si utilizza la ricerca contenuto &amp; nel centro sicurezza e conformità di Office 365, eDiscovery sul posto in Exchange Online e il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="82657-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="82657-108">Creare un'impostazione del registro di sistema per modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="82657-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="82657-109">Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="82657-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="82657-110">Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto.</span><span class="sxs-lookup"><span data-stu-id="82657-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="82657-111">Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, PstExportSize. reg.</span><span class="sxs-lookup"><span data-stu-id="82657-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="82657-p102">Nell'esempio precedente, il `PstSizeLimitInBytes` valore è impostato su 1.073.741.824 byte o circa 1 GB. Di seguito sono riportati alcuni altri valori di `PstSizeLimitInBytes` esempio per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="82657-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="82657-114">**Dimensioni in GB (circa)**</span><span class="sxs-lookup"><span data-stu-id="82657-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="82657-115">**Dimensioni in byte**</span><span class="sxs-lookup"><span data-stu-id="82657-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="82657-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="82657-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="82657-117">751619277</span><span class="sxs-lookup"><span data-stu-id="82657-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="82657-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="82657-118">2 GB</span></span>  <br/> |<span data-ttu-id="82657-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="82657-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="82657-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="82657-120">4 GB</span></span>  <br/> |<span data-ttu-id="82657-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="82657-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="82657-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="82657-122">8 GB</span></span>  <br/> |<span data-ttu-id="82657-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="82657-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="82657-124">Quando si `PstSizeLimitInBytes` esportano i risultati della ricerca, modificare il valore con le dimensioni massime desiderate di un file PST e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="82657-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="82657-125">In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="82657-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="82657-126">Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="82657-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="82657-127">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="82657-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="82657-128">L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="82657-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="82657-129">È possibile ripetere i passaggi 3-6 per modificare il valore per `PstSizeLimitInBytes` l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="82657-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="82657-130">Domande frequenti su come modificare le dimensioni predefinite dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="82657-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="82657-131">**Perché è la dimensione predefinita 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="82657-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="82657-132">Le dimensioni predefinite di 10 GB si basano sul feedback dei clienti; 10 GB è un buon bilanciamento tra la quantità ottimale di contenuto in un singolo file PST e la possibilità minima di danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="82657-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="82657-133">**È consigliabile aumentare o diminuire la dimensione predefinita dei file PST?**</span><span class="sxs-lookup"><span data-stu-id="82657-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="82657-p103">I clienti tendono a ridurre il limite di dimensione, in modo che i risultati della ricerca possano adattarsi ai supporti rimovibili che possono inviare fisicamente altre posizioni all'interno della propria organizzazione. Non è consigliabile aumentare le dimensioni predefinite perché i file PST di dimensioni superiori a 10 GB potrebbero avere problemi di danneggiamento.</span><span class="sxs-lookup"><span data-stu-id="82657-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="82657-136">**Per quale computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="82657-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="82657-137">È necessario modificare l'impostazione del registro di sistema in un computer locale in cui viene eseguito lo strumento di esportazione di eDiscovery di Office 365.</span><span class="sxs-lookup"><span data-stu-id="82657-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="82657-138">**Dopo aver modificato questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="82657-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="82657-p104">No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione di Office 365 eDiscovery è in esecuzione, sarà necessario chiuderlo e riavviarlo dopo la modifica di questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="82657-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="82657-141">**Una chiave del registro di sistema esistente viene modificata o viene creata una nuova chiave?**</span><span class="sxs-lookup"><span data-stu-id="82657-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="82657-p105">La prima volta che si esegue il file con estensione reg creato in questa procedura viene creata una nuova chiave del registro di sistema. L'impostazione viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="82657-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
