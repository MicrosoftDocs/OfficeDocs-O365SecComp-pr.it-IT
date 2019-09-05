---
title: Difendersi dagli attacchi Denial of Service in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Una panoramica degli attacchi DoS (Denial of Service).
ms.openlocfilehash: 94f87a11f396cb8ef09fd6d670d73ba8d1e88eda
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761662"
---
# <a name="defend-against-denial-of-service-attacks-in-office-365"></a>Difendersi dagli attacchi Denial of Service in Office 365

## <a name="introduction"></a>Introduzione

Microsoft offre un'infrastruttura affidabile per più di 200 servizi cloud ospitati in un'infrastruttura cloud globale di oltre 100 datacenter. Queste funzionalità sono:

- Microsoft Azure
- Microsoft Bing
- Microsoft Dynamics 365
- Microsoft Office 365
- Microsoft OneDrive
- Skype
- Xbox Live

In quanto organizzazione globale con una presenza Internet significativa e numerose proprietà di Internet importanti che forniscono servizi cloud, Microsoft è un obiettivo di grandi dimensioni comune per gli hacker e gli altri utenti dannosi. Il livello di comunicazione di rete tra client e Microsoft Cloud è uno dei principali obiettivi degli attacchi dannosi. In effetti, Microsoft è continuamente e persistente sotto una qualche forma di cyberattack basato sulla rete. In linea con questo, Microsoft utilizza principi di sicurezza per la difesa in profondità per proteggere i servizi e le reti cloud. Senza sistemi di attenuazione affidabili e persistenti che difendono tali attacchi, i servizi cloud di Microsoft sarebbero non in linea e non sono disponibili per i clienti.

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>Definizione e sintomi degli attacchi Denial of Service

Un modo per attaccare i servizi di rete consiste nel creare numerose richieste contro gli host del servizio per sopraffare la rete e i server per negare il servizio agli utenti legittimi. Questo è definito come un attacco Denial of Service (DoS). Quando l'attacco viene eseguito da più attori, endpoint e/o vettori, viene indicato come un attacco di tipo Denial-of-Service (DDoS) distribuito. Anche se i mezzi, i motivi e gli obiettivi variano, gli attacchi DoS e DDoS in genere compongono gli sforzi per impedire che un sito o un servizio Internet funzioni correttamente o a tutti, temporaneamente o a tempo indeterminato.

Il [team degli Stati Uniti per la preparazione alle emergenze del computer](https://www.us-cert.gov/) (US-CERT) definisce i sintomi degli attacchi DOS per includere:

- Prestazioni di rete insolitamente lente (quando si aprono file o si accede a siti Internet)
- Indisponibilità di un sito Web
- Impossibilità di accedere a un sito Web
- Notevole aumento della posta indesiderata ricevuta
- Disconnessione di una connessione Internet wireless o cablata
- Perdita di accesso a lungo termine al Web o a qualsiasi servizio Internet

## <a name="related-topics"></a>Argomenti correlati

- [I principi fondamentali di protezione contro gli attacchi Denial of Service](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Strategia di difesa Denial of Service di Microsoft](office-365-microsoft-dos-defense-strategy.md)
- [Difesa dei servizi cloud Microsoft in base agli attacchi Denial of Service](office-365-defending-cloud-services-against-dos-attacks.md)
