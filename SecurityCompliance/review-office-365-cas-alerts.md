---
title: Esaminare gli avvisi per intervenire in Office 365 Cloud App Security
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Utilizzare la pagina avvisi in Office 365 cloud app Security per visualizzare potenziali problemi e intervenire. È possibile eliminare o risolvere gli avvisi e, se necessario, sospendere un account utente.
ms.openlocfilehash: 701d80c3f890115c6c403fff21d2d0444d71c95a
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862468"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Esaminare gli avvisi per intervenire in Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
È possibile utilizzare la pagina avvisi in Office 365 cloud app Security per visualizzare potenziali problemi e, se necessario, intervenire.
  
> [!NOTE]
> Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o un amministratore della sicurezza. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="how-to-get-to-the-alerts-page"></a>Come accedere alla pagina avvisi

1. Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.
  
2. Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.<br/>![Nella pagina avvisi, è possibile visualizzare gli avvisi che sono stati attivati e tutte le azioni intraprese.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
 
> [!NOTE]
> gli avvisi per la sicurezza delle App Cloud sono visibili anche nel centro conformità di Office 365 security **** > & (vai a avvisi**visualizza**avvisi. Attualmente, tuttavia, è necessario risolvere questi avvisi sia nel portale cloud app Security che nel centro conformità di Office 365 Security &. Per ulteriori informazioni, vedere [viewIng cloud app Security Alerts](alert-policies.md#viewing-cloud-app-security-alerts). 
 
## <a name="review-and-handle-alerts"></a>Esaminare e gestire gli avvisi

Gli avvisi consentono di identificare le attività nell'ambiente cloud di Office 365 che potrebbe essere necessario esaminare ulteriormente. È inoltre possibile decidere di creare nuovi criteri o di modificare i criteri esistenti in base agli avvisi visualizzati. Ad esempio, se viene visualizzato un amministratore che accede da una posizione sconosciuta, è possibile decidere di impostare un criterio che impedisca agli amministratori di accedere a Office 365 da determinate posizioni.
  
> [!TIP]
> È possibile filtrare gli avvisi per **categoria** o per **gravità** , in modo da poter gestire prima quelli più importanti. 
  
Per ogni avviso, esaminare cosa lo ha causato in modo da poter decidere quale azione eseguire. Per ulteriori informazioni su un avviso e per eseguire operazioni, ad esempio la risoluzione dell'avviso o la sospensione di un account utente, scegliere l'avviso per aprire una pagina dei dettagli. Nella pagina dei dettagli, è possibile esaminare il registro attività, gli account e gli utenti correlati all'avviso e intraprendere azioni come le seguenti:
  
- **Ignora** Se l'avviso è un falso positivo, respingerlo. Facoltativamente, è possibile aggiungere un commento per spiegare il motivo per cui è stato respinto. 
    
- **Risoluzione degli avvisi** Se l'avviso è stato attivato da un'attività che si conosce non è una minaccia, risolverla. Facoltativamente, è possibile aggiungere un commento per spiegare perché è stato risolto. 
    
- **Sospensione** Se si sospetta che gli accessi non autorizzati su un account, ad esempio un utente che effettua l'accesso da un altro paese quando si è a conoscenza che la persona è fisicamente presente in un ufficio locale, è possibile [sospendere l'account](suspend-or-restore-an-account-in-ocas.md) mentre si indaga su cosa succede. 
    
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare un'attività](investigate-an-activity-in-office-365-cas.md)
    
- [Sospendere o ripristinare un account utente](suspend-or-restore-an-account-in-ocas.md)
    
- Visualizzare un elenco di [log del traffico Web e origini dati](web-traffic-logs-and-data-sources-for-ocas.md) supportate
    
- Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

