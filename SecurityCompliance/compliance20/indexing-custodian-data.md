---
title: Indicizzazione di dati depositaria avanzata
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 158af8acf4acdb8ad6650c377a23b44ed28c6f54
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607876"
---
# <a name="advanced-indexing-of-custodian-data"></a>Indicizzazione di dati depositaria avanzata

Quando un depositaria viene aggiunto a un caso eDiscovery avanzate (anteprima), qualsiasi contenuto in Office 365 che considerati come parzialmente indicizzato è rielaborata affinché sia possibile eseguire ricerche.  Questo processo viene chiamato *indicizzazione avanzata*. Contenuto può essere indicizzati parzialmente per diversi motivi, tra cui l'esistenza di immagini, tipi di file non supportati o quando si verificano indicizzazione limiti della dimensione dei file.  Per ulteriori informazioni sugli elementi indicizzati parzialmente, vedere [parzialmente indicizzato gli elementi della funzionalità di ricerca del contenuto in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).

## <a name="viewing-advanced-indexing-results"></a>Visualizzazione dei risultati di indicizzazione avanzati

Dopo aver completato il processo di indicizzazione avanzato, è possibile ottenere una conoscenza dell'efficacia di effettuare l'elaborazione.  Nella visualizzazione depositaria indicizzazione nel grafico Elenca tutti gli elementi aggiunti all' *indice ibrida*.  L'indice ibrido è dove eDiscovery avanzate (Preview) viene memorizzato il contenuto rielaborato.

Il grafico include inoltre il numero di elementi che richiedono la risoluzione dei problemi e un altro grafico degli errori per tipo di file. Per ulteriori informazioni, vedere [risoluzione dei problemi di errore durante l'elaborazione dei dati](error-remediation.md).

## <a name="updating-advanced-indexes-for-custodians"></a>Aggiornamento degli indici avanzati per depositari

Quando un depositaria viene aggiunto a un caso eDiscovery avanzate (anteprima), tutti gli elementi indicizzati parzialmente vengono nuovamente elaborati. Tuttavia, come specificato, elementi indicizzati più parzialmente possono essere aggiunti al cassetta postale dell'utente o account OneDrive.  Se necessario, è possibile aggiornare gli indici.

> [!NOTE]
> Aggiornamento degli indici depositaria è un processo di esecuzione prolungata. È consigliabile non aggiornare gli indici più volte al giorno in un caso.
