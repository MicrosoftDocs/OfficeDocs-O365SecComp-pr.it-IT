---
title: Distruzione dei dati di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una panoramica dei criteri di Microsoft relativi al riciclo, allo smaltimento o alla distruzione di unità disco e server del datacenter di Office 365.
ms.openlocfilehash: d273640dc12370386f08d16fe3f254800ede47b3
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696323"
---
# <a name="office-365-data-destruction"></a>Distruzione dei dati di Office 365

## <a name="physical-data-destruction"></a>Distruzione fisica dei dati

Microsoft dispone di criteri standard per la gestione dei dati che soddisfano il riciclo e lo smaltimento di unità disco e server non riusciti o in pensione. Prima di riutilizzare le unità disco all'interno di Office 365, Microsoft esegue un processo di disinfezione fisica coerente con l'Istituto nazionale degli standard e della tecnologia Special Publication 800-88 ([linee guida del NIST SP 800-88 per la sanificaZione dei contenuti multimediali](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) ). Tutte le unità disco di Office 365 vengono crittografate utilizzando la crittografia a livello di volume di BitLocker, quindi, in pratica, la cancellazione del NIST SP 800-88 conforme non è necessaria. Tuttavia, è ancora eseguito da Microsoft.

I dischi non riusciti utilizzati all'interno dei datacenter di Office 365 vengono distrutti fisicamente e controllati tramite il processo ISO. Il metodo di eliminazione appropriato è determinato dal tipo di risorsa. Per i dischi rigidi che non possono essere cancellati, Microsoft utilizza un processo di distruzione che distrugge i contenuti multimediali (ad esempio, si disintegra, polverizza o incenerisce) e rende impossibile il ripristino delle informazioni. Microsoft conserva anche tutti i record relativi alla distruzione. Microsoft esegue un processo di sanificazione simile nei server che vengono riutilizzati all'interno di Office 365. Queste linee guida comprendono sia la sanificazione elettronica sia quella fisica.

Le unità disco che non possono essere riutilizzate vengono eliminate utilizzando un processo di distruzione fisica eseguito nel sito all'interno del datacenter contenente i dischi da distruggere. I supporti di archiviazione designati per lo smaltimento vengono collocati in contenitori sicuri situati in ogni area del datacenter. Ogni stazione di collocazione sicura è monitorata da video sorveglianza. Una volta che un cassetto di eliminazione raggiunge circa 50% di capacità, il team di servizi del sito contatta il team di sicurezza fisica per coordinarne la rimozione. I servizi del sito personale quindi rimuovere il bidone di eliminazione in scorta da un responsabile della sicurezza fino a quando non viene inserito in un'area di archiviazione sicura per l'attesa di distruzione dei dati. I criteri e le procedure che regolano la gestione dei dispositivi per i cuscinetti durante lo smaltimento sono testati di routine, incluse le procedure per garantire la condizione di macchinari approvati per la distruzione.

Nel processo di distruzione dei dati, il disco viene prima cancellato in modo conforme al NIST 800-88 (se possibile) e quindi viene inserito in un trituratore industriale e demolito fisicamente. Microsoft mantiene la responsabilità per le risorse che lasciano il datacenter usando il NIST SP 800-88 per la pulizia/eliminazione coerente, la distruzione delle risorse, la crittografia, l'inventario accurato, il monitoraggio e la protezione della catena di custodia durante il trasporto. Questo processo viene monitorato tramite la televisione a circuito chiuso e viene emesso un certificato di distruzione al termine del completamento.

Microsoft utilizza unità di cancellazione dei dati da [Extreme Protocol Solutions](http://www.enterprisedataerasure.com/) (EPS). Il software EPS supporta i requisiti del NIST SP 800-88 per la pulizia e l'eliminazione/cancellazione sicura. Prima di eseguire la pulizia o la distruzione, viene creato un inventario da Microsoft Asset Manager. Se un fornitore viene utilizzato per la distruzione, il fornitore fornisce un certificato di distruzione per ogni risorsa distrutta, convalidata dall'Asset Manager.

## <a name="virtual-data-destruction"></a>Distruzione dei dati virtuali

Microsoft dispone di criteri e procedure per la gestione dei dati che richiamano anche la distruzione virtuale effettiva dei dati per proteggersi dalla possibilità che i dati vengano condivisi in modo inappropriato tra i tenant dei servizi o che siano accessibili dopo l'eliminazione definitiva del servizio. I dati eliminati dal servizio in un tenant non sono accessibili a un altro tenant del servizio anche se alcuni o tutti lo stesso archivio fisico sottostante vengono successivamente riassegnati. Si tratta di un risultato degli effetti aggravati di più tecnologie di virtualizzazione e frammentazione utilizzate per la scalabilità degli ambienti virtuali, dei comportamenti di eliminazione attivi delle applicazioni all'interno di ogni tenant del servizio (ad esempio, l'azzeramento delle [pagine](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)) e del necessario processi di crittografia dei contenuti multimediali e applicazioni.