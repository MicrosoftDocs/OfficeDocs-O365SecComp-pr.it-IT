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
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="7f430-103">Panoramica di archiviazione illimitato in Office 365</span><span class="sxs-lookup"><span data-stu-id="7f430-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="7f430-p101">In Office 365, cassette postali di archiviazione offrono agli utenti con lo spazio di archiviazione aggiuntivi delle cassette postali. Dopo la cassetta postale di archivio dell'utente è abilitata, fino a 100 GB di spazio di archiviazione aggiuntivo è disponibile. Quando viene raggiunto la quota di archiviazione di 100 GB, le organizzazioni hanno dovuto contatta Microsoft per richiesta ulteriore spazio di archiviazione per una cassetta postale di archivio. Che non è più il caso. La nuova funzionalità di archiviazione illimitata in Office 365 (denominato *espansione automatica di archiviazione*) offre una quantità di spazio di archiviazione di cassette postali di archiviazione illimitata. A questo punto, quando viene raggiunto la quota di archiviazione nella cassetta postale di archiviazione, Office 365 automaticamente aumenta la dimensione dell'archivio, il che significa che gli utenti non si esaurisca lo spazio di archiviazione delle cassette postali e gli amministratori non sarà necessario richiedere ulteriore spazio di archiviazione per cassette postali di archiviazione .</span><span class="sxs-lookup"><span data-stu-id="7f430-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="7f430-110">Per istruzioni dettagliate per l'attivazione di espansione automatica di archiviazione, vedere [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7f430-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f430-p102">L'espansione automatica archiviazione inoltre supporta le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f430-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="7f430-113">Funzionamento dell'archiviazione l'espansione automatica</span><span class="sxs-lookup"><span data-stu-id="7f430-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="7f430-p103">Come indicata in precedenza, altre cassette postali spazio di archiviazione viene creato quando è abilitata la cassetta postale di archivio dell'utente. Quando è abilitata l'espansione automatica di archiviazione, Office 365 controlla periodicamente le dimensioni della cassetta postale di archivio. Quando una cassetta postale di archivio Ottiene raggiungere il limite di archiviazione, Office 365 crea automaticamente ulteriore spazio di archiviazione per l'archivio. Se l'utente è in esecuzione da questo ulteriore spazio di archiviazione, Office 365 aggiunto uno spazio di archiviazione per l'archivio dell'utente. Questo processo viene eseguita automaticamente, che indica che gli amministratori non sono necessario richiedere ulteriori archiviazione o gestire l'espansione automatica di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7f430-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="7f430-119">Ecco una rapida panoramica del processo.</span><span class="sxs-lookup"><span data-stu-id="7f430-119">Here's a quick overview of the process.</span></span>
  
