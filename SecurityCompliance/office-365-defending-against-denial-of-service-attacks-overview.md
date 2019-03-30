---
title: Difesa contro gli attacchi Denial of Service in Office 365
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
description: Una panoramica degli attacchi DoS (Denial of Service).
ms.openlocfilehash: a7e67fcc87867190f345c5dad14e38a473420eab
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004073"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="79bf5-103">Difesa contro gli attacchi Denial of Service in Office 365</span><span class="sxs-lookup"><span data-stu-id="79bf5-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="79bf5-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="79bf5-104">Introduction</span></span>
<span data-ttu-id="79bf5-105">Microsoft offre un'infrastruttura affidabile per più di 200 servizi cloud, tra cui Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype e Xbox Live che sono ospitati nel cloud globale infrastruttura di più di 100 datacenter.</span><span class="sxs-lookup"><span data-stu-id="79bf5-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="79bf5-106">In quanto organizzazione globale con una presenza Internet significativa e numerose proprietà di Internet importanti che forniscono servizi cloud, Microsoft è un obiettivo di grandi dimensioni comune per gli hacker e gli altri utenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="79bf5-106">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="79bf5-107">La rete, ovvero il livello di comunicazione tra client e Microsoft Cloud, è uno dei principali obiettivi degli attacchi dannosi.</span><span class="sxs-lookup"><span data-stu-id="79bf5-107">The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="79bf5-108">Infatti, per molti anni, Microsoft è stata continuamente e persistente sotto una qualche forma di cyberattack basato sulla rete.</span><span class="sxs-lookup"><span data-stu-id="79bf5-108">In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack.</span></span> <span data-ttu-id="79bf5-109">Quasi tutte le volte, almeno una delle proprietà di Microsoft Internet sta vivendo una qualche forma di attacco.</span><span class="sxs-lookup"><span data-stu-id="79bf5-109">At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack.</span></span> <span data-ttu-id="79bf5-110">Senza sistemi di attenuazione affidabili e persistenti in grado di difendersi da tali attacchi, i servizi cloud di Microsoft sarebbero non in linea e non sono disponibili per i clienti.</span><span class="sxs-lookup"><span data-stu-id="79bf5-110">Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="79bf5-111">Microsoft utilizza i principi di sicurezza per la difesa in profondità per proteggere i servizi e le reti cloud.</span><span class="sxs-lookup"><span data-stu-id="79bf5-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="79bf5-112">Definizione e sintomi degli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="79bf5-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="79bf5-113">Un modo per attaccare i servizi di rete consiste nel creare numerose richieste nei confronti di un host del servizio per sopraffare la rete e i server per negare il servizio agli utenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="79bf5-113">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="79bf5-114">Questo è definito come un attacco Denial of Service (DoS).</span><span class="sxs-lookup"><span data-stu-id="79bf5-114">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="79bf5-115">Quando l'attacco viene eseguito da più attori, endpoint e/o vettori, viene indicato come un attacco di tipo Denial-of-Service (DDoS) distribuito.</span><span class="sxs-lookup"><span data-stu-id="79bf5-115">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="79bf5-116">Anche se i mezzi, i motivi e gli obiettivi variano, gli attacchi DoS e DDoS generalmente consistono negli sforzi di una persona o persone per impedire che un sito o servizio Internet funzioni correttamente o a tutti, temporaneamente o a tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="79bf5-116">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="79bf5-117">Il [team degli Stati Uniti](https://www.us-cert.gov/) per la preparazione alle emergenze del computer (US-CERT) definisce i sintomi degli attacchi DOS per includere:</span><span class="sxs-lookup"><span data-stu-id="79bf5-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="79bf5-118">Prestazioni di rete insolitamente lente (quando si aprono file o si accede a siti Internet)</span><span class="sxs-lookup"><span data-stu-id="79bf5-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="79bf5-119">Indisponibilità di un sito Web</span><span class="sxs-lookup"><span data-stu-id="79bf5-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="79bf5-120">Impossibilità di accedere a un sito Web</span><span class="sxs-lookup"><span data-stu-id="79bf5-120">Inability to access a Web site</span></span>
- <span data-ttu-id="79bf5-121">Notevole aumento della posta indesiderata ricevuta</span><span class="sxs-lookup"><span data-stu-id="79bf5-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="79bf5-122">Disconnessione di una connessione Internet wireless o cablata</span><span class="sxs-lookup"><span data-stu-id="79bf5-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="79bf5-123">Perdita di accesso a lungo termine al Web o a qualsiasi servizio Internet</span><span class="sxs-lookup"><span data-stu-id="79bf5-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="79bf5-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="79bf5-124">Related Topics</span></span>
- [<span data-ttu-id="79bf5-125">I principi fondamentali di protezione contro gli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="79bf5-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="79bf5-126">Strategia di difesa Denial of Service di Microsoft</span><span class="sxs-lookup"><span data-stu-id="79bf5-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="79bf5-127">Difesa dei servizi cloud Microsoft in base agli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="79bf5-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
