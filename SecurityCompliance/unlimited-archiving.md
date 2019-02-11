---
title: Panoramica di archiviazione illimitato in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Informazioni sull'espansione automatica archiviazione in Office 365, che fornisce un numero illimitato di archiviazione per le cassette postali di Exchange Online.
ms.openlocfilehash: 83eb49b3f2a7da418b61e509f44023809ed396c3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740818"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Panoramica di archiviazione illimitato in Office 365

In Office 365, cassette postali di archiviazione offrono agli utenti con lo spazio di archiviazione aggiuntivi delle cassette postali. Dopo la cassetta postale di archivio dell'utente è abilitata, fino a 100 GB di spazio di archiviazione aggiuntivo è disponibile. Quando viene raggiunto la quota di archiviazione di 100 GB, le organizzazioni hanno dovuto contatta Microsoft per richiesta ulteriore spazio di archiviazione per una cassetta postale di archivio. Che non è più il caso. La nuova funzionalità di archiviazione illimitata in Office 365 (denominato *espansione automatica di archiviazione*) offre una quantità di spazio di archiviazione di cassette postali di archiviazione illimitata. A questo punto, quando viene raggiunto la quota di archiviazione nella cassetta postale di archiviazione, Office 365 automaticamente aumenta la dimensione dell'archivio, il che significa che gli utenti non si esaurisca lo spazio di archiviazione delle cassette postali e gli amministratori non sarà necessario richiedere ulteriore spazio di archiviazione per cassette postali di archiviazione .
  
Per istruzioni dettagliate per l'attivazione di espansione automatica di archiviazione, vedere [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).
  
> [!NOTE]
> L'espansione automatica archiviazione inoltre supporta le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online. 
  
## <a name="how-auto-expanding-archiving-works"></a>Funzionamento dell'archiviazione l'espansione automatica

Come indicata in precedenza, altre cassette postali spazio di archiviazione viene creato quando è abilitata la cassetta postale di archivio dell'utente. Quando è abilitata l'espansione automatica di archiviazione, Office 365 controlla periodicamente le dimensioni della cassetta postale di archivio. Quando una cassetta postale di archivio Ottiene raggiungere il limite di archiviazione, Office 365 crea automaticamente ulteriore spazio di archiviazione per l'archivio. Se l'utente è in esecuzione da questo ulteriore spazio di archiviazione, Office 365 aggiunto uno spazio di archiviazione per l'archivio dell'utente. Questo processo viene eseguita automaticamente, che indica che gli amministratori non sono necessario richiedere ulteriori archiviazione o gestire l'espansione automatica di archiviazione. 
  
Ecco una rapida panoramica del processo.
  
