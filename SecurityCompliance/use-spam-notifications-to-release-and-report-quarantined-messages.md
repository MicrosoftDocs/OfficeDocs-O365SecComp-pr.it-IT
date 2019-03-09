---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Se l'amministratore abilita le notifiche per gli utenti, riceverà un messaggio di notifica che elenca i messaggi inviati alla cassetta postale che sono stati identificati come posta indesiderata, in blocco o in messaggi di phishing. È possibile rilasciare o segnalare i messaggi dopo la notifica.
ms.openlocfilehash: 7f68b70298fca7d8ed5f5e5b8dc9c727c3a6a6c1
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492725"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365

Se l'amministratore abilita le notifiche di posta indesiderata per gli utenti, riceverà un messaggio di notifica che elenca i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata e in quarantena
  
> [!TIP]
> Se si è un amministratore e si desidera abilitare questa funzionalità, è possibile scegliere l'opzione quando si [modifica un criterio di](https://go.microsoft.com/fwlink/?LinkId=800313)protezione da posta indesiderata predefinito. 
  
Il messaggio ricevuto include il numero di messaggi di posta indesiderata in quarantena e la data e l'ora (in formato UTC (Universal Coordinated Time) dell'ultimo messaggio nell'elenco. L'elenco include quanto segue per ogni messaggio:
  
- **Mittente** Il nome e l'indirizzo di posta elettronica del messaggio in quarantena. 
    
- **Oggetto** Oggetto del messaggio in quarantena. 
    
- **Data** Data e ora (in formato UTC) del messaggio in quarantena. 
    
- **Dimensioni** Le dimensioni del messaggio, in kilobyte (KB). 
    
Al momento, esistono due azioni che è possibile eseguire con un messaggio in quarantena:
  
- **Rilascia in posta in arrivo** Scegliere questa casella per inviare il messaggio alla posta in arrivo, in cui è possibile visualizzarla. 
    
- **Segnala come non** indesiderato Scegliere questa pagina per inviare una copia del messaggio a Microsoft per l'analisi. Il team di analisi di posta indesiderata, valuta e analizza il messaggio e a seconda dei risultati dell'analisi, regola il filtro di protezione da posta indesiderata per consentire l'inoltro del messaggio. 
    
Tenere presente quanto segue:
  
- I messaggi in quarantena perché hanno trovato una regola del flusso di posta non sono inclusi nei messaggi in quarantena dell'utente. Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena.
    
- È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.
    

