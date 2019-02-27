---
title: Aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Informazioni su come configurare il registro di sistema di Windows per aumentare la velocità effettiva dei dati quando si scaricano i risultati della &amp; ricerca e i dati di ricerca da Office 365 Security Compliance Center e Office 365 Advanced eDiscovery.
ms.openlocfilehash: a23525ada1ef5f36bc7df4fc738c712e22243bc0
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295429"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="ce3fb-103">Aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365</span><span class="sxs-lookup"><span data-stu-id="ce3fb-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="ce3fb-p101">Quando si utilizza lo strumento di esportazione di eDiscovery di Office 365 per scaricare i risultati di una ricerca di contenuto nel &amp; Centro sicurezza e conformità di Office 365 o scaricare i dati da Office 365 Advanced eDiscovery, lo strumento avvia un certo numero di esportazione simultanea operazioni per il download dei dati nel computer locale. Per impostazione predefinita, il numero di operazioni simultanee è impostato su 8 volte il numero di core nel computer che si sta utilizzando per scaricare i dati. Ad esempio, se si dispone di un computer dual core (che significa due unità di elaborazione centrale in un unico chip), il numero predefinito di operazioni di esportazione simultanee è 16. Per aumentare la velocità effettiva di trasferimento dei dati e velocizzare il processo di download, è possibile aumentare il numero di operazioni simultanee configurando un'impostazione del registro di sistema di Windows nel computer utilizzato per scaricare i risultati della ricerca. Per velocizzare il processo di download, è consigliabile iniziare con un'impostazione di 24 operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="ce3fb-p102">Se si scaricano i risultati della ricerca in una rete con larghezza di banda ridotta, l'aumento di questa impostazione può avere un impatto negativo. In alternativa, potrebbe essere possibile aumentare l'impostazione su più di 24 operazioni simultanee in una rete a larghezza di banda elevata (il numero massimo di operazioni simultanee è 512). Dopo aver configurato l'impostazione del registro di sistema, potrebbe essere necessario modificarla per individuare il numero ottimale di operazioni simultanee per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="ce3fb-112">Creare un'impostazione del registro di sistema per modificare il numero di operazioni simultanee durante l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="ce3fb-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="ce3fb-113">Eseguire la procedura seguente nel computer che verrà utilizzato per scaricare i risultati della ricerca dal centro conformità &amp; di sicurezza o dai dati di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="ce3fb-114">Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="ce3fb-115">Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, ConcurrentOperations. reg.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="ce3fb-116">Come spiegato in precedenza, si consiglia di iniziare con 24 operazioni simultanee e quindi modificare questa impostazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="ce3fb-117">In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="ce3fb-118">Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="ce3fb-119">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="ce3fb-120">L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="ce3fb-121">È possibile ripetere i passaggi 2-5 per modificare il valore per `DownloadConcurrency` l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ce3fb-p103">Dopo aver creato o modificato l' `DownloadConcurrency` impostazione del registro di sistema, assicurarsi di creare un nuovo processo di esportazione o di riavviare un processo di esportazione esistente per i risultati di ricerca o i dati che si desidera scaricare. Per ulteriori dettagli, vedere la sezione [ulteriori informazioni](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) .</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="ce3fb-124">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ce3fb-124">More information</span></span>

- <span data-ttu-id="ce3fb-p104">La prima volta che si esegue il file con estensione reg creato in questa procedura viene creata una nuova chiave del registro di sistema. L' `DownloadConcurrency` impostazione del registro di sistema viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="ce3fb-p105">Lo strumento di esportazione di eDiscovery di Office 365 utilizza l' [utilità AzCopy di Azure](https://go.microsoft.com/fwlink/?linkid=849949) per scaricare i &amp; dati di ricerca dal centro conformità di sicurezza o da Advanced eDiscovery. La configurazione `DownloadConcurrency` dell'impostazione del registro di sistema è simile all'utilizzo del parametro **/NC** quando si esegue l'utilità AzCopy. In questo modo, l' `"DownloadConcurrency=24"` impostazione del registro di sistema avrebbe lo stesso effetto dell'utilizzo `/NC:24` del valore del parametro con l'utilità AzCopy.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="ce3fb-p106">Se si interrompe un download di esportazione che è attualmente in corso e quindi lo si riavvia (tentando di scaricare di nuovo i risultati della ricerca), lo strumento di esportazione di Office 365 eDiscovery tenterà di riprendere lo stesso download. Pertanto, se si avvia un download, lo si interrompe e quindi si modifica `DownloadConcurrency` l'impostazione del registro di sistema, il download probabilmente avrà esito negativo se lo si riavvia (facendo clic su **Scarica risultati**esportati). Ciò è dovuto al fatto che lo strumento di esportazione tenterà di riprendere il download precedente utilizzando le impostazioni non valide perché è stata modificata l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="ce3fb-p107">Pertanto, dopo aver modificato l' `DownloadConcurrency` impostazione del registro di sistema, assicurarsi di riavviare il processo di esportazione facendo clic su **Riavvia esportazione**nel &amp; Centro sicurezza e conformità. È quindi possibile scaricare i risultati esportati. Per ulteriori informazioni sull'esportazione di dati e risultati della ricerca, vedere:</span><span class="sxs-lookup"><span data-stu-id="ce3fb-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="ce3fb-136">Esportare i risultati della ricerca del contenuto dal centro &amp; sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="ce3fb-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="ce3fb-137">Esportare i risultati in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ce3fb-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
