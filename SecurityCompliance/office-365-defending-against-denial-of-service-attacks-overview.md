---
title: La difesa contro gli attacchi Denial of Service in Office 365
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
description: Panoramica di attacchi Denial of Service (DoS).
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530193"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="a9f2a-103">La difesa contro gli attacchi Denial of Service in Office 365</span><span class="sxs-lookup"><span data-stu-id="a9f2a-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="a9f2a-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a9f2a-104">Introduction</span></span>
<span data-ttu-id="a9f2a-105">Microsoft offre un'infrastruttura di affidabilità per più di 200 cloud services, tra cui Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype e Xbox Live ospitate nel nostro cloud globale infrastruttura dei centri dati più di 100.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="a9f2a-p101">Un'organizzazione globale con una significativa presenza Internet e molte proprietà Internet evidente che offrono servizi cloud, Microsoft è una destinazione di grandi dimensioni, comune per utenti malintenzionati e di altri utenti non autorizzati. Rete - livello di comunicazione tra i client e Microsoft Cloud - è uno dei destinatari più importanti di attacchi dannosi. In realtà, per molti anni, Microsoft è stata continuamente e in modo permanente in una forma di cyberattack basate sulla rete. Quasi completamente scarico, almeno una delle proprietà di Microsoft Internet è stati riscontrati sorta di attacco. Senza sistemi attenuazione affidabile e persistente che possono migliorare la difesa contro gli attacchi, servizi cloud Microsoft è non in linea e disponibile per i clienti.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="a9f2a-111">Principi di protezione in difesa utilizzate da Microsoft per proteggere le reti e i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="a9f2a-112">Definizione e sintomi di attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="a9f2a-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="a9f2a-p102">Un modo per servizi di rete di attacchi consiste nel creare molte richieste contro gli host del servizio per sovraccaricare la rete e i server per negare servizio agli utenti legittimi. Questo è definito un attacco di tipo denial of service (DoS). L'attacco viene eseguita da più operatori, gli endpoint e/o vecteurs de, viene definito un attacco (DDoS) di tipo denial of service distribuito. Sebbene varino il mezzo, motivazioni e gli obiettivi, attacchi DoS e DDoS costituita in genere gli sforzi di una o più persone per impedire a un sito Internet o servizio funzioni correttamente o affatto, temporaneamente o per un tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="a9f2a-117">[Stati Uniti Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) definisce i sintomi di attacchi Denial of Service da includere:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="a9f2a-118">Prestazioni di rete lente insolitamente (quando apertura di file o l'accesso a siti Internet)</span><span class="sxs-lookup"><span data-stu-id="a9f2a-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="a9f2a-119">Non disponibilità di un sito Web</span><span class="sxs-lookup"><span data-stu-id="a9f2a-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="a9f2a-120">Impossibilità di accedere a un sito Web</span><span class="sxs-lookup"><span data-stu-id="a9f2a-120">Inability to access a Web site</span></span>
- <span data-ttu-id="a9f2a-121">Aumento significativo posta indesiderata ricevuta</span><span class="sxs-lookup"><span data-stu-id="a9f2a-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="a9f2a-122">Disconnessione di una connessione Internet wireless o cablata</span><span class="sxs-lookup"><span data-stu-id="a9f2a-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="a9f2a-123">Perdita a lungo termine di accesso per il Web o i servizi Internet</span><span class="sxs-lookup"><span data-stu-id="a9f2a-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9f2a-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a9f2a-124">Related Topics</span></span>
- [<span data-ttu-id="a9f2a-125">I principi fondamentali di protezione contro gli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="a9f2a-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="a9f2a-126">Strategia di difesa di tipo Denial of Service di Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9f2a-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="a9f2a-127">La difesa contro gli attacchi Denial of Service i servizi Cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9f2a-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
