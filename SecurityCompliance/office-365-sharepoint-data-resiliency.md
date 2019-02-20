---
title: Resilienza dei dati di Office 365 SharePoint
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Panoramica della resilienza dei dati in SharePoint online in Office 365.
ms.openlocfilehash: c550cb6572cb71b53cd544af64339129f72b888f
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090888"
---
# <a name="sharepoint-online-data-resiliency"></a>Resilienza dei dati di SharePoint Online
Un principio fondamentale per SharePoint Online consiste nel non avere mai una singola copia di qualsiasi elemento di dati. SharePoint Online utilizza la replica di SQL Server, che è un insieme di tecnologie per la copia e la distribuzione di dati e oggetti di database da un database a un altro e quindi la sincronizzazione tra i database per mantenere la coerenza. 

Ad esempio, quando un utente salva un file in SharePoint Online, il file viene suddiviso in blocchi, crittografato e archiviato all'interno di archiviazione BLOB di Azure. Azure Blob Service fornisce meccanismi per garantire l'integrità dei dati sia a livello dell'applicazione che dei livelli di trasporto. Questo post dettaglierà questi meccanismi dal punto di vista del servizio e del client. Il controllo MD5 è facoltativo nelle operazioni PUT e GET. Tuttavia, fornisce una funzione di convenienza per garantire l'integrità dei dati in rete quando si utilizza HTTP. Inoltre, poiché HTTPS fornisce la sicurezza del layer di trasporto, non è necessario il controllo MD5 aggiuntivo durante la connessione su HTTPS come sarebbe ridondante. Azure Blob Service fornisce un supporto di archiviazione durevole e utilizza la verifica dell'integrità per i dati archiviati. Le MD5's utilizzate quando si interagisce con un'applicazione vengono fornite per controllare l'integrità dei dati quando si trasferiscono tali dati tra l'applicazione e il servizio tramite HTTP. 

Per garantire l'integrità dei dati, il servizio Azure BLOB utilizza hash MD5 dei dati in un paio di modi diversi. È importante comprendere in che modo questi valori vengono calcolati, trasmessi, archiviati e infine applicati per progettare adeguatamente l'applicazione per utilizzarli per fornire l'integrità dei dati. Per ulteriori informazioni, vedere [Panoramica di Windows Azure BLOB MD5](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx). 

I metadati e i puntatori al file vengono archiviati in un database di SQL Server (il database del contenuto). Tutti i blocchi – file, pezzi di file e Delta di aggiornamento – sono archiviati come BLOB nell'archiviazione di Azure che vengono distribuiti in modo casuale su più account di archiviazione di Azure. Il database SQL è ospitato in un array di archiviazione RAID 10 che è sincronizzato in modo sincrono con un altro array di archiviazione RAID 10 in un rack separato all'interno dello stesso datacenter. Il log shipping asincrono viene quindi utilizzato per replicare i dati in un altro array di archiviazione RAID 10 in un secondo datacenter. Oltre a proteggere i dati con RAID 10 e la replica sincrona e asincrona, vengono eseguiti i backup dei dati pianificati, che vengono replicati in modo asincrono nel secondo datacenter. 

In SharePoint Online, i backup dei dati vengono eseguiti ogni 12 ore e conservati per 14 giorni. SharePoint Online utilizza anche un sistema di standby caldo che include i datacenter separati geograficamente associati all'interno della stessa area del percorso dati del cliente, ad esempio Chicago e San Antonio per i clienti che hanno eseguito il provisioning del tenant negli Stati Uniti. configurata come attiva/attiva. Ad esempio, esistono utenti Live che dispongono di Chicago come datacenter principale e San Antonio come datacenter di failover e gli utenti di Live che dispongono di San Antonio come datacenter principale e Chicago come datacenter di failover. 