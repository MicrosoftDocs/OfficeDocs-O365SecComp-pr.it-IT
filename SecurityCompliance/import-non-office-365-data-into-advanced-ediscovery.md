---
title: Importare i contenuti non Office 365 per l'analisi di Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Come eseguire la procedura per importare il contenuto che non viene archiviato in O365 in un BLOB di Azure in modo che possa essere analizzato con AeD
ms.openlocfilehash: 1019fa2e2429aeff8bd20bc3dfb266ab5fb25eaf
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217066"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="225c1-103">Importare i contenuti non Office 365 per l'analisi di Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="225c1-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="225c1-p101">Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365. Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non sono presenti in Office 365 (ad eccezione dei file PST) in un caso collegato, BLOB di archiviazione di Azure e analizzarli con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="225c1-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="225c1-p102">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="225c1-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="225c1-p103">È possibile acquistare un abbonamento a un componente aggiuntivo per l'archiviazione dei dati di Office 365 Advanced eDiscovery per il contenuto non Office 365. Questo è disponibile solo per il contenuto che deve essere analizzato con Advanced eDiscovery. Seguire i passaggi descritti in [buy or Edit and add-on per office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) e acquistare il componente aggiuntivo di archiviazione di Office 365 Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="225c1-p103">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content. This is exclusively available for content that is to be analyzed with Advanced eDiscovery. Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="225c1-112">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="225c1-112">Before you begin</span></span>

<span data-ttu-id="225c1-113">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="225c1-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="225c1-114">Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5</span><span class="sxs-lookup"><span data-stu-id="225c1-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="225c1-115">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="225c1-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="225c1-116">Un caso di eDiscovery esistente</span><span class="sxs-lookup"><span data-stu-id="225c1-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="225c1-p104">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias @ NomeDominio* . L' *alias @ DomainName* deve essere Users Office 365 alias and Domain. È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice. La cartella radice può contenere solo le cartelle *alias @ DomainName* , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="225c1-p104">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  . The  *alias@domainname*  must be users Office 365 alias and domain. You can collect all the  *alias@domainname*  folders into a root folder. The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="225c1-121">Un account che sia un Manager di eDiscovery o un amministratore di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="225c1-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="225c1-122">[Strumenti di archiviazione di Microsoft Azure](https://aka.ms/downloadazcopy) installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="225c1-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="225c1-123">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="225c1-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="225c1-p105">In qualità di Manager di eDiscovery o amministratore di eDiscovery, aprire **eDiscovery**e aprire il caso in cui verranno caricati i dati non di Office 365. Se è necessario creare un caso, vedere [gestire i casi di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="225c1-p105">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to. If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="225c1-126">Fare clic su **cambia in Advanced eDiscovery**</span><span class="sxs-lookup"><span data-stu-id="225c1-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="225c1-127">In **tipo di origine** selezionare **dati non Office 365**.</span><span class="sxs-lookup"><span data-stu-id="225c1-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="225c1-p106">Fare clic su **Aggiungi contenitore**. DeNominare il contenitore e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="225c1-p106">Click **Add container**. Name the container and add a description.</span></span>
    
5. <span data-ttu-id="225c1-130">Selezionare il contenitore appena aggiunto dall'elenco contenitore e copiare l'URL visualizzato nel riquadro dei dettagli del contenitore e quindi chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="225c1-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="225c1-131">Aprire un prompt dei comandi come amministratore e cambiare directory nella cartella in cui è installato AzCopy.</span><span class="sxs-lookup"><span data-stu-id="225c1-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="225c1-132">Creare la riga di comando di AzCopy per caricare i file in questo modo:</span><span class="sxs-lookup"><span data-stu-id="225c1-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="225c1-p107">AzCopy/Source: " *percorso completo della cartella radice nel computer locale* "/dest: " *URL del contenitore fino a ma non incluso il?* "/DestSAS: " *resto dell'URL del contenitore dall'? fino alla fine* "/S.</span><span class="sxs-lookup"><span data-stu-id="225c1-p107">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*  " /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="225c1-135">Ad esempio, utilizzando questi valori:</span><span class="sxs-lookup"><span data-stu-id="225c1-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="225c1-136">cartella radice-dati C:\Collected</span><span class="sxs-lookup"><span data-stu-id="225c1-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="225c1-137">URL del contenitore https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; SR =&amp;c si = NonOfficeData15%&amp;7C0 sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D</span><span class="sxs-lookup"><span data-stu-id="225c1-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="225c1-138">la sintassi della riga di comando di AzCopy è:</span><span class="sxs-lookup"><span data-stu-id="225c1-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="225c1-139">Per ulteriori informazioni sulla sintassi di Azcopy, vedere [trasferire dati con la Azcopy in Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="225c1-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="225c1-140">Deve essere presente una cartella radice per utente e il nome della cartella deve essere nel formato *alias @ NomeDominio* .</span><span class="sxs-lookup"><span data-stu-id="225c1-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="225c1-p108">Dopo aver completato il caricamento delle cartelle, tornare a Advanced eDiscovery. Il contenuto delle cartelle che è stato caricato è ora pronto per essere elaborato in Advanced eDiscovery. Selezionare il contenitore e fare clic sul pulsante elabora. Per ulteriori informazioni sull'elaborazione avanzata di eDiscovery, vedere, [eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="225c1-p108">Once the folders have finished uploading, switch back to Advanced eDiscovery. The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery. Select the container and click the Process button. For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="225c1-p109">Dopo che il contenitore è stato elaborato correttamente in Advanced eDiscovery, non sarà più possibile aggiungere nuovo contenuto allo spazio di archiviazione SAS in Azure. Se si raccolgono contenuto aggiuntivo e si desidera aggiungerlo al caso per l'analisi avanzata di eDiscovery, è necessario creare un nuovo contenitore di **dati non Office 365** e ripetere questa procedura.</span><span class="sxs-lookup"><span data-stu-id="225c1-p109">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure. If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="225c1-147">Se il contenitore non *elabora correttamente a causa di problemi di denominazione delle cartelle* e quindi si corregge i problemi, sarà comunque necessario creare un nuovo contenitore e riconnetterlo e caricarlo nuovamente utilizzando le procedure illustrate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="225c1-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  

