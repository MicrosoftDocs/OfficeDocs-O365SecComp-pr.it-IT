---
title: Crittografia di Office 365 per i dati in transito
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
description: 'Riepilogo: Breve spiegazione di come Microsoft consente di crittografare dati in transito.'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530254"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="48439-103">Crittografia di Office 365 per i dati in transito</span><span class="sxs-lookup"><span data-stu-id="48439-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="48439-104">Oltre a proteggere i dati relativi ai clienti statici, utilizzate da Microsoft tecnologie di crittografia per proteggere i dati dei clienti di Office 365 in transito.</span><span class="sxs-lookup"><span data-stu-id="48439-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="48439-105">Dati sono in corso:</span><span class="sxs-lookup"><span data-stu-id="48439-105">Data is in transit:</span></span>
- <span data-ttu-id="48439-106">Quando un client comunica con un server di Office 365.</span><span class="sxs-lookup"><span data-stu-id="48439-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="48439-107">Quando un server di Office 365 comunica con un altro server di Office 365. e</span><span class="sxs-lookup"><span data-stu-id="48439-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="48439-108">Quando un server di Office 365 comunica con un server non Office 365 (ad esempio, Exchange Online recapitando posta elettronica a un server di posta elettronica esterno).</span><span class="sxs-lookup"><span data-stu-id="48439-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="48439-p101">Centro dati tra le comunicazioni tra i server di Office 365 viene eseguita tramite TLS o IPsec e tutti i server per i clienti negoziare una sessione protetta tramite TLS con i computer client (ad esempio, Exchange Online utilizza TLS 1.2 con il livello di crittografia 256 bit utilizzato FIPS (FEDERAL Livello di 140-2 convalidato 2). (Per un elenco delle famiglie di prodotti di crittografia TLS supportate da Office 365, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) ). Ciò vale per i protocolli utilizzati dai client come Outlook, Skype per le aziende e Outlook sul web (ad esempio, HTTP, POP3 e così via).</span><span class="sxs-lookup"><span data-stu-id="48439-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="48439-p102">I certificati pubblici emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento Microsoft interno per proteggere la riservatezza dei dati trasmesse. Tutti i certificati rilasciati da Microsoft IT dispongono almeno a 2048 bit lunghezza e la conformità [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) richiede SSLAdmin verificare che i certificati emessi solo agli indirizzi IP pubblici e di proprietà di Microsoft. Tutti gli indirizzi IP che non soddisfano questo criterio vengono instradati tramite un processo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="48439-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="48439-p103">Tutti i dettagli di implementazione, ad esempio la versione di TLS in uso, se è abilitata Forward Secrecy (ADFS), l'ordine delle famiglie di prodotti di crittografia e così via, disponibili pubblicamente. Un modo per visualizzare i dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio Qualys SSL laboratori (www.ssllabs.com). Vengono riportati di seguito i collegamenti a pagine test automatizzato da Qualys che visualizzano le informazioni per i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="48439-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="48439-117">Portale di Office 365</span><span class="sxs-lookup"><span data-stu-id="48439-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="48439-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="48439-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="48439-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="48439-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="48439-120">Skype per le aziende (SIP)</span><span class="sxs-lookup"><span data-stu-id="48439-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="48439-121">Skype per le aziende (Web)</span><span class="sxs-lookup"><span data-stu-id="48439-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="48439-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="48439-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="48439-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48439-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="48439-124">Per Exchange Online Protection, gli URL variano in base a nomi tenant. Tuttavia, tutti i clienti possono testare Office 365 con **microsoft com.mail.protection.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="48439-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
