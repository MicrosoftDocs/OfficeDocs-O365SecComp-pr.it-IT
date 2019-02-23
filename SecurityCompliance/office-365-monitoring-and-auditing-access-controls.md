---
title: Office 365 monitoraggio e controllo dell'accesso ai controlli
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Sintesi: un riepilogo dei diversi controlli di accesso al monitoraggio e di controllo disponibili in Office 365.'
ms.openlocfilehash: 91d78ba3de41554755a7c19799eb1f7b25933b05
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217736"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Monitoraggio e controllo dei controlli di accesso in Office 365

Microsoft esegue il monitoraggio e il controllo estensivo di tutte le deleghe, tutti gli usi dei privilegi e tutte le operazioni che si verificano all'interno di Office 365. Il controllo di accesso di Office 365 è un processo automatizzato basato sul principio dei privilegi minimi e per incorporare i controlli di accesso ai dati e gli audit:
- Tutti gli accessi consentiti possono essere rintracciati in un utente univoco, rendendo gli amministratori responsabili per la gestione del contenuto del cliente.
- Le richieste di controllo di accesso, le approvazioni e i registri delle operazioni amministrative vengono acquisiti per l'analisi delle informazioni di sicurezza e degli eventi dannosi.
- I livelli di accesso vengono esaminati in tempo quasi reale in base all'appartenenza a un gruppo di sicurezza per garantire che solo gli utenti che dispongono di motivazioni aziendali autorizzate e soddisfino i requisiti di idoneità abbiano accesso ai sistemi.
- Office 365, i suoi controlli di accesso e i servizi di supporto, tra cui Azure Active Directory e i datacenter fisici, vengono regolarmente controllati da terze parti indipendenti per la conformità alla norma [iso/iec 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [iso/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC) [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)e altri [standard](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).
- Gli ingegneri di Office 365 sono tenuti a prendere annualmente una formazione di sicurezza per esaminare le procedure consigliate e i rischi di accesso elevato e riconoscere i criteri di sicurezza e privacy di Microsoft per continuare a mantenere i propri diritti al servizio.

Gli avvisi automatizzati vengono attivati quando viene rilevata un'attività sospetta, ad esempio più account di accesso non riusciti entro un breve periodo di tempo. Il team di risposta alla sicurezza di Office 365 utilizza l'apprendimento automatico e l'analisi dei dati di grandi dimensioni per esaminare e analizzare le attività per i modelli di accesso irregolare e rispondere in modo proattivo alle attività anomale e illecite. Microsoft impiega anche un team dedicato di tester di penetrazione e si impegna negli esercizi di team rosso e blu periodici per individuare i problemi di sicurezza e controllo di accesso nel servizio. I clienti possono anche verificare l'efficacia dei sistemi di controllo di accesso utilizzando i rapporti di controllo e l'API di gestione dell'attività fornita da Office 365. 

Per ulteriori informazioni, vedere [office 365 Management Activity API Reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).
