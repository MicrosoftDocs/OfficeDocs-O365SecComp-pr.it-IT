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
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="3b68c-103">Controlli di accesso di Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="3b68c-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="3b68c-p101">Accesso fisica e logica per l'ambiente di produzione di Yammer è limitato a un insieme di un numero ridotto di utenti (dell'infrastruttura e operazioni). Come per altri tecnici di Office 365, ingegneri Yammer dispongono zero la condizione per i dati dei clienti. Deve essere richiesto l'accesso utilizzando un sistema di controllo di accesso-in-time basato su approvazione allo stesso archivio protetto e non vi è un numero limitato di responsabili approvazione. Responsabili approvazione verificare la richiesta (ad esempio, si verifica se la richiesta è valido in base alle necessità, caso aziendale, ora e così via), quindi approvare o rifiutare la richiesta. Se la richiesta viene approvata, viene concesso l'accesso JIT per volta definita e limitato, dopo il quale automaticamente scadenza.</span><span class="sxs-lookup"><span data-stu-id="3b68c-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="3b68c-p102">Come per altri servizi di Office 365, tutti gli accessi all'ambiente di produzione Yammer utilizza l'autenticazione a più fattori. Tutta la cronologia di accesso e comando è attribuita a un utente e connesso e rivisto regolarmente dal team di protezione Yammer.</span><span class="sxs-lookup"><span data-stu-id="3b68c-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="3b68c-111">Per ulteriori informazioni sulla gestione e amministrazione di Yammer, vedere [Guida di amministrazione di Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="3b68c-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>