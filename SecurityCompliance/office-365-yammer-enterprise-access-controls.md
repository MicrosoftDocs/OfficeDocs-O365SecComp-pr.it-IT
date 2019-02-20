---
title: Controlli di accesso di Office 365 Yammer Enterprise
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "Riepilogo: breve riepilogo sui controlli di accesso di Yammer Enterprise nell'ambiente di produzione."
ms.openlocfilehash: 33126ee6acf42a97148c12917855535a8578e8cf
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090728"
---
# <a name="yammer-enterprise-access-controls"></a>Controlli di accesso di Yammer Enterprise 

L'accesso fisico e logico all'ambiente di produzione di Yammer è limitato a un gruppo di utenti molto piccolo (Infrastructure and Operations). Come per gli altri ingegneri di Office 365, gli ingegneri di Yammer hanno accesso a zero diritti ai dati dei clienti. L'accesso deve essere richiesto utilizzando un sistema di controllo di accesso just-in-time basato sull'approvazione analogo all'archivio protetto ed è presente un numero limitato di responsabili approvazione. I responsabili approvazione verificano la richiesta (ad esempio, verificano se la richiesta è legittima in base alle esigenze, al caso aziendale, al tempo e così via) e quindi approva o rifiuta la richiesta. Se la richiesta viene approvata, l'accesso JIT viene concesso per un periodo di tempo definito e limitato, dopo il quale scade automaticamente. 

Come per gli altri servizi di Office 365, tutti gli accessi all'ambiente di produzione di Yammer sfruttano l'autenticazione a più fattori. Tutti gli accessi e la cronologia dei comandi vengono assegnati a un utente e registrati e recensiti regolarmente dal team di sicurezza di Yammer.

Per ulteriori informazioni sull'amministrazione e la gestione di Yammer, vedere la Guida di amministrazione di [Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).