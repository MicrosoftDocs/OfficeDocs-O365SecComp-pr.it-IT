---
title: Caricare dati non Office 365 in un insieme da rivedere
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Importare i dati non di Office 365 in un set di revisione in un caso di eDiscovery avanzato.
ms.openlocfilehash: 37f8c2a5c97452845152e2a12578b9d243ab6711
ms.sourcegitcommit: 82ee560bf3ac84079764cbb4a2d858c321f65145
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "35840858"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="e2212-103">Caricare dati non Office 365 in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="e2212-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="e2212-104">Non tutti i documenti che devono essere analizzati in Advanced eDiscovery sono disponibili in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="e2212-105">Con la caratteristica di importazione di dati non di Office 365 in Advanced eDiscovery, è possibile caricare documenti che non sono presenti in Office 365 in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e2212-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="e2212-106">In questo articolo viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e2212-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="e2212-107">Advanced eDiscovery richiede un abbonamento a Microsoft 365 o Office 365 E5 per l'organizzazione o un abbonamento E3 con l'abbonamento al componente aggiuntivo per la conformità avanzato.</span><span class="sxs-lookup"><span data-stu-id="e2212-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="e2212-108">Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="e2212-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e2212-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="e2212-109">Before you begin</span></span>

<span data-ttu-id="e2212-110">Se si utilizza la funzionalità carica non Office 365 descritta in questo articolo, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e2212-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="e2212-111">A tutti i depositari ai quali si desidera associare il contenuto non di Office 365 deve essere assegnata una licenza E5 o una licenza E3 con una licenza per il componente aggiuntivo per la conformità avanzata.</span><span class="sxs-lookup"><span data-stu-id="e2212-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="e2212-112">Un caso avanzato di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="e2212-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="e2212-113">I depositari devono essere aggiunti al caso prima di poter caricare e associare ai dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="e2212-114">I dati non di Office 365 devono essere un tipo di file supportato da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e2212-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="e2212-115">Per ulteriori informazioni, vedere [tipi di file supportati in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="e2212-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="e2212-116">Tutti i file caricati in un set di revisione devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode.</span><span class="sxs-lookup"><span data-stu-id="e2212-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="e2212-117">I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias @ NomeDominio*.</span><span class="sxs-lookup"><span data-stu-id="e2212-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="e2212-118">L' *alias @ NomeDominio* deve essere l'alias e il dominio dell'utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-118">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="e2212-119">È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="e2212-119">You can collect all the *alias@domainname* folders in a root folder.</span></span> <span data-ttu-id="e2212-120">La cartella radice può contenere solo le cartelle *alias @ DomainName* .</span><span class="sxs-lookup"><span data-stu-id="e2212-120">The root folder can only contain the *alias@domainname* folders.</span></span> <span data-ttu-id="e2212-121">I file allentati nella cartella radice non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e2212-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="e2212-122">La struttura di cartelle per i dati non di Office 365 che si desidera caricare sarebbe simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e2212-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="e2212-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2212-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="e2212-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2212-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="e2212-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2212-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="e2212-126">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.</span><span class="sxs-lookup"><span data-stu-id="e2212-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Struttura di cartelle di caricamento dei dati non Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="e2212-128">Un account assegnato al gruppo di ruoli eDiscovery Manager (e aggiunto come amministratore di eDiscovery).</span><span class="sxs-lookup"><span data-stu-id="e2212-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="e2212-129">Strumenti di archiviazione di Microsoft Azure installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-129">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="e2212-130">Per installare AzCopy, vedere [Introduzione a AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="e2212-130">To install AzCopy, see [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> <span data-ttu-id="e2212-131">Assicurarsi di installare AzCopy nel percorso predefinito, che è **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="e2212-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="e2212-132">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e2212-132">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="e2212-133">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="e2212-133">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="e2212-134">Fare clic su **Revisione set**e quindi selezionare il set di revisione in cui caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-134">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="e2212-135">Se non si dispone di un set di recensioni, è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="e2212-135">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="e2212-136">Nel set di verifica fare clic su **Gestisci Revisione set**e quindi su **Visualizza caricamenti** nel riquadro **dati non di Office 365** .</span><span class="sxs-lookup"><span data-stu-id="e2212-136">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="e2212-137">Fare clic su **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2212-137">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="e2212-139">Il primo passaggio della procedura guidata consente di preparare una posizione di archiviazione di Azure protetta fornita da Microsoft per il caricamento dei file.</span><span class="sxs-lookup"><span data-stu-id="e2212-139">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="e2212-140">Al termine della preparazione, il pulsante **Avanti: carica file** diventa attivo.</span><span class="sxs-lookup"><span data-stu-id="e2212-140">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importazione non Office 365: preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="e2212-142">Fare clic su **Avanti: carica file**.</span><span class="sxs-lookup"><span data-stu-id="e2212-142">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="e2212-143">Nella pagina **Carica file** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2212-143">On the **Upload files** page, do the following:</span></span>

   ![Importazione non Office 365: caricamento di file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="e2212-145">un.</span><span class="sxs-lookup"><span data-stu-id="e2212-145">a.</span></span> <span data-ttu-id="e2212-146">Nella casella **percorso della posizione dei file** verificare o digitare il percorso della cartella principale in cui sono stati archiviati i dati non di Office 365 che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="e2212-146">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="e2212-147">Ad esempio, per il percorso dei file di esempio visualizzati nella **sezione prima di iniziare**, è necessario digitare **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="e2212-147">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="e2212-148">Se si specifica la posizione corretta, il comando AzCopy visualizzato nella casella sotto il percorso viene aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2212-148">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="e2212-149">b.</span><span class="sxs-lookup"><span data-stu-id="e2212-149">b.</span></span> <span data-ttu-id="e2212-150">Fare clic su **copia negli Appunti** per copiare il comando visualizzato nella casella.</span><span class="sxs-lookup"><span data-stu-id="e2212-150">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span> <span data-ttu-id="e2212-151">Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e2212-151">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="e2212-152">I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e2212-152">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

7. <span data-ttu-id="e2212-153">Avviare un prompt dei comandi di Windows, incollare il comando copiato nel passaggio precedente e quindi premere **invio** per avviare il comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="e2212-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="e2212-154">Dopo aver avviato il comando, i file non di Office 365 verranno caricati nel percorso di archiviazione di Azure preparato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="e2212-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importazione non Office 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="e2212-156">Se il comando AzCopy fornito ha esito negativo, fare riferimento a [risoluzione dei problemi AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="e2212-156">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

8. <span data-ttu-id="e2212-157">Tornare al centro sicurezza & conformità e fare clic su **Avanti: elabora file** nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e2212-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="e2212-158">In questo modo viene avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file non di Office 365 caricati nel percorso di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="e2212-158">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="e2212-159">Controllare lo stato di avanzamento dell'elaborazione dei file non di Office 365 nella pagina dei **file di processo** o nella scheda **processi** visualizzando un processo denominato **aggiunta di dati non di Office 365 a un set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="e2212-159">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="e2212-160">Al termine del processo, i nuovi file saranno disponibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e2212-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importazione non Office 365: elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="e2212-162">Al termine dell'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e2212-162">After the processing is finished, you can close the wizard.</span></span>