---
title: Monitoraggio di Office 365 e il controllo di accedere a controlli
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Riepilogo dei vari monitoraggio e controllo accesso controlli disponibili in Office 365.'
ms.openlocfilehash: 7ef25d62ce3c4fa320dd0b164183c6f67be7d76d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531320"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Monitoraggio e controllo di accedere a controlli in Office 365

Microsoft esegue estesa di monitoraggio e controllo di delega tutti, utilizzo di tutti i privilegi di e tutte le operazioni che si verificano in Office 365. Controllo dell'accesso 365 Office è un processo automatizzato basato sul principio dei privilegi minimi e per includere dati accedere a controlli e audit:
- Tutti gli accessi consentiti sono rintracciabili a un solo utente, effettuare amministratori responsabile per la gestione del contenuto dei clienti.
- Richieste di controllo di accesso, approvazioni e i registri di operazioni amministrative vengono acquisiti per l'analisi delle informazioni di protezione e degli eventi dannosi.
- Nella sezione livelli di accesso più vicina appartenenza al gruppo di protezione di base in tempo reale per assicurarsi che solo gli utenti sono autorizzati motivazioni aziendali e soddisfano tali requisiti abbiano accesso ai sistemi.
- Office 365, il relativo accedere a controlli e servizi di supporto, tra cui Azure Active Directory e i centri dati fisici, regolarmente vengono controllati da terzi indipendente per la conformità con [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC) [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)e altri [standard](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).
- Tecnici di Office 365 devono annuale formazione sulla sicurezza per esaminare i rischi e consigliate per l'accesso con privilegi elevati e confermare la protezione e riservatezza per continuare a gestire i diritti per il servizio di Microsoft.

Avvisi automatici vengono attivati quando viene rilevata qualche attività potenzialmente dannoso, ad esempio più account di accesso non riuscito all'interno di un breve periodo. Il team di risposta di protezione di Office 365 utilizza l'apprendimento e l'analisi dei dati di grandi dimensioni per esaminare e analizzare l'attività di modelli di accesso irregolare e per rispondere in modo proattivo alle attività anomala e illecita. Microsoft si avvale di un gruppo di tester penetrazione inoltre e svolge periodico team di colore rosso e blu esercitazioni per trovare protezione e controllo problemi nel servizio di accesso. I clienti possono inoltre verificare l'efficacia dei sistemi di controllo di accesso utilizzando l'attività di gestione API fornita da Office 365 e report di controllo. 

Per ulteriori informazioni, vedere [Guida di riferimento API di attività di gestione di Office 365](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) e [controllo e report in Office 365](office-365-auditing-and-reporting-overview.md).
