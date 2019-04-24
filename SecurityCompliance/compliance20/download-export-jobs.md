---
title: Scaricare processi di esportazione
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
ms.openlocfilehash: 904bc5f8a6d6cef937d55336e8f383957713769a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251910"
---
# <a name="download-export-jobs"></a>Scaricare processi di esportazione

Tutti i dati esportati vengono aggiunti a un BLOB di Microsoft Azure. In questo modo vengono fornite più opzioni per gestire i dati downstream. Sono disponibili diversi modi per accedere a un BLOB di Azure. Un metodo consiste nell'utilizzare Esplora archivi di Azure. Questo metodo supporta la connessione semplice, l'esplorazione e il download. Per ulteriori informazioni, visitare<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer>

1.  Per scaricare il contenuto dopo il completamento di un processo di esportazione, passare alla scheda Esporta e selezionare un processo di esportazione.

2.  Copiare il testo nella sezione "Locations" del riquadro a comparsa.

![](../media/eDiscoExportJob.png)

3.  Aprire Esplora archivi di Azure e fare clic sul pulsante "Connetti"

![](../media/AzureStorageConnect.png)

4.  Selezionare "usa un URI di firma di accesso condiviso" e fare clic su Avanti.

![](../media/AzureStorageConnect2.png)

5.  Incollare il testo percorso nella casella di testo URI e fare clic su Avanti.

![](../media/AzureStorageConnect3.png)

6.  Fare clic su Connetti

![](../media/AzureStorageConnect4.png)

In questo modo verrà aggiunta l'esportazione come oggetto nei contenitori di archiviazione/servizi associati SAS/BLOB. Sarà possibile esplorare l'esportazione e scaricare tutto o parti dell'esportazione.

![](../media/AzureStorageConnect5.png)