---
title: Indicizzazione avanzata dei dati dei responsabili
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
ms.openlocfilehash: f8f1a92f001bf8f9e23f54bbb05fbbcf443bf4b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218666"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="1482f-102">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="1482f-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="1482f-p101">Quando un custode viene aggiunto a un caso avanzato di eDiscovery (Preview), qualsiasi contenuto di Office 365 ritenuto rielaborato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.  Questo processo è denominato *Advanced*indicizzazione. Il contenuto può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, i tipi di file non supportati o l'indicizzazione dei limiti delle dimensioni dei file.  Per ulteriori informazioni sugli elementi parzialmente indicizzati, vedere [gli elementi parzialmente indicizzati in ricerca contenuto in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span><span class="sxs-lookup"><span data-stu-id="1482f-p101">When a custodian is added to an Advanced eDiscovery (Preview) case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.  This process is called *Advanced indexing*. Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.  To learn more about partially indexed items, see [Partially indexed items in Content Search in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span></span>

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="1482f-107">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="1482f-107">Viewing Advanced indexing results</span></span>

<span data-ttu-id="1482f-p102">Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.  Nella visualizzazione di inDicizzazione del custode, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.  L'indice ibrido è la posizione in cui Advanced eDiscovery (Preview) archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="1482f-p102">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.  In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.  The hybrid index is where Advanced eDiscovery (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="1482f-p103">Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="1482f-p103">The graph also includes the number of items that require remediation and another graph of errors by file type. For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="1482f-113">Aggiornamento degli indici avanzati per i depositari</span><span class="sxs-lookup"><span data-stu-id="1482f-113">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="1482f-p104">Quando un custode viene aggiunto a un caso avanzato di eDiscovery (anteprima), tutti gli elementi parzialmente indicizzati vengono rielaborati. Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.  Se necessario, è possibile aggiornare gli indici.</span><span class="sxs-lookup"><span data-stu-id="1482f-p104">When a custodian is added to an Advanced eDiscovery (Preview) case, all partially indexed items are re-processed. However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.  When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="1482f-p105">L'aggiornamento degli indici del custode è un processo di esecuzione prolungato. Si consiglia di non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="1482f-p105">Updating custodian indexes is a long running process. It's recommended that you don't update indexes more than once per day in a case.</span></span>
