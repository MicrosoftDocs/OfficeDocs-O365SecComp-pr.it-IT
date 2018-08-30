---
title: Capacità di recupero dei dati in Office 365
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
description: Acquisire familiarità con resilienza dei dati in Microsoft Office 365.
ms.openlocfilehash: 7d43c766615ff1520c6529427116c42795da8565
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531076"
---
# <a name="data-resiliency-in-office-365"></a>Capacità di recupero dei dati in Office 365

## <a name="introduction"></a>Introduzione
Data la natura complessa del cloud, Microsoft è attenzione che non è un caso in cui in verrà caso di problemi, bensì quando. È di progettazione dei servizi cloud per ottimizzare l'affidabilità e ridurre al minimo gli effetti negativi sulla clienti in caso di errori. Sono stati spostati oltre la strategia tradizionale di l'utilizzo di infrastruttura fisica complessa e aver creato la ridondanza direttamente in dei servizi cloud. Si utilizza una combinazione di software più intelligente che integra resilienza dei dati ai servizi e offre un'elevata disponibilità per i clienti e l'infrastruttura fisica meno complessa. 

## <a name="resiliency-and-recoverability-are-built-in"></a>Resilienza e la capacità di recupero sono incorporate 
Creazione resilienza e il ripristino si basa sul presupposto che l'infrastruttura e i processi sottostante avrà esito negativo in un determinato momento: hardware (infrastruttura) avrà esito negativo, gli utenti verranno commettere errori e software avrà bug. Sebbene sia corretto in modo che gli sviluppatori software non sono state pensare queste operazioni prima del cloud, come questi problemi sono stati gestiti in un'implementazione IT tipica era diverso prima del cloud: 
- Per prima cosa, hardware e infrastruttura di protezione sono stati significativi. In questo modo disporre di Datacenter con power significativi affidabilità 99,99% richieste e la ridondanza di rete e i server sono stati implementati con basata su hardware clustering doppi alimentatori, le interfacce di rete dual e simili. 
- In secondo luogo, processo è essenziale. Team operativi gestito procedure rigorose, modifiche sono state utilizzate windows, ed è stata spesso overhead di gestione di progetti importanti. 
- In terzo luogo, la distribuzione è stata effettuata una velocità glaciale. Distribuzione di codice senza proprietario dell'origine destinate in attesa per le versioni di patch e versione principale rilascia hardware necessarie per la sostituzione e significativa in conto capitale. Inoltre, l'unico modo per risolvere un problema è stato per eseguire il rollback. In questo modo, la maggior parte delle organizzazioni IT verrebbero distribuito solo principali versioni per evitare il lavoro di tenersi aggiornati. 
- Infine, la scala di sistemi distribuiti, nonché il livello di loro interconnectedness è stato passato molto più piccolo del è ora. 

Oggi, clienti si aspettano innovazioni continue Microsoft senza compromettere la qualità e si tratta di uno dei motivi per cui software e servizi Microsoft vengono create con resilienza e la capacità di recupero presente. 

## <a name="office-365-data-resiliency-principles"></a>Principi di resilienza dei dati di Office 365 
Resilienza si riferisce alla capacità di un servizio basato su cloud sostenere determinati tipi di errori e ancora rimangono completamente funzionante dalla prospettiva dei clienti. Resilienza dei dati significa che indipendentemente dalla quali gli errori generati in Office 365, i dati dei clienti critici rimangano invariato e non interessato. A tal fine, Office 365 servizi sono stati progettati circa cinque principi di resilienza specifico: 
- Esiste dati critici e non critici. Negli scenari di errore rari è possono rilasciare i dati non critici (ad esempio, se un messaggio è stato letto). Costo extreme, è necessario proteggere dati critici (ad esempio, i dati dei clienti, ad esempio messaggi di posta elettronica). Come degli obiettivi di progettazione, i messaggi di posta elettronica recapitato sono sempre critici e ad esempio, se un messaggio è stato letto è non critici. 
- Copie di dati di analisi devono essere separate in aree diverse di errore o altri guasto domini possibile (ad esempio, Data Center, accessibile dal credenziali single (processo, server o operatore)) per garantire l'isolamento degli errori. 
- Dati critici dei clienti devono essere controllati per con errori di qualsiasi parte del atomicità, coerenza, isolamento, la durata (acido). 
- Dati relativi ai clienti devono essere protetti da danneggiamento. Deve essere attivamente analizzate o monitorati, ripristinabile e ripristinabile. 
- La maggior parte dei risultati di perdita di dati dalle azioni dei clienti, pertanto consentono ai clienti di recuperare i propri utilizzando un'interfaccia utente grafica che consente di ripristinare gli elementi eliminati accidentalmente. 
 
Tramite la creazione dei servizi cloud per questi principi unitamente affidabile test e convalida, Office 365 è in grado di soddisfare e superare i requisiti dei clienti garantendo una piattaforma per l'innovazione continua e analisi utilizzo software. 

## <a name="related-links"></a>Collegamenti correlati

- [Gestione della corruzione dei dati](office-365-dealing-with-data-corruption.md)
- [Protezione malware e ransomware](office-365-malware-and-ransomware-protection.md)
- [Il monitoraggio e la riparazione automatica](office-365-monitoring-and-self-healing.md)
- [Resilienza dei dati di Exchange](office-365-exchange-data-resiliency.md)
- [Resilienza dei dati di SharePoint](office-365-sharepoint-data-resiliency.md)