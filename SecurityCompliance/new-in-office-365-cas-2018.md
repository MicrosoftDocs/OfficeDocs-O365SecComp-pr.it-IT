---
title: Novità di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Vedere cosa rilasciati durante 2018 per la protezione di Office 365 Cloud App
ms.openlocfilehash: f206273b0eff63e6740d80cd2550ae9fcec9a41c
ms.sourcegitcommit: 38ba284b793b080b77d9c9d94ae5a0b6c1ba689b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "29579814"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>Aggiornamenti di sicurezza di applicazione Cloud di Office 365 durante 2018

## <a name="office-365-cloud-app-security-release-138"></a>Versione di Office 365 Cloud App sicurezza 138

*Rilasciato il 23 dicembre 2018*

**In seguito [Microsoft Cloud App Security versione 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **Caricare l'accesso automatico con Docker su Windows** Protezione App cloud per Windows 10 supporta il caricamento automatico log ([Compresi i creatori di aggiornamento](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e versioni successive) e Windows Server ([versione 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709) e versioni successive) con Docker su Windows. [In questo articolo](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows) per ulteriori informazioni e configurare Docker, vedere.  

- **Integrazione del flusso di Microsoft** Protezione App cloud è ora integrato con [Microsoft flusso](https://docs.microsoft.com/flow/getting-started) per fornire playbooks di automazione e orchestrazione avviso personalizzato. [In questo articolo](https://docs.microsoft.com/cloud-app-security/flow-integration) per ulteriori informazioni e configurare l'integrazione con Microsoft Flow, vedere. 

## <a name="office-365-cloud-app-security-release-137"></a>Versione di Office 365 Cloud App sicurezza 137

*Rilasciati l'8 dicembre 2018*

**In seguito [Microsoft Cloud App Security versione 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **Sono stati aggiunti il supporto per Dynamics** Protezione di applicazione cloud ora incluso il supporto per le attività di Microsoft Dynamics supportati nel Registro di controllo di Office 365. 

- **Testine backup-nuova terminologia!** Per chiarezza è stato modificato il nome della funzionalità autorizzazioni App: viene ora chiamato App OAuth. 

## <a name="office-365-cloud-app-security-release-136"></a>Versione di Office 365 Cloud App sicurezza 136

*Rilasciato il 25 novembre 2018*

**In seguito [Microsoft Cloud App Security versione 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **Aggiornamenti di individuazione cloud** Il parser log personalizzato è stato migliorato per supportare aggiuntive e il traffico web più complesso i registri formati. Come parte di questi utenti miglioramenti ora può inserire intestazioni personalizzato per i file di registro CSV creati, utilizzare i delimitatori speciali per i file di chiave valore, del processo di formato di file del Registro di sistema e altro ancora.

- **Nuovo criterio di rilevamento anomalia: regole di manipolazione di posta in arrivo sospetti** Questo criterio profiles all'ambiente e gli avvisi di trigger quando sospette regole di eliminazione o spostamento dei messaggi o le cartelle vengono impostate su posta in arrivo dell'utente. Ciò potrebbe indicare che l'account dell'utente viene compromesso, che i messaggi vengono viene nascosto intenzionalmente e la cassetta postale viene utilizzata per distribuire la posta indesiderata o malware nell'organizzazione.

- **Supporto per i gruppi di criteri di autorizzazione delle app** Protezione di applicazione cloud offre la possibilità di definire criteri di autorizzazione delle app in modo più granulare, in base alle appartenenze ai gruppi di utenti autorizzati delle app. Ad esempio, gli amministratori possono decidere di impostare un criterio che consente di revocare App non comune se si richiede di autorizzazioni elevate, solo se gli utenti autorizzati le autorizzazioni sia membro del gruppo administrators.

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Protezione di Office 365 Cloud App rilascia 133, 134 e 135

*Rilasciato ottobre-novembre 2018*

**In seguito [Microsoft Cloud App Security versione 133, 134 e 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **Nuovi criteri di rilevamento anomalia** sono distribuzione gradualmente:
    
    - Il nuovo criterio **exfiltration dati per le applicazioni unsanctioned** viene attivato automaticamente per ricevere avvisi quando un utente o l'indirizzo IP viene utilizzata un'applicazione non viene negata per eseguire un'attività che è simile a un tentativo di accesso alle informazioni exfiltrate dall'organizzazione.
    
    - Il nuovo criterio di **più attività VM Elimina** l'ambiente di profili e genera avvisi quando gli utenti eliminano più macchine virtuali in una singola sessione, rispetto alla linea di base nella propria organizzazione.

- **Individuazione cloud supporto per i filtri** La funzionalità di Cloud App sicurezza Cloud individuazione ora con supporto migliorato per il parser di registro di sistema i filtri.

## <a name="office-365-cloud-app-security-release-131"></a>Versione di Office 365 Cloud App sicurezza 131

*Rilasciato il 16 settembre 2018*

**In seguito [Microsoft Cloud App Security versione 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **Automaticamente revocare le autorizzazioni per App OAuth rischioso** È ora possibile controllare quali App OAuth gli utenti abbiano accesso al, revoca dell'autorizzazione di app per le applicazioni di OAuth su Office. Quando si crea un criterio di autorizzazione delle App, è ora possibile impostare il criterio da revocare l'autorizzazione dell'app.

- **Individuazione cloud parser incorporato aggiuntivi supportati** Individuazione cloud supporta il formato del registro Forcepoint Web protezione Cloud.
  
## <a name="office-365-cloud-app-security-release-130"></a>Versione di Office 365 Cloud App sicurezza 130

*Rilasciato il 5 settembre 2018*

**In seguito [Microsoft Cloud App Security versione 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nuova barra dei menu** Per offrire un'esperienza di amministrazione più coerenza tra prodotti Microsoft 365 e consentono di eseguire il pivot più facilmente tra le soluzioni di protezione di Microsoft, la barra dei menu portale Cloud App protezione è spostato e il lato sinistro dello schermo. Questa struttura coerente esperienza utile per orientare familiarità quando si passa da un portale di protezione di Microsoft a un altro.<br/>![Barra dei menu nella sicurezza App Cloud di Office](media/OCAS-MenuBar.png)<br/>

- **Punteggio app OAuth impatto** È possibile inviare commenti e suggerimenti team la protezione applicazione Cloud per confermare se non esiste un'app OAuth individuata all'interno dell'organizzazione che sembra dannoso. Questa nuova funzionalità consente di far parte della community protezione e migliorare analisi e OAuth app rischio punteggio. Per ulteriori informazioni, vedere [gestire OAuth App](manage-app-permissions-in-ocas.md).

- **Parser di individuazione di nuovi Cloud** Parser di individuazione Cloud supportano ora iboss Secure Cloud Gateway e Sophos XG.

## <a name="office-365-cloud-app-security-release-128"></a>Versione di Office 365 Cloud App sicurezza 128

*Rilasciato il 5 agosto 2018* 
  
**In seguito [Microsoft Cloud App Security versione 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **App OAuth tra più applicazioni** Per le app OAuth è ora possibile escludere o approvare più applicazioni in una singola azione. Ad esempio, è possibile esaminare tutte le applicazioni che dispongono dell'autorizzazione per gli utenti dell'organizzazione, selezionare tutte le applicazioni che si desidera escludere e fare clic su app di esclusione per revocare il consenso tutti concesso e non è più che consente agli utenti di concedere l'autorizzazione per tali applicazioni. Per ulteriori informazioni, vedere [apps gestire OAuth con Office 365 Cloud App sicurezza](manage-app-permissions-in-ocas.md). 
    
- **Nuova query suggerite: applicazioni basate su cloud PILR pronto** Esiste una nuova query consigliata per consentire di identificare rilevati delle applicazioni che vengono PILR pronto. Come è noto, PILR ha recentemente è diventato una priorità superiore per gli amministratori di sicurezza. Questa query consente di identificare le applicazioni che vengono PILR pronto semplice e limitare i rischi per la valutazione dei rischi delle App non. Per utilizzare la nuova query nel dashboard di **Individuazione Cloud** , nella scheda **applicazioni Discovered** scegliere **query** > **applicazioni basate su cloud PILR pronto**.<br/>![Query App cloud PILR pronto](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Versione di Office 365 Cloud App sicurezza 126

*Rilasciato il 7 luglio 2018* 
  
**In seguito [Microsoft Cloud App Security versione 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Correzione automatica per le attività di sospette** È ora possibile impostare azioni di correzione automatica per sessione sospetta attivata in base ai criteri di rilevamento anomalia. Questo miglioramento consente di ricevere un avviso in modo istantaneo quando si verifica una violazione della e applicare automaticamente le azioni di governance, ad esempio sospendere utente. Per ulteriori informazioni, vedere [criteri di rilevamento anomalia nella sicurezza App Cloud di Office 365](anomaly-detection-policies-in-ocas.md).
    
- **Rilevamento automatico delle App OAuth rischioso** Oltre a indagare esistente delle App OAuth connesso all'ambiente, sicurezza App Cloud di Office 365 ora consente di impostare le notifiche automatiche per informare l'utente quando un'app OAuth soddisfa determinati criteri. Ad esempio, è possibile automaticamente essere avvisati quando vi sono applicazioni che richiedono un livello di autorizzazione elevata e sono stati autorizzati da più di 50 utenti. Per ulteriori informazioni, vedere [apps gestire OAuth con Office 365 Cloud App sicurezza](manage-app-permissions-in-ocas.md).
    
- **Supporto di gestione gestiti Provider di servizi di protezione (MSSP)** Protezione di Office 365 Cloud App ora offre un'esperienza migliore gestione a MSSPs e consente di configurare i partner esterni in qualità di amministratori con uno dei ruoli attualmente disponibili in Office 365 Cloud App sicurezza. Inoltre, agli amministratori dei diritti di accesso a uno o più tenant ora possono facilmente pivot tra il tenant. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Versione di Office 365 Cloud App sicurezza 124

*Rilasciati il 10 giugno 2018* 
  
**In seguito [Microsoft Cloud App Security versione 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Distribuzioni nell'ambito** Le organizzazioni aziendali in modo granulare è possono determinare quali utenti per monitorare e proteggere in base all'appartenenza. Questa funzionalità consente di selezionare gli utenti le cui attività non verranno visualizzate per una qualsiasi delle applicazioni protette. Livello di ambito di monitoraggio è particolarmente utile per la conformità e licenze. Alcune regole di conformità necessitano di evitare il monitoring agli utenti di alcune nazioni a causa di normative locali. E, è possibile monitorare un numero di utenti la possibilità di mantenersi rientrano nei valori delle licenze sicurezza App Cloud di Office 365. 
    
- **Nuovo server di posta elettronica** Il server di posta elettronica per la protezione di Office 365 Cloud App è stato modificato e utilizza gli intervalli di indirizzi IP diversi. Per assicurarsi che è possibile ottenere le notifiche, aggiungere i nuovi indirizzi IP per la proprietà consentite protezione da posta indesiderata. Per le organizzazioni che personalizzano le notifiche, Cloud App sicurezza è possibile ottenere questo per utente mediante MailChimp, un servizio di posta elettronica di terze parti. Per l'elenco di indirizzi IP del server posta elettronica e le istruzioni per l'attivazione di lavoro con MailChimp, vedere [requisiti di rete (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) e [le impostazioni di posta elettronica (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Versione di Office 365 Cloud App sicurezza 121

*Rilasciato 6 maggio 2018* 
  
**In seguito [Microsoft Cloud App Security versione 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Miglioramenti dei criteri per il rilevamento anomalia**. Criteri di rilevamento del titolo di Office 365 Cloud App anomalia sono stati migliorati per includere due nuovi tipi di individuazione che sono gradualmente distribuzione: 
    
  - **Attività Ransomware.** Funzionalità di rilevamento Ransomware sono state estese con rilevamento anomalia per assegnare più complete contro gli attacchi ransomware sofisticati. 
    
  - **Attività dell'utente è terminato.** Terminate consente di attività utente per monitorare gli account degli utenti terminati che potrebbe essere stato eseguito il deprovisioning nelle applicazioni aziendali, ma che potrebbe comunque avere accesso alle alcune risorse aziendali. 
    
    Per visualizzare i [criteri di rilevamento anomalia](anomaly-detection-policies-in-ocas.md)nel portale di protezione di Office 365 Cloud App, scegliere **controllo** \> **criteri**.
    
## <a name="office-365-cloud-app-security-release-120"></a>Versione di Office 365 Cloud App sicurezza 120

*Rilasciato il 22 aprile 2018* 
  
**In seguito [Microsoft Cloud App Security versione 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Le applicazioni interne come attività dell'utente**. Per Office 365 e Azure Active Directory (Azure Active Directory), si viene ora gradualmente distribuzione la possibilità per rilevare le applicazioni interne come attività dell'account utente eseguite dalle applicazioni di Office 365 e Azure Active Directory (interne ed esterne). In questo modo è possibile creare criteri per avvisare l'utente se un'applicazione esegue attività imprevista e non autorizzata. 
    
- **Esportare più campi nell'elenco App OAuth**. Quando si esporta un elenco di applicazioni OAuth in csv, campi aggiuntivi, ad esempio publisher, l'utilizzo di livello e community autorizzazioni sono inclusi per semplificare il processo di conformità e indagini. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Versione di Office 365 Cloud App sicurezza 119

*Rilasciato 1 aprile 2018* 
  
**In seguito [Microsoft Cloud App Security versione 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Miglioramenti al Cloud individuazione**. L'individuazione del Cloud vengono fornite ulteriori informazioni sugli utenti principali e gli indirizzi IP, facilitando per visualizzare i dettagli di utilizzo relativi a Office 365 e altre applicazioni. Per ulteriori informazioni, vedere [risultati di individuazione dell'esame app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).
    
    ![È stato aggiornato il dashboard di individuazione Cloud](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Versione di Office 365 Cloud App sicurezza 118

*Rilasciato 18 marzo 2018* 
  
**In seguito [Microsoft Cloud App Security versione 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Supporto barracuda**. Individuazione cloud supporta serie F Barracuda firewall e del flusso di serie F Barracuda firewall web log. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Versione di Office 365 Cloud App sicurezza 117

*Rilasciato 6 marzo 2018* 
  
**In seguito [Microsoft Cloud App Security versione 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **supporta i filtri**. Individuazione cloud supporta i filtri. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Versione di Office 365 Cloud App sicurezza 116

*Rilasciato 18 febbraio 2018* 
  
**In seguito [Microsoft Cloud App Security versione 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Miglioramenti apportati a criteri di rilevamento anomalia**. Rilevamento di anomalie in Criteri di sicurezza di Office 365 Cloud App sono stati migliorati con nuovi rilevamenti basata sullo scenario inclusi impossibili viaggi, attività da un indirizzo IP sospetto e tenta di più account di accesso non riuscito. I nuovi criteri vengono attivati automaticamente, che fornisce il rilevamento della casella rischio tra l'ambiente basato su cloud. Inoltre, i nuovi criteri di espongono i dati più dal motore di rilevamento di sicurezza di Office 365 Cloud App, che contribuisce di velocizzare il processo di analisi e include le minacce in corso. Per ulteriori informazioni, vedere l'articolo Microsoft Cloud App Security, [ottenere istantaneo analitica comportamento e rilevamento anomalia](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Supporto di log parser per i formati di punto di controllo**. Parser di registro Cloud individuazione supportano due ulteriori formati Checkpoint: XML e KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Versione di Office 365 Cloud App sicurezza 114

*Rilasciato 21 gennaio 2018* 
  
**In seguito [Microsoft Cloud App Security versione 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Lo stato del servizio**. È ora possibile controllare lo stato del servizio Office 365 Cloud App sicurezza corrente passando alla **Guida** \> **lo stato del sistema**. 
    
    ![Fare clic su Guida \> lo stato del sistema per visualizzare lo stato di integrità del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Le query personalizzate per registro attività**. A partire dalla versione 114, la possibilità di creare e salvare query personalizzate nel registro dell'attività è distribuzione gradualmente. Query personalizzate consentono di creare modelli di filtro che possono essere riutilizzati per il controllo approfondimento sul. Inoltre suggerito query sono stati aggiunti per fornire modelli di casella indagini per filtrare le attività e individuati app. Query suggerite includono filtri personalizzati per identificare i rischi, ad esempio delle attività di rappresentazione, attività amministratore, rischioso cloud non compatibili con archiviazione App, le applicazioni aziendali tramite crittografia debole i rischi di protezione. Utilizzare le query suggerite come punto di partenza, modificarli in base alle esigenze e salvarli in una nuova query. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Versione di Office 365 Cloud App sicurezza 113

*Rilasciati l'8 gennaio 2018* 
  
**In seguito [Microsoft Cloud App Security versione 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Supporto di log parser per formati generici**. Parser di registro Cloud individuazione supportano ora generici formati seguenti: LEEF, il formato CEF e W3C. 

## <a name="related-topics"></a>Argomenti correlati

[Novità di Office 365 Cloud App Security](new-in-office-365-cas.md)

[Per Office 365 Cloud App sicurezza, vedere gli aggiornamenti 2017](new-in-office-365-cas-2017.md)
    
[Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)