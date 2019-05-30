---
title: Esplora minacce (e rilevamenti in tempo reale)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Informazioni su Esplora risorse (e sui rilevamenti in tempo reale) &amp; nel centro sicurezza e conformità.
ms.openlocfilehash: 030f866c5e86daa3dc543bddae7152e19f377d3b
ms.sourcegitcommit: 6c0fcb82178a4ac26375545f328389a6852a81be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "34490532"
---
# <a name="threat-explorer-and-real-time-detections"></a>Esplora minacce (e rilevamenti in tempo reale)

Se l'organizzazione dispone [di office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) ed è necessario disporre delle [autorizzazioni necessarie](#required-licenses-and-permissions), è possibile individuare **esploratori** o rilevamenti in **tempo reale** (in precedenza rapporti in *tempo reale* , [vedere Novità](#new-features-in-real-time-detections)!). Nel centro sicurezza & Compliance, passare a **gestione minacce**, quindi scegliere **Esplora risorse** o rilevamenti in **tempo reale**. 

|Con ATP piano 2, è possibile vedere:  |Con ATP piano 1, è possibile visualizzare le informazioni seguenti:  |
|---------|---------|
|![Esplora minacce](media/threatmgmt-explorer.png)      |![Rilevamenti in tempo reale](media/threatmgmt-realtimedetections.png)         |

Con Esplora risorse (o rilevamenti in tempo reale), si dispone di un report potente che consente al team di operazioni di sicurezza di analizzare e rispondere alle minacce in modo efficace ed efficiente e assomiglia all'immagine seguente: 

