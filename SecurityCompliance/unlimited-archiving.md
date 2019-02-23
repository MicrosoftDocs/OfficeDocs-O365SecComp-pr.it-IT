---
title: Panoramica dell'archiviazione illimitata in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Informazioni sull'espansione automatica dell'archiviazione in Office 365, che fornisce un archivio di archiviazione illimitato per le cassette postali di Exchange Online.
ms.openlocfilehash: fa1fc2a8b2de577232a50ecb1f89b53d52012096
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223485"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="7b79f-103">Panoramica dell'archiviazione illimitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="7b79f-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="7b79f-p101">In Office 365, le cassette postali di archiviazione offrono agli utenti un ulteriore spazio di archiviazione. Dopo aver abilitato la cassetta postale di archiviazione di un utente, sono disponibili fino a 100 GB di spazio di archiviazione aggiuntivo. Quando viene raggiunta la quota di archiviazione di 100 GB, le organizzazioni devono contattare Microsoft per richiedere ulteriore spazio di archiviazione per una cassetta postale di archiviazione. Questo non è più il caso. La nuova funzionalità di archiviazione illimitata in Office 365 (chiamata *archiviazione in espansione automatica*) fornisce una quantità illimitata di spazio di archiviazione nelle cassette postali di archiviazione. A questo punto, quando viene raggiunta la quota di archiviazione nella cassetta postale di archivio, Office 365 aumenta automaticamente le dimensioni dell'archivio, il che significa che gli utenti non finiscono nello spazio di archiviazione delle cassette postali e gli amministratori non dovranno richiedere l'archiviazione aggiuntiva per le cassette postali di archiviazione .</span><span class="sxs-lookup"><span data-stu-id="7b79f-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="7b79f-110">Per istruzioni dettagliate per l'attivazione dell'archiviazione in espansione automatica, vedere Enable Unlimited [Archiving in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7b79f-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b79f-p102">L'archiviazione in espansione automatica supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="7b79f-113">Funzionamento dell'archiviazione con espansione automatica</span><span class="sxs-lookup"><span data-stu-id="7b79f-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="7b79f-p103">Come spiegato in precedenza, viene creato ulteriore spazio di archiviazione delle cassette postali quando la cassetta postale di archiviazione di un utente è abilitata. Quando l'archiviazione in espansione automatica è abilitata, Office 365 verifica periodicamente le dimensioni della cassetta postale di archiviazione. Quando una cassetta postale di archiviazione viene vicina al suo limite di memoria, Office 365 crea automaticamente ulteriore spazio di archiviazione per l'archivio. Se l'utente si esaurisce da questo spazio di archiviazione aggiuntivo, Office 365 aggiunge ulteriore spazio di archiviazione all'archivio dell'utente. Questo processo si verifica automaticamente, il che significa che gli amministratori non devono richiedere ulteriore archivio di archiviazione o gestire l'archiviazione con espansione automatica.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="7b79f-119">Ecco una breve panoramica del processo.</span><span class="sxs-lookup"><span data-stu-id="7b79f-119">Here's a quick overview of the process.</span></span>
  