![Panoramica del processo di archiviazione espansione automatica](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="7f430-p104">L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di archiviazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.</span><span class="sxs-lookup"><span data-stu-id="7f430-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="7f430-p105">Un amministratore consente l'espansione automatica di archiviazione per la cassetta postale. Quindi, quando la cassetta postale di archiviazione (inclusi la cartella elementi ripristinabili) raggiunge 90 GB, viene convertito in un archivio per l'espansione automatica e Office 365 consente di aggiungere spazio di archiviazione nell'archivio. Si noti che potrebbero essere necessari fino a 30 giorni per lo spazio di archiviazione aggiuntiva effettuare il provisioning.</span><span class="sxs-lookup"><span data-stu-id="7f430-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="7f430-126">Office 365 aggiunge automaticamente uno spazio di archiviazione nell'archivio quando necessario.</span><span class="sxs-lookup"><span data-stu-id="7f430-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f430-p106">Se una cassetta postale viene messa in attesa o assegnata a un criterio di conservazione di Office 365, la quota di archiviazione per le cassette postali di archiviazione viene aumentata a 110 GB quando è abilitata l'espansione automatica archiviazione. Analogamente, la quota di avviso viene aumentata a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="7f430-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="7f430-129">Che cosa viene spostato per lo spazio di archiviazione di archiviazione aggiuntivo?</span><span class="sxs-lookup"><span data-stu-id="7f430-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="7f430-p107">Per un utilizzo efficace di espansione automatica di archiviazione, potrebbero ottenere spostare le cartelle. Office 365 determina quali cartelle è state spostate quando si aggiunge ulteriore spazio di archiviazione nell'archivio. Quando una cartella viene spostata, viene automaticamente creata una sottocartella della cartella originale nella parte archive dell'elenco delle cartelle in Outlook. Questa nuova sottocartella punta a elementi che sono stati spostati. È la convenzione di denominazione utilizzati da Office 365 per specificare nome della cartella \*\* \<nome della cartella\>_yyyy (creati in mmm gg, aaaa h_mm)\*\*, dove:</span><span class="sxs-lookup"><span data-stu-id="7f430-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="7f430-135">**yyyy** è l'anno che sono stati ricevuti messaggi nella cartella.</span><span class="sxs-lookup"><span data-stu-id="7f430-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="7f430-136">**mmm gg, aaaa h_m** è la data e ora in cui la sottocartella è stata creata da Office 365, in formato UTC, basato sul fuso orario dell'utente e le impostazioni internazionali in Outlook.</span><span class="sxs-lookup"><span data-stu-id="7f430-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="7f430-137">Catture di schermata seguente mostra un elenco delle cartelle prima e dopo che i messaggi vengono spostati in un archivio espanse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f430-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="7f430-138">**Prima dell'aggiunta di spazio di archiviazione aggiuntivo**</span><span class="sxs-lookup"><span data-stu-id="7f430-138">**Before additional storage is added**</span></span>
  
![Elenco delle cartelle della cassetta postale di archiviazione prima di espansione automatica archive viene effettuato il provisioning](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="7f430-140">**Dopo l'aggiunta di spazio di archiviazione aggiuntivo**</span><span class="sxs-lookup"><span data-stu-id="7f430-140">**After additional storage is added**</span></span>
  
![Elenco delle cartelle della cassetta postale di archiviazione dopo l'espansione automatica archive viene effettuato il provisioning](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="7f430-142">Requisiti di Outlook per accedere agli elementi in un archivio espanse automaticamente</span><span class="sxs-lookup"><span data-stu-id="7f430-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="7f430-143">Per accedere ai messaggi che vengono archiviati in un archivio espanse automaticamente, gli utenti devono utilizzare uno dei seguenti client di Outlook:</span><span class="sxs-lookup"><span data-stu-id="7f430-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="7f430-144">2016 Outlook o Outlook 2019 per Windows</span><span class="sxs-lookup"><span data-stu-id="7f430-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="7f430-145">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="7f430-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="7f430-146">Outlook 2016 o 2019 Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="7f430-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7f430-p108">Gli utenti di Outlook 2013 possono accedere solo agli elementi che sono stati memorizzati in origine nella cassetta postale di archivio. Non saranno in grado di accedere agli elementi che viene spostate in archiviazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7f430-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="7f430-149">Ecco alcuni aspetti da considerare quando si utilizza Outlook o Outlook sul web di accesso ai messaggi archiviati in un archivio espanse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f430-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="7f430-150">È possibile accedere a qualsiasi cartella nella cassetta postale di archivio, comprese quelle che sono stati spostati per l'area di archiviazione automatica espansa.</span><span class="sxs-lookup"><span data-stu-id="7f430-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="7f430-p109">È possibile cercare gli elementi che sono stati spostati in un'area di spazio di archiviazione aggiuntivo solo per la ricerca a tali cartelle. Ciò significa che è necessario selezionare la cartella di archivio nell'elenco delle cartelle per selezionare l'opzione **Cartella corrente** come ambito di ricerca. Analogamente, se una cartella in un'area di archiviazione automatica espansa contiene sottocartelle, è necessario cercare ogni sottocartella separatamente.</span><span class="sxs-lookup"><span data-stu-id="7f430-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="7f430-154">I conteggi degli articoli in Outlook e il numero di lettura/Unread (in Outlook e Outlook sul web) in un archivio espanse automaticamente potrebbe non essere preciso.</span><span class="sxs-lookup"><span data-stu-id="7f430-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="7f430-155">È possibile eliminare gli elementi in una sottocartella che punta a un'area di archiviazione espanse automaticamente, ma non è possibile eliminare tali cartelle.</span><span class="sxs-lookup"><span data-stu-id="7f430-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="7f430-156">È possibile utilizzare la caratteristica Recupera elementi eliminati per recuperare un elemento che è stato eliminato da un'area di archiviazione automatica espansa.</span><span class="sxs-lookup"><span data-stu-id="7f430-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="7f430-157">L'espansione automatica di archiviazione e altre funzionalità di conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="7f430-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="7f430-158">In questa sezione viene illustrata la funzionalità tra l'espansione automatica di archiviazione e altri conformità di Office 365 e caratteristiche di governance dei dati.</span><span class="sxs-lookup"><span data-stu-id="7f430-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="7f430-159">vengono cercati anche **eDiscovery** - quando si utilizza uno strumento di eDiscovery di Office 365, ad esempio ricerca contenuto o In-Place eDiscovery, le aree di ulteriore spazio di archiviazione in un archivio espanse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f430-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="7f430-160">**Conservazione** - quando si posiziona una cassetta postale di archiviazione utilizzando gli strumenti, ad esempio conservazione per controversia legale in Exchange Online o eDiscovery case contiene e criteri di conservazione in & la protezione di Office 365 centro conformità, contenuto presente in un archivio espanso automatico è anche messa in attesa.</span><span class="sxs-lookup"><span data-stu-id="7f430-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security & Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="7f430-161">**Messaging records management (MRM)** - se si utilizzano criteri di eliminazione di gestione record di messaggistica in Exchange Online per eliminare definitivamente gli elementi scaduti cassetta postale, disponibile nell'archivio espanse automaticamente gli elementi scaduti saranno eliminate.</span><span class="sxs-lookup"><span data-stu-id="7f430-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="7f430-p110">**Importare servizio** - è possibile utilizzare il servizio Office 365 importare per importare i file PST archivio espanso automatica dell'utente. È possibile importare fino a 100 GB di dati dal file PST alla cassetta postale di archivio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7f430-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7f430-164">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7f430-164">More information</span></span>

<span data-ttu-id="7f430-165">Per ulteriori informazioni tecniche sull'espansione automatica archiviazione, vedere [Office 365: domande frequenti sugli archivi espansione automatica](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span><span class="sxs-lookup"><span data-stu-id="7f430-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>