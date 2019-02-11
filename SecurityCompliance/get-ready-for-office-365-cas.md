---
title: Preparare l'ambiente per Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: Introduzione all'utilizzo della protezione App Cloud di Office 365
ms.openlocfilehash: 1d1ae464278a5d9aafa5a176298f03174b6a37dc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603697"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>Preparare l'ambiente per Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |Si è seguito!  <br/> [Passaggio successivo](turn-on-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |[Avviare utilizzando](utilization-activities-for-ocas.md) <br/> |
   
Durante la preparazione per attivare e implementare la protezione di Office 365 Cloud App (precedentemente noto come gestire la sicurezza avanzata) per l'organizzazione, esistono alcuni aspetti da prendere in considerazione. Utilizzare questo articolo come guida per pianificare la protezione di Office 365 Cloud App.
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>Passaggio 1: Identificare e proteggere gli account di amministratore globali e sicurezza

Gli amministratori globali, sicurezza e lettori sicurezza potranno accedere al portale di protezione di applicazioni di Office 365 Cloud per visualizzare i criteri, analizzare gli avvisi e utilizzare i rapporti. Gli amministratori globali e sicurezza può definire i criteri ed eseguire altre azioni per proteggere l'organizzazione. (Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).) Esaminare gli account utente dell'organizzazione che dispongono di autorizzazioni elevate costituisce una precauzione. 
  
 **[Account amministratore globale Protect Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**. 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>Passaggio 2: Attivare la registrazione di controllo per l'organizzazione

Perché Office 365 Cloud App sicurezza per il funzionamento corretto, la registrazione di controllo deve essere attivata. Questo viene in genere eseguito da un amministratore di Exchange Online o un amministratore globale.
  
 **[Attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md)**. 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>Passaggio 3: Accedere al portale di Office 365 Cloud App Security

Per accedere al portale di Office 365 Cloud App Security [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e accesso. 

È inoltre possibile ottenere disponibili da Office 365 Security &amp; centro conformità. Ecco un modo efficace per eseguire questa operazione:

1. Accedere a [https://protection.office.com](https://protection.office.com) e accesso. (verrà visualizzata la sicurezza &amp; centro conformità.)
    
2. Accedere agli **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai alla protezione di Office 365 Cloud App** per accedere al portale di Office 365 Cloud App sicurezza.<br> ![Scegliere Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>Quando si passa al portale di Office 365 Cloud App sicurezza, la prima pagina che viene visualizzato è la pagina criteri, che è simile all'immagine seguente:<br>![Quando si passa al portale di protezione di applicazioni di Office 365 Cloud, si inizia con la pagina criteri](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>Passaggio 4: Definire i criteri e impostare avvisi &amp; azioni

Gli amministratori globali e sicurezza definire i criteri di sicurezza di Office 365 Cloud App. Durante il processo di definizione dei criteri, gli avvisi e le azioni vengono impostate anche. Un avviso è una notifica in base ai criteri viene visualizzato in una visualizzazione o inviata tramite posta elettronica. 
  
Esistono due tipi di avvisi di protezione di applicazioni di Office 365 Cloud: avvisi di rilevamento anomalia rilevare attività sospette e avvisi, attività che vengono definiti per le attività che possono essere atipiche per l'organizzazione. Avvisi avvisare gli amministratori globali e sicurezza in caso di un'attività nell'ambiente Office 365 è insolito che l'organizzazione.
  
Le risorse seguenti per ulteriori informazioni, vedere:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Leggere ed eseguire l'azione avvisi di protezione di Office 365 Cloud App](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a>Passaggio 5: Informazioni sull'utilizzo del cloud dell'organizzazione

Come amministratore globale, amministratore della sicurezza o lettore di protezione, informazioni sull'utilizzo del cloud dell'organizzazione tramite reports e un dashboard di individuazione Cloud (denominato anche produttività App Discovery). Questo dashboard vengono visualizzate informazioni su utenti, App, il traffico web e livelli di rischio.
  
![Nel portale di accesso client di Office 365, selezionare individuazione \> dashboard individuazione Cloud](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
Per passare al dashboard di individuazione applicazioni di produttività, nel portale Office 365 Cloud App sicurezza scegliere **individuazione** \> **individuazione Cloud dashboard**.
  
![Nel portale di accesso client di Office 365, selezionare individuazione](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
Per popolare relazioni con le informazioni che necessarie, caricare i file di registro da firewall dell'organizzazione e i proxy. Per ulteriori informazioni, vedere le risorse seguenti:
  
- [Creare i rapporti di individuazione applicazioni in Office 365 Cloud App Security](create-app-discovery-reports-in-ocas.md)
    
- [Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a>Passaggio 6: Gestire le app nell'organizzazione vengono utilizzati per accedere a Office 365

Un amministratore globale o un amministratore di sicurezza, è possibile gestire le applicazioni, ad esempio App personalizzate o applicazioni di terze parti, che gli utenti dell'organizzazione vengono utilizzato nei dispositivi con Office 365. Ad esempio, si supponga che un utente ha scaricato un'app personalizzata che si desidera utilizzare con Office 365. È possibile esaminare le applicazioni utilizzano persone, escludere applicazioni non attendibili o contrassegnare le applicazioni come approvati alle proprie esigenze di verifica. [Gestire OAuth App tramite Office 365 Cloud App sicurezza](manage-app-permissions-in-ocas.md).
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a>Passaggio 7: Utilizzare il server SIEM con Office 365 Cloud App protezione

L'organizzazione utilizza un server di gestione (SIEM) eventi e informazioni di protezione? Office 365 Cloud App protezione a questo punto è possibile integrare con il server SIEM per abilitare il monitoraggio centralizzato degli avvisi. Integrazione con un servizio SIEM consente di migliorare la protezione delle applicazioni cloud durante la gestione del flusso di lavoro di sicurezza normale, automazione delle procedure di sicurezza e la correlazione tra basata su cloud e locali degli eventi. L'agente SIEM viene eseguito sul server, utilizza gli avvisi di protezione di applicazioni di Office 365 Cloud e crea un flusso di tali avvisi nel server di SIEM. Vedere [SIEM dell'integrazione con Office 365 Cloud App protezione](integrate-your-siem-server-with-office-365-cas.md).
  
## <a name="next-steps"></a>Passaggi successivi

- [Attivare Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
- Provare la [Guida del laboratorio di testing](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) per un'esperienza pratica dove è possibile effettuare una dimostrazione delle funzionalità avanzate di protezione di applicazioni di Office 365 Cloud e creare un modello di prova. 
    

