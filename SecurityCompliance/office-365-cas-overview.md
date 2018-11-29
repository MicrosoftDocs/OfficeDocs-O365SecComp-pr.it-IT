---
title: Panoramica di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: "Protezione di Office 365 Cloud App offre offre informazioni sul attività sospette in Office 365 in modo che è possibile ricercare situazioni in cui sono potenzialmente problematici e, se necessario, eseguire un'azione per risolvere i problemi di sicurezza. "
ms.openlocfilehash: 722c305288798b38ac125a693d9d150446458324
ms.sourcegitcommit: cd452513d8761b2e50b4f9b6cf29422d146307ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864557"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Panoramica di Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|Si è seguito!  <br/> [Passaggio successivo](get-ready-for-office-365-cas.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |[Avviare utilizzando](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Protezione di Office 365 Cloud App è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, protezione di Office 365 Cloud App può essere acquistata come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
Protezione di Office 365 Cloud App vengono fornite informazioni sulle attività sospette in Office 365 in modo che è possibile ricercare situazioni in cui sono potenzialmente problematici e, se necessario, eseguire un'azione per risolvere i problemi di sicurezza. Con Office 365 Cloud App protezione, è possibile ricevere notifiche di trigger avvisi per attività atipiche o potenzialmente dannoso, vedere modalità di accesso e utilizzati, i dati dell'organizzazione in Office 365 sospendere gli account utente che attività sospette e richiedono agli utenti di eseguire nuovamente l'accesso alle app di Office 365 dopo un avviso se è stato attivato. In questo articolo per una panoramica delle funzionalità e caratteristiche di protezione di Office 365 Cloud App.
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>Come trovare il portale di Office 365 Cloud App Security

> [!NOTE]
> Per accedere al portale di Office 365 Cloud App sicurezza, è necessario essere un amministratore globale, amministratore della sicurezza o lettore di sicurezza. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
Accedere al portale di protezione di applicazioni di Office 365 Cloud mediante la protezione di Office 365 è possibile &amp; centro conformità. Ecco un modo efficace per eseguire questa operazione:
  
1. Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**. <br/>![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>(Se Office 365 Cloud App sicurezza non è ancora abilitato e si è un amministratore globale, di [attivare la protezione di Office 365 Cloud App](turn-on-office-365-cas.md).)
    
3. Scegliere **Vai a Office 365 Cloud App protezione**. 
    
## <a name="policies"></a>Criteri

Office 365 Cloud App sicurezza interagisce con i criteri definiti per l'organizzazione. Con Office 365 Cloud App protezione, l'organizzazione Ottiene molti criteri di rilevamento anomalia predefiniti e diversi modelli di criteri di attività. Questi criteri sono progettati per rilevare alterazioni generale, identificare gli utenti di effettuare l'accesso da un indirizzo IP rischioso, rilevare ransomware attività, rileva le attività di amministratore non aziendale indirizzi IP e altro ancora.
  
![Nel portale delle autorità di certificazione, scegliere controllo \> modelli per visualizzare o creare modelli di criteri](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
Per visualizzare/Usa modelli dei criteri, nel portale di Office 365 Cloud App protezione, passare al **controllo** \> **modelli**. 
  
![Nel portale di accesso client di Office 365, selezionare controllo](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
Per ulteriori informazioni sui criteri, vedere le risorse seguenti:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>Avvisi

Quando vengono definiti i criteri, gli avvisi notificare potenzialmente dannoso o atipiche attività che sono state rilevate. Per visualizzare gli avvisi per la propria organizzazione, selezionare **avvisi** sulla barra di spostamento nella parte superiore dello schermo. 
  
![Nella pagina avvisi, è possibile visualizzare gli avvisi sono state attivate e le azioni eseguite.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
Come gli avvisi verranno attivati è possibile rivedere per ulteriori informazioni sulle operazioni in corso. Quindi, se l'attività è ancora sospetto, è possibile eseguire l'azione. Ad esempio, è possibile inviare notifiche a un utente relativa a un problema sospendere un utente di accedere a Office 365 o richiedere a un utente per l'accesso alle app di Office 365.
  
Per ulteriori informazioni sugli avvisi, vedere le risorse seguenti:
  
- [Criteri delle attività e avvisi in Office 365 Cloud App Security](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md)
    
- [Leggere ed eseguire l'azione avvisi di protezione di Office 365 Cloud App](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>Registri delle attività

Consente di visualizzare informazioni sulle attività dell'utente nella pagina registro attività in Office 365 Cloud App Security.
  
![Nel portale di accesso client di Office 365, scegli indagare \> registro attività](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
Per accedere a questa pagina, nel portale Office 365 Cloud App sicurezza passare a **indagare** \> **registro attività**. 
  
![Nel portale di accesso client di Office 365, selezionare indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
È possibile utilizzare i registri di traffico web con Office 365 Cloud App protezione, troppo. Ulteriori dettagli inclusi in tali file di registro, la visibilità migliore, è necessario in attività dell'utente. È possibile utilizzare il file di registro da Barracuda, coprire blu, punto di controllo, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, calamari, Websence, Zscaler e altro ancora.
  
[Informazioni sulle origini dati e registri di traffico web per la protezione di Office 365 Cloud App](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="app-permissions"></a>Autorizzazioni dell'App

Con Office 365 Cloud App protezione, è possibile consentire o impedire agli utenti dell'organizzazione di utilizzare applicazioni di terze parti che accedono ai dati in Office 365.
  
![In accesso client di Office 365, è possibile accedere alla pagina gestire le autorizzazioni dell'App dal menu indagare.](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
Per accedere a questa pagina, passare a **indagare** \> **le autorizzazioni dell'App**. 
  
![Nel portale di accesso client di Office 365, selezionare indagare.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[Gestire le autorizzazioni delle app con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>Dashboard di individuazione cloud

Il **Dashboard di individuazione Cloud**, anche noto come **Individuazione di applicazioni di produttività**, vengono visualizzate informazioni sull'utilizzo delle app cloud all'interno dell'organizzazione. È possibile visualizzare informazioni sull'App, gli utenti, il traffico, le transazioni e così via utilizzando il dashboard. Il Dashboard di individuazione Cloud è simile all'immagine seguente: 
  
![Nel portale di accesso client di Office 365, selezionare individuazione \> dashboard individuazione Cloud](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
Per ottenere questo dashboard nel portale Office 365 Cloud App sicurezza passare a **individuazione** \> **individuazione Cloud dashboard**. 
  
![Nel portale di accesso client di Office 365, selezionare individuazione](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>Passaggi successivi

- Ottenere i [casi di utilizzo della protezione di Office 365 Cloud App e manuale dell'utente](https://aka.ms/O365CASGuide)
    
- [Preparazione di Office 365 Cloud App Security](get-ready-for-office-365-cas.md)
    

