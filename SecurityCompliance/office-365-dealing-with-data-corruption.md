---
title: Office 365 a che fare con il danneggiamento dei dati
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
description: Spiegazione del danneggiamento dei dati in Office 365 e le attività di Microsoft di prevenzione e ripristino.
ms.openlocfilehash: 087be23ce5dad1daf62357cb08e27c0a15962792
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530892"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>Gestire il danneggiamento dei dati in Office 365

Uno degli aspetti complessi dell'esecuzione di un servizio cloud su larga scala viene illustrato come gestire il danneggiamento dei dati, dato il volume elevato di dati e sistemi indipendenti. Il danneggiamento dei dati può essere causato da:
- Infrastruttura di applicazioni o di bug, corrompere alcune o tutte lo stato dell'applicazione 
- Hardware che consentono di perdita di dati o l'impossibilità di leggere i dati dei problemi 
- Errori operativi risorse umani 
- Malintenzionati e dipendenti malintenzionati 
- Problemi di servizi esterni che causare una perdita di dati 

Poiché maggiore resilienza sull'integrità dei dati significa meno interventi di danneggiamento dei dati, Microsoft ha creato in meccanismi di protezione di Office 365 per evitare il danneggiamento da avvenga, nonché sistemi e processi che consentono di ripristinare i dati in caso contrario. Controlli e i processi esistono all'interno di varie fasi del processo di rilascio engineering per aumentare la resilienza dal danneggiamento dei dati, tra cui:
- Struttura del sistema
- Le organizzazioni di codice e struttura 
- Revisione del codice 
- Unit test, test di integrazione e test di sistema
- Viaggio cavi/controlli di test 

In ambienti di produzione di Office 365, la replica peer tra Data Center garantisce che non vi siano sempre più copie live di tutti i dati. Script e immagini standard consentono di ripristinare perse server e i dati replicati viene utilizzati per ripristinare i dati dei clienti. A causa di dati incorporati resilienza dei controlli e i processi, con cui Microsoft gestisce i backup solo della documentazione di Office 365 information system (inclusa la documentazione di protezione), utilizzando la replica incorporata in SharePoint Online e il codice interno strumento di archivio, deposito di origine. Documentazione relativa al sistema verrà archiviato in SharePoint Online e deposito di origine contiene le immagini di sistema e delle applicazioni. SharePoint Online e deposito di origine di utilizzare il controllo delle versioni e replicato in quasi in tempo reale. 