---
title: Eliminazione dei dati in linea di SharePoint di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una spiegazione dell'eliminazione dei dati in SharePoint Online.
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411162"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="b8640-103">Eliminazione di dati in linea di SharePoint in Office 365</span><span class="sxs-lookup"><span data-stu-id="b8640-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="b8640-p101">SharePoint Online, gli oggetti vengono memorizzate come astratto codice nel database dell'applicazione. Quando un utente carica un file in SharePoint Online, tale file disassemblato e convertito nel codice dell'applicazione e archiviati in più tabelle su più database. In SharePoint Online, tutto il contenuto che carica un cliente viene suddiviso in parti crittografate (potenzialmente con più chiavi di crittografia AES 256 bit) e distribuito nel datacenter. Per informazioni dettagliate sul processo di suddivisione in blocchi di crittografia, vedere [crittografia nel Cloud Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8640-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="b8640-p102">In SharePoint Online, gli elementi vengono mantenuti per 93 giorni dal momento in cui che sono state eliminate dalla posizione originale. Rimanere nel Cestino del sito tutto il tempo, a meno che non li elimina da quest'ultimo o un utente Svuota il Cestino secondario. In tal caso, gli elementi di passare alla raccolta siti del Cestino, dove rimanere per il resto di 93 giorni. Per informazioni sul ripristino degli elementi eliminati, vedere [ripristino di elementi nel Cestino di un sito di SharePoint](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [il ripristino degli elementi dal Cestino raccolta siti eliminati](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Il periodo di mantenimento Cestino non può essere configurato in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b8640-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="b8640-113">Quando si elimina una raccolta siti, che si desidera eliminare anche la gerarchia dei siti nell'insieme e tutto il contenuto al loro interno:</span><span class="sxs-lookup"><span data-stu-id="b8640-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="b8640-114">Documenti e raccolte documenti</span><span class="sxs-lookup"><span data-stu-id="b8640-114">Documents and document libraries</span></span>
- <span data-ttu-id="b8640-115">Elenchi e dati</span><span class="sxs-lookup"><span data-stu-id="b8640-115">Lists and list data</span></span>
- <span data-ttu-id="b8640-116">Impostazioni di configurazione del sito</span><span class="sxs-lookup"><span data-stu-id="b8640-116">Site configuration settings</span></span>
- <span data-ttu-id="b8640-117">Ruoli e informazioni sulla sicurezza relativi al sito o i relativi siti secondari</span><span class="sxs-lookup"><span data-stu-id="b8640-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="b8640-118">Siti secondari di informazioni di sito Web, il contenuto e utente principale</span><span class="sxs-lookup"><span data-stu-id="b8640-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="b8640-119">Se accidentalmente si elimina una raccolta siti, può essere ripristinato da un globale o SharePoint admin utilizzando l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b8640-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="b8640-p103">Disco rigido eliminazione si verifica quando un utente elimina gli elementi eliminati dal Cestino, della raccolta siti quando scadono i periodi di conservazione e di backup oppure quando l'amministratore elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando un utente rigido Elimina (Elimina in modo permanente o Elimina) contenuto di SharePoint Online, tutte le chiavi di crittografia per i blocchi eliminati vengono eliminate. I blocchi su dischi che precedentemente memorizzate blocchi eliminati vengono contrassegnati come non utilizzati e disponibili per riutilizzare.</span><span class="sxs-lookup"><span data-stu-id="b8640-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
