---
title: Novità di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 10/31/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: Vedere What's new in sicurezza App Cloud di Office 365
ms.openlocfilehash: f661d0d541e84db89b7abd99fd77ef9a767a4cd0
ms.sourcegitcommit: 49abeb8e57a5ee622d72a3782175a989b1a2e3c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "25935573"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a>Novità di Office 365 Cloud App Security

In questo articolo per ottenere una rapida panoramica delle nuove funzionalità e gli aggiornamenti in Office 365 Cloud App Security (precedentemente noto come Gestione sicurezza avanzata di Office 365), che è una tecnologia [Microsoft Cloud App Security](https://aka.ms/whatiscas).
  
In questo articolo è stato aggiornato frequentemente, come funzionalità vengono aggiunte o migliorate. Circa due settimane dopo gli aggiornamenti di sicurezza di Microsoft Cloud App rilascio di aggiornamenti di sicurezza di applicazione Cloud di Office 365 e non tutti gli aggiornamenti di sicurezza di Microsoft Cloud App si applicano a Office 365 Cloud App sicurezza. Inoltre, le nuove funzionalità può richiedere una settimana o più dopo la data di rilascio possa essere visualizzata nell'ambiente di protezione di Office 365 Cloud App.
  
## <a name="office-365-cloud-app-security-release-130"></a>Versione di Office 365 Cloud App sicurezza 130

*Rilasciato il 5 settembre 2018*

**Rilascio con [Microsoft Cloud App Security versione 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **Nuova barra dei menu** Per offrire un'esperienza di amministrazione più coerenza tra prodotti Microsoft 365 e consentono di eseguire il pivot più facilmente tra le soluzioni di protezione di Microsoft, la barra dei menu portale Cloud App protezione è spostato e il lato sinistro dello schermo. Questa struttura coerente esperienza utile per orientare familiarità quando si passa da un portale di protezione di Microsoft a un altro.<br/>![Barra dei menu nella sicurezza App Cloud di Office](media/OCAS-MenuBar.png)<br/>

- **Punteggio app OAuth impatto** È possibile inviare commenti e suggerimenti team la protezione applicazione Cloud per confermare se non esiste un'app OAuth individuata all'interno dell'organizzazione che sembra dannoso. Questa nuova funzionalità consente di far parte della community protezione e migliorare analisi e OAuth app rischio punteggio. Per ulteriori informazioni vedere [Manage app permissions](manage-app-permissions-in-ocas.md).

- **Parser di individuazione di nuovi Cloud** Parser di individuazione Cloud supportano ora iboss Secure Cloud Gateway e Sophos XG.


## <a name="office-365-cloud-app-security-release-128"></a>Versione di Office 365 Cloud App sicurezza 128

*Rilasciato il 5 agosto 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **Autorizzazioni dell'App tra più applicazioni** Per le applicazioni che sono state concesse le autorizzazioni dell'app, è ora possibile escludere o approvare più applicazioni in una singola azione. Ad esempio, è possibile esaminare tutte le applicazioni che dispongono dell'autorizzazione per gli utenti dell'organizzazione, selezionare tutte le applicazioni che si desidera escludere e fare clic su app di esclusione per revocare il consenso tutti concesso e non è più che consente agli utenti di concedere l'autorizzazione per tali applicazioni. 
    
- **Nuova query suggerite: PILR pronto** Esiste una nuova query consigliata per consentire di identificare rilevati delle applicazioni che vengono PILR pronto. PILR ha recentemente è diventato una priorità superiore per gli amministratori di sicurezza. Questa query consente di identificare le applicazioni che vengono PILR pronto semplice e limitare i rischi per la valutazione dei rischi delle App non. 
    
## <a name="office-365-cloud-app-security-release-126"></a>Versione di Office 365 Cloud App sicurezza 126

*Rilasciato il 7 luglio 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Correzione automatica per le attività di sospette** È ora possibile impostare azioni di correzione automatica per sessione sospetta attivata in base ai criteri di rilevamento anomalia. Questo miglioramento consente di ricevere un avviso in modo istantaneo quando si verifica una violazione della e applicare automaticamente le azioni di governance, ad esempio sospendere utente. Per ulteriori informazioni, vedere [criteri di rilevamento anomalia nella sicurezza App Cloud di Office 365](anomaly-detection-policies-in-ocas.md).
    
- **Rilevamento automatico delle App OAuth rischioso** Oltre a indagare esistente delle App OAuth connesso all'ambiente, sicurezza App Cloud di Office 365 ora consente di impostare le notifiche automatiche per informare l'utente quando un'app OAuth soddisfa determinati criteri. Ad esempio, è possibile automaticamente essere avvisati quando vi sono applicazioni che richiedono un livello di autorizzazione elevata e sono stati autorizzati da più di 50 utenti. Per ulteriori informazioni, vedere [gestire le autorizzazioni di app con Office 365 Cloud App sicurezza](manage-app-permissions-in-ocas.md).
    
- **Supporto di gestione gestiti Provider di servizi di protezione (MSSP)** Protezione di Office 365 Cloud App ora offre un'esperienza migliore gestione a MSSPs e consente di configurare i partner esterni in qualità di amministratori con uno dei ruoli attualmente disponibili in Office 365 Cloud App sicurezza. Inoltre, agli amministratori dei diritti di accesso a uno o più tenant ora possono facilmente pivot tra il tenant. 
    
## <a name="office-365-cloud-app-security-release-124"></a>Versione di Office 365 Cloud App sicurezza 124

*Rilasciati il 10 giugno 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Distribuzioni nell'ambito** Le organizzazioni aziendali in modo granulare è possono determinare quali utenti per monitorare e proteggere in base all'appartenenza. Questa funzionalità consente di selezionare gli utenti le cui attività non verranno visualizzate per una qualsiasi delle applicazioni protette. Livello di ambito di monitoraggio è particolarmente utile per la conformità e licenze. Alcune regole di conformità necessitano di evitare il monitoring agli utenti di alcune nazioni a causa di normative locali. E, è possibile monitorare un numero di utenti la possibilità di mantenersi rientrano nei valori delle licenze sicurezza App Cloud di Office 365. 
    
- **Nuovo server di posta elettronica** Il server di posta elettronica per la protezione di Office 365 Cloud App è stato modificato e utilizza gli intervalli di indirizzi IP diversi. Per assicurarsi che è possibile ottenere le notifiche, aggiungere i nuovi indirizzi IP per la proprietà consentite protezione da posta indesiderata. Per le organizzazioni che personalizzano le notifiche, Cloud App sicurezza è possibile ottenere questo per utente mediante MailChimp, un servizio di posta elettronica di terze parti. Per l'elenco di indirizzi IP del server posta elettronica e le istruzioni per l'attivazione di lavoro con MailChimp, vedere [requisiti di rete (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) e [le impostazioni di posta elettronica (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## <a name="office-365-cloud-app-security-release-121"></a>Versione di Office 365 Cloud App sicurezza 121

*Rilasciato 6 maggio 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Miglioramenti dei criteri per il rilevamento anomalia**. Criteri di rilevamento del titolo di Office 365 Cloud App anomalia sono stati migliorati per includere due nuovi tipi di individuazione che sono gradualmente distribuzione: 
    
  - **Attività Ransomware.** Funzionalità di rilevamento Ransomware sono state estese con rilevamento anomalia per assegnare più complete contro gli attacchi ransomware sofisticati. 
    
  - **Attività dell'utente è terminato.** Terminate consente di attività utente per monitorare gli account degli utenti terminati che potrebbe essere stato eseguito il deprovisioning nelle applicazioni aziendali, ma che potrebbe comunque avere accesso alle alcune risorse aziendali. 
    
    Per visualizzare i [criteri di rilevamento anomalia](anomaly-detection-policies-in-ocas.md)nel portale di protezione di Office 365 Cloud App, scegliere **controllo** \> **criteri**.
    
## <a name="office-365-cloud-app-security-release-120"></a>Versione di Office 365 Cloud App sicurezza 120

*Rilasciato il 22 aprile 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Le applicazioni interne come attività dell'utente**. Per Office 365 e Azure Active Directory (Azure Active Directory), si viene ora gradualmente distribuzione la possibilità per rilevare le applicazioni interne come attività dell'account utente eseguite dalle applicazioni di Office 365 e Azure Active Directory (interne ed esterne). In questo modo è possibile creare criteri per avvisare l'utente se un'applicazione esegue attività imprevista e non autorizzata. 
    
- **Esportare più campi nell'elenco delle autorizzazioni dell'app**. Quando si esporta un elenco delle autorizzazioni app in csv, campi aggiuntivi, ad esempio publisher, l'utilizzo di livello e community autorizzazioni sono inclusi per semplificare il processo di conformità e indagini. 
    
## <a name="office-365-cloud-app-security-release-119"></a>Versione di Office 365 Cloud App sicurezza 119

*Rilasciato 1 aprile 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Miglioramenti al Cloud individuazione**. L'individuazione del Cloud vengono fornite ulteriori informazioni sugli utenti principali e gli indirizzi IP, facilitando per visualizzare i dettagli di utilizzo relativi a Office 365 e altre applicazioni. Per ulteriori informazioni, vedere [risultati di individuazione dell'esame app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).
    
    ![È stato aggiornato il dashboard di individuazione Cloud](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Versione di Office 365 Cloud App sicurezza 118

*Rilasciato 18 marzo 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Supporto barracuda**. Individuazione cloud supporta serie F Barracuda firewall e del flusso di serie F Barracuda firewall web log. 
    
## <a name="office-365-cloud-app-security-release-117"></a>Versione di Office 365 Cloud App sicurezza 117

*Rilasciato 6 marzo 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **supporta i filtri**. Individuazione cloud supporta i filtri. 
    
## <a name="office-365-cloud-app-security-release-116"></a>Versione di Office 365 Cloud App sicurezza 116

*Rilasciato 18 febbraio 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Miglioramenti apportati a criteri di rilevamento anomalia**. Rilevamento di anomalie in Criteri di sicurezza di Office 365 Cloud App sono stati migliorati con nuovi rilevamenti basata sullo scenario inclusi impossibili viaggi, attività da un indirizzo IP sospetto e tenta di più account di accesso non riuscito. I nuovi criteri vengono attivati automaticamente, che fornisce il rilevamento della casella rischio tra l'ambiente basato su cloud. Inoltre, i nuovi criteri di espongono i dati più dal motore di rilevamento di sicurezza di Office 365 Cloud App, che contribuisce di velocizzare il processo di analisi e include le minacce in corso. Per ulteriori informazioni, vedere l'articolo Microsoft Cloud App Security, [ottenere istantaneo analitica comportamento e rilevamento anomalia](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Supporto di log parser per i formati di punto di controllo**. Parser di registro Cloud individuazione supportano due ulteriori formati Checkpoint: XML e KPC. 
    
## <a name="office-365-cloud-app-security-release-114"></a>Versione di Office 365 Cloud App sicurezza 114

*Rilasciato 21 gennaio 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Lo stato del servizio**. È ora possibile controllare lo stato del servizio Office 365 Cloud App sicurezza corrente passando alla **Guida** \> **lo stato del sistema**. 
    
    ![Fare clic su Guida \> lo stato del sistema per visualizzare lo stato di integrità del sistema](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Le query personalizzate per registro attività**. A partire dalla versione 114, la possibilità di creare e salvare query personalizzate nel registro dell'attività è distribuzione gradualmente. Query personalizzate consentono di creare modelli di filtro che possono essere riutilizzati per il controllo approfondimento sul. Inoltre suggerito query sono stati aggiunti per fornire modelli di casella indagini per filtrare le attività e individuati app. Query suggerite includono filtri personalizzati per identificare i rischi, ad esempio delle attività di rappresentazione, attività amministratore, rischioso cloud non compatibili con archiviazione App, le applicazioni aziendali tramite crittografia debole i rischi di protezione. Utilizzare le query suggerite come punto di partenza, modificarli in base alle esigenze e salvarli in una nuova query. 
    
## <a name="office-365-cloud-app-security-release-113"></a>Versione di Office 365 Cloud App sicurezza 113

*Rilasciati l'8 gennaio 2018* 
  
**Rilascio con [Microsoft Cloud App Security versione 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Supporto di log parser per formati generici**. Parser di registro Cloud individuazione supportano ora generici formati seguenti: LEEF, il formato CEF e W3C. 
    
## <a name="office-365-cloud-app-security-release-112"></a>Versione di Office 365 Cloud App sicurezza 112

*Rilasciato il 24 dicembre 2017* 
  
**Rilascio con [Microsoft Cloud App Security versione 112](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**: 
  
- **Cassetto delle conoscenze pertinenti**. Nel Registro di attività, è ora possibile accedere il cassetto delle conoscenze pertinenti facendo clic su un nome utente o l'indirizzo IP. 
    
    ![Scegliere un nome utente o l'indirizzo IP per visualizzare il cassetto delle conoscenze pertinenti nel Registro di attività.](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- **Possibilità di visualizzare più attività con un clic**. Nel cassetto delle conoscenze rilevanti, è possibile fare clic sull'icona del clock per visualizzare tutte le attività eseguite all'interno di 48 ore di un'attività selezionata. 
    
    ![Nel cassetto rilevanti sui concetti, è possibile fare clic sull'icona orologio per visualizzare le attività eseguite all'interno di 48 ore di un'attività selezionata](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- **Miglioramenti di log parser per SRX Juniper**. Sono stati apportati miglioramenti al parser registro individuazione Cloud per SRX Juniper. 
    
## <a name="office-365-cloud-app-security-release-111"></a>Versione di Office 365 Cloud App sicurezza 111

*Rilasciati il 10 dicembre 2017* 
  
**Rilascio con [Microsoft Cloud App Security versione 111](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**: 
  
- **Miglioramenti relativi alla filtro fase**. Filtri temporali sono ora più semplici da utilizzare. Per accedere a un filtro di tempo, in una visualizzazione, ad esempio registro attività, i criteri, gli avvisi, utilizzando la visualizzazione avanzata, scegliere **Data** nell'elenco dei filtri. Scegliere un'opzione, ad esempio prima, dopo o in tra per applicare il filtro di tempo. 
    
    ![Utilizzare il filtro della data per visualizzare informazioni prima, dopo o tra le date.](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a>Versione di Office 365 Cloud App sicurezza 110

*Rilasciato il 26 novembre 2017* 
  
**Rilascio con [Microsoft Cloud App Security versione 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**: 
  
- **Integrazione del server SIEM ora in genere disponibile**. Connessione a Office 365 Cloud App protezione di server SIEM. È possibile inviare gli avvisi e le attività automaticamente al server SIEM della scelta configurando gli agenti SIEM. Vedere [integrazione con Office 365 Cloud App Security sul server SIEM](integrate-your-siem-server-with-office-365-cas.md).
    
- **Semplificare l'accesso al contenuto della Guida**. Utilizzando il nuovo punto interrogativo nell'angolo superiore destro, è possibile accedere il contenuto della Guida all'interno delle pagine del portale di Office 365 Cloud App sicurezza. Ogni collegamento è sensibile al contesto, che consentirà delle informazioni che necessarie, basate sulla pagina in che si è. 
    
- **Invia commenti e suggerimenti**. Utilizza la faccina sorridente nell'angolo superiore destro, è possibile inviare commenti e suggerimenti da tutte le pagine del portale di Office 365 Cloud App sicurezza. In questo modo è possibile segnalare errori richiede le nuove funzionalità e condividere l'esperienza dell'utente direttamente con il team di protezione di Office 365 Cloud App. 
    
## <a name="office-365-cloud-app-security-release-102"></a>Versione di Office 365 Cloud App sicurezza 102

*Rilasciato il 13 agosto 2017* 
  
**Rilascio con [Microsoft Cloud App Security versione 102](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**: 
  
- **Nuove azioni indagini utente** abilitare un livello aggiuntivo di drill-down per indagini utente. In una pagina indagare, è possibile al passaggio del mouse su un'attività, all'utente o account e applicarlo come filtro e da quest'ultimo, è possibile visualizzare gli eventi o attività correlate. 
    
## <a name="office-365-cloud-app-security-release-100"></a>Versione di Office 365 Cloud App sicurezza 100

*Rilasciato il 17 luglio 2017* 
  
**Rilascio con [Microsoft Cloud App Security versione 100](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**: 
  
- **Estensioni di protezione** è un nuovo dashboard a cui è possibile gestire centralmente tutte le estensioni di protezione per Office 365 Cloud App sicurezza, tra cui i token di API e gli agenti SIEM. Per visualizzare il dashboard di estensioni di protezione, procedere come segue: 
    
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. Accedere agli **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.
    
    ![In sicurezza &amp; centro conformità, selezionare avvisi \> gestione avanzata degli avvisi \> passare a gestione della protezione avanzata](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. Fare clic su **Impostazioni** \> **estensioni di protezione**.
    
    ![Scegliere le impostazioni nel portale ASM \> estensioni di protezione](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- **Migliori l'analisi**. Il meccanismo di analisi del Registro di individuazione Cloud sono stati apportati miglioramenti. Sono molto meno probabile che si verificano errori interni. 
    
- **Formati dei registri previsti**. Il formato previsto del registro per i registri di individuazione Cloud ora è elencati esempi di sia Registro di sistema e formato FTP. 
    
## <a name="related-topics"></a>Argomenti correlati

[Contenuto della Guida alla protezione App Cloud di Office 365](office-365-cas-help.md)
  
[Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)
  
[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

