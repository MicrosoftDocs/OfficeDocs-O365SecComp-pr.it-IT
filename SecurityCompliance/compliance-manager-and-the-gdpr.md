---
title: Microsoft Compliance Manager e GDPR
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: e41b28972dc2ada5c0591de0e73c04ea3306e039
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649961"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="e77f6-104">Microsoft Compliance Manager e GDPR</span><span class="sxs-lookup"><span data-stu-id="e77f6-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="e77f6-105">Il regolamento generale sulla protezione dei dati (GDPR) emanato dall'Unione europea può influire sulla strategia di conformità e sul mandato azioni specifiche per la gestione delle informazioni relative agli utenti e ai clienti utilizzati in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="e77f6-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="e77f6-106">Impostazioni di privacy dell'utente</span><span class="sxs-lookup"><span data-stu-id="e77f6-106">User Privacy settings</span></span>

<span data-ttu-id="e77f6-107">Alcune normative richiedono che un'organizzazione debba essere in grado di eliminare i dati della cronologia degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e77f6-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="e77f6-108">Compliance Manager fornisce **le funzioni delle impostazioni per la privacy degli utenti** che consentono agli amministratori di:</span><span class="sxs-lookup"><span data-stu-id="e77f6-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="e77f6-109">Cercare un utente</span><span class="sxs-lookup"><span data-stu-id="e77f6-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="e77f6-110">Esportare un report di cronologia dei dati dell'account</span><span class="sxs-lookup"><span data-stu-id="e77f6-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="e77f6-111">Eliminare la cronologia dei dati dell'utente</span><span class="sxs-lookup"><span data-stu-id="e77f6-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="e77f6-112">Cercare un utente</span><span class="sxs-lookup"><span data-stu-id="e77f6-112">Search for a user</span></span>

<span data-ttu-id="e77f6-113">Cercare un account utente:</span><span class="sxs-lookup"><span data-stu-id="e77f6-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="e77f6-114">Immettere l'alias di posta elettronica dell'utente (le informazioni a sinistra del simbolo @) e scegliere il nome del dominio dall'elenco dei suffissi di dominio a destra.</span><span class="sxs-lookup"><span data-stu-id="e77f6-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="e77f6-115">Per le organizzazioni con più domini registrati, controllare il suffisso del nome di dominio per assicurarsi che sia corretto.</span><span class="sxs-lookup"><span data-stu-id="e77f6-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="e77f6-116">Se il nome utente è stato immesso correttamente, selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="e77f6-117">Per gli account utente non restituiti, la pagina Visualizza l' **utente non trovato**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="e77f6-118">Controllare le informazioni sull'indirizzo di posta elettronica dell'utente e apportare le correzioni in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e77f6-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="e77f6-119">Per riprovare, selezionare **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="e77f6-120">Per gli account utente restituiti, il testo del pulsante cambia dalla **ricerca** alla **cancellazione**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="e77f6-121">Ciò indica che l'account utente restituito è il contesto operativo per le funzioni aggiuntive e che queste funzioni sono valide per questo account utente.</span><span class="sxs-lookup"><span data-stu-id="e77f6-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="e77f6-122">Per cancellare i risultati della ricerca e cercare un altro utente, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="e77f6-123">Esportare un report di cronologia dei dati dell'account</span><span class="sxs-lookup"><span data-stu-id="e77f6-123">Export a report of account data history</span></span>

<span data-ttu-id="e77f6-124">Per ogni account utente identificato, è possibile generare un report delle dipendenze collegate a questo account.</span><span class="sxs-lookup"><span data-stu-id="e77f6-124">For each user account identified, you can generate a report of dependencies linked to this account.</span></span> <span data-ttu-id="e77f6-125">Queste informazioni consentono di riassegnare gli elementi dell'azione aperta o di garantire l'accesso alle prove precedentemente caricate.</span><span class="sxs-lookup"><span data-stu-id="e77f6-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="e77f6-126">Per generare ed esportare un report:</span><span class="sxs-lookup"><span data-stu-id="e77f6-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="e77f6-127">Selezionare **Esporta** per generare e scaricare un report degli elementi azione di controllo di Compliance Manager attualmente assegnati all'account utente restituito e l'elenco dei documenti caricati da tale utente.</span><span class="sxs-lookup"><span data-stu-id="e77f6-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="e77f6-128">Se non sono state assegnate azioni o documenti caricati, un messaggio di errore indica che non sono presenti dati per questo utente.</span><span class="sxs-lookup"><span data-stu-id="e77f6-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="e77f6-129">Il report viene scaricato nello sfondo della finestra del browser attiva, se non viene visualizzato un popup per il download che si desidera controllare nella cronologia dei download del browser.</span><span class="sxs-lookup"><span data-stu-id="e77f6-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="e77f6-130">Aprire il documento per visualizzare i dati del report.</span><span class="sxs-lookup"><span data-stu-id="e77f6-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e77f6-131">I dati del report non sono un elenco cronologico che conserva e visualizza le modifiche di stato alla cronologia delle assegnazioni degli elementi di azione.</span><span class="sxs-lookup"><span data-stu-id="e77f6-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="e77f6-132">Il report generato è uno snapshot degli elementi azione di controllo assegnati al momento dell'esecuzione del report (data e timestamp scritti nel report).</span><span class="sxs-lookup"><span data-stu-id="e77f6-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="e77f6-133">Ad esempio, eventuali riassegnazioni successive di elementi azione determinano i diversi dati del rapporto snapshot se il report viene generato di nuovo per lo stesso utente.</span><span class="sxs-lookup"><span data-stu-id="e77f6-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="e77f6-134">Eliminare la cronologia dei dati dell'utente</span><span class="sxs-lookup"><span data-stu-id="e77f6-134">Delete user data history</span></span>

<span data-ttu-id="e77f6-135">Imposta tutti gli elementi azione di controllo assegnati all'utente restituito su' non assegnato '.</span><span class="sxs-lookup"><span data-stu-id="e77f6-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="e77f6-136">Imposta il valore **caricato** per tutti i documenti caricati dall'utente restituito su "rimosso dall'utente".</span><span class="sxs-lookup"><span data-stu-id="e77f6-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="e77f6-137">Per eliminare l'elemento di azione dell'account utente e la cronologia del caricamento del documento:</span><span class="sxs-lookup"><span data-stu-id="e77f6-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="e77f6-138">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-138">Select **Delete**.</span></span>

    <span data-ttu-id="e77f6-139">Viene visualizzata una finestra di dialogo di conferma, "*questo rimuove tutte le assegnazioni di elementi di azione di controllo e la cronologia del caricamento del documento per l'utente selezionato. Questa azione è permanente. Si è sicuri di voler continuare?*"</span><span class="sxs-lookup"><span data-stu-id="e77f6-139">A confirmation dialog is displayed, "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="e77f6-140">Per continuare seleziona **OK**, altrimenti seleziona **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="e77f6-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
