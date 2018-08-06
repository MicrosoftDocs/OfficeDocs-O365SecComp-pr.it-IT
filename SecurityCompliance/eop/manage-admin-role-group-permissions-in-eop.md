---
title: Gestione autorizzazioni gruppo di ruoli di amministratore in EOP
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 5d50c77c97f2c345aa3994e7fa3ecd2eea93a13a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026663"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>Gestione autorizzazioni gruppo di ruoli di amministratore in EOP
  
In Microsoft Exchange Online Protection (EOP), è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per rendere un utente membro di un gruppo o di gruppi di ruoli per poter assegnargli autorizzazioni per effettuare attività amministrative specifiche. È inoltre possibile rimuovere un utente da un gruppo o da gruppi di ruoli utilizzando l'interfaccia di amministrazione di Exchange.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 5-10 minuti
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Utenti, contatti e gruppi di ruoli" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md). 
    
- Alcune autorizzazione in Office 365 eseguono il mapping delle autorizzazioni dei gruppi di ruoli di amministratore di EOP. Per ulteriori informazioni, vedere la colonna "Ruolo in Exchange Online" nella sezione "Quali servizi sono disponibili per le mie autorizzazioni di Office 365?" in [Assegnazione di ruoli di amministratore](https://go.microsoft.com/fwlink/p/?LinkId=286708).
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="what-do-you-want-to-do"></a>Operazione desiderata

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>Aggiunta dei membri a gruppi di ruoli tramite EAC

1. Nell'interfaccia di amministrazione di Exchange, andare a **Autorizzazioni** \> **Ruoli amministratore**, fare clic sul gruppo di ruoli a cui aggiungere l'utente o gli utenti, quindi fare clic su **Modifica**![Icona Modifica](../media/ITPro-EAC-EditIcon.png).
    
2. In Membri, fare clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.png). Viene visualizzata la finestra Seleziona membri.
    
3. Cercare l'utente o gli utenti da aggiungere o selezionarli dall'elenco.
    
4. Una volta selezionati gli utenti che si desidera aggiungere, fare clic su **Aggiungi**, quindi fare clic su **OK**. La finestra Seleziona membri si chiude.
    
5. L'utente sarà stato aggiunto al riquadro **Membri**. Fare clic su **Salva**.
    
    > [!NOTE]
    > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi. 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>Rimozione di membri da un gruppo di ruoli di amministratore tramite EAC

1. Nell'interfaccia di amministrazione di Exchange, andare a **Autorizzazioni** \> **Ruoli amministratore**, fare clic sul gruppo di ruoli da cui rimuovere l'utente o gli utenti, quindi fare clic su **Modifica**![Icona Modifica](../media/ITPro-EAC-EditIcon.png).
    
2. In Membri, selezionare l'utente o gli utenti che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.png).
    
3. Fare clic su **Salva** per salvare la modifica al gruppo di ruoli e tornare alla pagina **Ruoli amministratore**. Per verificare di aver rimosso correttamente l'utente dal gruppo di ruoli amministratore, assicurarsi che il membro non venga più visualizzato in Membri nel riquadro dei dettagli del gruppo di ruoli selezionato. 
    
    > [!NOTE]
    > Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md)
  

