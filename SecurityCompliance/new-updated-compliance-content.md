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
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Aggiornamenti recenti a Microsoft 365 content Compliance

Analogamente alle funzionalità del centro conformità di Microsoft 365, il contenuto della guida è sempre in evoluzione. Stiamo creando continuamente nuovi articoli, aggiornando quelli esistenti ed eseguendo modifiche in base ai commenti e suggerimenti. Per vedere cosa c'è di nuovo e aggiornato questo mese, consulta la pagina seguente.

> [!TIP]
> Per rimanere al di sopra degli aggiornamenti delle funzionalità più recenti nel centro conformità Microsoft 365, vedere [What ' s New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="august-2019"></a>2019 agosto

### <a name="auditing"></a>Controllo

[Gestire il controllo delle cassette postali](enable-mailbox-auditing.md#more-information) Aggiornato<br>Sono stati aggiunti dettagli sul modo in cui gli eventi del registro di controllo delle cassette postali sono disponibili solo per gli utenti con licenze E5 o cassette postali in cui il controllo delle cassette postali è stato attivato manualmente Sono inoltre disponibili nuove linee guida sull'utilizzo del cmdlet **Search-MailboxAuditLog** in PowerShell di Exchange Online per eseguire ricerche nel log di controllo delle cassette postali per gli utenti senza licenze E5.

Eseguire [una ricerca nel registro di controllo di Office 365 per la risoluzione dei problemi comuni](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) Aggiornato<br>Nuova sezione sull'utilizzo dell'autenticazione pass-through per esaminare gli accessi riusciti da parte di utenti esterni.

### <a name="content-search--ediscovery"></a>Ricerca di contenuto & eDiscovery

[Configurare il filtro delle autorizzazioni per la ricerca di contenuto](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) Aggiornato<br>Sono stati aggiunti dettagli sull'utilizzo di un elenco di filtri, che consente di aggiungere una cassetta postale e filtri sito a un singolo filtro autorizzazioni di ricerca.

[Ricerca contenuto in Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) Aggiornato<br>Sono stati aggiunti dettagli sulla ricerca delle cassette postali disconnesse o deconcesse.

[Ricerca contenuto in Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) Aggiornato<br>
[Impostare i limiti di conformità per le indagini di eDiscovery in Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) Aggiornato<br>Sono stati aggiunti dettagli a entrambi gli articoli relativi alla ricerca di contenuto in ambienti multi-geo di SharePoint.

### <a name="data-governance"></a>Governance dei dati

[Panoramica dell'archiviazione illimitata in Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) Aggiornato<br>Sono stati aggiunti dettagli sul modo in cui Office 365 aggiunge un massimo di 20 archivi ausiliari per un totale di 1 TB di spazio di archiviazione aggiuntivo.

### <a name="data-investigations"></a>Indagini sui dati

[Eliminare gli elementi dal percorso originale](datainvestigations/delete-items-from-original-locations.md) nuovo<br>Ora disponibile in anteprima, è possibile selezionare gli elementi in un set di evidenze e quindi eliminarli temporaneamente dai percorsi originali in Exchange, SharePoint e OneDrive.

[Gestire un problema di fuoriuscita dei dati in Microsoft 365](datainvestigations/manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) Aggiornato<br>Sono stati aggiunti dettagli sull'utilizzo della nuova caratteristica ' Elimina elementi dalla posizione originale ' per eliminare i dati riversati.

### <a name="permissions"></a>Autorizzazioni

[Autorizzazioni nel centro sicurezza microsoft 365 e microsoft 365 Security Center](permissions-microsoft-365-compliance-security.md) nuovo<br>I nuovi gruppi di ruoli di Azure Active Directory sono stati rilasciati nell'anteprima pubblica.

### <a name="records-management"></a>Gestione dei record

[Panoramica del gestore del piano file (aggiornato)](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br>È stata aggiunta una tabella in cui sono elencati i valori validi da utilizzare nel modello di Excel.

### <a name="supervision"></a>Supervisione

[Criteri di supervisione in Office 365](supervision-policies.md) Aggiornato<br>Il supporto per i gruppi e le liste di distribuzione di Office 365 è stato chiarito, sono state aggiunte indicazioni per le corrispondenze in posta elettronica e allegati e è stato chiarito il supporto di Outlook entro i canali

### <a name="windows-information-protection"></a>Windows Information Protection

[Elenco delle app Microsoft illuminate per l'utilizzo con Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) Aggiornato <br>Microsoft 3D Viewer è ora un'app illuminata.
