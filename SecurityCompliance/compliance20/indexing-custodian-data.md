---
title: Indicizzazione di dati depositaria avanzata
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
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607876"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="462c8-102">Indicizzazione di dati depositaria avanzata</span><span class="sxs-lookup"><span data-stu-id="462c8-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="462c8-p101">Quando un depositaria viene aggiunto a un caso eDiscovery avanzate (anteprima), qualsiasi contenuto in Office 365 che considerati come parzialmente indicizzato è rielaborata affinché sia possibile eseguire ricerche.  Questo processo viene chiamato *indicizzazione avanzata*. Contenuto può essere indicizzati parzialmente per diversi motivi, tra cui l'esistenza di immagini, tipi di file non supportati o quando si verificano indicizzazione limiti della dimensione dei file.  Per ulteriori informazioni sugli elementi indicizzati parzialmente, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span><span class="sxs-lookup"><span data-stu-id="462c8-p101">When a custodian is added to an Advanced eDiscovery (Preview) case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.  This process is called *Advanced indexing*. Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.  To learn more about partially indexed items, see [Partially indexed items in Content Search in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span></span>

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="462c8-107">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="462c8-107">Viewing Advanced indexing results</span></span>

<span data-ttu-id="462c8-p102">Dopo aver completato il processo di indicizzazione avanzato, è possibile ottenere una conoscenza dell'efficacia di effettuare l'elaborazione.  Nella visualizzazione depositaria indicizzazione nel grafico Elenca tutti gli elementi aggiunti all' *indice ibrida*.  L'indice ibrido è dove eDiscovery avanzate (Preview) viene memorizzato il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="462c8-p102">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.  In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.  The hybrid index is where Advanced eDiscovery (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="462c8-p103">Il grafico include inoltre il numero di elementi che richiedono la risoluzione dei problemi e un altro grafico degli errori per tipo di file. Per ulteriori informazioni, vedere [risoluzione dei problemi di errore durante l'elaborazione dei dati](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="462c8-p103">The graph also includes the number of items that require remediation and another graph of errors by file type. For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="462c8-113">Aggiornamento degli indici avanzati per depositari</span><span class="sxs-lookup"><span data-stu-id="462c8-113">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="462c8-p104">Quando un depositaria viene aggiunto a un caso eDiscovery avanzate (anteprima), tutti gli elementi indicizzati parzialmente vengono nuovamente elaborati. Tuttavia, come specificato, elementi indicizzati più parzialmente possono essere aggiunti al cassetta postale dell'utente o account OneDrive.  Se necessario, è possibile aggiornare gli indici.</span><span class="sxs-lookup"><span data-stu-id="462c8-p104">When a custodian is added to an Advanced eDiscovery (Preview) case, all partially indexed items are re-processed. However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.  When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="462c8-p105">Aggiornamento degli indici depositaria è un processo di esecuzione prolungata. È consigliabile non aggiornare gli indici più volte al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="462c8-p105">Updating custodian indexes is a long running process. It's recommended that you don't update indexes more than once per day in a case.</span></span>
