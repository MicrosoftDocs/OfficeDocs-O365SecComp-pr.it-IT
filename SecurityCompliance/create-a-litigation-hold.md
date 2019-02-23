---
title: Creazione di un blocco per controversia legale in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218656"
---
# <a name="create-a-litigation-hold-in-office-365"></a>Creazione di un blocco per controversia legale in Office 365

È possibile inserire una cassetta postale sul blocco per controversia legale per mantenere tutto il contenuto delle cassette postali, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si posiziona una cassetta postale utente in conservazione per controversia legale, viene conservato anche il contenuto della cassetta postale di archiviazione dell'utente (se abilitata). Quando si crea un'esenzione, è possibile specificare una durata del blocco, denominata anche *blocco basato sul tempo*, in modo che gli elementi eliminati e modificati vengano conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato *blocco infinito*) oppure fino a quando non viene rimosso il blocco per controversia legale. Se si specifica un periodo di durata del blocco, viene calcolato a partire dalla data di ricezione di un messaggio o dalla creazione di un elemento della cassetta postale. 
  
Ecco cosa succede quando si crea un blocco per controversia legale.
  
- Gli elementi eliminati in modo definitivo dall'utente vengono conservati nella cartella elementi ripristinabili nella cassetta postale dell'utente per tutta la durata del blocco.
    
- Gli elementi eliminati dalla cartella elementi ripristinabili da parte dell'utente vengono conservati per la durata del blocco.
    
- La quota di archiviazione per la cartella elementi ripristinabili è aumentata da 30 GB a 110 GB.
    
- Gli elementi nelle cassette postali primarie e di archiviazione dell'utente vengono conservati
    
## <a name="before-you-begin"></a>Informazioni preliminari

- Per attivare il blocco per controversia legale in una cassetta postale di Exchange Online, deve essere assegnata una licenza di Exchange Online piano 2. Se a una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnarle una licenza di archiviazione Exchange Online separata per inserirla in blocco.
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>Inserire una cassetta postale in un blocco per controversia legale nell'interfaccia di amministrazione di Office 365

Di seguito sono riportati i passaggi per inserire un Maibox sul blocco per controversia legale utilizzando l'interfaccia di amministrazione di Office 365.

1. Accedere a https://portal.office.com/adminportal/home e accedere utilizzando l'account di amministratore globale.
2. Fare clic su utenti**attivi** nel riquadro di spostamento sinistro. **** > 
3. Selezionare l'utente di cui si desidera inserire la cassetta postale per il blocco per controversia legale.
4. Nella pagina del volo, fare clic su **impostazioni di posta**, quindi fare clic su **modifica** accanto a blocco per **controversia legale**.
5. Nella pagina **blocco per controversIa legale** fare clic sull'interruttore per attivare il blocco per controversia legale e completare le seguenti impostazioni facoltative che vengono visualizzate:
 
    ![O365_LitigationHold1. png](media/O365-LitigationHold1.png)

    a. **durata del blocco (giorni)** : utilizzare questa casella per creare un blocco basato sul tempo e specificare il periodo di conservazione degli elementi della cassetta postale quando la cassetta postale viene inserita nella conservazione per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione di un elemento della cassetta postale. Se si lascia vuota questa casella, gli elementi vengono conservati a tempo indeterminato o fino a quando non viene rimosso il blocco. Utilizzare giorni per specificare la durata.
    
    b. **Note** : utilizzare questa casella per informare l'utente che la cassetta postale è in blocco per controversia legale. La nota verrà visualizzata nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook.
     
    c. **pagina Web** : utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sul blocco per controversia legale. Questo URL viene visualizzato nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook.
 
6. Fare clic su **Salva** per creare il blocco per controversia legale.

Dopo aver creato il blocco, le impostazioni di posta elettronica nella pagina di volo indicano che il blocco per controversia legale è attivato per l'utente selezionato.

![O365_LitigationHold2. png](media/O365-LitigationHold2.png)

Per ulteriori informazioni sulla creazione e sulla gestione di controversia legale e sull'utilizzo di Exchange Online PowerShell per creare in blocco la controversia legale, vedere [posizionare una cassetta postale sul blocco per controversIa legale](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).
