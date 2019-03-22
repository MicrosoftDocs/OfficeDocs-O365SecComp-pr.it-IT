---
title: Gestire i processi in Advanced eDiscovery (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 84e2a8dc389d738b8bda1ab21101b2e5e40eee03
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737646"
---
# <a name="manage-jobs-in-advanced-ediscovery-preview"></a>Gestire i processi in Advanced eDiscovery (Preview)

Di seguito è indicato un elenco dei processi che vengono registrati nella scheda **processi** di un caso in Advanced eDiscovery (Preview).

| Tipo processo | Descrizione | Carichi di lavoro a cui si applica questo processo |
| :- | :- | :- |
| Reindicizzazione dei dati del custode | Quando un custode viene aggiunto a un caso, tutti gli elementi parzialmente indicizzati vengono reindicizzati con l'indicizzazione avanzata di eDiscovery, per ulteriori informazioni, vedere [Advanced indicizzazione dei dati del custode](indexing-custodian-data.md). | Advanced eDiscovery |
| Stima dei risultati della ricerca | La stima dei risultati della ricerca è il risultato della creazione e dell'esecuzione di una ricerca in base ai carichi di lavoro, ad esempio Exchange, SharePoint e OneDrive for business.  Le stime includono statistiche quali il numero di elementi restituiti dalla ricerca e dalle dimensioni.  Per ulteriori informazioni sulla ricerca, vedere [raccolta di dati per un caso in Advanced eDiscovery](collecting-data-for-ediscovery.md). | Advanced eDiscovery |
| Preparazione dell'anteprima di ricerca | La preparazione dei processi di anteprima di ricerca è il risultato della creazione e dell'esecuzione di una ricerca in base ai carichi di lavoro, ad esempio Exchange, SharePoint e OneDrive for business.  È disponibile un'anteprima dei risultati della ricerca per contribuire a determinare l'efficacia della ricerca.  Per ulteriori informazioni sulla ricerca, vedere [raccolta di dati per un caso in Advanced eDiscovery](collecting-data-for-ediscovery.md). | Advanced eDiscovery |
| Aggiunta di dati a un working set | Quando i risultati di una ricerca vengono aggiunti a un working set, è possibile aggiungere dati ai processi di working set.  Per ulteriori informazioni sulla gestione dei set di lavoro, vedere [Manage working sets in Advanced eDiscovery](managing-working-sets.md). | Advanced eDiscovery |
| Aggiunta di dati a un altro working set | L'aggiunta di dati a un altro processo di working set viene creata quando un utente sceglie di aggiungere i dati da un working set a un altro. | Advanced eDiscovery |
| Aggiunta di dati non di Office 365 a un working set | L'aggiunta di dati non Office 365 a un set di lavoro include l'elaborazione e l'aggiunta di dati a un set di lavoro caricato da un computer client che potrebbe essere pertinente a un caso, per ulteriori informazioni sull'aggiunta di dati non di Office 365, vedere [caricare i dati non office 365 in un working set](load-non-office365-data.md). | Advanced eDiscovery |
| Preparazione per la risoluzione degli errori |  | Advanced eDiscovery |
| Aggiunta di dati corretti a un working set | L'aggiunta di dati corretti a un working set si riferisce ai processi creati quando i file errati vengono corretti e caricati di nuovo in un working set di Office 365 Advanced eDiscovery.  Per ulteriori informazioni sulla correzione degli errori, vedere correzione degli [errori durante l'elaborazione dei dati](error-remediation.md). | Advanced eDiscovery |
| Confronto tra set di carico | Il confronto dei set di carico consente agli utenti di esaminare le differenze tra i carichi in working set, per ulteriori informazioni sui set di caricamento, vedere [gestire i set di carico](manage-load-sets.md). | Advanced eDiscovery |
| Contrassegnare i documenti | I processi di tagging dei documenti si verificano quando vengono contrassegnati più documenti in un working set.  Per ulteriori informazioni, vedere [tag Documents in a working set](tagging-documents.md). | Advanced eDiscovery |
| Esecuzione di analisi | L'esecuzione di processi di analisi si riferisce ai processi di elaborazione, tra cui l'identificazione quasi duplicata, l'analisi del thread di posta elettronica e l'analisi dei temi, per ulteriori informazioni su analisi, vedere [analizzare i dati in un working](analyzing-data-in-working-set.md) | Advanced eDiscovery |
| Preparazione dei dati per l'esportazione | La preparazione dei dati per i processi di esportazione è il risultato dell'esportazione di dati da un working set, per ulteriori informazioni sull'esportazione, vedere [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md). | Advanced eDiscovery |
