---
title: Note sulla versione di dati indagini (Preview) in Microsoft 365
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
description: In questo articolo viene descritta la nuova versione di eDiscovery avanzate (Preview) in Microsoft 365.
ms.openlocfilehash: bcf10f5154723709b1cde761b0e8d02540341a26
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636625"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Note sulla versione di dati indagini (Preview) in Microsoft 365

È possibile utilizzare il nuovo strumento dati indagini (Preview) in Microsoft 365 esaminare, analizzare e correggere i dati correlati risolte, ad esempio un problema di perdita di dati o un'indagine interna. Indagini pubblica anteprima dei dati viene fornita anticipati accesso alle caratteristiche e degli aggiornamenti futuri. Per ottenere accesso anticipato per le funzionalità più recenti, creare un nuovo indagini in indagini dati (Preview) in & la protezione di Office 365 centro conformità. Per ulteriori informazioni, vedere [gestione di un evento imprevisto perdita di dati in Microsoft 365](manage-data-spillage-incidents.md).

## <a name="whats-new"></a>Novità 

- **Indagini** - è possibile raggruppare le ricerche e risolte mediante la creazione di un'analisi. Gestire le indagini chi può accedere tramite l'aggiunta o rimozione di membri.  È anche possibile selezionare e contrassegnare le indagini preferite. Tenere traccia e monitorare l'attività all'interno di indagini utilizzando nuovi dashboard. Dopo aver completato l'analisi, è possibile chiudere o eliminarlo.

- **Utenti di interesse** -quando si aggiungono utenti a indagini come utenti di interesse, è possibile visualizzare le cassette postali, OneDrive for Business account e i siti Teams Microsoft. È possibile utilizzarli per definire l'ambito le ricerche di contenuto indagine. Per ulteriori informazioni su una persona di interesse, è inoltre possibile visualizzare i record correlati all'attività in Office 365 e altri servizi Microsoft di controllo.

- **Ricerche** – crea una ricerca a livello di organizzazione tramite varie funzionalità di ricerca condizione. Se si conoscono gli utenti o i siti che si desidera eseguire la ricerca, è possibile eseguire questa operazione aggiunta degli utenti come utenti di interesse o posizioni di siti specificati nella creazione guidata di ricerca. 

- **Risolte** -creare un nuovo incidente e aggiungere i risultati di ricerca che si desidera controllare. Può controllare i singoli documenti, annotare per lasciare note indagini ed esportare i risultati per spostare in un ambiente diverso. 

- **Esaminare** – utilizzo a nativo, testo e quasi nativo visualizzazione per esaminare i documenti aggiunti a un problema. È inoltre possibile applicare analitica ai documenti di raggruppare gli elementi duplicati, thread di posta elettronica e temi, che consentono di semplificare la revisione del problema. 

- **Redact contrassegna e aggiungere note** – redigi testo, applicare i tag e creare delle annotazioni come leggere i documenti.
  
- **Indicizzazione complete** – se sono presenti elementi indicizzati parzialmente, saranno nuovamente indicizzati su richiesta in modo che tutti i dati saranno disponibili per la ricerca.

- **Risoluzione dei problemi errore** – Remediate o download di elaborazione degli errori. È previsto il supporto di risoluzione dei problemi per i tipi di file di grandi dimensioni, i file e altri problemi relativi a errori di indicizzazione protetti da password. 

- **I processi** : lo stato di avanzamento di processi a esecuzione prolungata.

- **Elementi delle cassette postali rigido-delete** - nelle situazioni urgenti, potrebbe essere necessario eliminare definitivamente gli elementi non posizionato correttamente. A tale scopo, è possibile eseguire il **ComplianceSearchAction New-eliminare - PurgeType HardDelete** command in sicurezza & PowerShell centro conformità per rimuovere definitivamente gli elementi dalle cassette postali. Per ulteriori informazioni, vedere [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).
