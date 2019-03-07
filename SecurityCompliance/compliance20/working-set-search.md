---
title: Eseguire query sui dati in un set di lavoro
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454988"
---
# <a name="query-the-data-in-a-working-set"></a>Eseguire query sui dati in un set di lavoro

Nella maggior parte dei casi, sarà utile essere in grado di approfondire gli elementi presenti in un working set e organizzarli per la revisione in modo più efficiente. Le query all'interno di un working set consentono di eseguire questa operazione consentendo di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri definiti dall'utente in una sola volta.

## <a name="creating-and-running-a-query-within-a-working-set"></a>Creazione e esecuzione di una query all'interno di un working set

Per creare ed eseguire una query all'interno del working set, fare clic su "nuova query" nel working set. Dopo aver denominati la query e aver definito le condizioni, fare clic su "Salva" per eseguire la query. Per eseguire una query salvata in precedenza, è sufficiente fare clic sulla query salvata. Fare riferimento ai [campi dei metadati del documento](document-metadata-fields.md) per un elenco di metadati di cui è possibile eseguire la ricerca.

## <a name="building-your-query"></a>Creazione di una query

È possibile creare la query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave.

### <a name="condition-card"></a>Scheda condizione

Ogni campo ricercabile di un working set ha una corrispondente scheda di condizione che è possibile utilizzare per creare la query.

Sono disponibili più tipi di schede di condizione:
- FREETEXT: la scheda di stato FREETEXT viene utilizzata per i campi di testo, ad esempio subject. È possibile elencare più termini di ricerca separandoli con una virgola.
- Data: la scheda condizione data viene utilizzata per i campi data, ad esempio la data dell'Ultima modifica.
- Opzioni di ricerca: la scheda condizione opzioni di ricerca fornisce un elenco di valori possibili per il campo specifico del working set. Viene utilizzato per i campi come sender, in cui è presente un numero finito di valori possibili nel working set.
- Keyword: la scheda condizione parola chiave è una specifica istanza della scheda di condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL. Per ulteriori informazioni, vedere di seguito.

### <a name="query-language"></a>Lingua query

Oltre alle schede delle condizioni, è possibile utilizzare una lingua di query simile a KQL nella scheda Parole chiave per creare la query. Il linguaggio di query supporta la sintassi di KQL standard, come e, o, non e vicino (n). Supporta anche caratteri jolly con caratteri singoli (?) e caratteri jolly (*).