---
title: Limiti delle risorse di Office 365
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
description: 'Riepilogo: Informazioni sulle risorse i limiti per le diverse applicazioni in Office 365.'
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531465"
---
# <a name="resource-limits"></a><span data-ttu-id="ed862-103">Limiti della risorsa</span><span class="sxs-lookup"><span data-stu-id="ed862-103">Resource Limits</span></span>

<span data-ttu-id="ed862-p101">Limiti delle risorse vengono applicati tramite le quote (limiti) e la limitazione. Utilizzano entrambi i singoli servizi di Office 365 e Azure Active Directory. Limiti sono specifiche del servizio e in tempo reale con l'aggiunta di nuove funzionalità. Per ulteriori informazioni sui limiti correnti per i diversi servizi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed862-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="ed862-108">Azure Active Directory service limiti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="ed862-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="ed862-109">Limiti Exchange Online Limits</span><span class="sxs-lookup"><span data-stu-id="ed862-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="ed862-110">Limiti Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ed862-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="ed862-111">Limiti e limitazioni del software SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ed862-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="ed862-112">Skype i limiti aziendali</span><span class="sxs-lookup"><span data-stu-id="ed862-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="ed862-113">Limiti di velocità e API REST di Yammer</span><span class="sxs-lookup"><span data-stu-id="ed862-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="ed862-114">Limiti di dimensione file in oscillazione</span><span class="sxs-lookup"><span data-stu-id="ed862-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="ed862-p102">Oltre a questi limiti vengono utilizzati più meccanismi di limitazione in Office 365 e Azure Active Directory. Limitazione delle richieste all'interno del servizio è particolarmente importante, dal momento che le risorse di rete nei Data Center di Microsoft ottimizzate per l'ampia gamma di clienti che utilizzano i servizi. Meccanismi di limitazione includono:</span><span class="sxs-lookup"><span data-stu-id="ed862-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="ed862-118">Azure Active Directory e Office 365 caratteristica a livello utente limitazione cui limitare il numero di transazioni o chiamate simultanee, tramite script o codice, che possono essere eseguite da un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="ed862-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="ed862-p103">Predefinito PowerShell criterio di limitazione viene assegnato a ogni tenant durante la creazione del tenant. Queste impostazioni influiscono su altri elementi, ad esempio il numero massimo di sessioni simultanee di PowerShell che può essere aperto da un unico amministratore.</span><span class="sxs-lookup"><span data-stu-id="ed862-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="ed862-121">Ogni cliente Exchange Online è un criterio di servizi Web Exchange (EWS) predefinito che è ottimizzato per le operazioni dei client servizi Web Exchange e di limitazione che si applica a tutti i client di Outlook.</span><span class="sxs-lookup"><span data-stu-id="ed862-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
