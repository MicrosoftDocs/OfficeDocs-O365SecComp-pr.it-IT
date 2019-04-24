---
title: Novità di Office 365 cloud app Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Vedere cosa è stato rilasciato durante 2018 per Office 365 cloud app Security
ms.openlocfilehash: 986fb64eedf8184e7835d1fec41845fde13b294b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263162"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>Aggiornamenti per la sicurezza delle app cloud di Office 365 durante 2018

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 cloud app Security Release 138

*RiLasciati il 23 dicembre 2018*

**Dopo la [versione di sicurezza di Microsoft Cloud app 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **Caricamento automatico del registro tramite Docker su Windows** Cloud app Security ora supporta il caricamento automatico dei log per Windows 10 (aggiornamenti per i creatori di[cadute](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e versioni successive) e Windows Server ([versione 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709) e versioni successive) mediante l'utilizzo di Docker su Windows. Per ulteriori informazioni, vedere [questo articolo](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows) e Configure docker.  

- **Integrazione flusso Microsoft** Cloud app Security è ora integrato con [Microsoft Flow](https://docs.microsoft.com/flow/getting-started) per fornire gli schemi di automazione e orchestrazione degli avvisi personalizzati. Per ulteriori informazioni, vedere [l'articolo](https://docs.microsoft.com/cloud-app-security/flow-integration) relativo alla configurazione dell'integrazione del flusso Microsoft. 

## <a name="office-365-cloud-app-security-release-137"></a>Office 365 cloud app Security Release 137

*RiLasciati l'8 dicembre 2018*

**Dopo la [versione di sicurezza di Microsoft Cloud app 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **Aggiunta del supporto per la dinamica** Cloud app Security ora include il supporto per le attività di Microsoft Dynamics supportate nel log di controllo di Office 365. 

- **Heads Up – nuova terminologia!** Il nome delle funzionalità per le autorizzazioni delle app è stato modificato per maggiore chiarezza: ora viene chiamato OAuth Apps. 

## <a name="office-365-cloud-app-security-release-136"></a>Office 365 cloud app Security Release 136

*RiLasciata il 25 novembre 2018*

**Dopo la [versione di sicurezza di Microsoft Cloud app 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **Aggiornamenti del cloud Discovery** L'analizzatore di log personalizzato è stato migliorato per supportare formati di log del traffico Web aggiuntivi e complessi. Come parte di questi miglioramenti, gli utenti possono ora inserire intestazioni personalizzate per i file di registro CSV senza intestazioni, utilizzare delimitatori speciali per i file con valore Key, elaborare il formato di file syslog e altro ancora.

- **Nuovo criterio di rilevamento delle anomalie: regole di manipolazione della posta in arrivo** Questo criterio profila l'ambiente e attiva gli avvisi quando le regole sospette che eliminano o spostano i messaggi o le cartelle vengono impostate nella posta in arrivo di un utente. Questo potrebbe indicare che l'account dell'utente è stato compromesso, che i messaggi vengono nascosti intenzionalmente e che la cassetta postale viene utilizzata per distribuire posta indesiderata o malware nell'organizzazione.

- **Supporto per i gruppi nei criteri di autorizzazione delle app** Cloud app Security ora offre la possibilità di definire i criteri di autorizzazione delle app in modo più granulare, in base alle appartenenze ai gruppi degli utenti che hanno autorizzato le app. Ad esempio, un amministratore può decidere di impostare un criterio che revoca le app non comuni se richiede autorizzazioni elevate, solo se l'utente che ha autorizzato le autorizzazioni è un membro del gruppo Administrators.

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Office 365 cloud app Security rilascia 133, 134 e 135

*RiLasciati in ottobre-novembre 2018*

**Seguenti [Microsoft cloud app Security Release 133, 134 e 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- I **nuovi criteri di rilevamento** delle anomalie vengono implementati gradualmente:
    
    - Il nuovo criterio **di exfiltration dei dati per le app** non autorizzate viene automaticamente abilitato all'avviso quando un utente o un indirizzo IP utilizza un'app che non è autorizzata a eseguire un'attività simile a un tentativo di exfiltrate informazioni dall'organizzazione.
    
    - Il nuovo criterio per le **attività più Delete VM** profila l'ambiente e attiva gli avvisi quando gli utenti eliminano più macchine virtuali in una singola sessione, rispetto alla linea di base dell'organizzazione.

- **Supporto per l'individuazione del cloud per i-Filter** La funzionalità cloud app Security Cloud Discovery ha ora un supporto migliorato per il parser i-Filter syslog.

## <a name="office-365-cloud-app-security-release-131"></a>Office 365 cloud app Security Release 131

*RiLasciati il 16 settembre 2018*

**Dopo la [versione di sicurezza di Microsoft Cloud app 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **RevocaRe automaticamente le autorizzazioni per le applicazioni OAuth a rischio** È ora possibile controllare quali app OAuth gli utenti hanno accesso, revocando l'autorizzazione dell'app per le app OAuth su Office. Quando si creano criteri di autorizzazione per le app, è ora possibile impostare il criterio per revocare l'autorizzazione di un'app.

- **Individuazione cloud ulteriore parser incorporato supportato** Il cloud Discovery ora supporta il formato di registro cloud di Forcepoint Web Security.
  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 cloud app Security Release 130

*RiLasciati il 5 settembre 2018*

**Dopo la [versione di sicurezza di Microsoft Cloud app 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nuova barra di menu** Per offrire un'esperienza di amministratore più coerente tra i prodotti Microsoft 365 e per consentire l'utilizzo più agevole tra le soluzioni di sicurezza di Microsoft, la barra dei menu del portale di sicurezza cloud app è stata spostata sul lato sinistro dello schermo. Questa esperienza di navigazione coerente consente di orientarsi quando si passa da un portale di sicurezza di Microsoft a un altro.<br/>![Barra del menu in Office cloud app Security](media/OCAS-MenuBar.png)<br/>

- **Punteggio dell'applicazione OAuth di impatto** È ora possibile inviare commenti e suggerimenti per il team di sicurezza cloud app per sapere se nell'organizzazione è stata scoperta un'app OAuth che sembra dannosa. Questa nuova funzionalità consente di far parte della nostra community di sicurezza e di migliorare l'analisi e il Punteggio dei rischi per l'applicazione OAuth. Per ulteriori informazioni, vedere [Manage OAuth Apps](manage-app-permissions-in-ocas.md).

- **Nuovi analizzatori di individuazione cloud** Gli analizzatori cloud Discovery ora supportano iboss Secure Cloud gateway e Sophos XG.

## <a name="office-365-cloud-app-security-release-128"></a>Office 365 cloud app Security Release 128

*RiLasciati il 5 agosto 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **App OAuth su più app** Per le app OAuth, è ora possibile vietare o approvare più app in una singola azione. Ad esempio, è possibile esaminare tutte le app a cui è stata concessa l'autorizzazione da parte degli utenti dell'organizzazione, selezionare tutte le app che si desidera bandire, quindi fare clic su Ban Apps per revocare tutti i consensi concessi e non consentire agli utenti di concedere le autorizzazioni per tali app. Per ulteriori informazioni, vedere [Manage OAuth Apps using Office 365 cloud app Security](manage-app-permissions-in-ocas.md). 
    
- **Nuova query consigliata: app Cloud GDPR-Ready** È presente una nuova query consigliata per consentire all'utente di identificare le app scoperte che sono GDPR pronte. Come probabilmente già saprete, GDPR è diventato di recente una priorità assoluta per gli amministratori della sicurezza. Questa query consente di identificare facilmente le app che sono pronte per la GDPR e di attenuare le minacce valutando il rischio di applicazioni che non lo sono. Per utilizzare la nuova query, nel dashboard **individuazione cloud** , nella scheda **app individuate** , scegliere **query** > **GDPR-Ready Cloud Apps**.<br/>![Query delle app cloud di GDPR-Ready](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 cloud app Security Release 126

*RiLasciati il 7 luglio 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Correzione automatica per le attività sospette** È ora possibile impostare le azioni di correzione automatica per le sessioni sospette attivate dai criteri di rilevamento delle anomalie. Questo miglioramento consente di essere avvisati istantaneamente quando si verifica una violazione e di applicare automaticamente le azioni di governance, ad esempio Suspend User. Per ulteriori informazioni, vedere [criteri di rilevamento delle anomalie in Office 365 cloud app Security](anomaly-detection-policies-in-ocas.md).
    
- **Rilevamento automatizzato di applicazioni OAuth a rischio** Oltre all'analisi esistente delle app OAuth connesse all'ambiente, Office 365 cloud app Security ora consente di impostare notifiche automatizzate che consentono di sapere quando un'app OAuth soddisfa determinati criteri. Ad esempio, è possibile avvisare automaticamente quando sono presenti app che richiedono un livello di autorizzazione elevato e che sono state autorizzate da più di 50 utenti. Per ulteriori informazioni, vedere [Manage OAuth Apps using Office 365 cloud app Security](manage-app-permissions-in-ocas.md).
    
- **Supporto gestione provider di servizi di sicurezza gestiti (MSSP)** Office 365 cloud app Security ora offre una migliore esperienza di gestione a MSSPs e consente di configurare i partner esterni come amministratori con uno qualsiasi dei ruoli attualmente disponibili in Office 365 cloud app Security. Inoltre, gli amministratori che dispongono di diritti di accesso a più tenant possono ora essere facilmente pivot tra i tenant. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 cloud app Security Release 124

*RiLasciati il 10 giugno 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Distribuzioni con ambito** Le organizzazioni aziendali possono determinare in modo granulare gli utenti da monitorare e proteggere in base all'appartenenza a un gruppo. Questa funzionalità consente di selezionare gli utenti le cui attività non verranno visualizzate per le applicazioni protette. Il monitoraggio con ambito è particolarmente utile per la conformità e la gestione delle licenze. Alcune normative di conformità richiedono che l'utente non controlli gli utenti provenienti da determinati paesi a causa delle normative locali. In questo modo, è possibile monitorare meno utenti per rimanere entro i limiti delle licenze per la sicurezza delle app cloud di Office 365. 
    
- **Nuovo server di posta elettronica** Il server di posta elettronica per Office 365 cloud app Security è stato modificato e utilizza intervalli di indirizzi IP diversi. Per essere sicuri di ricevere notifiche, aggiungere i nuovi indirizzi IP alla whitelist di protezione da posta indesiderata. Per le organizzazioni che personalizzano le notifiche, cloud app Security consente di utilizzare MailChimp, un servizio di posta elettronica di terze parti. Per l'elenco degli indirizzi IP del server di posta e le istruzioni per l'abilitazione dell'utilizzo di MailChimp, vedere [Network requirements (Microsoft cloud app Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) and [mail Settings (Microsoft cloud app Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 cloud app Security Release 121

*RiLasciata il 6 maggio 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Miglioramenti ai criteri di rilevamento**delle anomalie. I criteri di rilevamento delle anomalie di Office 365 cloud app Security sono stati migliorati per includere due nuovi tipi di rilevamento delle minacce che vengono gradualmente implementati: 
    
  - **Attività ransomware.** Le funzionalità di rilevamento ransomware sono estese con il rilevamento delle anomalie per fornire una copertura più completa rispetto ai sofisticati attacchi ransomware. 
    
  - **Attività utente terminata.** L'attività utente terminata consente di monitorare gli account degli utenti terminati che potrebbero essere stati provisionati dalle applicazioni aziendali, ma che possono comunque avere accesso a determinate risorse aziendali. 
    
    per visualizzare i [criteri di rilevamento](anomaly-detection-policies-in-ocas.md)delle anomalie, nel portale Office 365 Cloud App Security fare clic su **criteri**di **controllo** \> .
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 cloud app Security Release 120

*RiLasciati il 22 aprile 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Applicazioni interne come attività utente**. Per Office 365 e Azure Active Directory (Azure AD), è ora possibile implementare gradualmente la possibilità di rilevare le applicazioni interne come attività dell'account utente eseguite dalle applicazioni di Office 365 e Azure AD (sia interne che esterne). In questo modo è possibile creare criteri per avvisare l'utente se un'applicazione esegue attività inattese e non autorizzate. 
    
- **Altri campi nell'esportazione dell'elenco delle app OAuth**. Quando si esporta un elenco delle app OAuth in formato CSV, sono inclusi campi aggiuntivi quali Publisher, livello di autorizzazioni e utilizzo della community per facilitare il processo di conformità e analisi. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 cloud app Security Release 119

*RiLasciati il 1 ° aprile 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- Miglioramenti apportati **al cloud Discovery**. The Cloud Discovery fornisce ulteriori informazioni su utenti e indirizzi IP principali, semplificando la visualizzazione dei dettagli sull'utilizzo di Office 365 e di altre app. Per ulteriori informazioni, vedere [Review app Discovery requests in Office 365 cloud app Security](review-app-discovery-findings-in-ocas.md).
    
    ![The Cloud Discovery dashboard è stato aggiornato](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 cloud app Security Release 118

*RiLasciata il 18 marzo 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Supporto Barracuda**. Il cloud Discovery ora supporta i firewall serie Barracuda F e lo streaming di log Web del Barracuda F-Series. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 cloud app Security Release 117

*RiLasciata il 6 marzo 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **supporto i-Filter**. Il cloud Discovery ora supporta i-FILTER. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 cloud app Security Release 116

*RiLasciati il 18 febbraio 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Miglioramenti ai criteri di rilevamento**delle anomalie. Criteri di rilevamento delle anomalie in Office 365 cloud app Security sono state migliorate con i nuovi rilevamenti basati su scenari, tra cui l'attività di viaggio impossibile da un indirizzo IP sospetto e più tentativi di accesso non riusciti. I nuovi criteri sono automaticamente abilitati, fornendo il rilevamento delle minacce fuori campo nell'ambiente cloud. Inoltre, i nuovi criteri espongono ulteriori dati dal motore di rilevamento di sicurezza di Office 365 cloud app, che consente di velocizzare il processo di analisi e di contenere minacce in corso. Per ulteriori informazioni, vedere l'articolo sulla sicurezza dell'app cloud di Microsoft, [ottenere analisi comportamentale istantanea e rilevamento di anomalie](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Supporto del parser dei log per i formati del checkpoint**. I parser del registro di individuazione cloud ora supportano due formati di checkpoint aggiuntivi: XML e KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 cloud app Security Release 114

*RiLasciata il 21 gennaio 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Stato del servizio**. è ora possibile controllare lo stato del servizio di sicurezza Cloud App di Office 365 in corso per **facilitare** \> **lo stato del sistema**. 
    
    ![Fare clic \> su stato del sistema di guida per visualizzare lo stato di integrità del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Query personalizzate per il registro attività**. A partire dalla versione 114, la possibilità di creare e salvare query personalizzate nel registro attività si sta gradualmente srotolando. Le query personalizzate consentono di creare modelli di filtro che possono essere riutilizzati per l'analisi Deep-Dive. Inoltre, sono state aggiunte query consigliate per fornire modelli di analisi di base per filtrare le attività e le app individuate. Le query suggerite includono filtri personalizzati per identificare i rischi, ad esempio le attività di rappresentazione, le attività di amministratore, le app di archiviazione cloud non conformi a rischio, le app Enterprise con crittografia debole e rischi per la sicurezza. Utilizzare le query suggerite come punto di partenza, modificarle in base alle esigenze e quindi salvarle come nuova query. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 cloud app Security Release 113

*RiLasciata l'8 gennaio 2018* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Supporto del parser dei log per i formati generici**. I parser del registro di individuazione cloud ora supportano i formati generici seguenti: LEEF, CEF e W3C. 

## <a name="related-topics"></a>Argomenti correlati

[Novità di Office 365 cloud app Security](new-in-office-365-cas.md)

[Vedere gli aggiornamenti 2017 per Office 365 cloud app Security](new-in-office-365-cas-2017.md)
    
[Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)