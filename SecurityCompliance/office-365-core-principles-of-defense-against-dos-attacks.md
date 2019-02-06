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
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>I principi fondamentali di protezione contro gli attacchi Denial of Service

Le tre principali principi dopo la difesa contro gli attacchi DoS rete assorbire, individuazione e attenuazione. Assorbire si verifica prima del rilevamento e rilevamento si verifica prima attenuazione. Assorbire è la miglior difesa contro un attacchi Denial of Service. Se non è rilevato l'attacco, non possono essere ridotti. Ma se non è assorbire attacco DoS più piccolo, servizi non sono continui di sopravvivenza tempo sufficiente per l'attacco da rilevare.

Ovviamente, in genere non è realizzabile economicamente per la maggior parte delle organizzazioni acquistare della capacità in eccesso necessaria per assorbire attacchi Denial of Service, in quanto richiede un ingente investimento in tecnologie e competenze tecniche. Evidenzia uno dei vantaggi dell'utilizzo dei servizi cloud Microsoft, per la protezione la scala una enorme ai servizi ci consente di fornire protezione della rete sicuro ai nostri clienti cloud in modo economico. Ma anche alla scala, tuttavia, è necessario ancora che un equilibrio tra assorbire, individuazione e attenuazione. Per individuare tale bilanciamento, è lo Studio tasso di crescita dell'attacco per calcolare la quantità dobbiamo accettabile.

Rilevamento è una sfida. È necessario cercare costantemente per utenti nuovi modi sono che si attacca o che tentano di annullare i sistemi. Rilevare - gt _ attenuare - rileva - gt _ gt _ attenuare i e così via, è uno stato perpetua, persistent continua per un tempo indefinito.

## <a name="defending-against-dos-attacks"></a>La difesa contro gli attacchi DoS

Per migliorare correttamente la difesa contro un attacco Denial of Service, il rilevamento anticipato è essenziale. Per rilevare un attacco prima che il sistema è sovraccarico, difensori possono eseguire un piano di risposta.

La formula seguente consentiranno di circa il tempo necessario per l'impatto di un attacco Denial of Service:

   **Capacità massima (in byte/sec) / tasso di crescita (in byte/sec) = tempo all'impatto (in byte/sec)**

Se il tempo di rilevamento si verifica dopo l'ora a impatto, è probabile che l'attacco Denial of Service avrà esito positivo. Se il tempo di rilevamento si verifica prima del tempo di impatto, i servizi di attacchi devono rimanere in linea e accessibile se vengono utilizzate le strategie di attenuazione. In questo modo, sono disponibili solo due operazioni che possono essere intraprese per migliorare la difesa contro gli attacchi DoS:
- Incrementare la capacità di passare ceiling di capacità massima (che a sua volta fornisce più tempo per rilevare un attacco); o
- Ridurre il tempo necessario per rilevare.

Aumentare la capacità ha un impatto diretto fiscale. È consigliabile che i clienti sviluppano assorbire almeno base capacità, per assicurarsi che è possibile restano valide anche un certo livello di attacco Denial of Service. La capacità di assorbire effettivo varierà a clienti, come ogni cliente con i propri soglie per esposizione, i rischi e spese finanziari. In sintesi, per motivi economici, a livello di ricerca e l'ora in modi per ridurre il tempo di rilevamento è in genere il sistema di difesa più economico.
