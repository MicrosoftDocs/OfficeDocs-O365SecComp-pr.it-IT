---
title: Novità nel centro conformità di Microsoft 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti. Scopri cosa c'è di nuovo e aggiornato in questo mese.
ms.openlocfilehash: e7600c2f84d0b591c6114c2a61c77d8e2c664056
ms.sourcegitcommit: 9fd606e8d912f4507fbcd9f1fcb9dfcfd20de08b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980802"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a><span data-ttu-id="b3da9-105">Aggiornamenti recenti a Microsoft 365 content Compliance</span><span class="sxs-lookup"><span data-stu-id="b3da9-105">Recent updates to Microsoft 365 compliance content</span></span>

<span data-ttu-id="b3da9-106">Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione.</span><span class="sxs-lookup"><span data-stu-id="b3da9-106">Just like features in the Microsoft 365 compliance center, our help content is always evolving.</span></span> <span data-ttu-id="b3da9-107">Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="b3da9-107">We’re continuously creating new articles, updating existing ones, and making changes based on your feedback.</span></span> <span data-ttu-id="b3da9-108">Per vedere cosa c'è di nuovo e aggiornato questo mese, consulta la pagina seguente.</span><span class="sxs-lookup"><span data-stu-id="b3da9-108">Take a look below to see what’s new and updated this month.</span></span>

> [!TIP]
> <span data-ttu-id="b3da9-109">Per rimanere al di sopra degli aggiornamenti delle funzionalità più recenti nel centro conformità Microsoft 365, vedere [What ' s New in the microsoft 365 Compliance Center](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="b3da9-109">To stay on top of the latest feature updates in the Microsoft 365 compliance center, check out [What's new in the Microsoft 365 compliance center](whats-new.md).</span></span>

## <a name="august-2019"></a><span data-ttu-id="b3da9-110">2019 agosto</span><span class="sxs-lookup"><span data-stu-id="b3da9-110">August 2019</span></span>

### <a name="auditing"></a><span data-ttu-id="b3da9-111">Controllo</span><span class="sxs-lookup"><span data-stu-id="b3da9-111">Auditing</span></span>

