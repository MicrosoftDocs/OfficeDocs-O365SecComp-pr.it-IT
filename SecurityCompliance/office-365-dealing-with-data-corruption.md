---
title: Office 365 a che fare con il danneggiamento dei dati
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Spiegazione del danneggiamento dei dati in Office 365 e le attività di Microsoft di prevenzione e ripristino.
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530892"
---
# <a name="dealing-with-data-corruption-in-office-365"></a><span data-ttu-id="21320-103">Gestire il danneggiamento dei dati in Office 365</span><span class="sxs-lookup"><span data-stu-id="21320-103">Dealing with Data Corruption in Office 365</span></span>

<span data-ttu-id="21320-p101">Uno degli aspetti complessi dell'esecuzione di un servizio cloud su larga scala viene illustrato come gestire il danneggiamento dei dati, dato il volume elevato di dati e sistemi indipendenti. Il danneggiamento dei dati può essere causato da:</span><span class="sxs-lookup"><span data-stu-id="21320-p101">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems. Data corruption can be caused by:</span></span>
- <span data-ttu-id="21320-106">Infrastruttura di applicazioni o di bug, corrompere alcune o tutte lo stato dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="21320-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span> 
- <span data-ttu-id="21320-107">Hardware che consentono di perdita di dati o l'impossibilità di leggere i dati dei problemi</span><span class="sxs-lookup"><span data-stu-id="21320-107">Hardware issues that result in lost data or an inability to read data</span></span> 
- <span data-ttu-id="21320-108">Errori operativi risorse umani</span><span class="sxs-lookup"><span data-stu-id="21320-108">Human operational errors</span></span> 
- <span data-ttu-id="21320-109">Malintenzionati e dipendenti malintenzionati</span><span class="sxs-lookup"><span data-stu-id="21320-109">Malicious hackers and disgruntled employees</span></span> 
- <span data-ttu-id="21320-110">Problemi di servizi esterni che causare una perdita di dati</span><span class="sxs-lookup"><span data-stu-id="21320-110">Incidents in external services that result in some loss of data</span></span> 

<span data-ttu-id="21320-p102">Poiché maggiore resilienza sull'integrità dei dati significa meno interventi di danneggiamento dei dati, Microsoft ha creato in meccanismi di protezione di Office 365 per evitare il danneggiamento da avvenga, nonché sistemi e processi che consentono di ripristinare i dati in caso contrario. Controlli e i processi esistono all'interno di varie fasi del processo di rilascio engineering per aumentare la resilienza dal danneggiamento dei dati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="21320-p102">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Office 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does. Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>
- <span data-ttu-id="21320-113">Struttura del sistema</span><span class="sxs-lookup"><span data-stu-id="21320-113">System Design</span></span>
- <span data-ttu-id="21320-114">Le organizzazioni di codice e struttura</span><span class="sxs-lookup"><span data-stu-id="21320-114">Code organization and structure</span></span> 
- <span data-ttu-id="21320-115">Revisione del codice</span><span class="sxs-lookup"><span data-stu-id="21320-115">Code review</span></span> 
- <span data-ttu-id="21320-116">Unit test, test di integrazione e test di sistema</span><span class="sxs-lookup"><span data-stu-id="21320-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="21320-117">Viaggio cavi/controlli di test</span><span class="sxs-lookup"><span data-stu-id="21320-117">Trip wires tests/gates</span></span> 

<span data-ttu-id="21320-p103">In ambienti di produzione di Office 365, la replica peer tra Data Center garantisce che non vi siano sempre più copie live di tutti i dati. Script e immagini standard consentono di ripristinare perse server e i dati replicati viene utilizzati per ripristinare i dati dei clienti. A causa di dati incorporati resilienza dei controlli e i processi, con cui Microsoft gestisce i backup solo della documentazione di Office 365 information system (inclusa la documentazione di protezione), utilizzando la replica incorporata in SharePoint Online e il codice interno strumento di archivio, deposito di origine. Documentazione relativa al sistema verrà archiviato in SharePoint Online e deposito di origine contiene le immagini di sistema e delle applicazioni. SharePoint Online e deposito di origine di utilizzare il controllo delle versioni e replicato in quasi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="21320-p103">Within Office 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data. Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data. Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Office 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot. System documentation is stored in SharePoint Online, and Source Depot contains system and application images. Both SharePoint Online and Source Depot use versioning and are replicated in near real-time.</span></span> 