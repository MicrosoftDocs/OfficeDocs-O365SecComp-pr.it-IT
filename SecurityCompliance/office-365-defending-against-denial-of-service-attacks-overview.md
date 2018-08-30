---
title: La difesa contro gli attacchi Denial of Service in Office 365
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
description: Panoramica di attacchi Denial of Service (DoS).
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530193"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>La difesa contro gli attacchi Denial of Service in Office 365

## <a name="introduction"></a>Introduzione
Microsoft offre un'infrastruttura di affidabilità per più di 200 cloud services, tra cui Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype e Xbox Live ospitate nel nostro cloud globale infrastruttura dei centri dati più di 100.

Un'organizzazione globale con una significativa presenza Internet e molte proprietà Internet evidente che offrono servizi cloud, Microsoft è una destinazione di grandi dimensioni, comune per utenti malintenzionati e di altri utenti non autorizzati. Rete - livello di comunicazione tra i client e Microsoft Cloud - è uno dei destinatari più importanti di attacchi dannosi. In realtà, per molti anni, Microsoft è stata continuamente e in modo permanente in una forma di cyberattack basate sulla rete. Quasi completamente scarico, almeno una delle proprietà di Microsoft Internet è stati riscontrati sorta di attacco. Senza sistemi attenuazione affidabile e persistente che possono migliorare la difesa contro gli attacchi, servizi cloud Microsoft è non in linea e disponibile per i clienti.

Principi di protezione in difesa utilizzate da Microsoft per proteggere le reti e i servizi cloud. 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>Definizione e sintomi di attacchi Denial of Service
Un modo per servizi di rete di attacchi consiste nel creare molte richieste contro gli host del servizio per sovraccaricare la rete e i server per negare servizio agli utenti legittimi. Questo è definito un attacco di tipo denial of service (DoS). L'attacco viene eseguita da più operatori, gli endpoint e/o vecteurs de, viene definito un attacco (DDoS) di tipo denial of service distribuito. Sebbene varino il mezzo, motivazioni e gli obiettivi, attacchi DoS e DDoS costituita in genere gli sforzi di una o più persone per impedire a un sito Internet o servizio funzioni correttamente o affatto, temporaneamente o per un tempo indefinito.

[Stati Uniti Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) definisce i sintomi di attacchi Denial of Service da includere:
- Prestazioni di rete lente insolitamente (quando apertura di file o l'accesso a siti Internet)
- Non disponibilità di un sito Web
- Impossibilità di accedere a un sito Web
- Aumento significativo posta indesiderata ricevuta
- Disconnessione di una connessione Internet wireless o cablata
- Perdita a lungo termine di accesso per il Web o i servizi Internet

## <a name="related-topics"></a>Argomenti correlati
- [I principi fondamentali di protezione contro gli attacchi Denial of Service](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Strategia di difesa di tipo Denial of Service di Microsoft](office-365-microsoft-dos-defense-strategy.md)
- [La difesa contro gli attacchi Denial of Service i servizi Cloud Microsoft](office-365-defending-cloud-services-against-dos-attacks.md)
