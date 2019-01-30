---
title: Analisi dei dati in un working set di eDiscovery avanzate (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a6284204fd709bcf936688f36f38f6b3283b1f98
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607879"
---
# <a name="analyzing-data-in-a-working-set-in-advanced-ediscovery-preview"></a>Analisi dei dati in un working set di eDiscovery avanzate (Preview)

Quando il numero di raccolti documenti di grandi dimensioni, può essere molto difficile esaminare tutte. EDiscovery avanzate (Preview) offre una serie di strumenti per analizzare i documenti in modo da ridurre il volume di documenti per la revisione senza perdita di informazioni e che consentono di organizzare i documenti in modo coerente. Per ulteriori informazioni su queste funzionalità, vedere:

- [Quasi duplicati](near-duplicates.md)
- [Messaggio di posta elettronica threading](email-threading.md)
- [Temi](themes.md)

Per analizzare i dati in un gruppo di lavoro:

1. Configurare le impostazioni di analitica per il case. Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analitica](configure-search-analytics-settings.md).
2. Aprire il set di lavoro che si desidera analizzare.
3. Passare a "Gestisci working set".
4. Fare clic su "Analizzare".

È possibile controllare lo stato di avanzamento dell'analisi della scheda processi nel caso specifico.

 Al termine dell'analisi, è possibile visualizzare report analitica, le query eseguite all'interno di lavoro è impostata su output dell'analisi (per ulteriori informazioni, vedere [Query all'interno del working set](working-set-search.md)) e visualizzare i documenti correlati di un determinato documento (per ulteriori informazioni, vedere [ Analisi dei dati nel working set](reviewing-data-in-working-set.md)).

## <a name="analytics-report"></a>Rapporto Analitica

Per visualizzare un report analitica per set in uso:

1. Aprire il working set.
2. Passare a "Gestisci working set".
3. Fare clic su "Report".

Il report include quattro componenti di analisi:

- **Suddivisione** - quanti messaggi di posta elettronica, gli allegati e documenti espansa sono state trovate nel set di lavoro.

- **Documenti (escluso allegati)** - numero di documenti espansa sono stati pivot univoco quasi duplicati di rotazione o un duplicato esatto di un altro documento.

- **Messaggi di posta elettronica** - quanti messaggi di posta elettronica sono state inclusives, inclusi copie, inclusi svantaggi o nessuna delle precedenti.

- **Allegati** - quante gli allegati di posta elettronica sono state univoci o duplicati di un allegato di posta elettronica diverso all'interno del working set.