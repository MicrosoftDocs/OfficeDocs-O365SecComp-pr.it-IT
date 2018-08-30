---
title: Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST file scaricato nel computer quando si esportano i risultati della ricerca eDiscovery.
ms.openlocfilehash: d38189c437154dbe27a084230d4d3fd4de418ece
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530266"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="668a8-103">Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="668a8-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="668a8-p101">Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per esportare i risultati della posta elettronica di una ricerca eDiscovery diversi strumenti di Microsoft eDiscovery, la dimensione predefinita di un file PST che può essere esportato è 10 GB. Se si desidera modificare la dimensione predefinita, è possibile modificare il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Uno dei motivi per eseguire questa operazione è un file PST può contenere il rimovibile, ad esempio un DVD, un CD-ROM o un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="668a8-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="668a8-107">Lo strumento di esportazione eDiscovery di Office 365 viene utilizzato per esportare i risultati della ricerca quando si utilizza ricerca contenuto in Office 365 Security &amp; centro conformità, eDiscovery In locale in Exchange Online e il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="668a8-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="668a8-108">Creare un'impostazione del Registro di sistema per modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="668a8-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="668a8-109">Eseguire la procedura seguente nel computer in cui verranno utilizzati per esportare i risultati di una ricerca eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="668a8-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="668a8-110">Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.</span><span class="sxs-lookup"><span data-stu-id="668a8-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="668a8-111">Salvare il testo seguente in un file di registro di sistema finestra con il suffisso nome del file con estensione reg; ad esempio, PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="668a8-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="668a8-p102">Nell'esempio precedente, il `PstSizeLimitInBytes` è impostata su 1.073.741.824 byte o circa 1 GB. Ecco alcuni altri valori di esempio per il `PstSizeLimitInBytes` impostazione.</span><span class="sxs-lookup"><span data-stu-id="668a8-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="668a8-114">**Dimensione in GB (circa)**</span><span class="sxs-lookup"><span data-stu-id="668a8-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="668a8-115">**Dimensioni in byte**</span><span class="sxs-lookup"><span data-stu-id="668a8-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="668a8-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="668a8-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="668a8-117">751619277</span><span class="sxs-lookup"><span data-stu-id="668a8-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="668a8-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="668a8-118">2 GB</span></span>  <br/> |<span data-ttu-id="668a8-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="668a8-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="668a8-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="668a8-120">4 GB</span></span>  <br/> |<span data-ttu-id="668a8-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="668a8-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="668a8-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="668a8-122">8 GB</span></span>  <br/> |<span data-ttu-id="668a8-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="668a8-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="668a8-124">Modifica la `PstSizeLimitInBytes` valore per la dimensione massima desiderata di un file PST quando si esportano i risultati della ricerca e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="668a8-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="668a8-125">In Esplora risorse fare clic o doppio clic sul file con estensione reg creata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="668a8-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="668a8-126">Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="668a8-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="668a8-127">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="668a8-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="668a8-128">L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="668a8-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="668a8-129">È possibile ripetere i passaggi da 3 a 6 per modificare il valore per il `PstSizeLimitInBytes` impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="668a8-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="668a8-130">Domande frequenti su come modificare la dimensione predefinita del file PST durante l'esportazione dei risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="668a8-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="668a8-131">**Il valore predefinito è un'altezza di 10 GB.**</span><span class="sxs-lookup"><span data-stu-id="668a8-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="668a8-132">La dimensione predefinita di 10 GB è basata su feedback dei clienti; 10 GB rappresenta un buon compromesso tra la quantità di contenuto in un singolo file PST e con una minima possibilità di danneggiamento dei file ottimale.</span><span class="sxs-lookup"><span data-stu-id="668a8-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="668a8-133">**È consigliabile aumentare o diminuire la dimensione predefinita del file PST?**</span><span class="sxs-lookup"><span data-stu-id="668a8-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="668a8-p103">I clienti tendono a diminuire la dimensione massima, in modo che i risultati della ricerca occupi rimovibile che può consegna fisica altre posizioni all'interno dell'organizzazione. Non è consigliabile aumentare le dimensioni predefinite perché file superiori a 10 GB potrebbe essere problemi di danneggiamento dei file PST.</span><span class="sxs-lookup"><span data-stu-id="668a8-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="668a8-136">**Il computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="668a8-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="668a8-137">È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale che si esegue lo strumento di esportazione eDiscovery di Office 365 in.</span><span class="sxs-lookup"><span data-stu-id="668a8-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="668a8-138">**Dopo che è possibile modificare questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="668a8-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="668a8-p104">No, non è necessario riavviare il computer. Ma, se lo strumento di esportazione eDiscovery di Office 365 è in esecuzione, è necessario chiudere e il riavvio viene dopo che si modifica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="668a8-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="668a8-141">**Ottenere modifica una chiave del Registro di sistema esistente o vengono creata una nuova chiave.**</span><span class="sxs-lookup"><span data-stu-id="668a8-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="668a8-p105">Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creato in questa procedura. L'impostazione viene quindi modificata ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg.</span><span class="sxs-lookup"><span data-stu-id="668a8-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
