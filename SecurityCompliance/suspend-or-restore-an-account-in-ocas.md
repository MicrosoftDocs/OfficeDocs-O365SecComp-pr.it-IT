---
title: Sospendere o ripristinare un account utente in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: 'Con Office 365 cloud app Security, le azioni di governance che è possibile intraprendere sono la sospensione o la sospensione di un account utente. '
ms.openlocfilehash: 6c34c04b6a1e389809b611db0ca2f30ecd8c0ada
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087395"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>Sospendere o ripristinare un account utente in Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
Si supponga di ricevere un avviso per il quale uno degli account utente dell'organizzazione per Office 365 è stato compromesso. In alternativa, si supponga di aver ricevuto un avviso che indica che è presente un errore in un account utente. Con Office 365 cloud app Security, è possibile sospendere un account utente e successivamente ripristinarlo dopo aver esaminato gli avvisi ricevuti.
  
> [!NOTE]
> Office 365 cloud app Security è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un altro abbonamento a Office 365 Enterprise, Office 365 cloud app Security può essere acquistato come componente aggiuntivo. (come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **aggiungi abbonamenti**). Per ulteriori informazioni, vedere [office 365 Platform Service Description: office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6). 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Per sospendere un account utente in Office 365 cloud app Security

Quando si sospende un account utente, si impedisce all'utente di accedere di nuovo. Lo stesso vale per la modifica dell'account utente direttamente in Office 365 per impostare lo stato di accesso per l' **accesso bloccato**.
  
> [!NOTE]
> Se si blocca un utente dall'accesso a Office 365, sospendendo o modificando lo stato di accesso, tenere presente che può richiedere un'ora o più per avere effetto su tutti i dispositivi e i client dell'utente ([modificare o modificare un utente in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). Se l'utente ha eseguito l'accesso a Office 365, il blocco avrà effetto ogni volta che Office 365 richiede la possibilità di accedere di nuovo. 
  
1. In qualità di amministratore [globale o amministratore della sicurezza](permissions-in-the-security-and-compliance-center.md), [https://protection.office.com](https://protection.office.com) passare a e accedere con l'account aziendale o dell'Istituto di istruzione. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel centro sicurezza &amp; e conformità, scegliere **avvisi** \> **Gestione avvisi avanzati**.
    
3. Scegliere **Vai a Office 365 cloud app Security**.<br>![Nel centro sicurezza &amp; e conformità, scegliere Gestisci avvisi avanzati per accedere a Office 365 cloud app Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>
  
4. Nella barra di spostamento nella parte superiore dello schermo, scegliere **avvisi**.
    
5. Nella colonna **avviso** fare doppio clic su un avviso relativo a un account utente specifico. 
    
6. In **account**, nella colonna **stato** scegliere ![l'icona](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> impostazioni impostazioni **Sospendi utente**.
    
## <a name="to-restore-a-user-account"></a>Per ripristinare un account utente

Vedere [ripristinare un utente in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare gli avvisi per intervenire in Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    
- [Gestire le app di OAuth con Office 365 Cloud App Security](manage-app-permissions-in-ocas.md)
    
- Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

