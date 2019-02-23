---
title: Principi fondamentali di Office 365 per la difesa dagli attacchi Denial of Service
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: In che modo Microsoft utilizza i principi fondamentali dell'assorbimento, del rilevamento e dell'attenuazione in difesa degli attacchi DoS (Denial of Service).
ms.openlocfilehash: dfe179924f7414b0120697023f3daf7e6b6661b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216006"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>I principi fondamentali di protezione contro gli attacchi Denial of Service

I tre principi fondamentali per la difesa dagli attacchi DoS basati sulla rete sono assorbimento, rilevamento e attenuazione. L'assorbimento avviene prima del rilevamento e il rilevamento avviene prima dell'attenuazione. L'assorbimento è la migliore difesa contro gli attacchi DoS. Se non è possibile rilevare l'attacco, non può essere attenuato. Tuttavia, se non è possibile assorbire anche il più piccolo attacco DoS, i servizi non sopravvivranno abbastanza a lungo per rilevare l'attacco.

Naturalmente, in generale, non è possibile per la maggior parte delle organizzazioni acquistare la capacità in eccesso necessaria per assorbire gli attacchi DoS, poiché ciò richiede un investimento considerevole in tecnologia e competenze tecniche. Questo evidenzia uno dei vantaggi per la sicurezza dell'utilizzo dei servizi cloud Microsoft; la scalabilità dei nostri servizi consente di offrire una protezione della rete elevata ai clienti cloud in modo economico. Tuttavia, anche a livello di scala, tuttavia, è necessario un bilanciamento tra assorbimento, rilevamento e attenuazione. Per trovare questo bilanciamento, è possibile studiare il tasso di crescita di un attacco per stimare quanto è necessario assorbire.

Il rilevamento è un gioco Cat-and-mouse. È necessario cercare continuamente i nuovi modi in cui gli utenti si attaccano o cercano di sconfiggere i sistemi. Detect-> mitigate-> Detect-> mitigate, ecc., è uno stato perpetuo e persistente che continuerà all'infinito.

## <a name="defending-against-dos-attacks"></a>Difesa dagli attacchi DoS

Per difendersi correttamente da un attacco DoS, è essenziale il rilevamento precoce. Se si rileva un attacco prima che il sistema venga sovraccaricato, i difensori possono eseguire un piano di risposta.

La formula seguente consentirà di approssimare il tempo necessario per l'impatto di un attacco DoS:

   **Capacità massima (in byte/sec)/frequenza di crescita (in byte/sec) = tempo di impatto (in byte/sec)**

Se il time-to-Detection si verifica dopo il time-to-Impact, è probabile che l'attacco DoS avrà esito positivo. Se il tempo di rilevamento si verifica prima del tempo di impatto, i servizi da attaccare devono rimanere online e accessibili, se si utilizzano le strategie di attenuazione. Pertanto, esistono solo due operazioni che è possibile eseguire per difendersi dagli attacchi DoS:
- Aumentare la capacità di innalzamento del limite massimo di capacità (che a sua volta fornisce più tempo per rilevare un attacco); o
- Consente di ridurre il tempo necessario per il rilevamento.

Aumentare la capacità ha un impatto fiscale diretto. Microsoft consiglia ai clienti di sviluppare almeno la capacità di assorbimento di base, per garantire che possano sopravvivere a un certo livello di attacco DoS. La capacità effettiva di assorbimento varia da cliente a cliente, in quanto ogni cliente ha le proprie soglie per l'esposizione, il rischio e l'esborso finanziario. In definitiva, per motivi economici, gli investimenti della ricerca e del tempo in termini di riduzione del tempo di rilevamento sono di solito la difesa più conveniente.
