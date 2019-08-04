---
title: Office 365 che si occupano di danneggiamento dei dati
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
description: Una spiegazione del danneggiamento dei dati in Office 365 e gli sforzi di prevenzione e ripristino di Microsoft.
ms.openlocfilehash: 4997ec0efb60d4e62e3a385af8bbd1a610c5290a
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786701"
---
# <a name="dealing-with-data-corruption-in-office-365"></a>Gestione del danneggiamento dei dati in Office 365

Uno degli aspetti impegnativi dell'esecuzione di un servizio cloud su vasta scala consiste nel gestire il danneggiamento dei dati, in base all'elevato volume di dati e ai sistemi indipendenti. Il danneggiamento dei dati può essere causato da:

- Bug dell'infrastruttura o dell'applicazione che danneggiano alcuni o tutti lo stato dell'applicazione
- Problemi relativi all'hardware che determinano la perdita di dati o l'impossibilità di leggere i dati
- Errori operativi umani
- Hacker maligni e dipendenti scontenti
- Eventi imprevisti nei servizi esterni che causano una perdita di dati

Poiché una maggiore resilienza nell'integrità dei dati comporta meno incidenti di danneggiamento dei dati, Microsoft ha incorporato i meccanismi di protezione di Office 365 per evitare che si verifichino danneggiamenti, nonché sistemi e processi che consentono di recuperare i dati in caso di problemi. I controlli e i processi sono presenti nelle varie fasi del processo di rilascio ingegneristico per aumentare la resilienza rispetto al danneggiamento dei dati, tra cui:

- Progettazione del sistema
- Organizzazione e struttura del codice
- Revisione del codice
- Unit test, test di integrazione e test di sistema
- Test/cancelli per cavi di viaggio

Negli ambienti di produzione di Office 365, la replica peer tra i datacenter garantisce che siano sempre presenti più copie live di tutti i dati. Le immagini e gli script standard vengono utilizzati per recuperare i server persi e i dati replicati vengono utilizzati per ripristinare i dati dei clienti. Grazie ai controlli e ai processi di resilienza dei dati incorporati, Microsoft mantiene solo i backup della documentazione del sistema di informazioni di Office 365 (inclusa la documentazione relativa alla sicurezza), utilizzando la replica incorporata in SharePoint Online e il codice interno strumento di repository, Source Depot. La documentazione del sistema è archiviata in SharePoint Online e Source Depot contiene immagini di sistema e applicazioni. Sia SharePoint Online che Source Depot utilizzano il controllo delle versioni e vengono replicati in tempo quasi reale.
