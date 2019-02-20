---
title: Eliminazione dei dati di Office 365 SharePoint Online
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Spiegazione dell'eliminazione dei dati in SharePoint Online.
ms.openlocfilehash: 48b108637e53b8ca4ab18b7b37e2fad7fbbd779c
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090858"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="54efb-103">Eliminazione dei dati di SharePoint online in Office 365</span><span class="sxs-lookup"><span data-stu-id="54efb-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="54efb-p101">SharePoint Online archivia gli oggetti come codice astratto all'interno dei database dell'applicazione. Quando un utente carica un file in SharePoint Online, tale file viene disassemblato e convertito in codice dell'applicazione e archiviato in più tabelle tra più database. In SharePoint Online, tutto il contenuto utilizzato dai caricamenti dei clienti è suddiviso in blocchi, crittografato (potenzialmente con più chiavi AES 256 bit) e distribuito in tutto il datacenter. Per informazioni dettagliate sul processo di blocco e la crittografia, vedere [crittografia nel cloud Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md).</span><span class="sxs-lookup"><span data-stu-id="54efb-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="54efb-p102">In SharePoint Online, gli elementi vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale. Rimangono nel cestino del sito per tutto il tempo, a meno che qualcuno non li elimini o svuoti quel cestino. In tal caso, gli elementi passano al cestino della raccolta siti, in cui restano per il resto dei 93 giorni. Per informazioni su come ripristinare gli elementi eliminati, vedere [ripristinare gli elementi nel cestino di un sito di SharePoint](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [ripristinare gli elementi eliminati dal cestino della raccolta siti](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Il tempo di conservazione del cestino non è configurabile in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="54efb-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="54efb-113">Quando si elimina una raccolta siti, si elimina anche la gerarchia dei siti nell'insieme e tutto il contenuto all'interno di essi:</span><span class="sxs-lookup"><span data-stu-id="54efb-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="54efb-114">Documenti e raccolte documenti</span><span class="sxs-lookup"><span data-stu-id="54efb-114">Documents and document libraries</span></span>
- <span data-ttu-id="54efb-115">Elenchi e dati di elenco</span><span class="sxs-lookup"><span data-stu-id="54efb-115">Lists and list data</span></span>
- <span data-ttu-id="54efb-116">Impostazioni di configurazione del sito</span><span class="sxs-lookup"><span data-stu-id="54efb-116">Site configuration settings</span></span>
- <span data-ttu-id="54efb-117">Informazioni sul ruolo e sulla sicurezza correlate al sito o ai relativi siti secondari</span><span class="sxs-lookup"><span data-stu-id="54efb-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="54efb-118">Siti secondari del sito Web principale, del relativo contenuto e delle informazioni utente</span><span class="sxs-lookup"><span data-stu-id="54efb-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="54efb-119">Se si elimina accidentalmente una raccolta siti, è possibile ripristinarla da un amministratore globale o di SharePoint utilizzando l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54efb-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="54efb-p103">L'eliminazione non consentita si verifica quando un utente elimina gli elementi eliminati dal cestino della raccolta siti, quando scade il periodo di conservazione e di backup oppure quando un amministratore Elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando un utente Elimina (Elimina definitivamente o Elimina in modo definitivo) contenuto da SharePoint Online, vengono eliminate anche tutte le chiavi di crittografia per i blocchi eliminati. I blocchi nei dischi che in precedenza sono stati memorizzati nei blocchi eliminati vengono contrassegnati come inutilizzati e disponibili per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="54efb-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
