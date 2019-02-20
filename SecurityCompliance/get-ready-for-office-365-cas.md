---
title: Preparare l'ambiente per Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.date: 02/15/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Introduzione all'utilizzo di Office 365 cloud app Security
ms.openlocfilehash: eef1a4f0465b583bb0f0589d213f61c9a15fd152
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087435"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Preparare l'ambiente per Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |Sei qui!  <br/> [Passaggio successivo](turn-on-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
   
Quando si prepara l'attivazione e l'implementazione di Office 365 cloud app Security per l'organizzazione, è necessario tenere conto di alcuni aspetti. Utilizzare questo articolo come guida per la pianificazione di Office 365 cloud app Security.
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>Passaggio 1: identificare e proteggere gli account di amministratore globale e di sicurezza

Gli amministratori globali, gli amministratori della sicurezza e i lettori di sicurezza possono accedere al portale di Office 365 cloud app Security per visualizzare i criteri, esaminare gli avvisi e utilizzare i report. Gli amministratori globali e gli amministratori della sicurezza possono definire i criteri e intraprendere altre azioni per proteggere l'organizzazione. Per ulteriori informazioni, vedere perMissions [in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md). Esaminare gli account utente dell'organizzazione che dispongono di autorizzazioni elevate come precauzione. 
  
 **[Proteggere gli account di amministratore globale di Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**. 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>Passaggio 2: abilitare la registrazione di controllo per l'organizzazione

Affinché Office 365 cloud app Security funzioni correttamente, è necessario che la registrazione di controllo sia attivata. Questo è in genere effettuato da un amministratore di Exchange Online o da un amministratore globale.
  
 **[Attiva o disattiva la ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md)**. 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>Passaggio 3: passare al portale di sicurezza delle app cloud di Office 365

È possibile accedere a Office 365 cloud app Security Portal accedendo a [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e accedendo. 

È inoltre possibile accedere al centro sicurezza &amp; e conformità di Office 365. Di seguito è indicato un ottimo metodo per eseguire la procedura:

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere. (questo porta al centro sicurezza &amp; e conformità).
    
2. Passare a **avvisi** \> per la **gestione degli avvisi avanzati**.
    
3. Scegliere **Vai a office 365 cloud app Security** per accedere al portale di Office 365 cloud app Security.<br> ![Scegliere Gestisci avvisi avanzati per accedere a Office 365 cloud app Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>Quando si passa al portale di sicurezza delle app cloud di Office 365, la prima pagina visualizzata è la pagina Criteri, che assomiglia all'immagine seguente:<br>![Quando si passa al portale di protezione delle app di Office 365 cloud, si inizia con la pagina Criteri](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>Passaggio 4: definire i criteri e impostare azioni &amp; avvisi

Gli amministratori globali e gli amministratori della sicurezza definiscono i criteri in Office 365 cloud app Security. Durante il processo di definizione dei criteri vengono impostati anche gli avvisi e le azioni. Un avviso è una notifica basata su criteri che viene visualizzata in una visualizzazione o viene inviata tramite posta elettronica. 
  
In Office 365 cloud app Security sono disponibili due tipi di avvisi: avvisi di rilevamento delle anomalie che individuano attività sospette e avvisi attività, definiti per attività che possono essere atipiche per la propria organizzazione. Gli avvisi avvisano gli amministratori globali e gli amministratori della sicurezza quando è presente un'attività nell'ambiente di Office 365 che è inusuale per l'organizzazione.
  
Per ulteriori informazioni, vedere le risorse seguenti:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Esaminare e intervenire sugli avvisi di sicurezza dell'app cloud di Office 365](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a>Passaggio 5: configurare il controllo delle app di accesso condizionale

Impostare e applicare i controlli nelle app dell'organizzazione, in base a determinate condizioni, ad esempio gli utenti che possono utilizzare le app e dove. Definire i criteri di accesso e di sessione delle app utente per determinare se i documenti sensibili possono essere scaricati e crittografati, bloccare l'accesso a determinate app, configurare la modalità di sola lettura per alcune app e limitare le sessioni degli utenti dalle reti non aziendali.

Per ulteriori informazioni, vedere le risorse seguenti:

- [Proteggere le app con Office 365 cloud app Security Conditional Access App Control](ocas-conditional-access-app-control.md)

- [Distribuire il controllo delle app di accesso condizionale per le app di Office 365](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a>Passaggio 6: informazioni sull'utilizzo del cloud dell'organizzazione

In qualità di amministratore globale, amministratore della sicurezza o lettore di sicurezza, è possibile ottenere informazioni sull'utilizzo del cloud dell'organizzazione tramite report e un dashboard di individuazione del cloud (denominato anche individuazione delle app per la produttività). Questo dashboard Visualizza informazioni su utenti, app, traffico Web e livelli di rischio.
  
![Nel portale di Office 365 CAS, scegliere Discover \> cloud Discovery dashboard](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
per accedere al dashboard di individuazione delle app per la produttività, nel portale di Office 365 cloud app Security, scegliere **Discover** \> **cloud discovery dashboard**.
  
![Nel portale di Office 365 CAS, scegliere Scopri](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
Per popolare i report con le informazioni necessarie, caricare i file di registro dai firewall e dai proxy dell'organizzazione. Per ulteriori informazioni, vedere le risorse seguenti:
  
- [Creare report di individuazione delle app in Office 365 cloud app Security](create-app-discovery-reports-in-ocas.md)
    
- [Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a>Passaggio 7: gestire le app che l'organizzazione utilizza per accedere a Office 365

In qualità di amministratore globale o amministratore della sicurezza, è possibile gestire le app, ad esempio le app personalizzate o le app di terze parti, che gli utenti dell'organizzazione utilizzano nei propri dispositivi con Office 365. Si supponga, ad esempio, che qualcuno abbia scaricato un'app personalizzata che si desidera utilizzare con Office 365. È possibile esaminare le app che gli utenti utilizzano, vietare le app non attendibili o contrassegnare le app come approvate per i propri scopi di tracciabilità. [Gestire le app OAuth con Office 365 cloud app Security](manage-app-permissions-in-ocas.md).
  
## <a name="step-8-create-a-maintenance-plan"></a>Passaggio 8: creare un piano di manutenzione

Dopo aver installato e configurato Office 365 cloud app Security, è necessario eseguire alcune attività di utilizzo come amministratore globale di Office 365 o amministratore della protezione per l'organizzazione. Eseguendo queste attività, è possibile garantire che Office 365 cloud app Security sia configurato correttamente, che i criteri siano aggiornati e che l'organizzazione realizzi il valore da Office 365. Utilizzare questo articolo come guida per pianificare queste attività. Vedere [attività di utilizzo dopo la distribuzione di Office 365 cloud app Security](utilization-activities-for-ocas.md).

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a>Optional Passaggio 9: utilizzare il server SIEM con Office 365 cloud app Security

L'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM)? Office 365 cloud app Security è ora in grado di integrarsi con il server SIEM per abilitare il monitoraggio centralizzato degli avvisi. L'integrazione con un servizio SIEM consente di proteggere meglio le applicazioni cloud mantenendo il flusso di lavoro di sicurezza usuale, automatizzando le procedure di sicurezza e la correlazione tra eventi basati su cloud e in locale. L'agente SIEM viene eseguito sul server, estrae gli avvisi da Office 365 cloud app Security e trasmette tali avvisi nel server SIEM. Vedere [Siem Integration with Office 365 cloud app Security](integrate-your-siem-server-with-office-365-cas.md).
  
## <a name="next-steps"></a>Passaggi successivi

- [Attivare Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
- Provare la [Guida del laboratorio](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) di testing per un'esperienza pratica in cui è possibile dimostrare le potenti funzionalità di Office 365 cloud app Security e creare una prova del concetto. 
    

