---
title: Esaminare i risultati di App Discovery in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: Esame dei report di individuazione app nella gestione della protezione avanzata consentono di ulteriori informazioni sull'utilizzano di applicazioni basate su cloud persone nell'organizzazione. Dopo aver creato i rapporti di individuazione app utilizzando i file di registro dai firewall e proxy, esaminare i risultati nel dashboard di individuazione applicazioni.
ms.openlocfilehash: 188ef87920b26069e7d99057662b3812be22e46c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530206"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>Esaminare i risultati di App Discovery in Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
Il dashboard di individuazione Cloud utilizza i registri di traffico web dell'organizzazione per fornire informazioni dettagliate sull'utilizzo delle app cloud. Se si invia un amministratore globale, l'amministratore della sicurezza o lettore di sicurezza e l'organizzazione ha [creato app individuazione rapporti di protezione di applicazioni di Office 365 Cloud](create-app-discovery-reports-in-ocas.md), è possibile utilizzare il dashboard di individuazione Cloud per comprendere come utenti nel organizzazione utilizza Office 365 e altre applicazioni basate su cloud. (Il dashboard di individuazione Cloud è noto anche come è produttività App Discovery).
  
 **A partire da 2018 marzo, il dashboard di individuazione Cloud con nuove funzionalità** che rendono più semplice visualizzare informazioni dettagliate sulla modalità di utilizzo personale della tua organizzazione Office 365 e altre applicazioni. 
  
![È stato aggiornato il dashboard di individuazione Cloud](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>Accedere al dashboard individuazione Cloud

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.
    
    (Se Office 365 Cloud App sicurezza non è ancora abilitato e si è un amministratore globale, di [attivare la protezione di Office 365 Cloud App](turn-on-office-365-cas.md).)
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.
    
4. Accedere a **individuazione** \> **individuazione Cloud dashboard**.
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>Vedere utenti principali, gli indirizzi IP, App e livelli di rischio

Il dashboard di individuazione Cloud viene fornita una panoramica in rapida di applicazioni che vengono utilizzati con Office 365 nell'organizzazione, tutti gli avvisi aperti, utenti principali e livelli di rischio.
  
![Cloud individuazione dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. Nella scheda **Dashboard** esaminare l'utilizzo di app cloud globale dell'organizzazione nella sezione Panoramica nella parte superiore dello schermo. 
    
2. Vedere le **categorie di Office 365** per le applicazioni che vengono utilizzati nell'organizzazione. 
    
3. Esaminare widget **Discovered App** di visualizzare i dati di utilizzo di Office 365 e altre App in questa visualizzazione. 
    
4. Esaminare il widget **utenti principali** e **gli indirizzi IP principali** per identificare gli utenti che utilizzano Office 365 e cloud App maggiormente all'interno dell'organizzazione. 
    
5. Visualizzazione della posizione App utilizzano persone dalla posizione geografica utilizzando il mapping **sede App** . 
    
6. Sopra l'area di mappe, esaminare il punteggio di rischio delle App rilevati in Panoramica **livelli di rischio** . È possibile esaminare i rischi per i gruppi e categorie utilizzato nell'area **Discovered App** stesso. Ad esempio, è possibile visualizzare la quantità di traffico in ogni raggruppamento è da apps elevato, medio o basso rischio. 
    
## <a name="dive-deeper-into-the-information"></a>Approfondisci le informazioni

È possibile utilizzare l'individuazione Cloud per rendere una più approfondita App, i sottodomini, indirizzi IP e gli utenti.
  
1. Nel dashboard di individuazione Cloud, fare clic sulla scheda **Discovered App** . 
    
2. Utilizzare la sezione filtri per visualizzare le App per nome, categoria, il livello di utilizzo o ultimo considerata data.
    
3. Nell'elenco dei risultati al passaggio del mouse per un nome di applicazione per visualizzare il collegamento **Visualizza i sottodomini** . 
    
    ![Al passaggio del mouse accanto a un'applicazione per visualizzare un collegamento per visualizzare i dettagli sottodominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)
  
    Informazioni dettagliate sull'app selezionata verranno visualizzato.
    
4. Per visualizzare informazioni dettagliate sugli indirizzi IP, fare clic sulla scheda **indirizzi IP** . 
    
    ![Individuazione cloud Visualizza informazioni dettagliate sugli indirizzi IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)
  
    Nell'elenco dei risultati, selezionare un singolo indirizzo IP per visualizzare informazioni più dettagliate.
    
5. Per visualizzare informazioni dettagliate sugli utenti di Office 365 all'interno dell'organizzazione, fare clic sulla scheda **utenti** . 
    
    ![Individuazione cloud - informazioni gli utenti](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>Esclude le entità

È possibile escludere alcune gli utenti o gli indirizzi IP per individuare le informazioni più specifiche.
  
1. Fare clic su **Impostazioni** \> **le impostazioni di individuazione Cloud**.
    
2. Scegliere **escludere le entità**.
    
3. Scegliere **gli utenti esclusi** o **gli indirizzi IP esclusi**.
    
4. Specificare gli utenti o gli indirizzi IP e nella casella **commenti** digitare informazioni sui motivi per cui si sono esclusi quegli utenti o gli indirizzi IP. 
    
5. Scegliere **Aggiungi**.
    
## <a name="next-steps"></a>Passaggi successivi

- [Leggere ed eseguire l'azione gli avvisi](review-office-365-cas-alerts.md)
    
- [Creare i rapporti di individuazione applicazioni](create-app-discovery-reports-in-ocas.md)
    
- Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)
    

