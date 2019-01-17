---
title: Gli avvisi di coda e le code
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono venire a conoscenza degli avvisi di coda e le code nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità.
ms.openlocfilehash: fe750e32136af095bb0ccff8544306db76a7a667
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685501"
---
# <a name="queue-alerts-and-queues"></a>Gli avvisi di coda e le code

## <a name="queue-alerts"></a>Avvisi di coda

Quando non è possibile inviare messaggi dall'organizzazione Office 365 per locale o server di posta elettronica partner utilizzando i connettori, i messaggi vengono accodati in Office 365. Esempi comuni che causano questa condizione sono:

- Il connettore è configurato correttamente.

- Sono state apportate modifiche di rete o del firewall nell'ambiente locale.

Office 365 continuerà a tentativi di recapito per 48 ore. Dopo 48 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noto anche come rapporti di mancato recapito o messaggi di rimbalzo).

Se il volume di posta elettronica in coda supera la soglia predefinita (il valore predefinito è messaggi 2000), gli avvisi è disponibili nel dashboard di flusso della posta a **avvisi recenti**e gli amministratori riceverà una notifica tramite posta elettronica (per l'indirizzo di posta elettronica alternativi) . Per configurare la soglia di avviso, limite giornaliero notifica e/o i destinatari dell'avviso, vedere la sezione **avvisi coda Personalizza** riportata di seguito.

![Avvisi di coda nell'area di avvisi recenti del dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Personalizzare gli avvisi di coda

Sui concetti del flusso di posta elettronica creare un criterio di avviso denominata **messaggi sono in ritardo** (la casella di controllo **Invia notifiche di posta elettronica** nella schermata riportato di seguito di sotto) trovato negli **avvisi** \> **Criteri di avviso**. È possibile modificare i destinatari della soglia e avviso facendo clic sul criterio.

![Spostamento degli avvisi](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Verrà visualizzato un nuovo blade informazioni criterio, è ora possibile fare clic su **Modifica criterio**.

![Criterio di modifica ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

Blade informazioni verrà modificate in **Modifica criteri**. È ora possibile modificare i destinatari di avviso tramite posta elettronica, il limite al numero di notifiche inviate al giorno e la soglia minima per attivare l'avviso (200 o più).

![Modificare criteri Blade](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Dettagli dell'avviso coda

Quando si fa clic sull'avviso, in un riquadro comparsa vengono visualizzati i dettagli dell'avviso.

![Selezionare un avviso relativo alla coda nell'area di avvisi recenti del dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![La coda avviso dettagli menu mobile & la protezione di Office 365 centro conformità](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

È possibile fare clic su **Visualizza coda** nei dettagli dell'avviso per visualizzare i dettagli della coda, problemi e collegamenti alle correzioni disponibili in un nuovo riquadro comparsa.

![La coda avviso dettagli menu mobile & la protezione di Office 365 centro conformità](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visualizza coda nei dettagli dell'avviso](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Code

Anche se il volume di messaggi in coda non sia stata superata la soglia, è possibile utilizzare ancora l'area delle **code** del dashboard di flusso di posta elettronica per visualizzare i messaggi che sono stati accodati per più di un'ora. È possibile utilizzare l'area delle **code** per monitorare il numero di messaggi in coda (il valore 0 indica che il flusso della posta OK) ed eseguire azioni prima che il numero di messaggi in coda diventi troppo grande.

![Code nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Quando si sceglie il numero di messaggi nelle **code**, i dettagli di coda e istruzioni su come risolvere un problema saranno visualizzati in un riquadro tendina (tendina stesso visualizzata fare clic su **Visualizza coda** i dettagli di un avviso relativo alla coda).

![Dettagli coda](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)
