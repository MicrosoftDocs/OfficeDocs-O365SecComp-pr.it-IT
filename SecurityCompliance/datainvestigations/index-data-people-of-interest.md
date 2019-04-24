---
title: Indicizzazione avanzata dei dati per un'indagine
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
ms.openlocfilehash: 9537cf743b89da7167ce3a37a5915027f4eb717a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260694"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Indicizzazione avanzata dei dati per un'indagine

Il contenuto del sistema attivo può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, tipi di file non supportati o durante l'indicizzazione dei limiti delle dimensioni dei file. Quando si ha a che fare con la fuoriuscita di dati ad alto rischio, è necessario assicurarsi che la ricerca abbia acquisito tutti i dati che si desidera esaminare. Quando una persona di interesse viene aggiunta a un'analisi dei dati, qualsiasi contenuto di Office 365 ritenuto rielaborato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile. Questo processo è denominato *Advanced*indicizzazione. 

Per ulteriori informazioni sull'elaborazione del supporto in Office 365 e sugli elementi parzialmente indicizzati, vedere:

- [Tipi di file supportati nelle indagini sui dati](supported-filetypes-datainvestigations.md)

- [Partially indexed items in Content Search in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)

- [Formati di file indicizzati dalla ricerca di Exchange](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visualizzazione dei risultati di indicizzazione avanzati

Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.  Nella visualizzazione indicizzazione persone di interesse, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.  L'indice ibrido è la posizione in cui l'analisi dei dati (Preview) archivia il contenuto rielaborato.

Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Aggiornamento degli indici avanzati per gli utenti interessati

Quando una persona di interesse viene aggiunta a un'analisi dei dati, tutti gli elementi parzialmente indicizzati vengono rielaborati. Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.  Se necessario, è possibile aggiornare gli indici.

> [!NOTE]
> L'aggiornamento degli indici degli utenti è un processo a esecuzione prolungata. Si consiglia di non aggiornare gli indici più di una volta al giorno in un'indagine.
