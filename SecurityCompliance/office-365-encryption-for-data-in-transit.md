---
title: Crittografia di Office 365 per i dati in transito
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Sintesi: breve descrizione del modo in cui Microsoft crittografa i dati in transito.'
ms.openlocfilehash: 987e923e242b47b07ad1ef65e5c7ce791c27d5bd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217506"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="b1e24-103">Crittografia di Office 365 per i dati in transito</span><span class="sxs-lookup"><span data-stu-id="b1e24-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="b1e24-104">Oltre a proteggere i dati dei clienti a riposo, Microsoft utilizza le tecnologie di crittografia per proteggere i dati dei clienti di Office 365 in transito.</span><span class="sxs-lookup"><span data-stu-id="b1e24-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="b1e24-105">I dati sono in transito:</span><span class="sxs-lookup"><span data-stu-id="b1e24-105">Data is in transit:</span></span>
- <span data-ttu-id="b1e24-106">Quando un computer client comunica con un server di Office 365;</span><span class="sxs-lookup"><span data-stu-id="b1e24-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="b1e24-107">Quando un server di Office 365 comunica con un altro server di Office 365; e</span><span class="sxs-lookup"><span data-stu-id="b1e24-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="b1e24-108">Quando un server di Office 365 comunica con un server non Office 365 (ad esempio, Exchange Online recapitare la posta elettronica a un server di posta elettronica esterno).</span><span class="sxs-lookup"><span data-stu-id="b1e24-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="b1e24-p101">Le comunicazioni tra i datacenter tra i server di Office 365 si verificano su TLS o IPsec e tutti i server rivolti ai clienti negoziano una sessione sicura tramite TLS con i computer client (ad esempio, Exchange Online utilizza TLS 1,2 con la forza di crittografia a 256 bit (FIPS 140-2 livello 2-convalidato). Per un elenco dei gruppi di crittografia TLS supportati da Office 365, vedere [informazioni di riferimento tecnico sulla crittografia in office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) . Questo vale per i protocolli utilizzati da client quali Outlook, Skype for business e Outlook sul Web (ad esempio, HTTP, POP3 e così via).</span><span class="sxs-lookup"><span data-stu-id="b1e24-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="b1e24-p102">I certificati pubblici vengono emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento interno di Microsoft per proteggere la riservatezza delle informazioni trasmesse. Tutti i certificati emessi da Microsoft hanno una lunghezza minima di 2048 bit e la conformità [](http://www.webtrust.org/homepage-documents/item70372.pdf) di WebTrust richiede SSLAdmin per assicurarsi che i certificati vengano emessi solo per gli indirizzi IP pubblici di proprietà di Microsoft. Tutti gli indirizzi IP che non rispondono a questo criterio vengono instradati tramite un processo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="b1e24-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="b1e24-p103">Tutti i dettagli sull'implementazione, ad esempio la versione di TLS utilizzata, l'abilitazione del segreto di inoltro (FS), l'ordine delle suite di crittografia e così via, sono disponibili pubblicamente. Un modo per visualizzare questi dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio Qualys SSL Labs (www.ssllabs.com). Di seguito sono riportati i collegamenti alle pagine di test automatizzate di Qualys che visualizzano le informazioni relative ai servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1e24-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="b1e24-117">Portale di Office 365</span><span class="sxs-lookup"><span data-stu-id="b1e24-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="b1e24-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1e24-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="b1e24-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b1e24-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="b1e24-120">Skype for business (SIP)</span><span class="sxs-lookup"><span data-stu-id="b1e24-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="b1e24-121">Skype for business (Web)</span><span class="sxs-lookup"><span data-stu-id="b1e24-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="b1e24-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b1e24-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="b1e24-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1e24-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="b1e24-124">Per Exchange Online Protection, gli URL variano in base ai nomi dei tenant; Tuttavia, tutti i clienti possono testare Office 365 utilizzando **Microsoft-com.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="b1e24-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
