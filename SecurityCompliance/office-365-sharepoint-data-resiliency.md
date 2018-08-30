---
title: Resilienza dei dati di SharePoint di Office 365
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
description: Panoramica di resilienza dei dati in SharePoint Online in Office 365.
ms.openlocfilehash: ba6259e8e582a4abcf0f184b162177119a57718f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530801"
---
# <a name="sharepoint-online-data-resiliency"></a>Resilienza dei dati in linea di SharePoint
Un principio chiave per SharePoint Online è mai avere una sola copia di qualsiasi tipo di dati. SharePoint Online utilizza la replica di SQL Server, che corrisponde a un insieme di tecnologie per la copia e la distribuzione dei dati e oggetti di database da un database a un altro e quindi la sincronizzazione dei database per garantire la coerenza. 

Ad esempio, quando un utente salva un file in SharePoint Online, il file è suddivisione in blocchi, crittografato e archiviato all'interno di archiviazione Blob di Azure. Servizio Blob Azure fornisce i meccanismi per garantire l'integrità dei dati sia livello di applicazione e trasporto. In questo post verrà descritte questi meccanismi dal punto di vista client e di servizio. Il controllo MD5 è facoltativo per le operazioni PUT sia GET; Tuttavia, ma fornisce funzionalità comodità per garantire l'integrità dei dati tra la rete quando si utilizza HTTP. Inoltre, poiché HTTPS fornisce transport layer security aggiuntive MD5 verifica non è necessario durante la connessione tramite HTTPS come ridondante. Azure Blob servizio fornisce un supporto di memorizzazione permanente e utilizza il proprio integrità verificare i dati memorizzati. Vengono fornite le MD5 utilizzati quando si interagisce con un'applicazione per la verifica dell'integrità dei dati per il trasferimento dei dati tra l'applicazione e il servizio tramite HTTP. 

Per garantire l'integrità dei dati Blob Azure servizio utilizza gli hash MD5 dei dati in due modi diversi. È importante comprendere come questi valori sono calcolati, trasmesse, archiviati e infine applicati per progettare correttamente l'applicazione di utilizzarli per garantire l'integrità dei dati. Per ulteriori informazioni, vedere [Panoramica MD5 Blob di Windows Azure](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx). 

I metadati e i puntatori a file vengono archiviati in un database di SQL Server (il database del contenuto). Tutti i blocchi – i file, tipi di file e aggiornamento delta – archiviati come BLOB in Azure di archiviazione in modo casuale distribuiti in più account di archiviazione Azure. Il database di SQL è ospitato in un array di archiviazione RAID 10 che viene utilizzato il mirroring sincrono a un altro array di archiviazione RAID 10 in un rack separato in stesso Data Center. La distribuzione dei log asincrona viene quindi utilizzato per replicare i dati in un altro array di archiviazione RAID 10 in un secondo Data Center. Oltre a proteggere i dati con RAID 10 e la replica sincrona e asincrona, backup pianificato dei dati vengono indirizzati a cui vengono replicati anche in modo asincrono al secondo centro dati. 

In SharePoint Online, backup dei dati vengono eseguite ogni 12 ore e mantenuto 14 giorni. SharePoint Online utilizza anche un sistema hot standby che include accoppiati centri dati geograficamente separata all'interno della stessa cliente dati percorso regione (ad esempio, Chicago ed Ezio nome alternativo del soggetto per i clienti che hanno eseguito il provisioning i tenant negli Stati Uniti) configurato come attivo/attivo. Esistono, ad esempio, gli utenti live includere Chicago come datacenter principale ed Ezio San come un Data Center di failover e live utenti che dispongono di nome alternativo del soggetto Ezio come datacenter principale e Chicago come i Data Center di failover. 