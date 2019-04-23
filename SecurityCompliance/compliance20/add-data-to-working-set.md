---
title: Aggiungere i risultati della ricerca a un set di lavoro
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958287"
---
# <a name="add-search-results-to-a-working-set"></a>Aggiungere i risultati della ricerca a un set di lavoro

Dopo aver identificato e raccolto le ricerche in Exchange, SharePoint e OneDrive for business, è possibile aggiungere i risultati a un working set. I working set rappresentano un insieme statico di documenti che verranno indicizzati per i risultati di ricerca fulminei, analizza per l'identificazione dei thread di posta elettronica, vicino al rilevamento e ai temi duplicati.  È inoltre possibile aggiungere dati provenienti da origini dati non di Office 365 per vivere affiancati ai dati raccolti da Office 365.

Per aggiungere dati a un working set, iniziare selezionando una ricerca, nella barra dei risultati di ricerca, fare clic sul pulsante *+ Add results to working set* .

![Aggiunta di dati a un working set](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

È quindi possibile scegliere di aggiungere a un working set esistente o a un *nuovo working set*.  Se si aggiunge un nuovo working set, specificare il nome e infine fare clic sul pulsante *Aggiungi* .

![Selezionare un working set](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

L'aggiunta di dati a un working set è una procedura di esecuzione prolungata, è possibile monitorare lo stato di avanzamento nella scheda processi o nella colonna *stato working set* nella scheda *ricerche* .  Il processo include la raccolta di elementi da Office 365 e infine ingestione dell'inDicizzazione di &.  Una volta completata l'elaborazione del working set, è possibile passare al working set facendo clic sulla scheda *working* sets e quindi su working set.  È quindi possibile passare alla ricerca, alla revisione, al tagging e all'esportazione di tutti i dati rilevanti.

## <a name="adding-a-sample-to-a-working-set"></a>Aggiunta di un esempio a un working set

Se si desidera convalidare i risultati della ricerca più thorougly prima di raccogliere tutti i documenti che sono stati recuperati dalla ricerca, è possibile aggiungere un campione casuale dei risultati della ricerca a un working set invece di aggiungere tutto.

Per aggiungere un esempio a un working set, iniziare selezionando una ricerca, nel riquadro a comparsa dei risultati di ricerca, fare clic su pulsante di *esempio* .

È quindi possibile scegliere il parametro del campionamento. Esistono due opzioni:
- Livello di confidenza e intervallo: le dimensioni del campione verranno scelte per soddisfare i parametri statistici specificati.
- Percentuale: la dimensione del campione verrà determinata in base al numero di elementi restituiti dalla ricerca e al parametro scelto.

Infine, scegliere il working set per aggiungere il campione. Da qui, è possibile controllare lo stato del processo esattamente come si farebbe per aggiungere un'intera ricerca in un working set. 