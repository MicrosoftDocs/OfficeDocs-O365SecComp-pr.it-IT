---
title: Scaricare processi di esportazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155148"
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