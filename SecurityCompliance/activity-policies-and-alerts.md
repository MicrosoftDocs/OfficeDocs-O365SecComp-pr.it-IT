---
title: Criteri delle attività e avvisi in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: Definire i criteri di attività con Office 365 cloud app Security per impostare gli avvisi da attivare quando si verificano o si verificano attività specifiche. Se si configurano i criteri per attivare gli avvisi, è possibile ricevere una notifica e monitorare le attività specifiche.
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219766"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Criteri delle attività e avvisi in Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](anomaly-detection-policies-in-ocas.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
   
Con Office 365 cloud app Security, i criteri di gestione cloud avanzati attivano gli avvisi per attività specifiche che si verificano o si verificano troppo spesso. Ad esempio, se un utente tenta di accedere a Office 365 e ha esito negativo di 70 volte in un minuto. Si supponga che un altro utente scaricherà 7.000 file o che sembri sia stato firmato dal Canada, quando l'utente dovrebbe trovarsi in un'altra posizione. O peggio, supponiamo che l'account di un utente sia stato compromesso e che un utente malintenzionato usi quell'account per accedere alle app cloud dell'organizzazione e ai dati sensibili.
  
Se sei un amministratore [globale o un amministratore della sicurezza](permissions-in-the-security-and-compliance-center.md), gli avvisi attività notificano quando si verificano eventi come questi. È quindi possibile intraprendere azioni specifiche, ad esempio la sospensione di un account utente fino a quando non è possibile esaminare cosa è successo.
  
> [!NOTE]
> I criteri di protezione delle app di Office 365 cloud sono diversi dai [criteri di avviso &amp; nel centro sicurezza e conformità di Office 365](alert-policies.md). I criteri di attività descritti in questo articolo sono definiti nel portale di Office 365 cloud app Security e consentono di gestire al meglio l'ambiente cloud dell'organizzazione. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

Verificare quanto segue:
  
- L'organizzazione dispone di [Office 365 cloud app Security](office-365-cas-overview.md)e il servizio è [attivato](turn-on-office-365-cas.md).
    
- La [registrazione di controllo](turn-audit-log-search-on-or-off.md) è attivata per l'ambiente Office 365. 
    
- Si è un amministratore globale o un amministratore della sicurezza per Office 365.
    
## <a name="create-a-new-activity-policy"></a>Creare un nuovo criterio di attività

1. In qualità di amministratore globale o amministratore della sicurezza, passare al cloud app Security Portal[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() ed eseguire l'accesso. <br>Verrà eseguita la pagina Criteri di protezione delle app di Office 365 cloud.<br>![Quando si passa al portale di protezione delle app di Office 365 cloud, si inizia con la pagina Criteri](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
2. Fare clic su **Crea criterio**, quindi selezionare **criteri attività**.<br>![Quando si crea un criterio in O365 CA, è possibile scegliere tra i criteri di attività e i criteri di rilevamento delle anomalie.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
3. Nella pagina **Crea criteri attività** specificare il nome e la **Descrizione**dei **criteri** . Per basare il criterio su un modello predefinito, sceglierne uno nell'elenco dei **modelli di criteri** o creare criteri personalizzati senza utilizzare un modello.<br>![È possibile creare criteri di attività con Office 365 cloud app Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
4. Scegliere un **criterio di gravità** (basso, medio o alto) che misuri la gravità del problema se questo criterio attiva un avviso. In questo modo è possibile filtrare gli avvisi durante la revisione in un secondo momento. 
    
5. Scegliere una **categoria** per questo criterio. Questo consente di filtrare e ordinare gli avvisi che sono stati attivati o di raggruppare i criteri quando vengono esaminati per apportare modifiche. 
    
6. Scegliere **filtri attività** per impostare altre azioni o metriche che attiveranno un avviso in base a questo criterio. 
    
7. In **parametri di corrispondenza attività**specificare se una violazione dei criteri verrà attivata quando una singola attività corrisponde ai filtri o se è necessario un numero specifico di attività ripetute prima che l'avviso venga attivato.<br>Se si seleziona **attività ripetute**, specificare il numero di attività, la tempistica e se una violazione conterà un utente all'interno di un'app specifica o per lo stesso utente con qualsiasi app.
    
8. Facoltativamente, è possibile selezionare **Crea avviso** per creare avvisi aggiuntivi per ricevere notifiche da questo criterio (tramite posta elettronica, messaggio di testo o entrambi).<br>Assicurarsi **che il provider di `no-reply@cloudappsecurity.com`posta elettronica non blocchi le e-mail inviate **. 
  
9. Scegliere le **azioni** da eseguire quando si attiva un avviso per sospendere l'utente o richiedere all'utente di accedere di nuovo alle app di Office 365. 
    
10. Scegliere **Crea** per completare la creazione del criterio. 
    
## <a name="next-steps"></a>Passaggi successivi

- [Criteri di rilevamento delle anomalie](anomaly-detection-policies-in-ocas.md)
    
- [Integrare il server SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- [Raggruppare gli indirizzi IP per semplificare la gestione](group-your-ip-addresses-in-ocas.md)
    

