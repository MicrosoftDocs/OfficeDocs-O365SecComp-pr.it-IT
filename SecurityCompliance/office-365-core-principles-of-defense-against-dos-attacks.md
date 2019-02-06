---
title: Office 365 principi di base del sistema di difesa contro gli attacchi Denial of Service
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Come Microsoft utilizza i principi di base di assorbire, individuazione e attenuazione della difesa contro gli attacchi di tipo denial of service (DoS).
ms.openlocfilehash: e313d5514e9bc493db78bebffca24a0fae4cbca7
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741099"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="60a1e-103">I principi fondamentali di protezione contro gli attacchi Denial of Service</span><span class="sxs-lookup"><span data-stu-id="60a1e-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="60a1e-p101">Le tre principali principi dopo la difesa contro gli attacchi DoS rete assorbire, individuazione e attenuazione. Assorbire si verifica prima del rilevamento e rilevamento si verifica prima attenuazione. Assorbire è la miglior difesa contro un attacchi Denial of Service. Se non è rilevato l'attacco, non possono essere ridotti. Ma se non è assorbire attacco DoS più piccolo, servizi non sono continui di sopravvivenza tempo sufficiente per l'attacco da rilevare.</span><span class="sxs-lookup"><span data-stu-id="60a1e-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="60a1e-p102">Ovviamente, in genere non è realizzabile economicamente per la maggior parte delle organizzazioni acquistare della capacità in eccesso necessaria per assorbire attacchi Denial of Service, in quanto richiede un ingente investimento in tecnologie e competenze tecniche. Evidenzia uno dei vantaggi dell'utilizzo dei servizi cloud Microsoft, per la protezione la scala una enorme ai servizi ci consente di fornire protezione della rete sicuro ai nostri clienti cloud in modo economico. Ma anche alla scala, tuttavia, è necessario ancora che un equilibrio tra assorbire, individuazione e attenuazione. Per individuare tale bilanciamento, è lo Studio tasso di crescita dell'attacco per calcolare la quantità dobbiamo accettabile.</span><span class="sxs-lookup"><span data-stu-id="60a1e-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="60a1e-p103">Rilevamento è una sfida. È necessario cercare costantemente per utenti nuovi modi sono che si attacca o che tentano di annullare i sistemi. Rilevare - gt _ attenuare - rileva - gt _ gt _ attenuare i e così via, è uno stato perpetua, persistent continua per un tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="60a1e-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="60a1e-116">La difesa contro gli attacchi DoS</span><span class="sxs-lookup"><span data-stu-id="60a1e-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="60a1e-p104">Per migliorare correttamente la difesa contro un attacco Denial of Service, il rilevamento anticipato è essenziale. Per rilevare un attacco prima che il sistema è sovraccarico, difensori possono eseguire un piano di risposta.</span><span class="sxs-lookup"><span data-stu-id="60a1e-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="60a1e-119">La formula seguente consentiranno di circa il tempo necessario per l'impatto di un attacco Denial of Service:</span><span class="sxs-lookup"><span data-stu-id="60a1e-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="60a1e-120">**Capacità massima (in byte/sec) / tasso di crescita (in byte/sec) = tempo all'impatto (in byte/sec)**</span><span class="sxs-lookup"><span data-stu-id="60a1e-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="60a1e-p105">Se il tempo di rilevamento si verifica dopo l'ora a impatto, è probabile che l'attacco Denial of Service avrà esito positivo. Se il tempo di rilevamento si verifica prima del tempo di impatto, i servizi di attacchi devono rimanere in linea e accessibile se vengono utilizzate le strategie di attenuazione. In questo modo, sono disponibili solo due operazioni che possono essere intraprese per migliorare la difesa contro gli attacchi DoS:</span><span class="sxs-lookup"><span data-stu-id="60a1e-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="60a1e-124">Incrementare la capacità di passare ceiling di capacità massima (che a sua volta fornisce più tempo per rilevare un attacco); o</span><span class="sxs-lookup"><span data-stu-id="60a1e-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="60a1e-125">Ridurre il tempo necessario per rilevare.</span><span class="sxs-lookup"><span data-stu-id="60a1e-125">Decrease the time to detect.</span></span>

<span data-ttu-id="60a1e-p106">Aumentare la capacità ha un impatto diretto fiscale. È consigliabile che i clienti sviluppano assorbire almeno base capacità, per assicurarsi che è possibile restano valide anche un certo livello di attacco Denial of Service. La capacità di assorbire effettivo varierà a clienti, come ogni cliente con i propri soglie per esposizione, i rischi e spese finanziari. In sintesi, per motivi economici, a livello di ricerca e l'ora in modi per ridurre il tempo di rilevamento è in genere il sistema di difesa più economico.</span><span class="sxs-lookup"><span data-stu-id="60a1e-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
