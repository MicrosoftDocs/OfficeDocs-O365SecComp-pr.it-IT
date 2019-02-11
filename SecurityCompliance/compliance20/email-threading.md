---
title: Threading posta elettronica
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
ms.openlocfilehash: d4328971a6b13c60c4d8b9f5b6db310d72a5b215
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29705997"
---
# <a name="email-threading"></a>Threading posta elettronica

È consigliabile una conversazione di posta elettronica succedendo per un po' di tempo. Nella maggior parte dei casi, il messaggio di posta elettronica ultimo sul thread includerà il contenuto di tutti i precedenti messaggi di posta elettronica; Per ottenere un contesto completo della conversazione che si sono verificati il thread, esaminare l'ultimo messaggio di posta elettronica. Messaggio di posta elettronica threading identifica tali messaggi di posta elettronica in modo che i revisori possono esaminare una frazione di raccolte documenti senza perdere alcun contesto.

## <a name="what-does-email-threading-do"></a>Che cosa threading posta elettronica?

Messaggio di posta elettronica threading analizza ogni messaggio di posta elettronica e desconstructs per singoli messaggi. ogni messaggio di posta elettronica è una serie di singoli messaggi. Quindi, analizza tutti i messaggi di posta elettronica nel working set per determinare se un messaggio di posta elettronica con contenuto univoco o se la catena interamente contenuta in un messaggio di posta elettronica diverso. Alla fine messaggi di posta elettronica sono suddivise in quattro categorie:

- **Inclusivo**: dell'ultimo messaggio nella posta elettronica con contenuto univoco e il messaggio di posta elettronica dispone di tutti gli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è completamente contenuto in questo messaggio di posta elettronica.


- **Inclusivo meno**: dell'ultimo messaggio nella posta elettronica con contenuto univoco, ma il messaggio di posta elettronica non contiene alcuni degli allegati che sono stati inclusi in altri messaggi di posta elettronica di cui il contenuto è completamente contenuto in questo messaggio di posta elettronica.

- **Copia inclusivo**: una copia esatta di un inclusi/inclusi meno posta elettronica

- **None**: il contenuto di questo messaggio di posta elettronica interamente contenuto in almeno un messaggio di posta elettronica è contrassegnato come sottrazione inclusi/inclusi.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Qual è la differenza dalle conversazioni di Outlook?
In breve, questo suoni molto simile a raggruppamenti di conversazione in Outlook. Esistono tuttavia alcune differenze importanti. Prendere in considerazione una conversazione di posta elettronica che ha ricevuto inoltrata a due conversazione; ad esempio, un utente ha risposto a un messaggio di posta elettronica che non è più recente della conversazione in modo che le ultime due messaggi di posta elettronica nella conversazione entrambi con contenuto univoco.

Outlook ancora per raggruppare i messaggi di posta elettronica in una singola conversazione; leggere l'ultima email implica manca il contesto della posta elettronica al penultimo, che contiene anche contenuto univoco. Poiché posta threading analizza ogni messaggio di posta elettronica in singoli componenti e li confronta, posta elettronica threading contrassegna entrambe le ultime due messaggi di posta elettronica come inclusives, assicurarsi che non perdere alcun contesto come leggere contrassegnato come inclusi tutti i messaggi di posta elettronica.