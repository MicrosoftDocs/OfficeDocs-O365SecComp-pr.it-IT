---
title: Caricare i dati non Office 365 in un working set
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 427b4c8c9dfffe351827a6869ae26a5356d646d8
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607916"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="396d1-102">Caricare i dati non Office 365 in un working set</span><span class="sxs-lookup"><span data-stu-id="396d1-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="396d1-p101">Non tutti i documenti che potrebbe essere necessario per l'analisi con Office 365 avanzate eDiscovery risiederanno in Office 365. Con il contenuto Non Office 365 importare funzionalità di eDiscovery avanzate che è possibile caricare documenti che non si trovano in Office 365 in un set di lavoro in modo che viene analizzato con eDiscovery avanzate. Questa procedura viene illustrato come portare i documenti non Office 365 in eDiscovery avanzate per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="396d1-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="396d1-p102">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile richiedere una valutazione di Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="396d1-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="396d1-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="396d1-108">Before you begin</span></span>
<span data-ttu-id="396d1-109">Utilizzando la caratteristica di caricamento Non Office 365, come descritto in questa procedura è necessario disporre:</span><span class="sxs-lookup"><span data-stu-id="396d1-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
* <span data-ttu-id="396d1-110">Un Office 365 E3 con sottoscrizione E5 o componente aggiuntivo di conformità avanzate</span><span class="sxs-lookup"><span data-stu-id="396d1-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
* <span data-ttu-id="396d1-111">Tutti i depositari viene caricato il cui contenuto non Office 365 devono disporre E3 con licenze E5 o componente aggiuntivo di conformità avanzate</span><span class="sxs-lookup"><span data-stu-id="396d1-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
* <span data-ttu-id="396d1-112">Un caso eDiscovery esistente</span><span class="sxs-lookup"><span data-stu-id="396d1-112">An existing eDiscovery case</span></span>
* <span data-ttu-id="396d1-p103">Tutti i file per caricamento raccolte in cartelle in cui vi è una cartella per depositaria e le cartelle è denominato in questo formato *alias@domainname* . *Alias@domainname* deve essere dominio e l'alias di utenti di Office 365. È possibile raccogliere tutte le cartelle *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non deve esistere alcun file separati nella cartella radice</span><span class="sxs-lookup"><span data-stu-id="396d1-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder</span></span>
* <span data-ttu-id="396d1-117">Un account che rappresenta una ricerca eDiscovery Manager o eDiscovery amministratore Microsoft Azure Storage installati gli strumenti in un computer che dispone dell'accesso per la struttura di cartelle del contenuto non Office 365.</span><span class="sxs-lookup"><span data-stu-id="396d1-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>
* <span data-ttu-id="396d1-118">Installare AzCopy, è possibile ottenere questo risultato da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="396d1-118">Install AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="396d1-119">Caricare il contenuto non Office 365 in eDiscovery avanzate</span><span class="sxs-lookup"><span data-stu-id="396d1-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>
1. <span data-ttu-id="396d1-p104">Come eDiscovery Manager o eDiscovery amministratore, aprire eDiscovery avanzate e quindi caso in cui verranno caricati i dati non Office 365.  Fare clic sulla scheda **utilizzo di insiemi** e quindi selezionare il set di lavoro che si desidera caricare i dati Non Office 365.  Se non è già stato creato un gruppo di lavoro, è possibile farlo a questo punto.  Infine, fare clic su **Gestisci meccanismi impostata** il **caricamento Visualizza** nella sezione dati Non Office 365</span><span class="sxs-lookup"><span data-stu-id="396d1-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="396d1-124">Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati Non Office 365.</span><span class="sxs-lookup"><span data-stu-id="396d1-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![Caricamento dei file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="396d1-p105">Il primo passaggio della procedura guidata prepara semplicemente blob Azure protetto per i file da caricare.  Dopo aver preparato compelted, fare clic sul **successivo: caricare i file** pulsante.</span><span class="sxs-lookup"><span data-stu-id="396d1-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![Non Office 365 importazione - preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="396d1-p106">Nel passaggio **caricare i file** , specificare il **percorso dei file**, si tratta in cui si trovano i dati Non Office 365 che si prevede di importazione.  L'impostazione nella posizione corretta assicura AzCopy comando viene aggiornato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="396d1-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="396d1-131">Se non è già installato AzCopy, è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="396d1-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="396d1-p107">Copiare il comando predefinito fare clic sul collegamento **Copia negli Appunti** . Avviare un prompt dei comandi di windows, incollare il comando e premere INVIO.  I file verranno caricati per l'archiviazione di blob Azure sicura per il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="396d1-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Importazione non-Office 365 - caricamento file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Importazione non Office 365 - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="396d1-p108">Infine, tornare al & sicurezza conformità e fare clic sul **successivo: elaborazione dei file** pulsante.  Verrà avviata elaborazione, l'estrazione di testo e l'indicizzazione dei file caricati.  È possibile verificare lo stato di avanzamento dell'elaborazione di seguito o sulla scheda **processi** .  Al termine, i nuovi file sarà disponibili nel set di lavoro.  Una volta completata l'elaborazione, è possibile chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="396d1-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![Importazione non-Office 365 - elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