![Panoramica del processo di archiviazione espansione automatica](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di archiviazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.
    
2. Un amministratore consente l'espansione automatica di archiviazione per la cassetta postale. Quindi, quando la cassetta postale di archiviazione (inclusi la cartella elementi ripristinabili) raggiunge 90 GB, viene convertito in un archivio per l'espansione automatica e Office 365 consente di aggiungere spazio di archiviazione nell'archivio. Si noti che potrebbero essere necessari fino a 30 giorni per lo spazio di archiviazione aggiuntiva effettuare il provisioning.
    
3. Office 365 aggiunge automaticamente uno spazio di archiviazione nell'archivio quando necessario.
  
> [!IMPORTANT]
> Se una cassetta postale viene messa in attesa o assegnata a un criterio di conservazione di Office 365, la quota di archiviazione per le cassette postali di archiviazione viene aumentata a 110 GB quando è abilitata l'espansione automatica archiviazione. Analogamente, la quota di avviso viene aumentata a 100 GB.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Che cosa viene spostato per lo spazio di archiviazione di archiviazione aggiuntivo?

Per un utilizzo efficace di espansione automatica di archiviazione, potrebbero ottenere spostare le cartelle. Office 365 determina quali cartelle è state spostate quando si aggiunge ulteriore spazio di archiviazione nell'archivio. Quando una cartella viene spostata, viene automaticamente creata una sottocartella della cartella originale nella parte archive dell'elenco delle cartelle in Outlook. Questa nuova sottocartella punta a elementi che sono stati spostati. È la convenzione di denominazione utilizzati da Office 365 per specificare nome della cartella ** \<nome della cartella\>_yyyy (creati in mmm gg, aaaa h_mm)**, dove: 
  
- **yyyy** è l'anno che sono stati ricevuti messaggi nella cartella. 
    
- **mmm gg, aaaa h_m** è la data e ora in cui la sottocartella è stata creata da Office 365, in formato UTC, basato sul fuso orario dell'utente e le impostazioni internazionali in Outlook. 
    
Catture di schermata seguente mostra un elenco delle cartelle prima e dopo che i messaggi vengono spostati in un archivio espanse automaticamente.
  
 **Prima dell'aggiunta di spazio di archiviazione aggiuntivo**
  
![Elenco delle cartelle della cassetta postale di archiviazione prima di espansione automatica archive viene effettuato il provisioning](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **Dopo l'aggiunta di spazio di archiviazione aggiuntivo**
  
![Elenco delle cartelle della cassetta postale di archiviazione dopo l'espansione automatica archive viene effettuato il provisioning](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisiti di Outlook per accedere agli elementi in un archivio espanse automaticamente

Per accedere ai messaggi che vengono archiviati in un archivio espanse automaticamente, gli utenti devono utilizzare uno dei seguenti client di Outlook:
  
- 2016 Outlook o Outlook 2019 per Windows
    
- Outlook sul web 
    
- Outlook 2016 o 2019 Outlook per Mac 
    
> [!NOTE]
> Gli utenti di Outlook 2013 possono accedere solo agli elementi che sono stati memorizzati in origine nella cassetta postale di archivio. Non saranno in grado di accedere agli elementi che viene spostate in archiviazione aggiuntive. 
  
Ecco alcuni aspetti da considerare quando si utilizza Outlook o Outlook sul web di accesso ai messaggi archiviati in un archivio espanse automaticamente.
  
- È possibile accedere a qualsiasi cartella nella cassetta postale di archivio, comprese quelle che sono stati spostati per l'area di archiviazione automatica espansa.
    
- È possibile cercare gli elementi che sono stati spostati in un'area di spazio di archiviazione aggiuntivo solo per la ricerca a tali cartelle. Ciò significa che è necessario selezionare la cartella di archivio nell'elenco delle cartelle per selezionare l'opzione **Cartella corrente** come ambito di ricerca. Analogamente, se una cartella in un'area di archiviazione automatica espansa contiene sottocartelle, è necessario cercare ogni sottocartella separatamente. 
    
- I conteggi degli articoli in Outlook e il numero di lettura/Unread (in Outlook e Outlook sul web) in un archivio espanse automaticamente potrebbe non essere preciso.
    
- È possibile eliminare gli elementi in una sottocartella che punta a un'area di archiviazione espanse automaticamente, ma non è possibile eliminare tali cartelle.
    
- È possibile utilizzare la caratteristica Recupera elementi eliminati per recuperare un elemento che è stato eliminato da un'area di archiviazione automatica espansa.
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>L'espansione automatica di archiviazione e altre funzionalità di conformità di Office 365

In questa sezione viene illustrata la funzionalità tra l'espansione automatica di archiviazione e altri conformità di Office 365 e caratteristiche di governance dei dati.
  
- vengono cercati anche **eDiscovery** - quando si utilizza uno strumento di eDiscovery di Office 365, ad esempio ricerca contenuto o In-Place eDiscovery, le aree di ulteriore spazio di archiviazione in un archivio espanse automaticamente.
    
- **Conservazione** - quando si posiziona una cassetta postale di archiviazione utilizzando gli strumenti, ad esempio conservazione per controversia legale in Exchange Online o eDiscovery case contiene e criteri di conservazione in & la protezione di Office 365 centro conformità, contenuto presente in un archivio espanso automatico è anche messa in attesa.
    
- **Messaging records management (MRM)** - se si utilizzano criteri di eliminazione di gestione record di messaggistica in Exchange Online per eliminare definitivamente gli elementi scaduti cassetta postale, disponibile nell'archivio espanse automaticamente gli elementi scaduti saranno eliminate.
    
- **Importare servizio** - è possibile utilizzare il servizio Office 365 importare per importare i file PST archivio espanso automatica dell'utente. È possibile importare fino a 100 GB di dati dal file PST alla cassetta postale di archivio dell'utente. 

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni tecniche sull'espansione automatica archiviazione, vedere [Office 365: domande frequenti sugli archivi espansione automatica](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).