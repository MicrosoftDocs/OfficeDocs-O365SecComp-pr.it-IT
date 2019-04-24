---
title: Controlli di accesso di Office 365 Yammer Enterprise
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
description: "Riepilogo: breve riepilogo sui controlli di accesso di Yammer Enterprise nell'ambiente di produzione."
ms.openlocfilehash: 61598235a010aaa1c578c449cb054073212a41f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262348"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="8db05-103">Controlli di accesso di Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="8db05-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="8db05-104">L'accesso fisico e logico all'ambiente di produzione di Yammer è limitato a un gruppo di utenti molto piccolo (Infrastructure and Operations).</span><span class="sxs-lookup"><span data-stu-id="8db05-104">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations).</span></span> <span data-ttu-id="8db05-105">Come per gli altri ingegneri di Office 365, gli ingegneri di Yammer hanno accesso a zero diritti ai dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8db05-105">As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data.</span></span> <span data-ttu-id="8db05-106">L'accesso deve essere richiesto utilizzando un sistema di controllo di accesso just-in-time basato sull'approvazione analogo all'archivio protetto ed è presente un numero limitato di responsabili approvazione.</span><span class="sxs-lookup"><span data-stu-id="8db05-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers.</span></span> <span data-ttu-id="8db05-107">I responsabili approvazione verificano la richiesta (ad esempio, verificano se la richiesta è legittima in base alle esigenze, al caso aziendale, al tempo e così via) e quindi approva o rifiuta la richiesta.</span><span class="sxs-lookup"><span data-stu-id="8db05-107">Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="8db05-108">Se la richiesta viene approvata, l'accesso JIT viene concesso per un periodo di tempo definito e limitato, dopo il quale scade automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8db05-108">If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="8db05-109">Come per gli altri servizi di Office 365, tutti gli accessi all'ambiente di produzione di Yammer sfruttano l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="8db05-109">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication.</span></span> <span data-ttu-id="8db05-110">Tutti gli accessi e la cronologia dei comandi vengono assegnati a un utente e registrati e recensiti regolarmente dal team di sicurezza di Yammer.</span><span class="sxs-lookup"><span data-stu-id="8db05-110">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="8db05-111">Per ulteriori informazioni sull'amministrazione e la gestione di Yammer, vedere la Guida di amministrazione di [Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="8db05-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>