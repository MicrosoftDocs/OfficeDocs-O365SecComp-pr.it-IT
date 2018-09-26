---
title: Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Informazioni su come configurare il Registro di sistema per aumentare la velocità effettiva di scaricare i risultati della ricerca e cercare i dati da Office 365 Security &amp; eDiscovery centro conformità e avanzate di Office 365.
ms.openlocfilehash: a05c2b786d1d1de7ff5014d12c708484345f908b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038119"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="04317-103">Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365</span><span class="sxs-lookup"><span data-stu-id="04317-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="04317-p101">Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per scaricare i risultati di una ricerca di contenuto in Office 365 Security &amp; dati centro conformità o download di Office 365 avanzate eDiscovery, lo strumento consente di avviare un certo numero di esportazione simultanee operazioni di scaricare i dati nel computer locale. Per impostazione predefinita, il numero di operazioni simultanee è impostato a 8 volte il numero di core nel computer in uso per scaricare i dati. Ad esempio, se si dispone di un computer dual-core (vale a dire due CPU su uno chip), il numero predefinito di operazioni di esportazione simultanee è 16. Per aumentare la velocità effettiva di trasferimento dati e velocizzare il processo di download, è possibile aumentare il numero di operazioni simultanee configurando un'impostazione del Registro di sistema di Windows nel computer utilizzato per scaricare i risultati della ricerca. Per velocizzare il processo di download, è consigliabile iniziare con un'impostazione di 24 operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="04317-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="04317-p102">Se si scarica i risultati della ricerca in una rete di larghezza di banda ridotta, l'aumento di questa impostazione può avere un impatto negativo. In alternativa, è possibile aumentare l'impostazione per più di 24 operazioni simultanee in una rete ampia larghezza di banda (il numero massimo di operazioni simultanee è 512). Dopo aver configurato questa impostazione del Registro di sistema, potrebbe essere necessario modificarla per trovare il numero di operazioni simultanee per l'ambiente ottimale.</span><span class="sxs-lookup"><span data-stu-id="04317-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="04317-112">Creare un registro di sistema è necessario per modificare il numero di operazioni simultanee per l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="04317-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="04317-113">Eseguire la procedura seguente nel computer in cui verrà utilizzata per scaricare i risultati di ricerca di sicurezza &amp; centro conformità o dati provenienti da eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="04317-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="04317-114">Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.</span><span class="sxs-lookup"><span data-stu-id="04317-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="04317-115">Salvare il testo seguente in un file di registro di sistema finestra con il suffisso nome del file con estensione reg; ad esempio, ConcurrentOperations.reg.</span><span class="sxs-lookup"><span data-stu-id="04317-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="04317-116">Precedente come descritto, è consigliabile iniziare con 24 operazioni concorrenti e quindi modificare questa impostazione a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="04317-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="04317-117">In Esplora risorse fare clic o doppio clic sul file con estensione reg creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="04317-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="04317-118">Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="04317-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="04317-119">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="04317-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="04317-120">L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="04317-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="04317-121">È possibile ripetere i passaggi 2-5 per modificare il valore per il `DownloadConcurrency` impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="04317-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="04317-p103">Dopo aver creato o modificare il `DownloadConcurrency` Registro di sistema impostazione, è necessario creare un nuovo processo di esportazione o riavviare un processo di esportazione esistente per i risultati di ricerca o dati che si desidera scaricare. Per ulteriori informazioni, vedere [ulteriori informazioni](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) .</span><span class="sxs-lookup"><span data-stu-id="04317-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="04317-124">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="04317-124">More information</span></span>

- <span data-ttu-id="04317-p104">Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creato in questa procedura. L'oggetto `DownloadConcurrency` impostazione del Registro di sistema viene modificato ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg.</span><span class="sxs-lookup"><span data-stu-id="04317-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="04317-p105">Lo strumento di esportazione eDiscovery di Office 365 utilizza l' [utilità AzCopy Azure](https://go.microsoft.com/fwlink/?linkid=849949) per scaricare i dati di ricerca di sicurezza &amp; centro conformità o da eDiscovery avanzate. Configurazione di `DownloadConcurrency` impostazione del Registro di sistema è simile all'utilizzo del parametro **/NC** quando si esegue l'utilità AzCopy. Pertanto l'impostazione del Registro di sistema di `"DownloadConcurrency=24"` avranno lo stesso effetto utilizzando il valore del parametro `/NC:24` con l'utilità AzCopy.</span><span class="sxs-lookup"><span data-stu-id="04317-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="04317-p106">Se si arresta un download di esportazione che è attualmente in esecuzione e quindi riavviare (provando a scaricare nuovamente i risultati della ricerca), lo strumento di esportazione eDiscovery di Office 365 tenterà di riprendere il download stesso. Pertanto, se si avvia un download, interrotto e quindi passare la `DownloadConcurrency` Registro di sistema impostazione, i download probabilmente non riuscirà se si riavvia (facendo clic su **Download esportare i risultati**). Ciò avviene perché lo strumento di esportazione verrà eseguito un tentativo di riprendere il download precedente utilizzando le impostazioni che non sono valide perché l'impostazione del Registro di sistema è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="04317-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="04317-p107">Pertanto, dopo aver modificato il `DownloadConcurrency` Registro di sistema impostazione, è necessario riavviare il processo di esportazione (facendo clic su **Riavvia export**) nella protezione &amp; centro conformità. È quindi possibile scaricare l'esportazione dei risultati. Per ulteriori informazioni sull'esportazione di dati e i risultati della ricerca, vedere:</span><span class="sxs-lookup"><span data-stu-id="04317-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="04317-136">Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="04317-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="04317-137">Esportare i risultati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="04317-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
