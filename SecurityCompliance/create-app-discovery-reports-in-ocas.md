---
title: Creare report sull'individuazione di app con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Creare report con Office 365 cloud app Security che consentano di comprendere in che modo gli utenti dell'organizzazione utilizzano Office 365 e altre app.
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259640"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Creare report sull'individuazione di app con Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
Office 365 cloud app Security consente agli amministratori globali, agli amministratori della sicurezza e ai lettori di sicurezza di acquisire informazioni sui servizi cloud che sono in uso in un'organizzazione. Ad esempio, è possibile visualizzare la posizione in cui gli utenti archiviano e collaborano ai documenti e la quantità di dati caricati nelle app o nei servizi esterni a Office 365.
  
Per generare un report di individuazione delle app, è necessario caricare manualmente i file di registro del traffico Web dai firewall e dai proxy, quindi l'analisi dei file di Office 365 cloud app viene analizzata e analizzata per il report.
  
> [!NOTE]
> Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="create-a-report-with-app-discovery"></a>Creare un report con l'individuazione delle app

Per creare un report di individuazione delle app, identificare l'origine dati del fornitore per i file di registro che si desidera analizzare, selezionare i file di registro e quindi richiedere il report.
  
> [!NOTE]
> Utilizzare i file di registro del traffico Web che includono i periodi di traffico di picco per ottenere la migliore rappresentazione di utilizzo nell'organizzazione. 
  
1. Raccogliere i [log del traffico Web e le origini dati per Office 365 cloud app Security](web-traffic-logs-and-data-sources-for-ocas.md).
    
2. Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere. 
       
3. Scegliere **Scopri** \> **Crea nuovo report**. <br>![Nel portale di Office 365 CAS, scegliere Scopri](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. Specificare un nome e una descrizione per il report e quindi selezionare l'origine dati per i log del traffico Web nell'elenco **origine dati** . <br>![In O365 CA, scegliere Scopri \> Crea nuovo rapporto](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>Se un'origine dati che si desidera utilizzare non è presente nell'elenco, è possibile richiederne l'aggiunta. Selezionare **altro** per **origine dati**e quindi digitare il nome dell'origine dati che si sta tentando di caricare. È possibile esaminare il registro e sapere se viene aggiunto il supporto per l'origine dati che lo ha generato. 
  
5. Passare al percorso dei file di registro raccolti e selezionare i file. È necessario che i file di registro siano stati generati dall'origine dati scelta per il report.
    
6. Fare clic su **Crea** per avviare il processo di creazione del report. 
    
7. Per visualizzare lo stato del report, fare clic su **Gestisci rapporti snapshot**. Quando un report è pronto, verrà visualizzata l'opzione **Visualizza rapporto** . 
    
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- [Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
- Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

