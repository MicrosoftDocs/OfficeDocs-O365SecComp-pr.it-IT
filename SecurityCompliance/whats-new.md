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
description: Aggiungiamo continuamente nuove funzionalità al centro conformità di Microsoft 365, risolvendo i problemi che vengono apportati e modificando in base ai commenti e suggerimenti. Scoprire cosa è stato fino a questo mese.
ms.openlocfilehash: b3adf13fe662640c2dbc21eea6a48e2629a1113c
ms.sourcegitcommit: 9fd606e8d912f4507fbcd9f1fcb9dfcfd20de08b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980432"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Novità nel centro conformità di Microsoft 365

Aggiungiamo continuamente nuove funzionalità al [centro conformità di Microsoft 365](microsoft-365-compliance-center.md), risolvendo i problemi che vengono apportati e modificando in base ai commenti e suggerimenti. Per sapere cosa è disponibile per l'utente, vedere di seguito. Alcune funzionalità vengono distribuite a velocità diverse per i clienti. Se non si vede ancora una funzionalità, provare ad aggiungersi alla [versione mirata](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Interessato a cosa succede in altri centri di amministrazione? Consultare questi articoli:<br>[Novità dell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[Novità dell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="august-2019"></a>2019 agosto

### <a name="data-investigations"></a>Indagini sui dati

Quando si esegue un'analisi dei dati, è ora possibile eliminare gli elementi dai percorsi originali. Questo significa che è possibile eliminare gli elementi da cassette postali di Exchange, siti di SharePoint e account di OneDrive nell'organizzazione. Dal momento che gli elementi sono stati raccolti come prova, è possibile che vengano conservate copie del gruppo di prove, in modo da poter indagare ulteriormente o conservare come riferimento. [Altre informazioni](datainvestigations/delete-items-from-original-locations.md)

## <a name="july-2019"></a>2019 luglio

### <a name="new-admin-roles"></a>Nuovi ruoli di amministratore

Sono stati rilasciati due nuovi ruoli di amministratore che consentono di gestire la sicurezza e la conformità nell'org. Dillo a tutti i tuoi amici.

- **Amministratore dei dati di conformità**. Gli utenti che dispongono di questo ruolo dispongono delle autorizzazioni per proteggere e monitorare i dati nel centro conformità di Microsoft 365, nell'interfaccia di amministrazione di Microsoft 365 e in Azure. Possono anche gestire tutto l'interfaccia di amministrazione di Exchange, Compliance Manager, teams & interfaccia di amministrazione di Skype for business e creare ticket di supporto per Azure e Microsoft 365.
- **Operatore di sicurezza**. Gli utenti che dispongono di questo ruolo possono gestire gli avvisi e disporre dell'accesso globale in sola lettura alle funzionalità correlate alla sicurezza, inclusi tutti gli elementi presenti in Microsoft 365 Security Center, Azure Active Directory, Identity Protection, Privileged Identity Management e Office 365 Centro sicurezza & conformità.

[Ulteriori informazioni su questi ruoli](https://docs.microsoft.com/office365/securitycompliance/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>Ricerca e filtro per i report

Non è più possibile scorrere un mare di report per trovare quelli desiderati. È ora possibile cercare i report (basati sui rispettivi titoli) e filtrare su categorie quali "label" e "Compliance" e fonti quali "Office 365" e "Microsoft cloud app Security".

![Acquisizione dello schermo dei pulsanti di ricerca e del filtro per i report con un filtro applicato](media/mcc_report_filtering.png)

### <a name="help-content"></a>Contenuto della Guida

Tirare su una sedia, prendere una tazza di caffè e lasciare che la nostra ultima conformità documenti di spazzare via.

**Advanced eDiscovery**
- [Esaminare le conversazioni in Advanced eDiscovery](compliance20/conversation-review-sets.md) Nuovo
- [Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery](compliance20/troubleshooting-azcopy.md)
- [Caricare dati non Office 365 in un insieme da rivedere](compliance20/load-non-office365-data.md)
- [Correzione degli errori durante l'elaborazione dei dati](compliance20/error-remediation.md)

**Archiviazione dei dati di terze parti**
- [Configurare un connettore per archiviare i dati di Bloomberg istantanei in Office 365](archive-instant-bloomberg-data.md)

**Controllo**
- [Controllare la condivisione per identificare risorse condivise con utenti esterni](use-sharing-auditing.md)
- [Guida di riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)
- [Risoluzione dei problemi relativi all'API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api)
- [Eseguire una ricerca nel log di controllo nel centro sicurezza & Compliance](search-the-audit-log-in-security-and-compliance.md)

**Crittografia**
- [Aggiornamento alle nuove funzionalità di Office 365 Message Encryption](legacy-information-for-message-encryption.md)

**Classificazione**
- [Creare tipi di informazioni riservate personalizzate con classificazione esatta basata sulla corrispondenza dei dati](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

**Governance dei dati**
- [Panoramica dei criteri di conservazione](retention-policies.md)

**Supervisione**
- [Criteri di supervisione in Office 365](supervision-policies.md)