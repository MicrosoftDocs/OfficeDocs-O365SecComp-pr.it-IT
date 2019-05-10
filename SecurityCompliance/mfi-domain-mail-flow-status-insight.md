---
title: Informazioni sullo stato del flusso di posta principale del dominio
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sulla panoramica dello stato del flusso di posta di dominio principale nel dashboard del flusso di posta nel centro sicurezza & Compliance.
ms.openlocfilehash: 851ef1438f111a36f69563670bbd0835a9956edc
ms.sourcegitcommit: e05e83212e7ca4e84f2ddb0de0297895b995338d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868593"
---
# <a name="top-domain-mail-flow-status-insight"></a>Informazioni sullo stato del flusso di posta principale del dominio

L'Insight **sullo stato del flusso di posta di dominio principale** offre lo stato corrente dei domini dell'organizzazione in termini di flusso di posta. Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.

![Informazioni sullo stato del flusso di dominio superiore nel dashboard del flusso di posta nel centro sicurezza & Compliance](media/domain-mail-flow-status-selected.png)

Quando si fa clic su **Visualizza dettagli** nell'Insight, viene visualizzato un riquadro a comparsa per visualizzare ulteriori dettagli sullo stato di ciascun dominio.

Un segno di spunta verde per un dominio indica che il record MX corrente (quando si è visualizzato il dashboard per la visualizzazione del flusso di posta) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.

Una x rossa per un dominio indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore. Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato. Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.

![Il riquadro a comparsa dettagli nell'Insight sullo stato del flusso di dominio superiore](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security _AMP_ Compliance Center](mail-flow-insights-v2.md).
