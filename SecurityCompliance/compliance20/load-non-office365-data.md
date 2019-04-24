---
title: Caricare dati non Office 365 in un set di lavoro
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2ac12cf8c447e3341724d9e853da0f32b7c232fb
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242943"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="3d4dd-102">Caricare dati non Office 365 in un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="3d4dd-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="3d4dd-103">Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="3d4dd-104">Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un working set, in modo da essere analizzati con Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="3d4dd-105">In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="3d4dd-106">Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="3d4dd-107">Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3d4dd-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="3d4dd-108">Before you begin</span></span>
<span data-ttu-id="3d4dd-109">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="3d4dd-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="3d4dd-110">Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="3d4dd-111">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="3d4dd-112">Un caso di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="3d4dd-113">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias @ NomeDominio* .</span><span class="sxs-lookup"><span data-stu-id="3d4dd-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="3d4dd-114">L' *alias @ DomainName* deve essere Users Office 365 alias and Domain.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="3d4dd-115">È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="3d4dd-116">La cartella radice può contenere solo le cartelle *alias @ DomainName* , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

   <span data-ttu-id="3d4dd-117">La struttura delle cartelle per i dati non di Office 365 che si intende caricare dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3d4dd-117">The folder structure for the non-Office 365 data you plan to upload should look something like the following:</span></span>

   - <span data-ttu-id="3d4dd-118">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d4dd-118">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="3d4dd-119">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d4dd-119">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="3d4dd-120">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d4dd-120">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="3d4dd-121">Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono indirizzi SMTP dei depositari nel caso.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-121">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are SMTP addresses of custodians in the case.</span></span>

![Struttura di cartelle di caricamento dei dati non Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="3d4dd-123">Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-123">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="3d4dd-124">Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3d4dd-124">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="3d4dd-125">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3d4dd-125">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="3d4dd-126">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-126">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="3d4dd-127">Fare clic sulla scheda **working set** , quindi selezionare il working set a cui si desidera caricare i dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-127">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="3d4dd-128">Se non è stato ancora creato un working set, è possibile farlo adesso.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-128">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="3d4dd-129">Infine, fare clic su **Gestisci set di lavoro** e quindi visualizzare i **caricamenti** nella sezione dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-129">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section.</span></span>

2. <span data-ttu-id="3d4dd-130">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-130">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="3d4dd-132">Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-132">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="3d4dd-133">Una volta completata la preparazione, fare clic sul pulsante **Avanti: carica file** .</span><span class="sxs-lookup"><span data-stu-id="3d4dd-133">Once preparation is completed, click the **Next: Upload files** button.</span></span>

![Importazione non Office 365-preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="3d4dd-135">Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-135">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="3d4dd-136">L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-136">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="3d4dd-137">Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="3d4dd-137">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="3d4dd-138">Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** .</span><span class="sxs-lookup"><span data-stu-id="3d4dd-138">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="3d4dd-139">Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-139">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="3d4dd-140">I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-140">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importazione/caricamento di file non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Non Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

> [!NOTE]
> <span data-ttu-id="3d4dd-143">Se il comando AzCopy fornito ha esito negativo, fare riferimento a [risoluzione dei problemi AzCopy in Advanced eDiscovery (Preview)](troubleshooting-azcopy.md) .</span><span class="sxs-lookup"><span data-stu-id="3d4dd-143">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery (Preview)](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="3d4dd-144">Infine, tornare alla conformità & sicurezza e fare clic sul pulsante **Avanti: elabora file** .</span><span class="sxs-lookup"><span data-stu-id="3d4dd-144">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="3d4dd-145">Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-145">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="3d4dd-146">È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel working set.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-146">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="3d4dd-147">Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3d4dd-147">Once processing is complete, you can dismiss the wizard.</span></span>

![File del processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

