---
title: Gestione dei record in Microsoft 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Con la gestione dei record in Microsoft 365, è possibile applicare le pianificazioni di conservazione specifiche dell'organizzazione in un piano file per gestire la conservazione, la dichiarazione dei record e la disposizione in supporto per il ciclo di vita del contenuto completo.
ms.openlocfilehash: f399fbf29c549c3b0cba47f82bdb3b508a3c5819
ms.sourcegitcommit: 7f00f765e8fa674ce1c8c66f5b89b6bea45e13ac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "34379213"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="f2a15-103">Gestione dei record in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f2a15-103">Records management in Office 365</span></span>

<span data-ttu-id="f2a15-104">Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record aziendali, legali e HR tra i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="f2a15-104">Organizations of all types require a records-management solution to manage business, legal, and HR records across their corporate data.</span></span> <span data-ttu-id="f2a15-105">La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non sono più di valore o non più obbligatorio ai fini aziendali.</span><span class="sxs-lookup"><span data-stu-id="f2a15-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of  items that are no longer of value or no longer required for business purposes.</span></span>

<span data-ttu-id="f2a15-106">La soluzione di gestione dei record supporta i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f2a15-106">The records-management solution supports the following elements:</span></span> 

-   <span data-ttu-id="f2a15-107">**Etichetta come record**.</span><span class="sxs-lookup"><span data-stu-id="f2a15-107">**Label as a record**.</span></span> <span data-ttu-id="f2a15-108">Pubblicare le etichette di record](labels.md#using-retention-labels-for-records-management) da applicare agli utenti finali o le [etichette di record auto applicanti](labels.md#applying-a-retention-label-automatically-based-on-conditions) agli elementi che contengono informazioni sensibili, parole chiave o tipi di contenuto specifici.</span><span class="sxs-lookup"><span data-stu-id="f2a15-108">Publish [record labels](labels.md#using-retention-labels-for-records-management) to be applied by end users, or [auto-apply record labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to items containing specific sensitive information, keywords or content types.</span></span>

-   <span data-ttu-id="f2a15-109">Stabilire criteri di conservazione e di eliminazione nell'etichetta di record\*\*.</span><span class="sxs-lookup"><span data-stu-id="f2a15-109">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="f2a15-110">Definire i periodi di [conservazione](retention-policies.md#retaining-content-for-a-specific-period-of-time) e disposizione](retention-policies.md#deleting-content-thats-older-than-a-specific-age) in base a diversi fattori, tra cui la data dell'ultima modifica o creazione.</span><span class="sxs-lookup"><span data-stu-id="f2a15-110">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on a variety of factors including the date last modified or created.</span></span>

-   <span data-ttu-id="f2a15-111">Attivare la conservazione basata su eventi\*\* con la [conservazione basata su eventi](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="f2a15-111">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

-   <span data-ttu-id="f2a15-112">**Eseguire la migrazione e gestire il piano di conservazione con il piano file** e usare [gestione del piano di archiviazione](file-plan-manager.md) da inserire nel piano di conservazione esistente oppure crearne di nuovi con descrittori di file e gerarchie in espansione.</span><span class="sxs-lookup"><span data-stu-id="f2a15-112">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

-   <span data-ttu-id="f2a15-113">Rivedere e convalidare la disposizione\*\* con la [revisione della disposizione](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="f2a15-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

-   <span data-ttu-id="f2a15-114">Esaminare gli elementi eliminati con la revisione di disposizione ed esportare un report di disposizione](disposition-reviews.md#export-the-disposition-items) per ulteriori convalide e report.</span><span class="sxs-lookup"><span data-stu-id="f2a15-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

-   <span data-ttu-id="f2a15-115">Impostare autorizzazioni specifiche\*\* per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f2a15-115">**Set specific permissions** for records manager functions in your organization to [have the right access](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f2a15-116">Con la soluzione di gestione dei record in Microsoft 365, è possibile incorporare le pianificazioni di conservazione dell'organizzazione in un piano file per gestire la conservazione, la dichiarazione dei record e la disposizione in supporto per il ciclo di vita del contenuto completo.</span><span class="sxs-lookup"><span data-stu-id="f2a15-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span> 
