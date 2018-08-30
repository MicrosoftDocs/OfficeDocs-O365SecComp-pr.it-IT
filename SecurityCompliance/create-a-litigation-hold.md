---
title: Creare una conservazione per controversia legale in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: 18b3b3a42e5671b1507522c89faaa4ae34198831
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531197"
---
# <a name="create-a-litigation-hold-in-office-365"></a>Creare una conservazione per controversia legale in Office 365

È possibile effettuare una cassetta postale di conservazione per controversia legale per mantenere tutto il contenuto delle cassette postali, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si effettua una cassetta postale utente conservazione per controversia legale, contenuto nella cassetta postale di archivio dell'utente (se abilitato) viene inoltre mantenuto. Quando si crea un'esenzione, è possibile specificare un intervallo di tempo di attesa (denominato anche un' *archiviazione con scadenza*) in modo da eliminare ed elementi modificati vengono mantenuti per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. Oppure è possibile mantenere solo il contenuto per un tempo indefinito (noti come un' *attesa infinita*) fino a quando non viene rimossa la conservazione per controversia legale. Se si specifica una periodo di durata della conservazione, viene calcolata dalla data di ricezione di un messaggio o viene creato un elemento della cassetta postale. 
  
Ecco cosa succede quando si crea una conservazione per controversia legale.
  
- Gli elementi eliminati in modo permanente dall'utente vengono mantenuti nella cartella elementi ripristinabili nella cassetta postale dell'utente per la durata dell'esenzione.
    
- Gli elementi eliminati dalla cartella elementi ripristinabili dall'utente vengono mantenuti per tutta la durata dell'esenzione.
    
- La quota di archiviazione per la cartella elementi recuperabili viene aumentata da 30 GB a 110 GB.
    
- Vengono conservati gli elementi in principale dell'utente e le cassette postali di archiviazione
    
## <a name="before-you-begin"></a>Informazioni preliminari

- Per inserire una cassetta postale di Exchange Online sulla conservazione per controversia legale, deve essere assegnato una licenza di Exchange Online piano 2. Se una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnarlo una licenza separata archiviazione Exchange Online per mettere in attesa.
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>Inserire una cassetta postale conservazione per controversia legale nell'interfaccia di amministrazione di Office 365

Ecco la procedura per bloccare un iniziata la conservazione per controversia legale utilizzando l'interfaccia di amministrazione di Office 365.

1. Accedere a https://portal.office.com/adminportal/home e accedere utilizzando l'account amministratore globale.
2. Fare clic su **utenti** > **utenti attivi** nel riquadro di spostamento a sinistra.
3. Selezionare l'utente la cui cassetta postale desiderata per bloccare la conservazione per controversia legale.
4. Nella pagina di accesso rapido, fare clic su **Impostazioni posta elettronica**e quindi fare clic su **Edit** accanto alla **conservazione per controversia legale**.
5. Scegliere Attiva o disattiva per attivare la conservazione per controversia legale e completare le seguenti opzioni facoltative che vengono visualizzate nella pagina **conservazione per controversia legale** :
 
    ![O365_LitigationHold1.PNG](media/O365-LitigationHold1.png)

    r. **durata della conservazione (giorni)** -utilizzare questa casella per creare un'esenzione basate sul tempo e specificare il tempo di mantenimento degli elementi della cassetta postale quando viene effettuata la cassetta postale di conservazione per controversia legale. La durata viene calcolata dalla data di ricezione o creato un elemento della cassetta postale. Se si lascia vuota questa casella, di mantenimento degli elementi per un tempo indefinito o fino alla rimozione. Utilizzare i giorni lavorativi per specificare la durata.
    
    b. **Nota** : utilizzare questa casella per informare l'utente delle relative cassette postali sono controversie legali. La nota viene visualizzata nella pagina informazioni Account nella cassetta postale dell'utente se utilizzano Outlook 2010 o versioni successive. Per accedere a questa pagina, gli utenti possono fare clic su **File** di Outlook.
     
    **pagina Web** - c. utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sulla conservazione per controversia legale. Questo URL verrà visualizzato nella pagina informazioni Account nella cassetta postale dell'utente che utilizzano Outlook 2010 o versioni successive. Per accedere a questa pagina, gli utenti possono fare clic su **File** di Outlook.
 
6. Fare clic su **Salva** per creare la conservazione per controversia legale.

Dopo aver creato la conservazione, le impostazioni di posta elettronica nella pagina di accesso rapido Mostra di conservazione per controversia legale è attivata per l'utente selezionato.

![O365_LitigationHold2.PNG](media/O365-LitigationHold2.png)

Per ulteriori informazioni sulla creazione e gestione delle esenzioni controversie legali e utilizzo di Exchange Online PowerShell per creare controversia contiene, vedere [Place una cassetta postale di conservazione per controversia legale](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).
