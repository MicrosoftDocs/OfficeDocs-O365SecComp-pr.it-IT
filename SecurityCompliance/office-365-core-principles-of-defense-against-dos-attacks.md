---
title: Principi fondamentali di Office 365 per la difesa dagli attacchi Denial of Service
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: In che modo Microsoft utilizza i principi fondamentali dell'assorbimento, del rilevamento e dell'attenuazione in difesa degli attacchi DoS (Denial of Service).
ms.openlocfilehash: 17dc583258cdb4781dbe2a715e1ce153ee769ed3
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091008"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="bd6a1-103">I principi fondamentali di protezione contro gli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="bd6a1-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="bd6a1-p101">I tre principi fondamentali per la difesa dagli attacchi DoS basati sulla rete sono assorbimento, rilevamento e attenuazione. L'assorbimento avviene prima del rilevamento e il rilevamento avviene prima dell'attenuazione. L'assorbimento è la migliore difesa contro gli attacchi DoS. Se non è possibile rilevare l'attacco, non può essere attenuato. Tuttavia, se non è possibile assorbire anche il più piccolo attacco DoS, i servizi non sopravvivranno abbastanza a lungo per rilevare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="bd6a1-p102">Naturalmente, in generale, non è possibile per la maggior parte delle organizzazioni acquistare la capacità in eccesso necessaria per assorbire gli attacchi DoS, poiché ciò richiede un investimento considerevole in tecnologia e competenze tecniche. Questo evidenzia uno dei vantaggi per la sicurezza dell'utilizzo dei servizi cloud Microsoft; la scalabilità dei nostri servizi consente di offrire una protezione della rete elevata ai clienti cloud in modo economico. Tuttavia, anche a livello di scala, tuttavia, è necessario un bilanciamento tra assorbimento, rilevamento e attenuazione. Per trovare questo bilanciamento, è possibile studiare il tasso di crescita di un attacco per stimare quanto è necessario assorbire.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="bd6a1-p103">Il rilevamento è un gioco Cat-and-mouse. È necessario cercare continuamente i nuovi modi in cui gli utenti si attaccano o cercano di sconfiggere i sistemi. Detect-> mitigate-> Detect-> mitigate, ecc., è uno stato perpetuo e persistente che continuerà all'infinito.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="bd6a1-116">Difesa dagli attacchi DoS</span><span class="sxs-lookup"><span data-stu-id="bd6a1-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="bd6a1-p104">Per difendersi correttamente da un attacco DoS, è essenziale il rilevamento precoce. Se si rileva un attacco prima che il sistema venga sovraccaricato, i difensori possono eseguire un piano di risposta.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="bd6a1-119">La formula seguente consentirà di approssimare il tempo necessario per l'impatto di un attacco DoS:</span><span class="sxs-lookup"><span data-stu-id="bd6a1-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="bd6a1-120">**Capacità massima (in byte/sec)/frequenza di crescita (in byte/sec) = tempo di impatto (in byte/sec)**</span><span class="sxs-lookup"><span data-stu-id="bd6a1-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="bd6a1-p105">Se il time-to-Detection si verifica dopo il time-to-Impact, è probabile che l'attacco DoS avrà esito positivo. Se il tempo di rilevamento si verifica prima del tempo di impatto, i servizi da attaccare devono rimanere online e accessibili, se si utilizzano le strategie di attenuazione. Pertanto, esistono solo due operazioni che è possibile eseguire per difendersi dagli attacchi DoS:</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="bd6a1-124">Aumentare la capacità di innalzamento del limite massimo di capacità (che a sua volta fornisce più tempo per rilevare un attacco); o</span><span class="sxs-lookup"><span data-stu-id="bd6a1-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="bd6a1-125">Consente di ridurre il tempo necessario per il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-125">Decrease the time to detect.</span></span>

<span data-ttu-id="bd6a1-p106">Aumentare la capacità ha un impatto fiscale diretto. Microsoft consiglia ai clienti di sviluppare almeno la capacità di assorbimento di base, per garantire che possano sopravvivere a un certo livello di attacco DoS. La capacità effettiva di assorbimento varia da cliente a cliente, in quanto ogni cliente ha le proprie soglie per l'esposizione, il rischio e l'esborso finanziario. In definitiva, per motivi economici, gli investimenti della ricerca e del tempo in termini di riduzione del tempo di rilevamento sono di solito la difesa più conveniente.</span><span class="sxs-lookup"><span data-stu-id="bd6a1-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
