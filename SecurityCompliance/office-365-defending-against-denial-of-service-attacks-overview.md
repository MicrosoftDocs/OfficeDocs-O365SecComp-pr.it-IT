---
title: Difendersi dagli attacchi Denial of Service in Office 365
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
ms.openlocfilehash: df3ab233271f02b91f16f8954972a61000bf4d3b
ms.sourcegitcommit: aa60a6cdf83c67576e858668d1182cd4fffeb5e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "33622476"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="ee72e-103">Difendersi dagli attacchi Denial of Service in Office 365</span><span class="sxs-lookup"><span data-stu-id="ee72e-103">Defend Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="ee72e-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="ee72e-104">Introduction</span></span>

<span data-ttu-id="ee72e-105">Microsoft offre un'infrastruttura affidabile per più di 200 servizi cloud ospitati in un'infrastruttura cloud globale di oltre 100 datacenter.</span><span class="sxs-lookup"><span data-stu-id="ee72e-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services hosted in a global cloud infrastructure of more than 100 datacenters.</span></span> <span data-ttu-id="ee72e-106">Queste funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="ee72e-106">These include:</span></span>

- <span data-ttu-id="ee72e-107">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="ee72e-107">Microsoft Azure</span></span>
- <span data-ttu-id="ee72e-108">Microsoft Bing</span><span class="sxs-lookup"><span data-stu-id="ee72e-108">Microsoft Bing</span></span>
- <span data-ttu-id="ee72e-109">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ee72e-109">Microsoft Dynamics 365</span></span>
- <span data-ttu-id="ee72e-110">Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="ee72e-110">Microsoft Office 365</span></span>
- <span data-ttu-id="ee72e-111">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="ee72e-111">Microsoft OneDrive</span></span>
- <span data-ttu-id="ee72e-112">Skype</span><span class="sxs-lookup"><span data-stu-id="ee72e-112">Skype</span></span>
- <span data-ttu-id="ee72e-113">Xbox Live</span><span class="sxs-lookup"><span data-stu-id="ee72e-113">Xbox Live</span></span>

<span data-ttu-id="ee72e-114">In quanto organizzazione globale con una presenza Internet significativa e numerose proprietà di Internet importanti che forniscono servizi cloud, Microsoft è un obiettivo di grandi dimensioni comune per gli hacker e gli altri utenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="ee72e-114">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="ee72e-115">Il livello di comunicazione di rete tra client e Microsoft Cloud è uno dei principali obiettivi degli attacchi dannosi.</span><span class="sxs-lookup"><span data-stu-id="ee72e-115">The network communication layer between clients and the Microsoft Cloud is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="ee72e-116">In effetti, Microsoft è continuamente e persistente sotto una qualche forma di attacco cibernetico basato sulla rete.</span><span class="sxs-lookup"><span data-stu-id="ee72e-116">In fact, Microsoft is continuously and persistently under some form of network-based cyber-attack.</span></span> <span data-ttu-id="ee72e-117">In linea con questo, Microsoft utilizza principi di sicurezza per la difesa in profondità per proteggere i servizi e le reti cloud.</span><span class="sxs-lookup"><span data-stu-id="ee72e-117">In line with this, Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> <span data-ttu-id="ee72e-118">Senza sistemi di attenuazione affidabili e persistenti che difendono tali attacchi, i servizi cloud di Microsoft sarebbero non in linea e non sono disponibili per i clienti.</span><span class="sxs-lookup"><span data-stu-id="ee72e-118">Without reliable and persistent mitigation systems that defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="ee72e-119">Definizione e sintomi degli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="ee72e-119">Definition and Symptoms of Denial-of-Service Attacks</span></span>

<span data-ttu-id="ee72e-120">Un modo per attaccare i servizi di rete consiste nel creare numerose richieste contro gli host del servizio per sopraffare la rete e i server per negare il servizio agli utenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="ee72e-120">One way to attack network services is to create many requests against service hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="ee72e-121">Questo è definito come un attacco Denial of Service (DoS).</span><span class="sxs-lookup"><span data-stu-id="ee72e-121">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="ee72e-122">Quando l'attacco viene eseguito da più attori, endpoint e/o vettori, viene indicato come un attacco di tipo Denial-of-Service (DDoS) distribuito.</span><span class="sxs-lookup"><span data-stu-id="ee72e-122">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="ee72e-123">Anche se i mezzi, i motivi e gli obiettivi variano, gli attacchi DoS e DDoS in genere compongono gli sforzi per impedire che un sito o un servizio Internet funzioni correttamente o a tutti, temporaneamente o a tempo indeterminato.</span><span class="sxs-lookup"><span data-stu-id="ee72e-123">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of efforts to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="ee72e-124">Il [team degli Stati Uniti](https://www.us-cert.gov/) per la preparazione alle emergenze del computer (US-CERT) definisce i sintomi degli attacchi DOS per includere:</span><span class="sxs-lookup"><span data-stu-id="ee72e-124">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>

- <span data-ttu-id="ee72e-125">Prestazioni di rete insolitamente lente (quando si aprono file o si accede a siti Internet)</span><span class="sxs-lookup"><span data-stu-id="ee72e-125">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="ee72e-126">Indisponibilità di un sito Web</span><span class="sxs-lookup"><span data-stu-id="ee72e-126">Unavailability of a Web site</span></span>
- <span data-ttu-id="ee72e-127">Impossibilità di accedere a un sito Web</span><span class="sxs-lookup"><span data-stu-id="ee72e-127">Inability to access a Web site</span></span>
- <span data-ttu-id="ee72e-128">Notevole aumento della posta indesiderata ricevuta</span><span class="sxs-lookup"><span data-stu-id="ee72e-128">Dramatic increase in received spam</span></span>
- <span data-ttu-id="ee72e-129">Disconnessione di una connessione Internet wireless o cablata</span><span class="sxs-lookup"><span data-stu-id="ee72e-129">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="ee72e-130">Perdita di accesso a lungo termine al Web o a qualsiasi servizio Internet</span><span class="sxs-lookup"><span data-stu-id="ee72e-130">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee72e-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ee72e-131">Related Topics</span></span>

- [<span data-ttu-id="ee72e-132">I principi fondamentali di protezione contro gli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="ee72e-132">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="ee72e-133">Strategia di difesa Denial of Service di Microsoft</span><span class="sxs-lookup"><span data-stu-id="ee72e-133">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="ee72e-134">Difesa dei servizi cloud Microsoft in base agli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="ee72e-134">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)
