---
title: Scaricare processi di esportazione
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
ms.openlocfilehash: 904bc5f8a6d6cef937d55336e8f383957713769a
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475696"
---
# <a name="download-export-jobs"></a><span data-ttu-id="45caa-102">Scaricare processi di esportazione</span><span class="sxs-lookup"><span data-stu-id="45caa-102">Download export jobs</span></span>

<span data-ttu-id="45caa-103">Tutti i dati esportati vengono aggiunti a un BLOB di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="45caa-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="45caa-104">In questo modo vengono fornite più opzioni per gestire i dati downstream.</span><span class="sxs-lookup"><span data-stu-id="45caa-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="45caa-105">Sono disponibili diversi modi per accedere a un BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="45caa-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="45caa-106">Un metodo consiste nell'utilizzare Esplora archivi di Azure.</span><span class="sxs-lookup"><span data-stu-id="45caa-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="45caa-107">Questo metodo supporta la connessione semplice, l'esplorazione e il download.</span><span class="sxs-lookup"><span data-stu-id="45caa-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="45caa-108">Per ulteriori informazioni, visitare<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="45caa-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="45caa-109">Per scaricare il contenuto dopo il completamento di un processo di esportazione, passare alla scheda Esporta e selezionare un processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="45caa-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="45caa-110">Copiare il testo nella sezione "Locations" del riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="45caa-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="45caa-111">Aprire Esplora archivi di Azure e fare clic sul pulsante "Connetti"</span><span class="sxs-lookup"><span data-stu-id="45caa-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="45caa-112">Selezionare "usa un URI di firma di accesso condiviso" e fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="45caa-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="45caa-113">Incollare il testo percorso nella casella di testo URI e fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="45caa-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="45caa-114">Fare clic su Connetti</span><span class="sxs-lookup"><span data-stu-id="45caa-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="45caa-115">In questo modo verrà aggiunta l'esportazione come oggetto nei contenitori di archiviazione/servizi associati SAS/BLOB.</span><span class="sxs-lookup"><span data-stu-id="45caa-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="45caa-116">Sarà possibile esplorare l'esportazione e scaricare tutto o parti dell'esportazione.</span><span class="sxs-lookup"><span data-stu-id="45caa-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)