---
title: Esaminare i risultati dell'individuazione di app in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: La revisione dei rapporti di individuazione delle app in Office 365 cloud app Security consente di ottenere ulteriori informazioni sul modo in cui gli utenti dell'organizzazione utilizzano le app cloud. Dopo aver creato i report di individuazione delle app utilizzando i file di log dai firewall e dai proxy, esaminare i risultati nel dashboard di individuazione delle app.
ms.openlocfilehash: f50ad372450b2a1404829eeb6f6964c1d954dccd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264972"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>Esaminare i risultati dell'individuazione di app in Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
Il dashboard di individuazione cloud è compatibile con i log del traffico web dell'organizzazione per fornire informazioni dettagliate sull'utilizzo delle app cloud. Se si è un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza e l'organizzazione ha [creato rapporti di individuazione delle app in Office 365 cloud app Security](create-app-discovery-reports-in-ocas.md), è possibile utilizzare il dashboard di individuazione cloud per acquisire informazioni sul modo in cui le persone nella propria l'organizzazione utilizza Office 365 e altre app cloud. (Il dashboard di individuazione cloud è noto anche come individuazione delle app per la produttività).
  
 Il dashboard di individuazione cloud consente di visualizzare informazioni dettagliate sul modo in cui gli utenti dell'organizzazione utilizzano Office 365 e altre app. 
  
![The Cloud Discovery dashboard è stato aggiornato](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>Accedere al dashboard di individuazione cloud

1. Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.
    
2. Andare a **Discover** \> **cloud Discovery dashboard**.
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>Visualizzare gli utenti principali, gli indirizzi IP, le app e i livelli di rischio

The Cloud Discovery dashboard offre una panoramica delle app che vengono utilizzate con Office 365 nell'organizzazione, eventuali avvisi aperti, utenti principali e livelli di rischio.
  
![Dashboaard Discovery cloud](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. Nella scheda **Dashboard** , esaminare l'utilizzo globale delle app Cloud nell'organizzazione nella sezione Panoramica nella parte superiore dello schermo. 
    
2. Vedere le **categorie di Office 365** per le app che vengono utilizzate nell'organizzazione. 
    
3. Consultare il widget **Apps individuati** per visualizzare l'utilizzo di Office 365 e di altre app in questa visualizzazione. 
    
4. Esaminare gli **utenti principali** e il widget **indirizzi IP principali** per identificare coloro che utilizzano le app di Office 365 e cloud più all'interno dell'organizzazione. 
    
5. Vedere dove le app persone stanno usando sono per località geografica usando la mappa del **percorso delle app** . 
    
6. Sopra l'area mappe, esaminare il Punteggio di rischio delle app individuate nella panoramica dei **livelli di rischio** . È possibile esaminare i rischi per gli stessi gruppi e le stesse categorie utilizzati nell'area **app scoperte** . Ad esempio, è possibile visualizzare la quantità di traffico in ogni raggruppamento proveniente da applicazioni di alto, medio o basso rischio. 
    
## <a name="dive-deeper-into-the-information"></a>Immergersi più in profondità nelle informazioni

È possibile utilizzare il cloud Discovery per approfondire le app, i sottodomini, gli indirizzi IP e gli utenti.
  
1. Nel dashboard individuazione cloud, scegliere la scheda **app individuate** . 
    
2. Utilizzare la sezione filtri per visualizzare le app in base al nome, alla categoria, al livello di utilizzo o alla data dell'ultima visualizzazione.
    
3. Nell'elenco dei risultati, posizionare il puntatore del mouse su un nome di app per rivelare il collegamento **Visualizza** i sottodomini.<br/> ![Posizionare il puntatore del mouse accanto a un'app per rivelare un collegamento per visualizzare i dettagli del sottodominio](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>Verranno visualizzate informazioni dettagliate sull'app selezionata.
    
4. Per visualizzare i dettagli sugli indirizzi IP, scegliere la scheda **indirizzi IP** .<br/>![Individuazione cloud Visualizza informazioni dettagliate sugli indirizzi IP](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>Nell'elenco dei risultati, selezionare un singolo indirizzo IP per visualizzare informazioni più dettagliate.
    
5. Per visualizzare i dettagli relativi agli utenti di Office 365 all'interno dell'organizzazione, scegliere la scheda **utenti** .<br/>![Discovery Cloud-informazioni sugli utenti](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>Escludi entità

È possibile escludere alcuni utenti di sistema o indirizzi IP per concentrarsi su informazioni più specifiche.
  
1. Scegliere Settings **cloud Discovery Settings**. **** \>
    
2. Scegliere **Escludi entità**.
    
3. Scegliere **gli utenti esclusi** o **gli indirizzi IP esclusi**.
    
4. Specificare gli utenti o gli indirizzi IP e, nella casella **Commenti** , digitare le informazioni sui motivi per cui si escludono gli utenti o gli indirizzi IP. 
    
5. Scegliere **Aggiungi**.
    
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- [Creare report di individuazione delle app](create-app-discovery-reports-in-ocas.md)
    
- Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

