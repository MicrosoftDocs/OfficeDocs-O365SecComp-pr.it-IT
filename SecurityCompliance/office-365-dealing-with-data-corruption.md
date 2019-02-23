---
title: Office 365 che si occupano di danneggiamento dei dati
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una spiegazione del danneggiamento dei dati in Office 365 e gli sforzi di prevenzione e ripristino di Microsoft.
ms.openlocfilehash: d33cb298c432db45d560e4c2876d9ac34ab9d6f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216546"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="71827-103">Gestione del danneggiamento dei dati in Office 365</span><span class="sxs-lookup"><span data-stu-id="71827-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="71827-p101">Uno degli aspetti impegnativi dell'esecuzione di un servizio cloud su vasta scala consiste nel gestire il danneggiamento dei dati, in base all'elevato volume di dati e ai sistemi indipendenti. Il danneggiamento dei dati può essere causato da:</span><span class="sxs-lookup"><span data-stu-id="71827-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="71827-106">Bug dell'infrastruttura o dell'applicazione che danneggiano alcuni o tutti lo stato dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="71827-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="71827-107">Problemi relativi all'hardware che determinano la perdita di dati o l'impossibilità di leggere i dati</span><span class="sxs-lookup"><span data-stu-id="71827-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="71827-108">Errori operativi umani</span><span class="sxs-lookup"><span data-stu-id="71827-108">Human operational errors</span></span> 
- <span data-ttu-id="71827-109">Hacker maligni e dipendenti scontenti</span><span class="sxs-lookup"><span data-stu-id="71827-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="71827-110">Eventi imPrevisti nei servizi esterni che causano una perdita di dati</span><span class="sxs-lookup"><span data-stu-id="71827-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="71827-p102">Poiché una maggiore resilienza nell'integrità dei dati comporta meno incidenti di danneggiamento dei dati, Microsoft ha incorporato i meccanismi di protezione di Office 365 per evitare che si verifichino danneggiamenti, nonché sistemi e processi che consentono di recuperare i dati in caso di problemi. I controlli e i processi sono presenti nelle varie fasi del processo di rilascio ingegneristico per aumentare la resilienza rispetto al danneggiamento dei dati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="71827-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="71827-113">Progettazione del sistema</span><span class="sxs-lookup"><span data-stu-id="71827-113">System Design</span></span>
- <span data-ttu-id="71827-114">Organizzazione e struttura del codice</span><span class="sxs-lookup"><span data-stu-id="71827-114">Code organization and structure</span></span> 
- <span data-ttu-id="71827-115">Revisione del codice</span><span class="sxs-lookup"><span data-stu-id="71827-115">Code review</span></span> 
- <span data-ttu-id="71827-116">Unit test, test di integrazione e test di sistema</span><span class="sxs-lookup"><span data-stu-id="71827-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="71827-117">Test/cancelli per cavi di viaggio</span><span class="sxs-lookup"><span data-stu-id="71827-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="71827-p103">Negli ambienti di produzione di Office 365, la replica peer tra i datacenter garantisce che siano sempre presenti più copie live di tutti i dati. Le immagini e gli script standard vengono utilizzati per recuperare i server persi e i dati replicati vengono utilizzati per ripristinare i dati dei clienti. Grazie ai controlli e ai processi di resilienza dei dati incorporati, Microsoft mantiene solo i backup della documentazione del sistema di informazioni di Office 365 (inclusa la documentazione relativa alla sicurezza), utilizzando la replica incorporata in SharePoint Online e il codice interno strumento di repository, Source Depot. La documentazione del sistema è archiviata in SharePoint Online e Source Depot contiene immagini di sistema e applicazioni. Sia SharePoint Online che Source Depot utilizzano il controllo delle versioni e vengono replicati in tempo quasi reale.</span><span class="sxs-lookup"><span data-stu-id="71827-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 