![Panoramica del processo di archiviazione in espansione automatica](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="7b79f-p104">L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di memorizzazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="7b79f-p105">Un amministratore consente di abilitare l'espansione automatica dell'archiviazione per la cassetta postale. Successivamente, quando la cassetta postale di archiviazione (inclusa la cartella elementi ripristinabili) raggiunge 90 GB, viene convertita in un archivio in espansione automatica e Office 365 aggiunge lo spazio di archiviazione all'archivio. Tenere presente che possono essere necessari fino a 30 giorni per il provisioning dello spazio di archiviazione aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="7b79f-126">Office 365 aggiunge automaticamente ulteriore spazio di archiviazione all'archivio, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7b79f-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7b79f-p106">Se una cassetta postale viene conservata o assegnata a un criterio di conservazione di Office 365, la quota di archiviazione per l'archivio Maibox viene aumentata a 110 GB quando l'archiviazione in espansione automatica è abilitata. Analogamente, la quota di avviso per l'archiviazione viene aumentata a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="7b79f-129">Cosa viene spostato nello spazio di archiviazione aggiuntivo dell'archivio?</span><span class="sxs-lookup"><span data-stu-id="7b79f-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="7b79f-p107">Per utilizzare in modo efficiente l'archiviazione di un archivio automatico, è possibile che le cartelle vengano spostate. Office 365 determina quali cartelle vengono spostate quando viene aggiunta un'ulteriore archiviazione all'archivio. Quando una cartella viene spostata, viene creata automaticamente una sottocartella nella cartella originale nella parte relativa all'archivio dell'elenco delle cartelle in Outlook. Questa nuova sottocartella punta agli elementi che sono stati spostati. la convenzione di denominazione utilizzata da Office 365 per assegnare un nome alla cartella è \*\* \<il nome\>della cartella _yyyy (creato in mmm gg, yyyy h_mm)\*\*, dove:</span><span class="sxs-lookup"><span data-stu-id="7b79f-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="7b79f-135">**yyyy** è l'anno in cui sono stati ricevuti i messaggi nella cartella.</span><span class="sxs-lookup"><span data-stu-id="7b79f-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="7b79f-136">**mmm gg, yyyy h_m** è la data e l'ora in cui la sottocartella è stata creata da Office 365, in formato UTC, in base al fuso orario e alle impostazioni internazionali dell'utente in Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b79f-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="7b79f-137">Nelle schermate seguenti viene visualizzato un elenco di cartelle prima e dopo che i messaggi vengono spostati in un archivio con espansione automatica.</span><span class="sxs-lookup"><span data-stu-id="7b79f-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="7b79f-138">**Prima dell'aggiunta dell'archiviazione aggiuntiva**</span><span class="sxs-lookup"><span data-stu-id="7b79f-138">**Before additional storage is added**</span></span>
  
![Elenco delle cartelle della cassetta postale di archiviazione prima del provisioning dell'archivio con espansione automatica](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="7b79f-140">**Dopo l'aggiunta dell'archiviazione aggiuntiva**</span><span class="sxs-lookup"><span data-stu-id="7b79f-140">**After additional storage is added**</span></span>
  
![Elenco delle cartelle della cassetta postale di archiviazione dopo il provisioning dell'archivio con espansione automatica](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="7b79f-142">Requisiti di Outlook per l'accesso agli elementi in un archivio con espansione automatica</span><span class="sxs-lookup"><span data-stu-id="7b79f-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="7b79f-143">Per accedere ai messaggi archiviati in un archivio con espansione automatica, è necessario che gli utenti utilizzino uno dei client Outlook seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b79f-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="7b79f-144">Outlook 2016 o Outlook 2019 per Windows</span><span class="sxs-lookup"><span data-stu-id="7b79f-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="7b79f-145">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="7b79f-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="7b79f-146">Outlook 2016 o Outlook 2019 per Mac</span><span class="sxs-lookup"><span data-stu-id="7b79f-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7b79f-p108">Gli utenti di Outlook 2013 possono accedere solo agli elementi archiviati in origine nella cassetta postale di archiviazione. Non saranno in grado di accedere agli elementi spostati in un archivio di archiviazione aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="7b79f-149">Di seguito sono riportate alcune considerazioni da prendere in considerazione quando si utilizza Outlook o Outlook sul Web per accedere ai messaggi archiviati in un archivio con espansione automatica.</span><span class="sxs-lookup"><span data-stu-id="7b79f-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="7b79f-150">È possibile accedere a qualsiasi cartella nella cassetta postale di archiviazione, incluse quelle che sono state spostate nell'area di archiviazione espansa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7b79f-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="7b79f-p109">È possibile cercare gli elementi spostati in un'area di archiviazione aggiuntiva solo eseguendo una ricerca nella cartella stessa. Questo significa che è necessario selezionare la cartella di archiviazione nell'elenco delle cartelle per selezionare l'opzione **cartella corrente** come ambito di ricerca. Analogamente, se una cartella in un'area di archiviazione espansa automaticamente contiene sottocartelle, è necessario eseguire la ricerca separatamente in ogni sottocartella.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="7b79f-154">I conteggi degli elementi in Outlook e i conteggi di lettura/non lettura (in Outlook e Outlook sul Web) in un archivio con espansione automatica potrebbero non essere accurati.</span><span class="sxs-lookup"><span data-stu-id="7b79f-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="7b79f-155">È possibile eliminare gli elementi in una sottocartella che punta a un'area di archiviazione espansa automaticamente, ma la cartella stessa non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="7b79f-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="7b79f-156">Non è possibile utilizzare la funzionalità Recupera elementi eliminati per recuperare un elemento che è stato eliminato da un'area di archiviazione espansa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7b79f-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="7b79f-157">Archiviazione in espansione automatica e altre funzionalità di conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="7b79f-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="7b79f-158">In questa sezione viene illustrata la funzionalità tra l'archiviazione in espansione automatica e altre funzionalità di conformità e governance dei dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b79f-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="7b79f-159">**eDiscovery** -quando si utilizza uno strumento di eDiscovery di Office 365, ad esempio la ricerca di contenuto o eDiscovery sul posto, vengono cercate anche le aree di archiviazione aggiuntive in un archivio con espansione automatica.</span><span class="sxs-lookup"><span data-stu-id="7b79f-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="7b79f-160">**Conservazione** : quando si attiva il blocco di una cassetta postale utilizzando strumenti come il blocco per controversia legale in Exchange Online o eDiscovery e i criteri di conservazione nel centro conformità & sicurezza di Office 365, il contenuto presente in un archivio auto-espanso è anche posto in attesa.</span><span class="sxs-lookup"><span data-stu-id="7b79f-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security & Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="7b79f-161">**Gestione record di messaggistica** -se si utilizzano i criteri di eliminazione dei messaggi di posta elettronica in Exchange Online per eliminare definitivamente gli elementi della cassetta postale scaduta, verranno eliminati anche gli elementi scaduti che si trovano nell'archivio auto-espanso.</span><span class="sxs-lookup"><span data-stu-id="7b79f-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="7b79f-p110">**Import Service** -è possibile utilizzare il servizio di importazione di Office 365 per importare i file PST nell'archivio automatico espanso di un utente. È possibile importare fino a 100 GB di dati da file PST nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7b79f-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7b79f-164">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7b79f-164">More information</span></span>

<span data-ttu-id="7b79f-165">Per ulteriori informazioni tecniche sull'archiviazione in espansione automatica, vedere [Office 365: auto-expandIng Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span><span class="sxs-lookup"><span data-stu-id="7b79f-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>