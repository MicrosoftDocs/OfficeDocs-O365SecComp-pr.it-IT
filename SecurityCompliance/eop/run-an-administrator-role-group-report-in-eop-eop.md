---
title: 'Eseguire il rapporto del gruppo di ruoli amministratore in EOP '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Quando un amministratore aggiunge membri o rimuove membri dai gruppi di ruoli amministratore, Microsoft Exchange Online Protection (EOP) registra ogni occorrenza.
ms.openlocfilehash: 49311faa4ee54fafa1c05a2314ed2f9d74cbe5a5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027203"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Eseguire il rapporto del gruppo di ruoli amministratore in EOP 

 Quando un amministratore aggiunge membri o rimuove membri dai gruppi di ruoli amministratore, Microsoft Exchange Online Protection (EOP) registra ogni occorrenza. Quando si esegue un rapporto del gruppo di ruoli amministratore nell'interfaccia di amministrazione di Exchange, le voci vengono visualizzate come risultati di ricerca e includono i gruppi di ruolo interessati, chi ha modificato l'appartenenza al gruppo di ruoli e quando e quali aggiornamenti dell'appartenenza sono stati effettuati. Utilizzare questo rapporto per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 2 minuti
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Rapporti" dell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md). 
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Esecuzione del report del gruppo di ruoli amministratore tramite EAC

Eseguire il rapporto di un gruppo di ruoli amministratore per trovare le modifiche ai gruppi di ruoli di gestione nell'organizzazione in uno specifico intervallo di tempo.
  
1. Nell'interfaccia di amministrazione di Exchange selezionare **Gestione della conformità** \> **Controllo**, quindi fare clic su **Esegui il rapporto di un gruppo di ruoli amministratore**.
    
2. Scegliere **Data di inizio** e **Data di fine**. Per impostazione predefinita, il rapporto cerca le modifiche apportate ai gruppi di ruoli amministratore nelle ultime due settimane.
    
3. Per visualizzare le modifiche per un gruppo di ruoli specifico, fare clic su **Seleziona gruppi di ruoli**. Selezionare il gruppo o i gruppi di ruoli nella finestra di dialogo successiva, quindi fare clic su **OK**. È inoltre possibile lasciare il campo vuoto per trovare tutti i gruppi di ruolo modificati.
    
4. Fare clic su **Cerca**.
    
Se utilizzando i criteri specificati vengono trovate delle modifiche, queste verranno visualizzate nel riquadro dei risultati. Fare clic su un gruppo di ruoli nei risultati della ricerca per visualizzare le modifiche nel riquadro dei dettagli.
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

Se è stato eseguito correttamente un report dei gruppi di ruoli di amministratore, i gruppi di ruoli modificati entro l'intervallo di date vengono visualizzati nel riquadro dei risultati della ricerca. Se non è presente alcun risultato, non è stata eseguita alcuna modifica entro l'intervallo di date specificato. Se è prevista la presenza di risultati, modificare l'intervallo di date, quindi eseguire di nuovo il report.
  
## <a name="monitor-changes-to-role-group-membership"></a>Monitorare le modifiche apportate all'appartenenza ai gruppi di ruoli

Quando si aggiungono o si rimuovono i membri di un gruppo di ruoli, nei risultati di ricerca visualizzati nel riquadro dei dettagli viene indicato che l'appartenenza al gruppo di ruoli è stata aggiornata e vengono elencati i membri correnti. I risultati non dichiarano in modo esplicito quale utente è stato aggiunto o rimosso.
  
Per determinare se un utente è stato aggiunto o rimosso, è necessario confrontare due voci separate del rapporto. Ad esempio, osservare le voci di registro seguenti per il gruppo di ruoli **HelpDesk**: 
  
 **27.01.13 16:43:00**
  
 **Amministratore**
  
 **Membri aggiornati: Administrator;annb,florencef;pilarp**
  
 **06.02.13 10:09:00**
  
 **Amministratore**
  
 **Membri aggiornati: Administrator;annb;florencef;pilarp;tonip**
  
 **19.02.13 14.12**
  
 **Amministratore**
  
 **Membri aggiornati: Administrator;annb;florencef;tonip**
  
In questo esempio, l'account utente Amministratore ha apportato le modifiche seguenti:
  
- Il 06.02.13 è stato aggiunto l'utente michaela.
    
- Il 19.02.13 è stato rimosso l'utente adrianag.
    

