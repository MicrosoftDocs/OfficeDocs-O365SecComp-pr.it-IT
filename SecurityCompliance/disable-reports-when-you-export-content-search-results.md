---
title: Disabilitare report quando si esportano i risultati di ricerca del contenuto in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Modificare il Registro di sistema nel computer locale per disabilitare il report quando si esportano i risultati di ricerca di contenuto da Office 365 Security &amp; Comliance Center. Disabilitare questi rapporti consente di ridurre il tempo di download e di risparmiare spazio su disco.
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531326"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="00380-104">Disabilitare report quando si esportano i risultati di ricerca del contenuto in Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="00380-104">Disable reports when you export Content Search results in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="00380-p102">Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per esportare i risultati di una ricerca di contenuto per la protezione &amp; centro conformità, lo strumento verrà creato automaticamente ed Esporta due rapporti che contengono ulteriori informazioni sul contenuto esportato. Questi rapporti sono file Results.csv e il file manifest (vedere la sezione [domande frequenti sulla disattivazione del report di esportazione](#frequently-asked-questions-about-disabling-export-reports) in questo argomento per una descrizione dettagliata di questi rapporti). Poiché questi file possono essere molto grandi, è possibile ridurre il tempo di download e salvare lo spazio su disco per impedire che questi file da esportare. È possibile eseguire questo modificando il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Se si desidera includere i risultati in un secondo momento, è possibile modificare l'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="00380-p102">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security &amp; Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content. These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports). Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported. You can do this by changing the Windows Registry on the computer that you use to export the search results. If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="00380-110">Creare le impostazioni del Registro di sistema per disabilitare l'esportazione dei rapporti</span><span class="sxs-lookup"><span data-stu-id="00380-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="00380-111">Eseguire la procedura seguente nel computer in cui verranno utilizzati per esportare i risultati della ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="00380-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="00380-112">Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.</span><span class="sxs-lookup"><span data-stu-id="00380-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="00380-113">Eseguire uno o entrambi i passaggi seguenti, in base al quale report esportazione da disattivare.</span><span class="sxs-lookup"><span data-stu-id="00380-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="00380-114">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="00380-114">**Results.csv**</span></span>
    
      <span data-ttu-id="00380-115">Salvare il testo seguente in un file di registro di sistema di Windows utilizzando il suffisso nome del file con estensione reg; ad esempio, DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="00380-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="00380-116">**File manifest. Xml**</span><span class="sxs-lookup"><span data-stu-id="00380-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="00380-117">Salvare il testo seguente in un file di registro di sistema di Windows utilizzando il suffisso nome del file con estensione reg; ad esempio, DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="00380-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="00380-118">In Esplora risorse fare clic o doppio clic sul file con estensione reg creata nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="00380-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="00380-119">Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="00380-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="00380-120">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="00380-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="00380-121">L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="00380-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="00380-122">Modificare le impostazioni del Registro di sistema per abilitare di nuovo l'esportazione dei rapporti</span><span class="sxs-lookup"><span data-stu-id="00380-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="00380-p103">Se è disabilitata per i rapporti Results.csv e manifest creando i file con estensione reg nella procedura precedente, è possibile modificare tali file per riattivare un report in modo che l'esportazione dei risultati della ricerca. Nel computer in cui verranno utilizzati per esportare i risultati della ricerca di contenuto, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="00380-p103">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results. Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="00380-125">Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.</span><span class="sxs-lookup"><span data-stu-id="00380-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="00380-126">Modificare uno o entrambi i file con estensione reg modifica creata nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="00380-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="00380-127">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="00380-127">**Results.csv**</span></span>
    
        <span data-ttu-id="00380-p104">Aprire il file DisableResultsCsv.reg nel blocco note, modificare il valore `False` a `True`e quindi salvare il file. Ad esempio, dopo aver modificato il file, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="00380-p104">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="00380-130">**File manifest. Xml**</span><span class="sxs-lookup"><span data-stu-id="00380-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="00380-p105">Aprire il file DisableManifestXml.reg nel blocco note, modificare il valore `False` a `True`e quindi salvare il file. Ad esempio, dopo aver modificato il file, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="00380-p105">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="00380-133">In Esplora risorse fare clic su o fare doppio clic su un file con estensione reg che è stato modificato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="00380-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="00380-134">Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="00380-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="00380-135">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="00380-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="00380-136">L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="00380-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="00380-137">Domande frequenti sulla disabilitazione di esportazione dei rapporti</span><span class="sxs-lookup"><span data-stu-id="00380-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="00380-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="00380-138"></span></span>

 <span data-ttu-id="00380-139">**Che cosa sono i rapporti Results.csv e file manifest. Xml?**</span><span class="sxs-lookup"><span data-stu-id="00380-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="00380-140">I file manifest. XML e Results.csv contengono ulteriori informazioni sul contenuto che è stata esportata.</span><span class="sxs-lookup"><span data-stu-id="00380-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="00380-p106">Documento di Excel **Results.csv** che contiene informazioni su ogni elemento è disponibile come download come risultato di ricerca. Per la posta elettronica, il registro risultato contiene informazioni su ogni messaggio, tra cui:</span><span class="sxs-lookup"><span data-stu-id="00380-p106">**Results.csv** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="00380-143">Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).</span><span class="sxs-lookup"><span data-stu-id="00380-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="00380-144">La data in cui è stato inviato o ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="00380-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="00380-145">La riga dell'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="00380-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="00380-146">Il mittente e i destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="00380-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="00380-p107">Indica se il messaggio è un messaggio duplicato se è abilitata la deduplicazione per l'esportazione dei risultati della ricerca. I messaggi duplicati dispone di un valore nella colonna **ID articolo padre** che identifica il messaggio come duplicato. Il valore nella colonna **ID articolo padre** è uguale al valore nella colonna **DocumentId elemento** del messaggio è stato esportato.</span><span class="sxs-lookup"><span data-stu-id="00380-p107">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results. Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate. The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="00380-150">Per i documenti di SharePoint e OneDrive per i siti di Business, registro risultato contiene informazioni su tutti i documenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="00380-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="00380-151">L'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="00380-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="00380-152">L’URL per la raccolta di siti in cui si trova il documento.</span><span class="sxs-lookup"><span data-stu-id="00380-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="00380-153">La data dell'ultima modifica al documento.</span><span class="sxs-lookup"><span data-stu-id="00380-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="00380-154">Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).</span><span class="sxs-lookup"><span data-stu-id="00380-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="00380-p108">**Manifest** un file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. Le informazioni contenute in questo report corrisponde al rapporto Results.csv, ma è nel formato specificato dal modello di riferimento Electronic Discovery (EDRM). Per ulteriori informazioni su EDRM, vedere [https://www.edrm.net](https://www.edrm.net).</span><span class="sxs-lookup"><span data-stu-id="00380-p108">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results. The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM). For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="00380-158">**Se opportuno disabilitare esportazione questi rapporti?**</span><span class="sxs-lookup"><span data-stu-id="00380-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="00380-p109">Dipende dalle esigenze specifiche. Molte organizzazioni non sono necessarie ulteriori informazioni sui risultati di ricerca e non è necessario questi rapporti.</span><span class="sxs-lookup"><span data-stu-id="00380-p109">It depends on your specific needs. Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="00380-161">**Il computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="00380-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="00380-162">È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale che si esegue lo strumento di esportazione eDiscovery di Office 365 in.</span><span class="sxs-lookup"><span data-stu-id="00380-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="00380-163">**Dopo che è possibile modificare questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="00380-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="00380-p110">No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione eDiscovery di Office 365 è in esecuzione, è necessario chiuderlo e quindi riavviarlo dopo aver modificato l'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="00380-p110">No, you don't have to restart the computer. But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="00380-166">**Ottenere modifica una chiave del Registro di sistema esistente o vengono creata una nuova chiave.**</span><span class="sxs-lookup"><span data-stu-id="00380-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="00380-p111">Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creata nella procedura in questo argomento. L'impostazione viene quindi modificata ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg.</span><span class="sxs-lookup"><span data-stu-id="00380-p111">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
