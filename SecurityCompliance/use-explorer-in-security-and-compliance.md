---
title: Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/31/2019
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
ms.openlocfilehash: c782e5962164b7d35947befe526c20f7dc0943d5
ms.sourcegitcommit: 691370682825a7601bd4b77d0a8c4b51ed15682f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2019
ms.locfileid: "31014015"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>Utilizzo di Esplora minacce nel centro &amp; sicurezza e conformità

Se l'organizzazione dispone di [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP) ed è necessario disporre delle autorizzazioni necessarie, è possibile utilizzare l'esploratore di minacce (denominato anche Esplora risorse) per identificare e analizzare le minacce. Per utilizzare Esplora risorse, nel centro sicurezza &amp; e conformità, accedere a **gestione** \> **** minacce.

![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Explorer è uno strumento potente e quasi in tempo reale che consente ai team di operazioni di sicurezza di analizzare e rispondere alle &amp; minacce nel centro sicurezza e conformità. Di seguito sono riportate alcune delle operazioni che è possibile eseguire:
- [Vedere malware rilevato dalle funzionalità di sicurezza di Office 365](#see-malware-detected-in-email-by-technology)
- [Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto](#view-data-about-phishing-urls-and-click-verdict)
- [Avviare un processo di analisi e risposta automatizzato da una visualizzazione in Esplora risorse](#start-automated-investigation-and-response)
- ... [e altro ancora](#more-ways-to-use-explorer)!

## <a name="see-malware-detected-in-email-by-technology"></a>Vedere malware rilevato in posta elettronica dalla tecnologia

Si supponga di voler vedere il malware rilevato nella posta elettronica e la tecnologia in Office 365. A tale scopo, utilizzare la visualizzazione malware di > per la [posta elettronica](threat-explorer-views.md#email--malware) di Esplora risorse.

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Scegliere**malware** **tramite posta elettronica** > dal menu **Visualizza** .<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. Fare clic su **mittente**e quindi scegliere**tecnologia di rilevamento**di **base** > .<br/>Le tecnologie di rilevamento sono ora disponibili come filtri per il report.<br/>![Tecnologie di rilevamento di malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. Selezionare un'opzione e quindi fare clic sul pulsante Aggiorna per applicare il filtro.<br/>![Tecnologia di rilevamento selezionata](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

Il rapporto viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione di tecnologia selezionata. Da qui, è possibile eseguire un'ulteriore analisi.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto

Si supponga di voler vedere tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL che sono stati consentiti, bloccati e ignorati.  L'identificazione degli URL a cui è stato fatto clic richiede [collegamenti sicuri ATP](atp-safe-links.md). (Accertarsi di aver configurato e applicato i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) agli utenti per la protezione e la registrazione di clic di verdetti da ATP Safe Links.) Per esaminare gli URL di phishing nei messaggi e fare clic su URL nei messaggi di phishing, utilizzare la visualizzazione [phishing > di posta elettronica](threat-explorer-views.md#email--phish) di Esplora risorse.

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Nel menu **Visualizza** scegliere **posta elettronica** > **phishing**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailPhishMenu.png)<br/>
3. Fare clic su **sender**e quindi scegliere **urls** > ****.
4. Selezionare una o più opzioni, ad esempio **bloccate** e **bloccate**, e quindi fare clic sul pulsante **Aggiorna** per applicare il filtro.<br/>![URL e fare clic su verdetti](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

Il rapporto viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL seguente:
1. Gli URL **principali** sono gli URL contenuti nei messaggi che sono stati filtrati fino a e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione posta elettronica di phishing, in genere l'elenco conterrà URL legittimi. I pirati inFormatici includono una combinazione di URL buoni e cattivi nei loro messaggi per cercare di farli recapitare, ma renderà i collegamenti dannosi più interessanti per l'utente a cui fare clic. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica (Nota: questa colonna non viene visualizzata per semplificare la visualizzazione).
2. I **clic principali** sono gli URL con collegamenti sicuri che sono stati selezionati, ordinati in base al numero di clic totale (la colonna non viene visualizzata per semplificare la visualizzazione). Numeri totali per colonna indicano i collegamenti sicuri fare clic su conteggio verdetto per ogni URL selezionato. Nella visualizzazione posta elettronica di phishing, questi sono più spesso collegamenti sospetti o malevoli, ma possono includere URL puliti che si verificano nei messaggi di phishing. Gli URL che fanno clic su collegamenti non spostati non verranno visualizzati qui.

Le due tabelle degli URL mostrano gli URL principali nei messaggi di posta elettronica di phishing in base allo stato di recapito e visualizzano gli URL che sono stati bloccati (o sono stati visitati nonostante un avviso), in modo da poter capire quali collegamenti negativi sono stati ricevuti dagli utenti e interagito con gli utenti. Da qui, è possibile eseguire un'ulteriore analisi. Ad esempio, al di sotto del grafico, è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione. 

![URL di Esplora risorse bloccati](media/ExplorerPhishClickVerdictURLs.png) 

Selezionare un URL per visualizzare informazioni più dettagliate. Si noti che nella finestra di dialogo URL a comparsa, il filtro nei messaggi di posta elettronica viene rimosso per visualizzare la visualizzazione completa dell'esposizione dell'URL nell'ambiente in uso. In questo modo è possibile filtrare i messaggi di posta elettronica in Esplora risorse a quelli di cui si è preoccupati, individuare URL specifici che sono potenziali minacce e quindi espandere la propria comprensione dell'esposizione all'URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL al Visualizzazione di Esplora risorse.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come posta indesiderata, non inDesiderata o phishing tramite il [componente aggiuntivo segnala messaggio per Outlook e Outlook sul Web](enable-the-report-message-add-in.md). A tale scopo, utilizzare la visualizzazione [> di posta elettronica segnalaTa dall'utente](threat-explorer-views.md#email--user-reported) di Esplora risorse.

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce.
2. Nel menu **Visualizza** scegliere la **posta elettronica** > **segnalata dall'utente**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. Fare clic su **mittente**e quindi scegliere**tipo di report**di **base** > .
4. Selezionare un'opzione, ad esempio **phishing**, e quindi fare clic sul pulsante **Aggiorna** . <br/>![Phishing segnalati dall'utente](media/EmailUserReportedReportType.png)<br/> 

Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come tentativo di phishing. È possibile utilizzare queste informazioni per eseguire un'ulteriore analisi e, se necessario, regolare i [criteri di anti-phishing ATP](set-up-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Avviare l'analisi e la risposta automatizzata

(Nuovo!) L' [analisi e la risposta automatizzate](automated-investigation-response-office.md), aggiunte di recente a ATP piano 2, possono salvare il team delle operazioni di sicurezza molto tempo e fatica nell'analisi e nell'attenuazione degli attacchi cibernetici. Oltre a configurare gli avvisi che possono attivare un PlayBook per la sicurezza, è possibile avviare un processo di analisi e risposta automatizzato da una visualizzazione di Esplora risorse. 

Per ulteriori informazioni, vedere [esempio: un amministratore della sicurezza attiva un'indagine da Esplora minacce](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer"></a>Altre modalità di utilizzo di Esplora risorse

Oltre agli scenari descritti in questo articolo, sono disponibili molte altre opzioni per la creazione di report con Esplora risorse. 
- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Ottenere una panoramica delle visualizzazioni in Esplora minacce](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

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

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
