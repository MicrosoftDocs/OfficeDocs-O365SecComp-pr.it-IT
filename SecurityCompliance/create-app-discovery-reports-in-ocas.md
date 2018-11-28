---
title: Creare i report dell’individuazione di app con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: Creare report con Office 365 Cloud App sicurezza che consentono di comprendere come vengono utilizzati gli utenti dell'organizzazione Office 365 e altre applicazioni.
ms.openlocfilehash: f801c70e839a62b5bbb5423ff5e7c513dd1f09b4
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706300"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>Creare i report dell’individuazione di app con Office 365 Cloud App Security

Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
Protezione di Office 365 Cloud App consente agli amministratori globali, gli amministratori della protezione e lettori sicurezza approfondire servizi cloud utilizzano utenti dell'organizzazione. Ad esempio, è possibile visualizzare gli utenti archiviazione che collaborano sui documenti e la quantità di dati è in fase di caricamento per le applicazioni o servizi che si trovano all'esterno di Office 365.
  
Per generare un report di individuazione applicazioni, è caricare manualmente i file di registro del traffico web dai firewall e i proxy e quindi protezione di Office 365 Cloud App analizza e consente di analizzare i file per il report.
  
> [!NOTE]
> È necessario essere un amministratore globale, l'amministratore della sicurezza o lettore di protezione per eseguire le attività descritte in questo articolo. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="create-a-report-with-app-discovery"></a>Creare un rapporto con individuazione app

Per creare un report di individuazione applicazioni, si identifica l'origine dati di un fornitore per i file di registro che si desidera avere analizzata, selezionare i file di registro e quindi richiede il report.
  
> [!NOTE]
> Utilizzare i file di log del traffico web che includono i periodi di picco traffico per ottenere la migliore rappresentazione dei dati di utilizzo nella propria organizzazione. 
  
1. Raccogliere i [registri di traffico web e le origini dati per la protezione di Office 365 Cloud App](web-traffic-logs-and-data-sources-for-ocas.md).
    
2. Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere utilizzando l'account di lavoro o della scuola. 
    
3. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.
    
4. Scegliere **Vai a Office 365 Cloud App protezione**.
    
5. Scegliere **individuazione** \> **Crea un nuovo report**.
    
    ![Nel portale di accesso client di Office 365, selezionare individuazione](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. Specificare un nome e una descrizione per il report e quindi selezionare l'origine dati per i registri di traffico web nell'elenco **origine dati** . 
    
    ![In accesso client di Office 365, selezionare individuazione \> creare nuovi report](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > Se un'origine dati che si desidera utilizzare non è elencata, è possibile richiedere che da aggiungere. Selezionare **altri** per **origine dati**e quindi digitare il nome dell'origine dati che si sta tentando di caricare. Si verrà esaminare il registro e consentono di conoscere se viene aggiunto il supporto per l'origine dati che lo ha generato. 
  
7. Passare al percorso dei file di registro che raccolti e selezionare i file. I file di registro devono essere stati generati dall'origine dati che si è scelto per il report.
    
8. Fare clic su **Crea** per avviare il processo di creazione di report. 
    
9. Per visualizzare lo stato del report, fare clic su **Gestisci snapshot rapporti**. Quando un report è pronto, verrà visualizzato l'opzione **Visualizza report** . 
    
## <a name="next-steps"></a>Passaggi successivi

- [Leggere ed eseguire l'azione gli avvisi](review-office-365-cas-alerts.md)
    
- [Esaminare i risultati dell’individuazione di app in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md)
    
- Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)
    

