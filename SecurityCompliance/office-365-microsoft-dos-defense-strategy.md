---
title: Office 365 strategia di difesa DoS di Microsoft
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una panoramica della strategia di difesa Microsoft per la gestione degli attacchi DoS (Denial of Service).
ms.openlocfilehash: acc0c74ae9ed434d4718d7b8b3bd9429b3245d46
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219986"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Strategia di difesa Denial of Service di Microsoft

La strategia di Microsoft per la difesa dagli attacchi DoS (Denial of Service) basati sulla rete è un po' univoca grazie alla nostra scalabilità e all'impronta globale. Questa scala consente a Microsoft di utilizzare strategie e tecniche che possono corrispondere a poche organizzazioni (provider o organizzazioni dei clienti). La pietra miliare della nostra strategia DoS è la nostra presenza globale. Microsoft si impegna con provider Internet, provider di peering (pubblici e privati) e società private in tutto il mondo, dandoci una presenza Internet significativa (che a questo proposito è pari a circa ogni 18 mesi). La presenza di un'area di questo tipo consente a Microsoft di assorbire gli attacchi su una superficie molto ampia.

Data la nostra natura unica, Microsoft utilizza processi di rilevamento e attenuazione che differiscono da quelli utilizzati dalle grandi imprese. La nostra strategia si basa su una separazione tra rilevamento e attenuazione, oltre a una attenuazione globale e distribuita attraverso i numerosi spigoli. Molte aziende utilizzano soluzioni di terze parti che rilevano e attenuano gli attacchi ai margini. Quando la capacità dei Edge è cresciuta, è emerso che il significato di qualsiasi attacco contro spigoli singoli o particolari era molto basso. A causa della nostra configurazione univoca, sono stati separati i componenti di rilevamento e attenuazione. È stato distribuito un rilevamento a più livelli che consente di rilevare gli attacchi più vicini ai propri punti di saturazione mantenendo la riduzione globale al limite. Questa strategia garantisce la possibilità di gestire più attacchi simultanei.

Una delle difese più efficienti e low cost impiegate da Microsoft contro gli attacchi DoS è quella di ridurre la superficie di attacco. In questo modo, è possibile eliminare il traffico indesiderato sul lato opposto all'analisi, all'elaborazione e al lavaggio dei dati in linea.

All'interfaccia con la rete pubblica, Microsoft utilizza dispositivi di sicurezza speciali per il firewall, la traduzione degli indirizzi di rete e le funzioni di filtro IP. È inoltre possibile utilizzare il routing multi-path (ECMP) globale. Il routing globale di ECMP è un Framework di rete che garantisce la disponibilità di più percorsi globali per il raggiungimento di un servizio. Grazie a questi percorsi multipli, un attacco contro il servizio dovrebbe essere limitato all'area da cui proviene l'attacco: altre aree dovrebbero essere inalterate da questo attacco, in quanto gli utenti finali utilizzeranno altri percorsi per raggiungere il servizio nelle aree geografiche. Inoltre, è stato sviluppato un sistema di rilevamento e correlazione DoS interno che utilizza dati di flusso, metriche delle prestazioni e altre informazioni. Si tratta di un servizio cloud iperscala in esecuzione in Microsoft Azure che analizza i dati raccolti da vari punti su reti e servizi Microsoft. Un team di risposta agli incidenti DoS tra i carichi di lavoro identifica i ruoli e le responsabilità tra i team, i criteri per le escalation e i protocolli per l'aggancio di vari team e per la gestione degli incidenti. Queste soluzioni forniscono una protezione basata sulla rete dagli attacchi DoS.

Infine, i carichi di lavoro basati sul cloud sono configurati con soglie ottimizzate in base al protocollo e all'utilizzo della larghezza di banda necessario per proteggere in modo univoco il carico di lavoro.
