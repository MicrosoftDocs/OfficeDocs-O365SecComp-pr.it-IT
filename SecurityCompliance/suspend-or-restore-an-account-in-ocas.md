---
title: Sospendere o ripristinare un account utente in Office 365 Cloud App Security
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
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 Cloud App protezione, è possibile eseguire le operazioni di governance sono di sospendere o riprendere un account utente. '
ms.openlocfilehash: a5c75edefc6ddb87b5676c4253aafe04817f6a1d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530393"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Sospendere o ripristinare un account utente in Office 365 Cloud App Security

Gestione di sicurezza avanzata di Office 365 è sicurezza App Cloud di Office 365.
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
Si supponga che si riceve un avviso che uno degli account utente dell'organizzazione per Office 365 è stato danneggiato. In alternativa, si supponga che è stato ricevuto un avviso indicante che si verificano problemi con un account utente. Con Office 365 Cloud App protezione, è possibile sospendere un account utente e ripristinarla successivamente dopo che sono state analizzate avvisi ricevuti.
  
> [!NOTE]
> Protezione di Office 365 Cloud App è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, protezione di Office 365 Cloud App può essere acquistata come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Per sospendere un account utente in Office 365 Cloud App Security

Quando si sospende un account utente, si impedisce all'utente di effettuare nuovamente l'accesso. È identico modifica l'account utente direttamente in Office 365 per impostare lo stato di accesso di **accesso bloccato**.
  
> [!NOTE]
> Se si blocca un utente di accedere a Office 365, sospendendo li o si modifica lo stato di accesso, tenere presente che può richiedere un'ora o richiesto per rendere effettive in tutti i dispositivi e client ([modificare o cambiare un utente in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) dell'utente. Se l'utente ha eseguito l'accesso a Office 365, il blocco avrà effetto ogni volta che Office 365 richiede l'accesso. 
  
1. Come [amministratore globale o amministratore di protezione](permissions-in-the-security-and-compliance-center.md), passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.
    
5. Nella colonna **avviso** fare doppio clic su un avviso che fa riferimento a un account utente specifico. 
    
6. Nella casella **account**, nella colonna **stato** , scegliere impostazioni ![icona impostazioni](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **utente Suspend**.
    
## <a name="to-restore-a-user-account"></a>Per ripristinare un account utente

Vedere [ripristino di un utente in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    
- [Gestire le autorizzazioni dell'app con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
    
- Esaminare le [attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)
    

