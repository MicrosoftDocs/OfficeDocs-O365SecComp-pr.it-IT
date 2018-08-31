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
ms.collection: Strat_O365_Enterprise
description: "Riepilogo: Un breve riepilogo su Yammer Enterprise accedere a controlli nell'ambiente di produzione."
ms.openlocfilehash: 3f51e63c16022353e743b57d8e977f2ea2e6a835
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531321"
---
# <a name="yammer-enterprise-access-controls"></a>Controlli di accesso di Yammer Enterprise 

Accesso fisica e logica per l'ambiente di produzione di Yammer è limitato a un insieme di un numero ridotto di utenti (dell'infrastruttura e operazioni). Come per altri tecnici di Office 365, ingegneri Yammer dispongono zero la condizione per i dati dei clienti. Deve essere richiesto l'accesso utilizzando un sistema di controllo di accesso-in-time basato su approvazione allo stesso archivio protetto e non vi è un numero limitato di responsabili approvazione. Responsabili approvazione verificare la richiesta (ad esempio, si verifica se la richiesta è valido in base alle necessità, caso aziendale, ora e così via), quindi approvare o rifiutare la richiesta. Se la richiesta viene approvata, viene concesso l'accesso JIT per volta definita e limitato, dopo il quale automaticamente scadenza. 

Come per altri servizi di Office 365, tutti gli accessi all'ambiente di produzione Yammer utilizza l'autenticazione a più fattori. Tutta la cronologia di accesso e comando è attribuita a un utente e connesso e rivisto regolarmente dal team di protezione Yammer.

Per ulteriori informazioni sulla gestione e amministrazione di Yammer, vedere [Guida di amministrazione di Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).