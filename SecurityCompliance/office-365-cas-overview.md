---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 cloud app Security consente di approfondire le attività sospette in Office 365, in modo da poter esaminare le situazioni potenzialmente problematiche e, se necessario, intervenire per risolvere i problemi di sicurezza. '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001209"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Overview of Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|Sei qui!  <br/> [Passaggio successivo](get-ready-for-office-365-cas.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Office 365 cloud app Security è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un altro abbonamento a Office 365 Enterprise, Office 365 cloud app Security può essere acquistato come componente aggiuntivo. (come amministratore globale, nell'interfaccia di amministrazione di Microsoft 365, scegliere **fatturazione** \> **aggiungi abbonamenti**). Per ulteriori informazioni, vedere [office 365 Platform Service Description: office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) e [acquistare o modificare un componente aggiuntivo per Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on). 
  
Office 365 cloud app Security fornisce informazioni sull'attività sospetta in Office 365, in modo da poter esaminare le situazioni potenzialmente problematiche e, se necessario, intervenire per risolvere i problemi di sicurezza. Con Office 365 cloud app Security, è possibile ricevere notifiche degli avvisi attivati per attività atipiche o sospette, vedere come si accede e si utilizzano i dati dell'organizzazione in Office 365, sospendere gli account utente che presentano attività sospette e richiedere Gli utenti di eseguire l'accesso alle app di Office 365 dopo che è stato attivato un avviso. Leggere questo articolo per ottenere una panoramica delle funzionalità e delle funzionalità di sicurezza delle app di Office 365 cloud.
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>Come trovare il portale di sicurezza delle app cloud di Office 365

> [!NOTE]
> Per accedere al portale di Office 365 cloud app Security, è necessario essere un amministratore globale di Office 365, un amministratore della sicurezza o un lettore di sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
È possibile accedere a Office 365 cloud app Security Portal accedendo a [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e accedendo. 

È inoltre possibile accedere al centro sicurezza &amp; e conformità di Office 365. Di seguito è indicato un ottimo metodo per eseguire la procedura:
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità.
    
2. Nel centro sicurezza &amp; e conformità, scegliere **avvisi** \> **Gestione avvisi avanzati**. <br/>![Scegliere Gestisci avvisi avanzati per accedere a Office 365 cloud app Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>Se Office 365 cloud app Security non è ancora abilitato e si è un amministratore globale, [attivare office 365 cloud app Security](turn-on-office-365-cas.md).
    
3. Scegliere **Vai a Office 365 cloud app Security**. 
    
## <a name="policies"></a>Generali

Office 365 cloud app Security è compatibile con i criteri definiti per l'organizzazione. Con Office 365 cloud app Security, l'organizzazione riceve numerosi criteri di rilevamento delle anomalie predefinite e diversi modelli per i criteri di attività. Questi criteri sono stati studiati per rilevare anomalie generali, identificare gli utenti che accedono a un indirizzo IP rischioso, rilevare attività ransomware, rilevare attività amministrative da indirizzi IP non aziendali e altro ancora.
  
![Nel portale CAS, scegliere modelli di \> controllo per visualizzare o creare modelli di criteri](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
per visualizzare o utilizzare i modelli di criteri, nel portale Office 365 Cloud App Security accedere a **** \> **modelli**di controllo. 
  
![Nel portale O365 CAS, scegliere Control](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
Per ulteriori informazioni sui criteri, vedere le risorse seguenti:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>Avvisi

Quando vengono definiti i criteri, gli avvisi segnalano le attività sospette o atipiche rilevate. Per visualizzare gli avvisi per l'organizzazione, scegliere **avvisi** nella barra di spostamento nella parte superiore dello schermo. 
  
![Nella pagina avvisi, è possibile visualizzare gli avvisi che sono stati attivati e tutte le azioni intraprese.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
Quando vengono attivati gli avvisi, è possibile esaminarli per ottenere ulteriori informazioni su ciò che accade. Se l'attività è ancora sospetta, è possibile eseguire un'azione. Ad esempio, è possibile informare un utente su un problema, sospendere un utente dall'accesso a Office 365 o richiedere a un utente di eseguire l'accesso alle app di Office 365.
  
Per ulteriori informazioni sugli avvisi, vedere le risorse seguenti:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Esaminare e intervenire sugli avvisi di sicurezza dell'app cloud di Office 365](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>Registri attività

Visualizzare le informazioni sulle attività degli utenti nella pagina del registro attività in Office 365 cloud app Security.
  
![Nel portale O365 CAS, scegliere indagare \> attività log](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
per accedere a questa pagina, nel portale di protezione delle App di Office 365 Cloud accedere a **analizza** \> **log attività**. 
  
![Nel portale O365 CAS, scegliere indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
È anche possibile utilizzare i log del traffico Web con Office 365 cloud app Security. Maggiore è il dettaglio incluso nei file di registro, maggiore è la visibilità che si avrà nelle attività degli utenti. È possibile utilizzare i file di registro di Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, palo alto, Sophos, Squid, Websence, zscaler e altro ancora.
  
[Informazioni sui log del traffico Web e le origini dati per Office 365 cloud app Security](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>App OAuth

Con Office 365 cloud app Security, è possibile consentire o impedire agli utenti dell'organizzazione di utilizzare app di terze parti che accedono ai dati in Office 365.
  
![In O365 CA, è possibile accedere alla pagina Gestisci OAuth Apps dal menu indaga.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
Per accedere a questa pagina, passare a **analisi** \> delle **app OAuth**. 
  
![Nel portale O365 CAS, scegliere indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Gestire le app di OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>Dashboard di individuazione del cloud

Il **Dashboard Discovery cloud**, noto anche come **individuazione delle app**per la produttività, Visualizza informazioni sull'utilizzo delle app cloud all'interno dell'organizzazione. È possibile visualizzare le informazioni sulle app, gli utenti, il traffico, le transazioni e altro ancora usando questo dashboard. Il dashboard di individuazione cloud è simile all'immagine seguente: 
  
![Nel portale di Office 365 CAS, scegliere Discover \> cloud Discovery dashboard](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
per accedere a questo dashboard, nel portale di Office 365 cloud App Security accedere a **Discover** \> **cloud Discovery dashboard**. 
  
![Nel portale di Office 365 CAS, scegliere Scopri](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>Passaggi successivi

- Ottenere i [casi di utilizzo e la guida sull'utilizzo di Office 365 cloud app Security](https://aka.ms/O365CASGuide)
    
- [Preparare l'ambiente per Office 365 Cloud App Security](get-ready-for-office-365-cas.md)
    

