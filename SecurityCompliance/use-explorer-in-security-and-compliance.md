---
title: Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Informazioni su Explorer (denominato anche Esplora minacce) nel centro sicurezza &amp; e conformità.
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732259"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità

Se l'organizzazione dispone di [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)e si dispone delle autorizzazioni necessarie, è possibile utilizzare l'esploratore di minacce per identificare e analizzare le minacce. Ad esempio, è possibile identificare ed eliminare messaggi di posta elettronica dannosi che sono stati recapitati oppure vedere malware rilevati dalle funzionalità di sicurezza di Office 365. L'esploratore di minacce (noto anche come esploratore) è uno strumento potente quasi in tempo reale che consente ai team di operazioni di sicurezza di analizzare e rispondere &amp; alle minacce nel centro sicurezza e conformità.
  
![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
Per utilizzare Esplora risorse, nel centro &amp; sicurezza e conformità, accedere a **gestione** \> **** minacce.

> [!IMPORTANT]
> Office 365 Threat Intelligence è ora Office 365 Advanced Threat Protection piano 2, insieme a ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
      
## <a name="explorer-overview"></a>Panoramica di Esplora risorse

Se nell'organizzazione sono presenti le [funzionalità di analisi e risposta](office-365-ti.md) alle minacce di Office 365 (inclusa in ATP piano 2) e si dispone delle autorizzazioni necessarie, è possibile utilizzare l'esploratore di minacce (denominato anche Esplora risorse) per identificare e analizzare le minacce. Nel centro sicurezza &amp; e conformità, accedere a **gestione** \> **** minacce.

![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

In questo articolo vengono descritte alcune operazioni che è possibile eseguire con Esplora risorse (sono disponibili molte altre possibilità):

- [Vedere quali tipi di malware sono stati rilevati nella posta elettronica](#see-malware-detected-in-email-by-technology)e dalla tecnologia di protezione dalle minacce (protezione antimalware, allegati sicuri di ATP e così via)

- [Visualizzare i dati relativi ai collegamenti di phishing (URL)](#view-data-about-phishing-urls-and-click-verdict)e quali sono i verdetti di clic (gli URL sono stati bloccati, consentiti o visitati nonostante gli avvisi)

- [Esaminare i messaggi di posta elettronica segnalati come posta indesiderata, non indesiderata o phishing](#review-email-messages-reported-by-users)e identificare eventuali tendenze (ad esempio un numero di messaggi più grande del solito segnalati come phishing) 

## <a name="see-malware-detected-in-email-by-technology"></a>Vedere malware rilevato in posta elettronica dalla tecnologia

Si supponga di voler vedere il malware rilevato nella posta elettronica e la tecnologia in Office 365. A tale scopo, utilizzare la visualizzazione malware di > per la [posta elettronica](threat-explorer-views.md#email--malware) di Esplora risorse.

1. In Office 365 Security & compliance Center ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Scegliere**malware** **tramite posta elettronica** > dal menu **Visualizza** .<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. Fare clic su **mittente**e quindi scegliere**tecnologia di rilevamento**di **base** > .<br/>Le tecnologie di rilevamento sono ora disponibili come filtri per il report.<br/>![Tecnologie di rilevamento di malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. Selezionare un'opzione e quindi fare clic sul pulsante Aggiorna per applicare il filtro.<br/>![Tecnologia di rilevamento selezionata](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

Il rapporto viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione di tecnologia selezionata. Da qui, è possibile eseguire un'ulteriore analisi.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto

Si supponga di voler vedere tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL che sono stati consentiti, bloccati e ignorati. A tale scopo, utilizzare la visualizzazione [_GT_ phishing di posta elettronica](threat-explorer-views.md#email--phish) di Esplora risorse.

1. In Office 365 Security & compliance Center ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Nel menu **Visualizza** scegliere **posta elettronica** > **phishing**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailPhishMenu.png)<br/>
3. Fare clic su **sender**e quindi scegliere **urls** > ****.
4. Selezionare una o più opzioni, ad esempio **bloccate** e **bloccate**, e quindi fare clic sul pulsante **Aggiorna** per applicare il filtro.<br/>![URL e fare clic su verdetti](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

Il rapporto viene aggiornato per visualizzare gli URL di phishing rilevati nel messaggio di posta elettronica che sono stati bloccati (o visitati nonostante un avviso), insieme allo stato di recapito della posta elettronica. Da qui, è possibile eseguire un'ulteriore analisi. Ad esempio, al di sotto del grafico, è possibile visualizzare gli URL principali che sono stati bloccati nella posta elettronica dell'organizzazione. 

![URL di Esplora risorse bloccati](media/ExplorerPhishClickVerdictURLs.png) 

Selezionare un URL per visualizzare informazioni più dettagliate.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come posta indesiderata, non inDesiderata o phishing tramite il [componente aggiuntivo segnala messaggio per Outlook e Outlook sul Web](enable-the-report-message-add-in.md). A tale scopo, utilizzare la visualizzazione [> di posta elettronica segnalaTa dall'utente](threat-explorer-views.md#email--user-reported) di Esplora risorse.

1. In Office 365 Security & compliance Center ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Nel menu **Visualizza** scegliere la **posta elettronica** > **segnalata dall'utente**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. Fare clic su **mittente**e quindi scegliere**tipo di report**di **base** > .
4. Selezionare un'opzione, ad esempio **phishing**, e quindi fare clic sul pulsante **Aggiorna** . <br/>![Phishing segnalati dall'utente](media/EmailUserReportedReportType.png)<br/> 

Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come tentativo di phishing. È possibile utilizzare queste informazioni per eseguire un'ulteriore analisi e, se necessario, regolare i [criteri di anti-phishing ATP](set-up-anti-phishing-policies.md).

## <a name="theres-more"></a>Sono disponibili altre informazioni.

Oltre ai tre scenari descritti in questo articolo, sono disponibili numerosi scenari di creazione di report con Esplora risorse. Di seguito sono riportati alcuni esempi:

- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)

- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

- [Ottenere una panoramica delle visualizzazioni in Esplora minacce](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a>Come ottenere Esplora risorse

Explorer è incluso in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md). 

Per visualizzare e utilizzare Esplora risorse, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza. 

- Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:
    - Gestione organizzazione
    - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ())
    - Lettore di sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a>Argomenti correlati

- [Indagine automatizzata e risposta (aria)](automated-investigation-response-office.md)

- [Visualizzazioni di Esplora minacce](threat-explorer-views.md)

- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
