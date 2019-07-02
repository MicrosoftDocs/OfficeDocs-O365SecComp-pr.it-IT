---
title: Office 365 monitoraggio e controllo dell'accesso ai controlli
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Sintesi: un riepilogo dei diversi controlli di accesso al monitoraggio e di controllo disponibili in Office 365.'
ms.openlocfilehash: 39ee2b535c89419e161558cba2122e325228ffb1
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520716"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>Monitoraggio e controllo dei controlli di accesso in Office 365

Microsoft esegue il monitoraggio e il controllo estensivo di tutte le delega, i privilegi e le operazioni che si verificano all'interno di Office 365. Il controllo di accesso di Office 365 è un processo automatizzato basato sul principio dei privilegi minimi e sull'integrazione dei controlli di accesso ai dati e degli audit:

- Tutti gli accessi consentiti possono essere rintracciati in un utente univoco. Gli amministratori sono responsabili della gestione del contenuto dei clienti.
- Le richieste di controllo di accesso, le approvazioni e i registri delle operazioni amministrative vengono acquisiti per l'analisi della sicurezza e degli eventi dannosi.
- I livelli di accesso vengono esaminati in tempo quasi reale in base all'appartenenza a un gruppo di sicurezza per garantire che solo gli utenti che dispongono di motivazioni aziendali autorizzate e soddisfino i requisiti di idoneità abbiano accesso ai sistemi.
- Office 365, i suoi controlli di accesso e i servizi di supporto, tra cui Azure Active Directory e i datacenter fisici, vengono regolarmente controllati da terze parti indipendenti per la conformità alla norma [iso/iec 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [iso/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC) [ FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)e altri [standard](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).
- Gli ingegneri di Office 365 devono eseguire annualmente corsi di sicurezza, esaminare le procedure consigliate per l'accesso con privilegi elevati e riconoscere i criteri di sicurezza e privacy di Microsoft per mantenere i diritti per il servizio.

Gli avvisi automatici vengono attivati quando vengono rilevate attività sospette, ad esempio più account di accesso non riusciti entro un breve periodo. Il team di risposta alla sicurezza di Office 365 utilizza l'apprendimento automatico e l'analisi dei dati di grandi dimensioni per esaminare e analizzare l'attività, cercare modelli di accesso irregolari e rispondere in modo proattivo a attività anomale e illecite. Microsoft impiega anche un team dedicato di tester di penetrazione e si impegna negli esercizi di team rosso e blu periodici per individuare i problemi di sicurezza e controllo di accesso nel servizio. I clienti possono verificare l'efficacia dei sistemi di controllo di accesso usando i rapporti di controllo e l'API di gestione dell'attività fornita da Office 365.

Per ulteriori informazioni, vedere [office 365 Management Activity API Reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).
