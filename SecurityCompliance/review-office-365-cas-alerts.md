---
title: Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: Utilizzare la pagina avvisi di protezione di applicazioni di Office 365 Cloud per visualizzare i potenziali problemi ed eseguire azioni. È possibile ignorare o risolvere gli avvisi e se necessario, sospendere un account utente.
ms.openlocfilehash: 62431adc73354e573978781f120a11746aef08d9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530188"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |
   
È possibile utilizzare la pagina avvisi di protezione di Office 365 Cloud App per visualizzare problemi potenziali e, se necessario, eseguire l'azione necessaria.
  
> [!NOTE]
> È necessario essere un amministratore globale o sicurezza per eseguire le attività in questo articolo. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="how-to-get-to-the-alerts-page"></a>Come ottenere la pagina avvisi

1. Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. 
    
2. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.
    
    ![Nella pagina avvisi, è possibile visualizzare gli avvisi sono state attivate e le azioni eseguite.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a>Revisione e gestire gli avvisi

Gli avvisi consentono di identificare le attività nell'ambiente Office 365 cloud che è possibile eseguire un'analisi approfondita. È inoltre possibile decidere di creare nuovi criteri o modificare criteri esistenti in base ad avvisi che viene visualizzato. Ad esempio, se è disponibile un amministratore l'accesso da una posizione strana, può decidere impostare un criterio che impedisce agli amministratori di accedere a Office 365 da determinate posizioni.
  
> [!TIP]
> È possibile filtrare gli avvisi per **categoria** o per **gravità** in modo che è possibile gestire innanzitutto i più importanti. 
  
Per ciascun avviso, esaminare la causa per stabilire l'azione da intraprendere. Per visualizzare ulteriori dettagli su un avviso e per eseguire l'azione, ad esempio la risoluzione dell'avviso o sospendere un account di utenti, fare clic sull'avviso per aprire una pagina dei dettagli. Nella pagina dettagli è possibile esaminare il registro attività, gli account e gli utenti che sono correlati all'avviso ed eseguire azioni, tra cui:
  
- **Eliminare** Se l'avviso è falso positivo, chiuderla. È facoltativamente possibile aggiungere un commento che spiega perché chiusa. 
    
- **Risolvere avviso** Se è stato generato l'avviso per un'attività che si conosce non sia una minaccia, risolvere il problema. È facoltativamente possibile aggiungere un commento che spiega perché si risolti. 
    
- **Sospendere** Se si sospetta accesso non autorizzato aggiuntivi su un account, ad esempio, un utente l'accesso da un altro paese quando si conosce tale persona si trova fisicamente presso un ufficio locale, mentre è possibile [sospendere l'account](suspend-or-restore-an-account-in-ocas.md) analizzare ciò che avviene. 
    
## <a name="next-steps"></a>Passaggi successivi

- [Provare a utilizzare un'attività](investigate-an-activity-in-office-365-cas.md)
    
- [Sospendere o il ripristino di un account utente](suspend-or-restore-an-account-in-ocas.md)
    
- Visualizzare un elenco di [origini dati e registri di traffico Web](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)
    

