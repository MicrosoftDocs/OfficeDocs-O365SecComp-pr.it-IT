---
title: Eliminare gli elementi nella cartella elementi recuperabili di cassette postali basate su cloud in attesa - della Guida di amministrazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Per gli amministratori: eliminare gli elementi nella cartella elementi recuperabili di un utente di una cassetta postale di Exchange Online, anche se tale cassetta postale viene messa in attesa legale. Si tratta in modo efficace per eliminare i dati che sono stata inavvertitamente passati in Office 365.'
ms.openlocfilehash: 0519e389f05ed9952090fb9b163a05d18e3bd762
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23014030"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="ea871-104">Eliminare gli elementi nella cartella elementi recuperabili di cassette postali basate su cloud in attesa - della Guida di amministrazione</span><span class="sxs-lookup"><span data-stu-id="ea871-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="ea871-p102">Per proteggere da eliminazioni accidentali o intenzionali è presente la cartella elementi recuperabili per una cassetta postale di Exchange Online. Viene inoltre utilizzato per archiviare gli elementi vengono mantenuti e accedono dalla funzionalità di conformità di Office 365, ad esempio eDiscovery e conservazioni ricerche. In alcune situazioni, tuttavia, le organizzazioni potrebbero essere dati che sono stati mantenuti inavvertitamente nella cartella elementi ripristinabili è necessario eliminare. Ad esempio, un utente involontariamente inviare o di inoltrare un messaggio di posta elettronica contenente informazioni che possono avere conseguenze gravi business o informazioni riservate. Anche se il messaggio viene eliminato definitivamente, potrebbe essere conservato per un tempo indefinito perché una conservazione a fini giudiziari è stato inserito nella cassetta postale. In questo scenario è noto come perdita di dati in quanto i dati sono stati inavvertitamente passati in Office 365. In questi casi, è possibile eliminare elementi nella cartella elementi recuperabili di un utente per una cassetta postale di Exchange Online, anche se tale cassetta postale viene messa in attesa con una delle funzionalità di attesa diverse in Office 365. Questi tipi di conservazioni includono controversia contiene, archiviazioni sul posto, esenzioni eDiscovery e criteri di conservazione di Office 365 creati in Office 365 Security &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="ea871-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="ea871-p103">In questo articolo viene illustrato come eliminare gli elementi dalla cartella elementi recuperabili per le cassette postali basate su cloud che in attesa. Questa procedura, è necessario disabilitare l'accesso alla cassetta postale e disattivazione ripristino di singoli elementi, disabilitare l'Assistente cartelle gestite dall'elaborazione della cassetta postale, rimuovere temporaneamente la conservazione, eliminazione di elementi dalla cartella elementi recuperabili e quindi il ripristino la cassetta postale per la configurazione precedente. Di seguito è il processo:</span><span class="sxs-lookup"><span data-stu-id="ea871-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="ea871-116">Passaggio 1: Raccolta delle informazioni sulla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="ea871-117">Passaggio 2: Preparare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="ea871-118">Passaggio 3: Rimuovere tutte le esenzioni dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="ea871-119">Passaggio 4: Eliminare gli elementi nella cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="ea871-119">Step 4: Delete items in the Recoverable Items folder</span></span>](#step-4-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="ea871-120">Passaggio 5: Ripristinare la cassetta postale allo stato precedente</span><span class="sxs-lookup"><span data-stu-id="ea871-120">Step 5: Revert the mailbox to its previous state</span></span>](#step-5-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="ea871-p104">Le procedure descritte in questo articolo genera dati vengono eliminati definitivamente dalla cassetta postale di Exchange Online. Significa che i messaggi eliminati dalla cartella elementi ripristinabili non possono essere recuperati e non saranno disponibili per esibizione o per altri motivi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che viene messa in attesa come parte di una conservazione per controversia legale, archiviazione sul posto, tenere premuto eDiscovery oppure il criterio di conservazione di Office 365 creato in Office 365 Security &amp; centro conformità, controllo con la gestione dei record o legale reparti prima della rimozione dell'esenzione. L'organizzazione potrebbe disporre di un criterio che definisce se una cassetta postale in attesa o un problema di perdita dei dati ha la priorità.</span><span class="sxs-lookup"><span data-stu-id="ea871-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ea871-125">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="ea871-125">Before you begin</span></span>

- <span data-ttu-id="ea871-126">È necessario assegnare entrambi i seguenti ruoli di gestione di Exchange Online per cercare ed eliminare messaggi dalla cartella elementi ripristinabili nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ea871-126">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 4.</span></span>
    
  - <span data-ttu-id="ea871-p105">**Cassetta postale di ricerca** - questo ruolo consente di cercare cassette postali nell'organizzazione. Gli amministratori di Exchange non sono assegnati al ruolo per impostazione predefinita. Per assegnare questo ruolo, aggiungere l'utente come membro del gruppo di ruoli gestione individuazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea871-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="ea871-p106">**Cassetta postale di importazione ed esportazione** : questo ruolo consente di eliminare i messaggi dalla cassetta postale dell'utente. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruolo. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea871-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="ea871-p107">La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Ciò avviene perché non è possibile applicare nuovamente una conservazione o criteri di conservazione di Office 365, a una cassetta postale inattiva dopo la rimozione. Quando si rimuove un'esenzione da una cassetta postale inattiva, viene modificato in una normale cassetta postale eliminata e verranno eliminato definitivamente dall'organizzazione dopo che viene elaborato dall'Assistente cartelle gestite.</span><span class="sxs-lookup"><span data-stu-id="ea871-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="ea871-p108">È possibile eseguire questa procedura per una cassetta postale che è stata assegnata un criterio di conservazione di Office 365 è stata bloccata con un blocco di conservazione. Ciò avviene perché un blocco di conservazione impedisce la rimozione o ad eccezione della cassetta postale dal criterio di conservazione di Office 365 e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sul blocco di criteri di conservazione, vedere [il blocco di un criterio di conservazione](retention-policies.md#locking-a-retention-policy).</span><span class="sxs-lookup"><span data-stu-id="ea871-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="ea871-p109">Se una cassetta postale non viene messa in attesa o non dispone di individuazione di singoli elementi, è sufficiente eliminare gli elementi dalla cartella elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere [cercare ed eliminare i messaggi ](https://go.microsoft.com/fwlink/?linkid=852453).</span><span class="sxs-lookup"><span data-stu-id="ea871-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="ea871-141">Passaggio 1: Raccolta delle informazioni sulla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-141">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="ea871-p110">Il primo passaggio consiste nel raggruppare le proprietà selezionate dalla cassetta postale di destinazione che incide questa procedura. Assicurarsi di prendere nota di queste impostazioni o li si salva un file di testo poiché sarà modificare alcune di queste proprietà e quindi ripristinare i valori originali nel passaggio 5, dopo l'eliminazione degli elementi dalla cartella elementi ripristinabili. Ecco un elenco di proprietà della cassetta postale che è necessario raccogliere.</span><span class="sxs-lookup"><span data-stu-id="ea871-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 5, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="ea871-145">*SingleItemRecoveryEnabled* e *RetainDeletedItemsFor* ; Se necessario, si verrà disattivare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ea871-145">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="ea871-p111">*LitigationHoldEnabled* e *InPlaceHolds* ; è necessario identificare tutte le esenzioni inserite nella cassetta postale in modo che è possibile rimuovere temporaneamente nel passaggio 3. Vedere la sezione [informazioni](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) per suggerimenti su come identificare la conservazione di tipo che può essere messa in una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="ea871-p112">Inoltre, è necessario ottenere la cassetta postale di impostazioni di accesso client in modo che è possibile disattivare temporaneamente essi in modo che il proprietario (o altri utenti) non possono accedere alla cassetta postale durante la procedura. Infine, è possibile ottenere le dimensioni correnti e il numero di elementi nella cartella elementi ripristinabili. Dopo l'eliminazione degli elementi nella cartella elementi ripristinabili nel passaggio 4, si utilizzerà queste informazioni per verificare che gli elementi sono state effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="ea871-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 4, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="ea871-p113">[Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e password di un account amministratore che è stato assegnato i ruoli di gestione appropriati in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea871-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="ea871-153">Eseguire il comando seguente per ottenere informazioni sul ripristino di singoli elementi e il periodo di mantenimento elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="ea871-153">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="ea871-p114">Se il ripristino di singoli elementi è attivato, è necessario disabilitare nel passaggio 2. Se non viene impostato il periodo di mantenimento elementi eliminati per 30 giorni (il valore massimo in Exchange Online), quindi è possibile aumentare nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ea871-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="ea871-156">Eseguire il comando seguente per ottenere le impostazioni di accesso per la cassetta postale della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-156">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="ea871-157">Si verrà disabilitare tutti questi metodi di accesso nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ea871-157">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="ea871-158">Eseguire il comando seguente per ottenere informazioni sulle esenzioni e Office 365 i criteri di conservazione applicati alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-158">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="ea871-159">Se non esistono troppi valori nella proprietà *InPlaceHolds* e non tutti gli elementi visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore in una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="ea871-159">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="ea871-160">Eseguire il comando seguente per ottenere informazioni su eventuali criteri di conservazione a livello di organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea871-160">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="ea871-161">Se l'organizzazione dispone di eventuali criteri di conservazione a livello di organizzazione Office 365, è necessario escludere la cassetta postale da questi criteri nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ea871-161">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="ea871-162">Se non esistono troppi valori nella proprietà *InPlaceHolds* e non tutti gli elementi visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore in una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="ea871-162">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="ea871-163">Eseguire il comando seguente per ottenere le dimensioni corrente e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea871-163">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="ea871-164">Se è abilitata cassetta postale di archivio dell'utente, eseguire il comando seguente per ottenere le dimensioni e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale di archivio.</span><span class="sxs-lookup"><span data-stu-id="ea871-164">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="ea871-p115">Quando si eliminano elementi nel passaggio 4, è possibile scegliere di eliminare o non eliminare elementi contenuti nella cartella elementi ripristinabili nella cassetta postale di archivio principale dell'utente. Si noti che se l'espansione automatica di archiviazione è abilitata per la cassetta postale, gli elementi in una cassetta postale di archivio ausiliaria non vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="ea871-p115">When you delete items in Step 4, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="ea871-167">Passaggio 2: Preparare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-167">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="ea871-168">Dopo aver raccolto e il salvataggio delle informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea871-168">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="ea871-169">**Disabilitare l'accesso client alla cassetta postale** in modo che il proprietario della cassetta postale non può accedere alle cassette postali e apportare le modifiche ai dati delle cassette postali durante la procedura.</span><span class="sxs-lookup"><span data-stu-id="ea871-169">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="ea871-170">**Aumentare il periodo di mantenimento elementi eliminati** a 30 giorni (il valore massimo in Exchange Online) in modo che gli elementi non vengono cancellati dalla cartella elementi recuperabili prima di eliminarli nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ea871-170">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 4.</span></span> 
    
- <span data-ttu-id="ea871-171">**Disattivazione ripristino di un singolo elemento** in modo che gli elementi non verrà mantenuto (per la durata del periodo di mantenimento elementi eliminati) che sono state eliminate dalla cartella elementi ripristinabili nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ea871-171">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 4.</span></span> 
    
- <span data-ttu-id="ea871-172">**Disattivare l'Assistente cartelle gestite** in modo che non elaborare la cassetta postale e conservazione degli elementi eliminati nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ea871-172">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 4.</span></span> 
    
<span data-ttu-id="ea871-173">Eseguire la procedura seguente in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea871-173">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="ea871-p116">Eseguire il seguente comando per disabilitare tutti i client l'accesso alla cassetta postale. La sintassi del comando si presuppone che tutti i metodi di accesso client siano stati abilitati per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="ea871-p117">Potrebbero richiedere fino a 60 minuti per disabilitare tutti i metodi di accesso client per la cassetta postale. Si noti che la disattivazione di questi metodi di accesso non disconnettere proprietario della cassetta postale che attualmente effettuati l'accesso. Se il proprietario non viene eseguito l'accesso, quindi non saranno in grado di accedere alla cassetta postale dopo che questi metodi di accesso sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="ea871-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="ea871-p118">Eseguire il comando seguente per aumentare il numero massimo di 30 giorni del periodo di mantenimento elementi eliminati. Si presuppone che l'impostazione corrente è minore di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea871-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="ea871-181">Eseguire il seguente comando per disabilitare il ripristino di un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="ea871-181">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="ea871-p119">Potrebbero richiedere fino a 60 minuti per disattivare il ripristino di un singolo elemento. Non eliminare gli elementi nella cartella elementi ripristinabili fino questo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="ea871-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="ea871-p120">Eseguire il comando seguente per impedire l'Assistente cartelle gestite di elaborazione della cassetta postale. Come indicato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se un criterio di conservazione di Office 365 con un blocco di conservazione non viene applicato alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="ea871-186">Passaggio 3: Rimuovere tutte le esenzioni dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="ea871-186">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="ea871-p121">L'ultimo passaggio prima che è possibile eliminare gli elementi dalla cartella elementi ripristinabili è per rimuovere tutte le esenzioni (identificato nel passaggio 1) inserite nella cassetta postale. Tutte le esenzioni devono essere eliminate in modo che non verranno mantenuti gli elementi che sono state eliminate dalla cartella elementi ripristinabili. Nelle sezioni seguenti contengono informazioni sulla rimozione di diversi tipi di conservazioni su una cassetta postale. Vedere la sezione [informazioni](#more-information) per suggerimenti su come identificare la conservazione di tipo che può essere messa in una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="ea871-191">Come descritto in precedenza, verificare con la gestione dei record o reparti legali prima di rimuovere un'esenzione da una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-191">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="ea871-192">Conservazione in caso di dispute</span><span class="sxs-lookup"><span data-stu-id="ea871-192">Litigation Hold</span></span>
  
<span data-ttu-id="ea871-193">Eseguire il seguente comando in Exchange Online PowerShell per rimuovere una conservazione per controversia legale dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-193">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="ea871-p122">Equivale a disattivare i metodi di accesso client e il ripristino di un singolo elemento, può richiedere fino a 60 minuti per rimuovere la conservazione per controversia legale. Non eliminare elementi dalla cartella elementi ripristinabili fino questo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="ea871-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="ea871-196">Blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="ea871-196">In-Place Hold</span></span>
  
<span data-ttu-id="ea871-p123">Eseguire il seguente comando in Exchange Online PowerShell per identificare l'archiviazione sul posto che viene inserito nella cassetta postale. Utilizzare il GUID per l'archiviazione sul posto identificato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea871-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="ea871-p124">Dopo aver identificato In-Place Hold, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span><span class="sxs-lookup"><span data-stu-id="ea871-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="ea871-201">Office 365 applicati criteri di conservazione cassette postali specifiche</span><span class="sxs-lookup"><span data-stu-id="ea871-201">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="ea871-p125">Eseguire il comando seguente in [protezione di Office 365 &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare il criterio di conservazione di Office 365 applicato alla cassetta postale. Utilizzare il GUID (escluso il `mbx` o `skp` prefisso) per il criterio di conservazione identificato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea871-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="ea871-204">Dopo aver identificato i criteri di conservazione, passare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione identificato nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ea871-204">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="ea871-205">Criteri di conservazione a livello di organizzazione Office 365</span><span class="sxs-lookup"><span data-stu-id="ea871-205">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="ea871-p126">Livello di organizzazione e i criteri di conservazione Exchange livello Office 365 vengono applicati a tutte le cassette postali nell'organizzazione. Vengono applicati a livello di organizzazione (non il livello delle cassette postali) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Eseguire il comando seguente in [protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione a livello di organizzazione Office 365. Utilizzare il GUID (escluso il `mbx` prefisso) per i criteri di conservazione a livello di organizzazione identificato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea871-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="ea871-p127">Dopo aver identificato i criteri di conservazione a livello di organizzazione Office 365, passare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare ogni criterio di conservazione in tutta l'organizzazione è definito il precedente passaggio e aggiungere la cassetta postale per l'elenco dei destinatari esclusi. In questo modo verrà rimosso cassetta postale dell'utente dal criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ea871-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 
  
 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="ea871-212">contiene i casi eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ea871-212">eDiscovery case holds</span></span>
  
<span data-ttu-id="ea871-p128">Eseguire i seguenti comandi [protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare la conservazione associata a un caso eDiscovery applicato alla cassetta postale. Utilizzare il GUID (escluso il `UniH` prefisso) per eDiscovery attesa identificato nel passaggio 1. Si noti che il secondo comando viene visualizzato il nome del caso eDiscovery che esenzione associata; il terzo comando viene visualizzato il nome dell'esenzione.</span><span class="sxs-lookup"><span data-stu-id="ea871-p128">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="ea871-p129">Dopo aver identificato il nome del caso eDiscovery e conservazione, passare al **ricerca &amp; indagini** \> pagina **eDiscovery** la protezione &amp; centro conformità, aprire il caso e rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [gestione dei casi di eDiscovery in Office 365 Security &amp; centro conformità](manage-ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="ea871-p129">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="ea871-218">Passaggio 4: Eliminare gli elementi nella cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="ea871-218">Step 4: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="ea871-p130">A questo punto si è pronti per eliminare gli elementi nella cartella elementi ripristinabili effettivamente utilizzando il cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) in Exchange Online PowerShell. Sono disponibili tre opzioni quando si esegue il cmdlet **Search-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="ea871-p130">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="ea871-221">Copiare gli elementi in una cassetta postale di destinazione prima di eliminarli in modo che è possibile esaminare gli elementi, se necessario, prima di eliminarli.</span><span class="sxs-lookup"><span data-stu-id="ea871-221">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="ea871-222">Copiare gli elementi in una cassetta postale di destinazione ed eliminarle nello stesso comando.</span><span class="sxs-lookup"><span data-stu-id="ea871-222">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="ea871-223">Eliminare gli elementi senza vengono copiati in una cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ea871-223">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="ea871-p131">Si noti che gli elementi nella cartella elementi ripristinabili nella cassetta postale di archivio principale dell'utente verranno eliminati anche quando si esegue il * * Search-Mailbox * * cmdlet. Per evitare questo problema, è possibile includere l'opzione *DoNotIncludeArchive* . E come descritto in precedenza, se l'archiviazione l'espansione automatica è abilitata per la cassetta postale di * * Search-Mailbox * * cmdlet non elementi eliminati in una cassetta postale di archivio ausiliaria. Per ulteriori informazioni sull'espansione automatica archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ea871-p131">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the ** Search-Mailbox ** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the ** Search-Mailbox ** cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea871-p132">Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="ea871-p132">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="ea871-p133">Nell'esempio seguente mostra la sintassi dei comandi per ognuna di queste opzioni. Utilizzano questi esempi di `-SearchQuery size>0` valore del parametro, che elimina tutti gli elementi da tutte le sottocartelle nella cartella elementi ripristinabili. Se si desidera eliminare solo gli elementi che soddisfano le condizioni specifiche, è possibile utilizzare anche il parametro *SearchQuery* consente di specificare altre condizioni, ad esempio l'oggetto di un messaggio o un intervallo di date. Vedere gli [altri esempi di utilizzo del parametro SearchQuery](#other-examples-of-using-the-searchquery-parameter) riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="ea871-p133">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="ea871-234">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ea871-234">Example 1</span></span>

<span data-ttu-id="ea871-p134">In questo esempio copia tutti gli elementi nella cartella elementi ripristinabili dell'utente in una cartella di cassetta postale di individuazione dell'organizzazione. Consente di controllare gli elementi prima di eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="ea871-p134">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="ea871-p135">Nell'esempio precedente, non è necessario copiare gli elementi per la cassetta postale di individuazione. È possibile copiare i messaggi a qualsiasi cassetta postale di destinazione. Tuttavia, per impedire l'accesso ai dati delle cassette postali riservate, è consigliabile copiare messaggi in una cassetta postale che dispone dell'accesso limitato per il personale autorizzato. Per impostazione predefinita, l'accesso per la cassetta postale di individuazione predefinita è limitato ai membri del gruppo di ruoli gestione individuazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea871-p135">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="ea871-241">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ea871-241">Example 2</span></span>

<span data-ttu-id="ea871-242">In questo esempio copia tutti gli elementi nella cartella elementi ripristinabili dell'utente in una cartella nella cassetta postale di individuazione dell'organizzazione e quindi Elimina gli elementi dalla cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea871-242">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="ea871-243">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="ea871-243">Example 3</span></span>

<span data-ttu-id="ea871-244">In questo esempio consente di eliminare tutti gli elementi nella cartella elementi ripristinabili dell'utente, senza copiarli una cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ea871-244">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="ea871-245">Altri esempi di utilizzo del parametro SearchQuery</span><span class="sxs-lookup"><span data-stu-id="ea871-245">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="ea871-p136">Di seguito sono forniti alcuni esempi dell'utilizzo del parametro *SearchQuery* per individuare i messaggi specifici. Se si utilizza il parametro *SearchQuery* consente di eseguire ricerche per gli elementi specifici, è consigliabile copiare i risultati della ricerca per una cassetta postale di destinazione in modo che sia possibile esaminare i risultati della ricerca e quindi modificare la query se necessario prima di eliminare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea871-p136">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="ea871-248">In questo esempio restituisce i messaggi che contengono una frase specifica nel campo oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea871-248">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="ea871-249">In questo esempio restituisce i messaggi inviati all'interno dell'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="ea871-249">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="ea871-250">In questo esempio restituisce i messaggi inviati alla persona specificata.</span><span class="sxs-lookup"><span data-stu-id="ea871-250">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="ea871-251">Verificare che gli elementi sono stati eliminati</span><span class="sxs-lookup"><span data-stu-id="ea871-251">Verify that items were deleted</span></span>

<span data-ttu-id="ea871-p137">Per verificare che è stato eliminato elementi dalla cartella elementi recuperabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** di Exchange Online PowerShell per controllare le dimensioni e numero di elementi nella cartella elementi recuperabili. È possibile confrontare le statistiche con quelle che raccolte nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea871-p137">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="ea871-254">Eseguire il comando seguente in per ottenere le dimensioni corrente e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea871-254">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="ea871-255">Eseguire il comando seguente per ottenere le dimensioni e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale di archivio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea871-255">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-5-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="ea871-256">Passaggio 5: Ripristinare la cassetta postale allo stato precedente</span><span class="sxs-lookup"><span data-stu-id="ea871-256">Step 5: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="ea871-p138">Il passaggio finale consiste nel ripristinare la cassetta postale torna alla configurazione precedente. Ciò significa reimpostazione le proprietà modificate nel passaggio 2 e la riapplicazione esenzioni rimosso nel passaggio 3. Includono:</span><span class="sxs-lookup"><span data-stu-id="ea871-p138">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="ea871-p139">Modifica del periodo di mantenimento elementi eliminati sul valore precedente. In alternativa, è possibile lasciare questa impostazione per 30 giorni, il valore massimo di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea871-p139">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="ea871-262">Riabilitazione di ripristino di un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="ea871-262">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="ea871-263">Riabilitazione di metodi di accesso client in modo che il proprietario può accedere alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-263">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="ea871-264">Riapplicazione le esenzioni e i criteri di conservazione Office 365 che sia stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="ea871-264">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="ea871-265">Riabilitazione Assistente cartelle gestite per elaborare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-265">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ea871-266">È consigliabile attendere 24 ore dopo la riapplicazione un'esenzione o Office 365 retention policy (e verifica sul posto) prima che si riabilita l'Assistente cartelle gestite per elaborare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-266">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="ea871-267">Eseguire la procedura seguente (nella sequenza specificata) in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea871-267">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="ea871-p140">Esegui il comando seguente per modificare il periodo di mantenimento elementi eliminati eseguire il valore originale. Si presuppone che l'impostazione precedente è minore di 30 giorni. ad esempio 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea871-p140">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="ea871-270">Eseguire il comando seguente per abilitare di nuovo il ripristino di un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="ea871-270">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="ea871-271">Eseguire il comando seguente per abilitare di nuovo tutti i metodi di accesso client per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-271">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="ea871-p141">Riapplicare le conservazioni rimosso nel passaggio 3. A seconda del tipo di attesa, utilizzare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="ea871-p141">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="ea871-274">**Conservazione in caso di dispute**</span><span class="sxs-lookup"><span data-stu-id="ea871-274">**Litigation Hold**</span></span>
    
    <span data-ttu-id="ea871-275">Eseguire il comando seguente per abilitare di nuovo un conservazione per controversia legale per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-275">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="ea871-276">**Conservazione in locale**</span><span class="sxs-lookup"><span data-stu-id="ea871-276">**In-Place Hold**</span></span>
    
    <span data-ttu-id="ea871-277">Utilizzare EAC (o Exchange Online PowerShell) per aggiungere la cassetta postale In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="ea871-277">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="ea871-278">**Office 365 applicati criteri di conservazione cassette postali specifiche**</span><span class="sxs-lookup"><span data-stu-id="ea871-278">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="ea871-p142">Utilizzare la protezione &amp; centro conformità per aggiungere la cassetta postale il criterio di conservazione di Office 365. Andare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione e aggiungere la cassetta postale all'elenco dei destinatari che viene applicato il criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ea871-p142">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="ea871-281">**Criteri di conservazione a livello di organizzazione Office 365**</span><span class="sxs-lookup"><span data-stu-id="ea871-281">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="ea871-p143">Se è stato rimosso un livello di organizzazione o un criterio di conservazione di Exchange a livello escludendo dal criterio, quindi utilizzare la protezione &amp; centro conformità per rimuovere la cassetta postale dall'elenco di escludere gli utenti. Andare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione a livello di organizzazione e rimuovere la cassetta postale dall'elenco dei destinatari esclusi. In questo modo applicherà nuovamente il criterio di conservazione cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea871-p143">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="ea871-285">**contiene i casi eDiscovery**</span><span class="sxs-lookup"><span data-stu-id="ea871-285">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="ea871-p144">Utilizzare la protezione &amp; centro conformità per aggiungere la cassetta postale di eseguire il backup dell'esenzione associata a un caso eDiscovery. Visitare il **ricerca &amp; indagini** \> pagina **eDiscovery** la protezione &amp; centro conformità, aprire il caso e aggiungere la cassetta postale dell'esenzione.</span><span class="sxs-lookup"><span data-stu-id="ea871-p144">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="ea871-p145">Eseguire il comando seguente per consentire l'Assistente cartelle gestite di elaborare nuovamente la cassetta postale. Come affermato in precedenza, è consigliabile attendere 24 ore dopo la riapplicazione un'esenzione o Office 365 retention policy (e verifica sul posto) prima che si riabilita l'Assistente cartelle gestite.</span><span class="sxs-lookup"><span data-stu-id="ea871-p145">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="ea871-290">Per verificare che la cassetta postale è stata ripristinata nuovamente la configurazione precedente, è possibile eseguire i comandi seguenti e quindi confrontare le impostazioni di quelle raccolte nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea871-290">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="ea871-291">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ea871-291">More information</span></span>

<span data-ttu-id="ea871-p146">Di seguito è riportata una tabella in cui viene illustrato come identificare i diversi tipi di conservazioni in base ai valori nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox** o **Get-OrganizationConfig** . Come precedentemente illustrato, è necessario rimuovere tutte le esenzioni e criteri di conservazione di Office 365 da una cassetta postale prima correttamente possono eliminare gli elementi nella cartella elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="ea871-p146">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="ea871-294">**Tipo di blocco**</span><span class="sxs-lookup"><span data-stu-id="ea871-294">**Hold type**</span></span>|<span data-ttu-id="ea871-295">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="ea871-295">**Example value**</span></span>|<span data-ttu-id="ea871-296">**Come identificare la conservazione**</span><span class="sxs-lookup"><span data-stu-id="ea871-296">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea871-297">Blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="ea871-297">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="ea871-298">La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.</span><span class="sxs-lookup"><span data-stu-id="ea871-298">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="ea871-299">Blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="ea871-299">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="ea871-p147">La proprietà *InPlaceHolds* contiene il GUID In-Place Hold che viene inserito nella cassetta postale. È possibile stabilire che ciò avviene an In-Place Hold perché il GUID non inizia con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="ea871-p147">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="ea871-302">È possibile utilizzare il comando  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span><span class="sxs-lookup"><span data-stu-id="ea871-302">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="ea871-303">FL' comando in Exchange Online PowerShell per ottenere informazioni sull'archiviazione sul posto nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-303">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="ea871-304">Criteri di conservazione di Office 365 in sicurezza &amp; centro conformità applicate a determinate cassette postali</span><span class="sxs-lookup"><span data-stu-id="ea871-304">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="ea871-305">oppure</span><span class="sxs-lookup"><span data-stu-id="ea871-305">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="ea871-p148">Quando si esegue il cmdlet **Get-Mailbox** , la proprietà *InPlaceHolds* contiene inoltre i GUID di Office 365 i criteri di conservazione applicati alla cassetta postale. È possibile identificare i criteri di conservazione in quanto il GUID inizia con la `mbx` prefisso. Si noti che se il GUID del criterio di conservazione inizia con la `skp` prefisso, che indica che viene applicato il criterio di conservazione Skype per le conversazioni di Business.</span><span class="sxs-lookup"><span data-stu-id="ea871-p148">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="ea871-309">Al criterio di conservazione identità Office 365 applicato alla cassetta postale, eseguire il comando seguente in sicurezza &amp; PowerShell centro conformità:</span><span class="sxs-lookup"><span data-stu-id="ea871-309">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/><span data-ttu-id="ea871-310">"Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="ea871-310">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="ea871-311">Nome FL`<br/><br/>Be sure to remove the  `mbx` or  `skp' quando si esegue questo comando.</span><span class="sxs-lookup"><span data-stu-id="ea871-311">FL Name`<br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="ea871-312">Criteri di conservazione a livello di organizzazione Office 365 in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="ea871-312">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="ea871-313">Nessun valore</span><span class="sxs-lookup"><span data-stu-id="ea871-313">No value</span></span>  <br/> <span data-ttu-id="ea871-314">oppure</span><span class="sxs-lookup"><span data-stu-id="ea871-314">or</span></span>  <br/>  <span data-ttu-id="ea871-315">`-mbxe9b52bf7ab3b46a286308ecb29624696`(indica che la cassetta postale è escluso da un criterio a livello di organizzazione)</span><span class="sxs-lookup"><span data-stu-id="ea871-315">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="ea871-316">Anche se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , ancora potrebbero verificarsi uno o più a livello di organizzazione Office 365 criteri di conservazione applicati alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ea871-316">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="ea871-317">Per verificare questa impostazione, è possibile eseguire il "Get-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="ea871-317">To verify this, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="ea871-318">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="ea871-318">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="ea871-319">Nome FL`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `mbx -`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696'</span><span class="sxs-lookup"><span data-stu-id="ea871-319">FL Name`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696\`</span></span> <br/> |
|<span data-ttu-id="ea871-320">caso di eDiscovery attesa nella protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="ea871-320">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="ea871-p149">La proprietà *InPlaceHolds* contiene anche il GUID di qualsiasi sospensione associata a un caso eDiscovery in sicurezza &amp; centro conformità che può essere messa sulla cassetta postale. È possibile sapere si tratta di un'esenzione casi di eDiscovery in quanto il GUID inizia con la `UniH` prefisso.</span><span class="sxs-lookup"><span data-stu-id="ea871-p149">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="ea871-p150">È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in sicurezza &amp; PowerShell centro conformità per ottenere informazioni relative al caso eDiscovery esenzione sulla cassetta postale associata. Ad esempio, è possibile eseguire il comando "Get-CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="ea871-p150">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="ea871-325">Nome FL` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`$CaseHold.CaseId Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="ea871-325">FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="ea871-326">Nome FL'</span><span class="sxs-lookup"><span data-stu-id="ea871-326">FL Name\`</span></span>


