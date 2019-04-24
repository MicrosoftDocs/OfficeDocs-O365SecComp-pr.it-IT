---
title: Analizzare i dati in un working set in Advanced eDiscovery (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243237"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>Analizzare i dati in un working set in Advanced eDiscovery (Preview)

Quando il numero di documenti raccolti è di grandi dimensioni, può essere molto difficile rivederli tutti. Advanced eDiscovery (Preview) fornisce una serie di strumenti per analizzare i documenti per ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in modo coerente. Per ulteriori informazioni su queste funzionalità, vedere:

- [Rilevamento dei documenti simili](near-duplicates.md)
- [Threading posta elettronica](email-threading.md)
- [Temi](themes.md)

Per analizzare i dati in un working set:

1. Configurare le impostazioni di analisi per il caso. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).
2. Aprire il working set che si desidera analizzare.
3. Andare a "Gestisci working set".
4. Fare clic su "analyze".

È possibile controllare lo stato di avanzamento dell'analisi nella scheda processi del caso.

 Dopo aver completato l'analisi, è possibile visualizzare il report di analisi, eseguire query all'interno del working set su output dell'analisi (per ulteriori informazioni, vedere [query all'interno del working set](working-set-search.md)) e vedere documenti correlati di un documento specifico (per ulteriori informazioni, vedere [ Revisione dei dati in working set](reviewing-data-in-working-set.md)).

## <a name="analytics-report"></a>Report di analisi

Per visualizzare un report di analisi per il working set:

1. Aprire il working set.
2. Andare a "Gestisci working set".
3. Fare clic su "report".

Il report ha quattro componenti dall'analisi:

- **Breakdown** : numero di messaggi di posta elettronica, allegati e documenti sciolti presenti nel working set.

- **Documenti (esclusi gli allegati)** -quanti documenti sfusi sono stati pivot, unici in prossimità di duplicati di un pivot o duplicati esatti di un altro documento.

- **Messaggi** di posta elettronica-numero di messaggi di posta elettronica inclusi, copie inclusive, svantaggi inclusi o nessuno di questi.

- **Allegati** : quanti allegati di posta elettronica sono stati univoci o duplicati di un allegato di posta elettronica diverso all'interno del working set.