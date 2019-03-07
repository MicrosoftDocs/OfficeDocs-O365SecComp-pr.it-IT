---
title: Approfondimenti sulle regole del flusso di posta lento
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Gli amministratori possono ottenere informazioni sull'Insight delle regole del flusso di posta lenta nel dashboard del flusso di posta in Office 365 Security & Compliance Center.
ms.openlocfilehash: 8188ee0da15ac337499866783ca4f2d893062d5b
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454878"
---
# <a name="slow-mail-flow-rules-insight"></a>Approfondimenti sulle regole del flusso di posta lento

Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione. Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione. Esempi di questi tipi di regole sono:

- Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.

- Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.

- Condizioni che utilizzano il controllo del contenuto negli allegati.

L'Insight consentirà di identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.

![Una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta nel centro conformità di Office 365 Security &](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

Quando si fa clic su **Visualizza dettagli**, viene visualizzato un riquadro a comparsa dove è possibile esaminare la regola. Nel riquadro a comparsa, è anche possibile fare clic su **Visualizza messaggi di esempio** per visualizzare il tipo di messaggi interessati dalla regola.

![Riquadro a comparsa dopo aver fatto clic su Visualizza dettagli in una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
