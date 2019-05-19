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
description: ''
ms.openlocfilehash: 86d858994f95176ea4d415405c4043f7e7c5308e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155008"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="f9627-102">Caricare dati non Office 365 in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="f9627-102">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="f9627-103">Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="f9627-104">Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un set di revisione in modo che vengano analizzati con Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f9627-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a review set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="f9627-105">In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f9627-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="f9627-106">Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9627-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="f9627-107">Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="f9627-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f9627-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="f9627-108">Before you begin</span></span>

<span data-ttu-id="f9627-109">Se si utilizza la funzionalità carica non Office 365, come descritto in questo articolo, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9627-109">Using the upload Non-Office 365 feature as described in this article requires that you have the following:</span></span>

- <span data-ttu-id="f9627-110">Un abbonamento a Office 365 o Microsoft 365 E5 o un abbonamento E3 con l'abbonamento al componente aggiuntivo per la conformità avanzato.</span><span class="sxs-lookup"><span data-stu-id="f9627-110">An Office 365 or Microsoft 365 E5 subscription or an E3 subscription with the Advanced Compliance add-on subscription.</span></span>

- <span data-ttu-id="f9627-111">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono disporre di una licenza E3 con una licenza per il componente aggiuntivo per la conformità avanzata o con una licenza E5.</span><span class="sxs-lookup"><span data-stu-id="f9627-111">All custodians whose non-Office 365 content will be uploaded must have E3 license with an Advanced Compliance add-on license or have an E5 license.</span></span>

- <span data-ttu-id="f9627-112">Un caso avanzato di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="f9627-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="f9627-113">I depositari devono essere aggiunti al caso prima di caricare i dati non di Office 365 associati.</span><span class="sxs-lookup"><span data-stu-id="f9627-113">Custodians must be added to the case before you upload the non-Office 365 data that's associated to them.</span></span>

- <span data-ttu-id="f9627-114">Tutti i file che verranno caricati devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode.</span><span class="sxs-lookup"><span data-stu-id="f9627-114">All files that will be uploaded must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="f9627-115">I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias @ NomeDominio*.</span><span class="sxs-lookup"><span data-stu-id="f9627-115">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="f9627-116">L' *alias @ NomeDominio* deve essere l'alias e il dominio dell'utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-116">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="f9627-117">È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="f9627-117">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="f9627-118">La cartella radice può contenere solo le cartelle *alias @ DomainName* ; non sono consentiti file sciolti nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="f9627-118">The root folder can only contain the *alias@domainname* folders; loose files aren't allowed in the root folder.</span></span>

   <span data-ttu-id="f9627-119">Ad esempio, la struttura di cartelle per i dati non di Office 365 che si desidera caricare sarebbe simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f9627-119">For example, the folder structure for the non-Office 365 data that you want to upload would be similar to the following:</span></span>

   - <span data-ttu-id="f9627-120">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9627-120">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="f9627-121">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9627-121">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="f9627-122">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9627-122">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="f9627-123">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.</span><span class="sxs-lookup"><span data-stu-id="f9627-123">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Struttura di cartelle di caricamento dei dati non Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="f9627-125">Un account che sia un Manager di eDiscovery o un amministratore di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f9627-125">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>

- <span data-ttu-id="f9627-126">Strumenti di archiviazione di Microsoft Azure installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-126">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="f9627-127">Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="f9627-127">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="f9627-128">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f9627-128">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="f9627-129">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="f9627-129">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="f9627-130">Fare clic sulla scheda **revisione dei set** , quindi selezionare il set di revisione in cui si desidera caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-130">Click the **review sets** tab, then select the review set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="f9627-131">Se non è stato ancora creato un set di revisione, è possibile farlo adesso.</span><span class="sxs-lookup"><span data-stu-id="f9627-131">If you have not already created a review set, you can do so now.</span></span>  <span data-ttu-id="f9627-132">Infine, fare clic su **Gestisci Revisione set** e quindi su **Visualizza caricamenti** nel riquadro dei dati \* \* non Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-132">Finally, click **Manage review set** and then click **View uploads** in the \*\*Non-Office 365 data tile.</span></span>

2. <span data-ttu-id="f9627-133">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9627-133">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="f9627-135">Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="f9627-135">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="f9627-136">Una volta completata la preparazione, fare clic sul pulsante **Avanti: carica file** .</span><span class="sxs-lookup"><span data-stu-id="f9627-136">Once preparation is completed, click the **Next: Upload files** button.</span></span>

   ![Importazione non Office 365-preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="f9627-138">Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="f9627-138">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="f9627-139">L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f9627-139">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9627-140">Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="f9627-140">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="f9627-141">Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** .</span><span class="sxs-lookup"><span data-stu-id="f9627-141">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="f9627-142">Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="f9627-142">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="f9627-143">I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f9627-143">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

   ![Importazione/caricamento di file non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![Non Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="f9627-146">Se il comando AzCopy fornito ha esito negativo, fare riferimento a [risoluzione dei problemi AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="f9627-146">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="f9627-147">Infine, tornare alla conformità & sicurezza e fare clic sul pulsante **Avanti: elabora file** .</span><span class="sxs-lookup"><span data-stu-id="f9627-147">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="f9627-148">Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.</span><span class="sxs-lookup"><span data-stu-id="f9627-148">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="f9627-149">È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="f9627-149">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the review set.</span></span>  <span data-ttu-id="f9627-150">Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f9627-150">Once processing is complete, you can dismiss the wizard.</span></span>

   ![File del processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

