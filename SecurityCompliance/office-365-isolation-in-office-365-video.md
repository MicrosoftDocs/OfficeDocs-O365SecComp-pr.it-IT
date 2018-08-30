---
title: Isolamento dei Tenant Office 365 in Video di Office 365
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
description: 'Riepilogo: Informazioni di isolamento tenant di Office 365 Video.'
ms.openlocfilehash: 9476047d56161ec2589fdf743d7ee837ea558865
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531064"
---
# <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video

> [!NOTE]
> Video di Office 365 verrà sostituito da Microsoft Stream. Per ulteriori informazioni sul nuovo servizio di video di organizzazione per l'aggiunta di business intelligence per la collaborazione video e informazioni sui piani di transizione per i clienti di Office 365 Video correnti, vedere [eseguire la migrazione al flusso di Office 365 Video](https://docs.microsoft.com/stream/).

## <a name="introduction"></a>Introduzione
Archiviazione Azure viene utilizzato per archiviare i dati di più servizi di Office 365, tra cui Video di Office 365 e oscillazione. Archiviazione Azure include archiviazione Blob, che corrisponde a un archivio di oggetti altamente scalabile, basato su REST cloud che viene utilizzato per l'archiviazione dei dati non strutturati. Archiviazione Azure utilizza un modello di controllo di accesso semplice. ogni sottoscrizione di Azure è possibile creare uno o più account di archiviazione. Ogni Account di archiviazione con una singola chiave segreta che consente di controllare l'accesso a tutti i dati in tale Account di archiviazione. Questo oggetto supporta lo scenario tipico in cui l'archiviazione è associata alle applicazioni e le applicazioni dispongono del controllo completo dei dati associati; ad esempio Sway archiviando il contenuto in archiviazione Azure. Tutto il contenuto dei clienti per oscillazione viene archiviato in account di un'archiviazione condivisa Azure. Contenuto di ogni utente è in una struttura di directory separata di BLOB in archiviazione Azure.

I sistemi di gestione dell'accesso per gli ambienti clienti (ad esempio, il portale di Azure, SMAPI e così via) sono isolati all'interno di un'applicazione Azure gestita da Microsoft. Ciò logicamente separa l'infrastruttura di accesso clienti dal livello di archiviazione e nelle applicazioni personalizzate.

## <a name="tenant-isolation-in-office-365-video"></a>Isolamento del tenant in Office 365 Video
[Video di Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) è un portale aziendale che fornisce alle organizzazioni con una destinazione esigenze di sicurezza, a livello di organizzazione per la registrazione, condivisione e scoperta del contenuto video. In Office 365 Video video di ogni tenant viene mantenuti isolato e crittografati in tutti i percorsi e sono disponibile solo per gli utenti autenticati che dispongono di accesso e le autorizzazioni per il video dell'organizzazione. Video di Office 365 utilizza una combinazione di tecnologie per ottenere questo risultato:
- SharePoint Online viene utilizzato per l'archiviazione dei metadati (video titolo, descrizione, ecc.) e il file video. Fornisce inoltre il livello di sicurezza e conformità (tra cui autenticazione) e le funzionalità di ricerca.
- Servizi multimediali Azure fornisce transcodifica, flussi adattivi, recapito sicuro (utilizzando la crittografia AES) e funzionalità di anteprima.

[Servizi di Azure Media](https://azure.microsoft.com/services/media-services/) è una piattaforma-as-a-service che offre per l'abilitazione dei flussi di lavoro end-to-end media nel cloud. La piattaforma fornisce un'API REST per il caricamento, codifica, la crittografia (con PlayReady) e il recapito di dati multimediali tramite Data Center Azure tutto il mondo.

Tutti i caricamenti per il Video di Office 365 si verificano tramite HTTPS. Quando viene caricato un file video, viene archiviato in SharePoint Online e una copia del file viene inviata tramite un canale crittografato Azure Media Services. Azure servizi Media transcodifica i dati del video in diversi formati ottimizzati per la visualizzazione di utilizzo (ad esempio, per dispositivi mobili, larghezza di banda ridotta, ampia larghezza di banda e così via). Questi file, insieme ai file originale acquisite durante il caricamento, vengono archiviati in archiviazione Blob di Azure. I file vengono crittografati tramite AES 128 per l'algoritmo di crittografia comuni MPEG della creazione del pacchetto (o una versione precedente di PlayReady) per la riproduzione e crittografate tramite AES 256 crittografia di archiviazione prima di essere memorizzato in archiviazione Blob di Azure. (Utilizzando Azure Media Services Client SDK, i clienti possono controllare quali la crittografia è utilizzata. Ad esempio, un cliente potrebbe applicare Azure Media Services archiviazione la crittografia (AES 256) a una risorsa preziosa media prima del caricamento archiviazione Blob di Azure.)

Servizi di Azure multimediale genera inoltre un'anteprima del video, che trasmette insieme anteprima metadati in SharePoint Online tramite un canale crittografato.
