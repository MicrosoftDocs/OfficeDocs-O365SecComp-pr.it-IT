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
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 50fcf679b5cd17a079765bfca5435088bef4c06e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217686"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="969a8-102">Caricare dati non Office 365 in un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="969a8-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="969a8-p101">Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365. Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un working set, in modo da essere analizzati con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="969a8-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="969a8-p102">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile richiedere una valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="969a8-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="969a8-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="969a8-108">Before you begin</span></span>
<span data-ttu-id="969a8-109">Se si utilizza la funzionalità carica non Office 365 come descritto in questa procedura, è necessario disporre di:</span><span class="sxs-lookup"><span data-stu-id="969a8-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="969a8-110">Un Office 365 E3 con un componente aggiuntivo di conformità avanzato o un abbonamento E5.</span><span class="sxs-lookup"><span data-stu-id="969a8-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="969a8-111">Tutti i depositari il cui contenuto non Office 365 verrà caricato devono avere E3 con licenze di componenti aggiuntivi o E5 con Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="969a8-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="969a8-112">Un caso di eDiscovery esistente.</span><span class="sxs-lookup"><span data-stu-id="969a8-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="969a8-p103">Tutti i file per il caricamento raccolti in cartelle in cui è presente una cartella per ogni custode e il nome delle cartelle è in questo formato *alias @ NomeDominio* . L' *alias @ DomainName* deve essere Users Office 365 alias and Domain. È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice. La cartella radice può contenere solo le cartelle *alias @ DomainName* , non devono essere presenti file liberi nella cartella radice.</span><span class="sxs-lookup"><span data-stu-id="969a8-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="969a8-117">Un account che sia uno eDiscovery Manager o eDiscovery Administrator Microsoft Azure Storage Tools installato su un computer che ha accesso alla struttura di cartelle di contenuto non Office 365.</span><span class="sxs-lookup"><span data-stu-id="969a8-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="969a8-118">Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="969a8-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="969a8-119">Caricare il contenuto non Office 365 in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="969a8-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="969a8-p104">Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.  Fare clic sulla scheda **working set** , quindi selezionare il working set a cui si desidera caricare i dati non di Office 365.  Se non è stato ancora creato un working set, è possibile farlo adesso.  Infine, fare clic su **Gestisci set di lavoro** e quindi visualizzare i **caricamenti** nella sezione dati non di Office 365</span><span class="sxs-lookup"><span data-stu-id="969a8-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="969a8-124">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.</span><span class="sxs-lookup"><span data-stu-id="969a8-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="969a8-p105">Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.  Dopo la preparazione, fare clic sul pulsante **Avanti: carica file** .</span><span class="sxs-lookup"><span data-stu-id="969a8-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Importazione non Office 365-preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="969a8-p106">Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.  L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="969a8-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="969a8-131">Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="969a8-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="969a8-p107">Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** . Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.  I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="969a8-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importazione/caricamento di file non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Non Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="969a8-p108">Infine, tornare alla conformità & sicurezza e fare clic sul pulsante **Avanti: elabora file** .  Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.  È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel working set.  Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="969a8-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![File del processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

