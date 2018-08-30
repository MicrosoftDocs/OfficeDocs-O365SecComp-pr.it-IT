---
title: Strategia di difesa di Microsoft Office 365 DoS
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Panoramica della strategia di difesa di Microsoft per la gestione di attacchi denial of service (DoS).
ms.openlocfilehash: f172db5080ef73402c7e9bc61720eb0f87e844ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530203"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Strategia di difesa di tipo Denial of Service di Microsoft

La strategia Microsoft per la difesa contro basate sulla rete gli attacchi di tipo denial of service (DoS) è un po' univoca per la scalabilità e connotazione. Questa scala consente a Microsoft utilizzare strategie e le tecniche che possono corrispondere a alcune organizzazioni (provider o organizzazioni cliente). L'elemento fondamentale della strategia DoS si avvale la presenza globali. Microsoft coinvolge con provider, provider peering (pubblici e privati) e private Internet le aziende in tutto il mondo, per un una significativa presenza Internet (che in questo modo, raddoppiata intorno a ogni 18 mesi). Con questa presenza grande consente a Microsoft di assorbire gli attacchi di tipo tra una molto grande della superficie di attacco.

Dato il nostro peculiari, Microsoft utilizza i processi di rilevamento e attenuazione diversi da quelli utilizzati per le grandi aziende. Strategia si basa su una separazione di rilevamento e attenuazione, nonché attenuazione globale, distribuita attraverso i bordi molti. Molte aziende utilizzano soluzioni di terze parti che rileva e ridurre gli attacchi in corrispondenza del bordo. Come raggiunge dimensioni la capacità di server perimetrali, era chiaro che l'importanza di un attacco bordi singoli o specifici è molto ridotta. Separate per la configurazione univoca, i componenti di rilevamento e attenuazione. È stato distribuito il rilevamento a più livelli che consente di rilevare attacchi per i punti di saturazione mantenendo attenuazione globale in corrispondenza del bordo. Questa strategia assicura, è possibile gestire gli attacchi contemporaneamente più.

Uno della difesa più efficace ed economica utilizzate da Microsoft contro gli attacchi DoS deve ridurre la superficie di attacco. In questo modo ci consente di eliminare il traffico indesiderato in corrispondenza del bordo, anziché un'analisi, elaborazione e lo scrubbing inline dati.

Livello di interfaccia di rete pubblica, Microsoft utilizza periferiche di protezione speciali per firewall, NAT e funzioni di filtraggio IP. È inoltre possibile utilizzare routing globale è uguale a costo multi-path (ECMP). Distribuzione globale ECMP è un'infrastruttura di rete che garantisce sono presenti più percorsi globali di raggiungere un servizio. Grazie a questi più percorsi, un attacco in base al servizio deve essere limitato per l'area da cui proviene l'attacco – altre aree dovrebbero essere influenzate da questo attacco, come gli utenti finali utilizzano altri percorsi per raggiungere il servizio in tali aree. Abbiamo inoltre sviluppato i propri DoS correlazione e rilevamento sistema interno che utilizza dati del flusso, le metriche delle prestazioni e altre informazioni. Si tratta di un servizio cloud superscalari eseguite in Microsoft Azure che analizza i dati raccolti da punti diversi per le reti Microsoft e i servizi. Un team di intervento DoS tra carico di lavoro vengono identificati i ruoli e responsabilità tutti i criteri per le misure correttive i team e i protocolli per la partecipazione a vari team e per la gestione degli eventi imprevisti. Queste soluzioni offrono basate sulla rete protezione da attacchi Denial of Service.

Infine, basata su cloud carichi di lavoro devono essere configurate con soglie ottimizzate basate sul proprio protocollo ed è necessario proteggere in modo univoco il carico di utilizzo della larghezza di banda.
