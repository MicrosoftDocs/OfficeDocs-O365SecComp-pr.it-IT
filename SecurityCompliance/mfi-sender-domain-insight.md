---
title: Risolvere le informazioni dettagliate del dominio del mittente
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sull'Insight del dominio del mittente Fix nel dashboard del flusso di posta nel centro sicurezza & Compliance.
ms.openlocfilehash: 181f224064b5f31fd17c348cc4547826fbcd29a9
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158708"
---
# <a name="fix-sender-domain-insight"></a>Risolvere le informazioni dettagliate del dominio del mittente

Office 365 richiede l'invio di messaggi da ambienti di posta elettronica locali interni a Office 365 per rispondere a determinati criteri di sicurezza:

- È stato creato un connettore in ingresso in Office 365 per autenticare le connessioni SMTP dal server di posta elettronica locale utilizzando l'indirizzo IP di origine o un certificato.

- Il server di posta elettronica locale è stato configurato per inoltrare la posta elettronica tramite Office 365 al mondo esterno.

- Nella configurazione, una delle seguenti affermazioni è vera:

  - Il dominio di posta elettronica del mittente è registrato nell'organizzazione di Office 365. Per ulteriori informazioni, vedere Add Domains in Office 365.

  - Il server di posta elettronica locale è configurato per l'utilizzo di un certificato per l'invio di posta elettronica a Office 365, il certificato contiene o corrisponde esattamente a un nome di dominio registrato in Office 365 ed è stato creato un connettore basato su certificato in Office 365 con tale dominio. 

I messaggi che non soddisfano i criteri non verranno attribuiti all'organizzazione e potrebbero essere rifiutati.

La **correzione del dominio del mittente** consente di visualizzare la posta elettronica dall'ambiente locale che non soddisfa i criteri, consente di identificare le macchine e gli account utente potenzialmente compromessi nell'ambiente di posta elettronica locale, contribuendo a eseguire azioni di correzione.

![L'Insight del dominio del mittente Fix nel dashboard del flusso di posta nel centro sicurezza & Compliance](media/sender-domain-insight-selected.png)

Quando si fa clic su **Visualizza dettagli**, si viene indirizzati a un altro widget con maggiori dettagli, come illustrato nel diagramma seguente:

![Il widget dettagli nell'Insight del dominio del mittente FIX](media/sender-domain-view-details.png)

Verrà visualizzato il connettore in ingresso utilizzato per recapitare i messaggi a Office 365. È inoltre possibile fare clic su **Visualizza ID messaggio di esempio** per visualizzare i dettagli relativi ai messaggi inviati dall'ambiente di posta elettronica locale. Poiché questi messaggi sono stati rifiutati da Office 365, non è possibile utilizzare la traccia dei messaggi, ma gli ID del messaggio di esempio possono essere rintracciati nell'ambiente di posta elettronica locale.

![Visualizzare gli ID dei messaggi di esempio nell'Insight del dominio del mittente FIX](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security _AMP_ Compliance Center](mail-flow-insights-v2.md).
