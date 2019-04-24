---
title: Note sulla versione per Advanced eDiscovery (Preview)
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
description: In questo articolo sono contenute le note sulla versione per Advanced eDiscovery (Preview).
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240941"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a><span data-ttu-id="c71da-103">Note sulla versione per Advanced eDiscovery (Preview)</span><span class="sxs-lookup"><span data-stu-id="c71da-103">Release notes for Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="c71da-104">Il programma di anteprima pubblica per Advanced eDiscovery è il modo in cui ottenere un accesso precoce alle funzionalità e agli aggiornamenti imminenti.</span><span class="sxs-lookup"><span data-stu-id="c71da-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="c71da-105">Per ottenere un accesso rapido alle funzionalità più recenti, è sufficiente creare e utilizzare un caso avanzato di eDiscovery (anteprima) nel centro conformità & sicurezza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c71da-105">To get early access to the newest features, just create and use an Advanced eDiscovery (Preview) case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c71da-106">Per ulteriori informazioni, vedere [Create a New Case](create-new-ediscovery-case.md).</span><span class="sxs-lookup"><span data-stu-id="c71da-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="c71da-107">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="c71da-107">Known issues</span></span>

<span data-ttu-id="c71da-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="c71da-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="c71da-109">I dati corrispondenti a un modulo creato prima del 31 gennaio 2019 non saranno disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode.</span><span class="sxs-lookup"><span data-stu-id="c71da-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="c71da-110">I moduli creati dopo questa data saranno disponibili per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c71da-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="c71da-111">Un modulo creato da un utente può comunque ricevere risposte anche dopo che l'utente che ha creato il modulo è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="c71da-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="c71da-112">Tuttavia, i dati corrispondenti per tali risposte (che si sono verificati dopo l'eliminazione della cassetta postale di custode) non saranno disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode.</span><span class="sxs-lookup"><span data-stu-id="c71da-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span>
 
<span data-ttu-id="c71da-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="c71da-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="c71da-114">Se un utente modifica un dominio subito prima dell'eliminazione dell'account utente per il proprietario del dominio, tali modifiche potrebbero non essere disponibili per la ricerca quando si utilizza lo strumento di ricerca in Advanced eDiscovery (Preview) per cercare le cassette postali del custode.</span><span class="sxs-lookup"><span data-stu-id="c71da-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="c71da-115">L'ondeggiamento blocca le modifiche apportate a un ondeggiamento non appena riceve un segnale che l'account è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="c71da-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="c71da-116">Tuttavia, c'è una piccola possibilità che un ondeggiamento può essere modificato prima che questo segnale venga ricevuto.</span><span class="sxs-lookup"><span data-stu-id="c71da-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="c71da-117">Problemi risolti in questa versione</span><span class="sxs-lookup"><span data-stu-id="c71da-117">Issues fixed in this release</span></span>

- <span data-ttu-id="c71da-118">DCR: gestione delle eccezioni per gli elementi non indicizzati e gli elementi orfani</span><span class="sxs-lookup"><span data-stu-id="c71da-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="c71da-119">DCR: notifiche di blocco</span><span class="sxs-lookup"><span data-stu-id="c71da-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="c71da-120">DCR: depositari in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c71da-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="c71da-121">Novità</span><span class="sxs-lookup"><span data-stu-id="c71da-121">What’s new</span></span>

- <span data-ttu-id="c71da-122">**Riprogettata la struttura di spostamento nel centro sicurezza _AMP_ Compliance** – Advanced eDiscovery (Preview) ha un aspetto nuovo.</span><span class="sxs-lookup"><span data-stu-id="c71da-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery (Preview) has a new look and feel.</span></span> <span data-ttu-id="c71da-123">Utilizzare Advanced eDiscovery (Preview) per gestire più del flusso di lavoro del caso.</span><span class="sxs-lookup"><span data-stu-id="c71da-123">Use Advanced eDiscovery (Preview) to manage more of your case workflow.</span></span>

- <span data-ttu-id="c71da-124">**Gestione dei casi** : supporto aggiuntivo per nuovi tipi di case.</span><span class="sxs-lookup"><span data-stu-id="c71da-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="c71da-125">È inoltre possibile selezionare e salvare i casi recenti e preferiti.</span><span class="sxs-lookup"><span data-stu-id="c71da-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="c71da-126">Tenere conto e monitorare le attività all'interno e tra i casi tramite i nuovi dashboard.</span><span class="sxs-lookup"><span data-stu-id="c71da-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="c71da-127">**Gestione dei depositari** : aggiungere e rimuovere utenti come depositari dei dati all'interno di un caso.</span><span class="sxs-lookup"><span data-stu-id="c71da-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="c71da-128">**Integrazione di Exchange, OneDrive e teams** : aggiungere automaticamente la cassetta postale corrente di un utente, l'account OneDrive for business e i siti di Microsoft Teams a un caso.</span><span class="sxs-lookup"><span data-stu-id="c71da-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="c71da-129">**Comunicazioni del custode** – inviare e gestire notifiche di blocco legale per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c71da-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="c71da-130">**Portale custode** – nuovo portale per i depositari per accedere alle notifiche di archiviazione attiva.</span><span class="sxs-lookup"><span data-stu-id="c71da-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="c71da-131">**Deep** indicizzazione: rieseguire la ricerca per indicizzazione degli elementi parzialmente indicizzati su richiesta.</span><span class="sxs-lookup"><span data-stu-id="c71da-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="c71da-132">Correzione degli errori: correzione o download di un **errore** di elaborazione; Questo include il supporto per la correzione di tipi di file di grandi dimensioni, file protetti da password e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="c71da-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="c71da-133">**Miglioramenti alla ricerca** : creare una ricerca identificando i depositari e/o le posizioni.</span><span class="sxs-lookup"><span data-stu-id="c71da-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="c71da-134">**Working sets** – gestire, monitorare e controllare insiemi statici di documenti.</span><span class="sxs-lookup"><span data-stu-id="c71da-134">**Working sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="c71da-135">**Recensione** : utilizzare una visualizzazione nativa, di testo e quasi nativa per esaminare i documenti aggiunti al working set.</span><span class="sxs-lookup"><span data-stu-id="c71da-135">**Review** – Use a native, text, and near-native view to review documents added to your working set.</span></span>

- <span data-ttu-id="c71da-136">**Redigere, tag e** annotazioni – testo di redigere, applicare i tag e creare annotazioni durante la revisione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="c71da-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="c71da-137">**Revisione con tecnologia di analisi**: utilizzare eDiscovery Analytics per individuare, cercare ed eliminare i risultati all'interno di un working set.</span><span class="sxs-lookup"><span data-stu-id="c71da-137">**Analytics-powered review**– Leverage eDiscovery analytics to find, search, and cull results within a working set.</span></span>

- <span data-ttu-id="c71da-138">**Jobs** – verifica lo stato dei processi con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="c71da-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="c71da-139">**Nuove attività di controllo** : monitorare e visualizzare nuove attività di controllo per Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c71da-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>