![Passare a gestione \> minacce](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con questo rapporto, è possibile:
- [Vedere malware rilevato dalle funzionalità di sicurezza di Office 365](#see-malware-detected-in-email-by-technology)
- [Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto](#view-data-about-phishing-urls-and-click-verdict)
- [Avviare un processo di analisi e risposta automatizzato da una visualizzazione in Esplora risorse](#start-automated-investigation-and-response) (Solo ATP piano 2)
- ... [Esaminare messaggi di posta elettronica dannosi e altro ancora](#more-ways-to-use-explorer-or-real-time-detections)!

## <a name="new-features-in-real-time-detections"></a>Nuove funzionalità nei rilevamenti in tempo reale

Per i clienti di Office 365 ATP Plan 1, il rapporto sui rilevamenti in *tempo reale* è stato precedentemente definito *rapporti in tempo reale*. Oltre alla modifica del nome, vengono implementate diverse nuove funzionalità e miglioramenti:

- Nella visualizzazione phishing, è possibile visualizzare ulteriori dettagli sugli URL rilevati tramite [collegamenti sicuri di ATP](atp-safe-links.md). I nuovi dettagli e funzionalità includono:
  - URL nei messaggi di posta elettronica
  - Filtro in base alle informazioni sull'URL
  - Informazioni sugli URL visualizzati nei grafici dati
  - Data e ora di clic dei dati relativi ai clic nei messaggi

- Ogni volta che c'è una modifica in un URL fare clic su verdetto, verrà visualizzato un avviso. URL fare clic su verdetti possono variare quando la reputazione di un URL cambia dopo la detonazione o quando un utente protetto da collegamenti sicuri ATP sostituisce un [avviso di collegamenti sicuri ATP](atp-safe-links-warning-pages.md).  
 
Questi miglioramenti consentono agli amministratori della sicurezza dell'organizzazione di visualizzare più dettagli rispetto a prima. Gli amministratori della sicurezza possono visualizzare le informazioni sui domini URL, gli URL mancanti, fare clic su verdetti e altro ancora, quindi regolare i criteri ATP di Office 365 in modo appropriato.

> [!NOTE]
> Anche se queste funzionalità sono in anteprima, i dati URL saranno disponibili per un numero limitato di giorni. 

## <a name="see-malware-detected-in-email-by-technology"></a>Vedere malware rilevato in posta elettronica dalla tecnologia

Si supponga di voler vedere il malware rilevato nella posta elettronica, tramite la tecnologia Office 365. A tale scopo, utilizzare la visualizzazione malware di > per la [posta elettronica](threat-explorer-views.md#email--malware) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce (o rilevamenti in **tempo reale**). In questo esempio viene utilizzato Esplora.

2. Scegliere**malware** **tramite posta elettronica** > dal menu **Visualizza** .<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailMalwareMenu.png)<br/>

3. Fare clic su **mittente**e quindi scegliere**tecnologia di rilevamento**di **base** > .<br/>Le tecnologie di rilevamento sono ora disponibili come filtri per il report.<br/>![Tecnologie di rilevamento di malware](media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. Selezionare un'opzione e quindi fare clic sul pulsante **Aggiorna** per applicare il filtro.<br/>![Tecnologia di rilevamento selezionata](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

Il rapporto viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione di tecnologia selezionata. Da qui, è possibile eseguire un'ulteriore analisi.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visualizzare i dati relativi agli URL di phishing e fare clic su verdetto

Si supponga di voler visualizzare i tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL consentiti, bloccati e ignorati. L'identificazione degli URL che sono stati cliccati richiede la configurazione di [collegamenti sicuri ATP](atp-safe-links.md) . Assicurarsi di aver configurato i criteri per i [collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) per la protezione e la registrazione di un clic dei verdetti da ATP Safe Links. 

Per esaminare gli URL di phishing nei messaggi e fare clic su URL nei messaggi di phishing, utilizzare la visualizzazione [phishing > di posta elettronica](threat-explorer-views.md#email--phish) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce (o rilevamenti in **tempo reale**). In questo esempio viene utilizzato Esplora.

2. Nel menu **Visualizza** scegliere **posta elettronica** > **phishing**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewEmailPhishMenu.png)<br/>

3. Fare clic su **sender**e quindi scegliere **urls** > ****.

4. Selezionare una o più opzioni, ad esempio **bloccate** e **bloccate**, e quindi fare clic sul pulsante **Aggiorna** che si trova nella stessa riga delle opzioni per applicare il filtro. (Non aggiornare la finestra del browser.)<br/>![URL e fare clic su verdetti](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    Il rapporto viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del rapporto:

   1. Gli URL **principali** sono gli URL contenuti nei messaggi che sono stati filtrati fino a e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione posta elettronica di phishing, in genere l'elenco conterrà URL legittimi. I pirati informatici includono una combinazione di URL buoni e cattivi nei messaggi per cercare di farli recapitare, ma renderà i collegamenti dannosi più interessanti per l'utente da fare clic su. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica (Nota: questa colonna non viene visualizzata per semplificare la visualizzazione).

   2. I **clic principali** sono gli URL con collegamenti sicuri che sono stati selezionati, ordinati in base al numero di clic totale (la colonna non viene visualizzata per semplificare la visualizzazione). Numeri totali per colonna indicano i collegamenti sicuri fare clic su conteggio verdetto per ogni URL selezionato. Nella visualizzazione posta elettronica di phishing, questi sono più spesso URL sospetti o dannosi, ma possono includere URL puliti presenti nei messaggi di phishing. Gli URL che fanno clic su collegamenti non spostati non verranno visualizzati qui.
   
   Le due tabelle degli URL mostrano gli URL principali nei messaggi di posta elettronica di phishing tramite l'azione e la posizione di recapito e visualizzano gli URL che sono stati bloccati (o sono stati visitati nonostante un avviso), in modo da poter capire quali potenziali collegamenti non validi sono stati ricevuti dagli utenti e interagito con gli utenti. Da qui, è possibile eseguire un'ulteriore analisi. Ad esempio, al di sotto del grafico, è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.
   
   ![URL di Esplora risorse bloccati](media/ExplorerPhishClickVerdictURLs.png)
   
   Selezionare un URL per visualizzare informazioni più dettagliate. Si noti che nella finestra di dialogo URL a comparsa, il filtro nei messaggi di posta elettronica viene rimosso per visualizzare la visualizzazione completa dell'esposizione dell'URL nell'ambiente in uso. In questo modo è possibile filtrare i messaggi di posta elettronica in Esplora risorse a quelli di cui si è preoccupati, individuare URL specifici che sono potenziali minacce e quindi espandere la propria comprensione dell'esposizione all'URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL al Visualizzazione di Esplora risorse.

## <a name="review-email-messages-reported-by-users"></a>Esaminare i messaggi di posta elettronica segnalati dagli utenti

Si supponga di voler visualizzare i messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come posta indesiderata, non indesiderata o phishing tramite il [componente aggiuntivo per Outlook e Outlook sul Web](enable-the-report-message-add-in.md). A tale scopo, utilizzare la visualizzazione del [messaggio di posta elettronica > visualizzato dall'utente](threat-explorer-views.md#email--user-reported) di Esplora risorse (o rilevamenti in tempo reale).

1. Nel centro sicurezza & Compliance ([https://protection.office.com](https://protection.office.com)), scegliere **gestione** > **** minacce (o rilevamenti in **tempo reale**). In questo esempio viene utilizzato Esplora.

2. Nel menu **Visualizza** scegliere la **posta elettronica** > **segnalata dall'utente**.<br/>![Menu Visualizza per Esplora risorse](media/ExplorerViewMenuEmailUserReported.png)<br/>

3. Fare clic su **mittente**e quindi scegliere**tipo di report**di **base** > .

4. Selezionare un'opzione, ad esempio **phishing**, e quindi fare clic sul pulsante **Aggiorna** . <br/>![Phishing segnalati dall'utente](media/EmailUserReportedReportType.png)<br/> 

Il rapporto viene aggiornato per visualizzare i dati relativi ai messaggi di posta elettronica che gli utenti dell'organizzazione hanno segnalato come tentativo di phishing. È possibile utilizzare queste informazioni per eseguire un'ulteriore analisi e, se necessario, regolare i [criteri di anti-phishing ATP](set-up-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Avviare l'analisi e la risposta automatizzata

> [!NOTE]
> Le funzionalità di ricerca e risposta automatizzate sono disponibili in **office 365 ATP piano 2** e **Office 365 E5**.

(Nuovo!) L' [analisi e la risposta automatizzate](automated-investigation-response-office.md) sono in grado di salvare il team delle operazioni di sicurezza molto tempo e sforzi per analizzare e mitigare gli attacchi cibernetici. Oltre a configurare gli avvisi che possono attivare un PlayBook per la sicurezza, è possibile avviare un processo di analisi e risposta automatizzato da una visualizzazione di Esplora risorse. 

Per ulteriori informazioni, vedere [esempio: un amministratore della sicurezza attiva un'analisi da Esplora risorse](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Altre modalità di utilizzo di Esplora risorse (o rilevamenti in tempo reale)

Oltre agli scenari descritti in questo articolo, sono disponibili molte altre opzioni per la creazione di report con Esplora risorse (o rilevamenti in tempo reale). 
- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Ottenere una panoramica delle visualizzazioni in Esplora minacce (e rilevamenti in tempo reale)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

È necessario disporre di [Office 365 ATP](office-365-atp.md) per ottenere rilevamenti di Esplora risorse o in tempo reale.
- Explorer è incluso in Office 365 ATP piano 2. 
- Il rapporto sui rilevamenti in tempo reale è incluso in Office 365 ATP Plan 1.

Per visualizzare e utilizzare esplorazioni o rilevamenti in tempo reale, è necessario disporre delle autorizzazioni appropriate, ad esempio quelle concesse a un amministratore della sicurezza o a un lettore di sicurezza. 

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
  