<span data-ttu-id="b3da9-112">[Gestire il controllo delle cassette postali](enable-mailbox-auditing.md#more-information) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-112">[Manage mailbox auditing](enable-mailbox-auditing.md#more-information) (updated)</span></span><br><span data-ttu-id="b3da9-113">Sono stati aggiunti dettagli sul modo in cui gli eventi del registro di controllo delle cassette postali sono disponibili solo per gli utenti con licenze E5 o cassette postali in cui il controllo delle cassette postali è stato attivato manualmente Sono inoltre disponibili nuove linee guida sull'utilizzo del cmdlet **Search-MailboxAuditLog** in PowerShell di Exchange Online per eseguire ricerche nel log di controllo delle cassette postali per gli utenti senza licenze E5.</span><span class="sxs-lookup"><span data-stu-id="b3da9-113">Added details about how mailbox audit log events are available only for users with E5 licenses or mailboxes where mailbox auditing was manually turned on by an admin. Also new guidance about using the **Search-MailboxAuditLog** cmdlet in Exchange Online PowerShell to search the mailbox audit log for users without E5 licenses.</span></span>

<span data-ttu-id="b3da9-114">Eseguire [una ricerca nel registro di controllo di Office 365 per la risoluzione dei problemi comuni](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-114">[Search the Office 365 audit log to troubleshoot common scenarios](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) (updated)</span></span><br><span data-ttu-id="b3da9-115">Nuova sezione sull'utilizzo dell'autenticazione pass-through per esaminare gli accessi riusciti da parte di utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="b3da9-115">New section about using pass-through authentication to investigate successful logins by external users.</span></span>

### <a name="content-search--ediscovery"></a><span data-ttu-id="b3da9-116">Ricerca di contenuto & eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b3da9-116">Content Search & eDiscovery</span></span>

<span data-ttu-id="b3da9-117">[Configurare il filtro delle autorizzazioni per la ricerca di contenuto](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-117">[Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) (updated)</span></span><br><span data-ttu-id="b3da9-118">Sono stati aggiunti dettagli sull'utilizzo di un elenco di filtri, che consente di aggiungere una cassetta postale e filtri sito a un singolo filtro autorizzazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b3da9-118">Added details about using a filters list, which lets you add a mailbox and site filters to a single search permissions filter.</span></span>

<span data-ttu-id="b3da9-119">[Ricerca contenuto in Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-119">[Content search in Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) (updated)</span></span><br><span data-ttu-id="b3da9-120">Sono stati aggiunti dettagli sulla ricerca delle cassette postali disconnesse o deconcesse.</span><span class="sxs-lookup"><span data-stu-id="b3da9-120">Added details about searching disconnected or de-licensed mailboxes.</span></span>

<span data-ttu-id="b3da9-121">[Ricerca contenuto in Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-121">[Content search in Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) (updated)</span></span><br>
<span data-ttu-id="b3da9-122">[Impostare i limiti di conformità per le indagini di eDiscovery in Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-122">[Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) (updated)</span></span><br><span data-ttu-id="b3da9-123">Sono stati aggiunti dettagli a entrambi gli articoli relativi alla ricerca di contenuto in ambienti multi-geo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b3da9-123">Added details to both articles about searching for content in SharePoint multi-geo environments.</span></span>

### <a name="data-governance"></a><span data-ttu-id="b3da9-124">Governance dei dati</span><span class="sxs-lookup"><span data-stu-id="b3da9-124">Data governance</span></span>

<span data-ttu-id="b3da9-125">[Panoramica dell'archiviazione illimitata in Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-125">[Overview of unlimited archiving in Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) (updated)</span></span><br><span data-ttu-id="b3da9-126">Sono stati aggiunti dettagli sul modo in cui Office 365 aggiunge un massimo di 20 archivi ausiliari per un totale di 1 TB di spazio di archiviazione aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b3da9-126">Added details about how Office 365 adds a maximum of 20 auxiliary archives for a total of 1 TB of additional storage.</span></span>

### <a name="data-investigations"></a><span data-ttu-id="b3da9-127">Indagini sui dati</span><span class="sxs-lookup"><span data-stu-id="b3da9-127">Data investigations</span></span>

<span data-ttu-id="b3da9-128">[Eliminare gli elementi dal percorso originale](datainvestigations/delete-items-from-original-locations.md) nuovo</span><span class="sxs-lookup"><span data-stu-id="b3da9-128">[Delete items from their original location](datainvestigations/delete-items-from-original-locations.md) (new)</span></span><br><span data-ttu-id="b3da9-129">Ora disponibile in anteprima, è possibile selezionare gli elementi in un set di evidenze e quindi eliminarli temporaneamente dai percorsi originali in Exchange, SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b3da9-129">Now available in preview, you can select items in an evidence set and then soft-delete them from their original locations in Exchange, SharePoint, and OneDrive.</span></span>

<span data-ttu-id="b3da9-130">[Gestire un problema di fuoriuscita dei dati in Microsoft 365](datainvestigations/manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-130">[Manage a data spillage incident in Microsoft 365](datainvestigations/manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) (updated)</span></span><br><span data-ttu-id="b3da9-131">Sono stati aggiunti dettagli sull'utilizzo della nuova caratteristica ' Elimina elementi dalla posizione originale ' per eliminare i dati riversati.</span><span class="sxs-lookup"><span data-stu-id="b3da9-131">Added details about using the new ‘Delete items from their original location’ feature to delete spilled data.</span></span>

### <a name="permissions"></a><span data-ttu-id="b3da9-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b3da9-132">Permissions</span></span>

<span data-ttu-id="b3da9-133">[Autorizzazioni nel centro sicurezza microsoft 365 e microsoft 365 Security Center](permissions-microsoft-365-compliance-security.md) nuovo</span><span class="sxs-lookup"><span data-stu-id="b3da9-133">[Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](permissions-microsoft-365-compliance-security.md) (new)</span></span><br><span data-ttu-id="b3da9-134">I nuovi gruppi di ruoli di Azure Active Directory sono stati rilasciati nell'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="b3da9-134">New Azure Active Directory role groups were released to public preview.</span></span>

### <a name="records-management"></a><span data-ttu-id="b3da9-135">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b3da9-135">Records management</span></span>

[<span data-ttu-id="b3da9-136">Panoramica del gestore del piano file (aggiornato)</span><span class="sxs-lookup"><span data-stu-id="b3da9-136">Overview of file plan manager (updated)</span></span>](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br><span data-ttu-id="b3da9-137">È stata aggiunta una tabella in cui sono elencati i valori validi da utilizzare nel modello di Excel.</span><span class="sxs-lookup"><span data-stu-id="b3da9-137">Added a table that lists the valid values to be used in the Excel template.</span></span>

### <a name="supervision"></a><span data-ttu-id="b3da9-138">Supervisione</span><span class="sxs-lookup"><span data-stu-id="b3da9-138">Supervision</span></span>

<span data-ttu-id="b3da9-139">[Criteri di supervisione in Office 365](supervision-policies.md) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-139">[Supervision policies in Office 365](supervision-policies.md) (updated)</span></span><br><span data-ttu-id="b3da9-140">Il supporto per i gruppi e le liste di distribuzione di Office 365 è stato chiarito, sono state aggiunte indicazioni per le corrispondenze in posta elettronica e allegati e è stato chiarito il supporto di Outlook entro i canali</span><span class="sxs-lookup"><span data-stu-id="b3da9-140">Clarified Office 365 group and distribution list support, added guidance for keyword matches in both email and attachments, and clarified Outlook support within Teams channels.</span></span>

### <a name="windows-information-protection"></a><span data-ttu-id="b3da9-141">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="b3da9-141">Windows Information Protection</span></span>

<span data-ttu-id="b3da9-142">[Elenco delle app Microsoft illuminate per l'utilizzo con Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) Aggiornato</span><span class="sxs-lookup"><span data-stu-id="b3da9-142">[List of enlightened Microsoft apps for use with Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) (updated)</span></span> <br><span data-ttu-id="b3da9-143">Microsoft 3D Viewer è ora un'app illuminata.</span><span class="sxs-lookup"><span data-stu-id="b3da9-143">Microsoft 3D Viewer is now an enlightened app.</span></span>
