---
title: Eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa-Guida per l'amministratore
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Per gli amministratori: eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa legale. Si tratta di un modo efficace per eliminare i dati che sono stati accidentalmente riversati in Office 365.'
ms.openlocfilehash: 4b7b12b33a2364d76b5d7dab6c7e94dc8f00d151
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296179"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="0c55d-104">Eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa-Guida per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="0c55d-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="0c55d-p102">La cartella elementi ripristinabili per una cassetta postale di Exchange Online esiste per proteggere da eliminazioni accidentali o dannose. Viene inoltre utilizzato per archiviare gli elementi conservati e accessibili dalle funzionalità di conformità di Office 365, ad esempio le ricerche di eDiscovery e le esenzioni. Tuttavia, in alcune situazioni le organizzazioni potrebbero avere dati che sono stati inavvertitamente conservati nella cartella elementi ripristinabili che devono essere eliminati. Ad esempio, un utente potrebbe inconsapevolmente inviare o inoltrare un messaggio di posta elettronica contenente informazioni riservate o informazioni che potrebbero avere gravi conseguenze per le aziende. Anche se il messaggio è stato eliminato definitivamente, potrebbe essere conservato per un periodo di tempo indefinito perché nella cassetta postale è stata inserita una conservazione legale. Questo scenario è noto come versamento dei dati poiché i dati sono stati inavvertitamente riversati in Office 365. In questi casi, è possibile eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa con una delle diverse funzionalità di archiviazione di Office 365. Questi tipi di esenzioni includono la conservazione per controversia legale, le esenzioni sul posto, le esenzioni eDiscovery e i criteri di mantenimento &amp; di Office 365 creati nel centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="0c55d-p103">In questo articolo viene illustrato come eliminare gli elementi dalla cartella elementi ripristinabili per le cassette postali basate sul cloud che sono in attesa. Questa procedura comporta la disattivazione dell'accesso alla cassetta postale e la disabilitazione del ripristino di un singolo elemento, la disattivazione dell'Assistente cartelle gestite dall'elaborazione della cassetta postale, la rimozione temporanea del blocco, l'eliminazione degli elementi dalla cartella elementi ripristinabili e il ripristino la cassetta postale alla configurazione precedente. Ecco il processo:</span><span class="sxs-lookup"><span data-stu-id="0c55d-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="0c55d-116">Passaggio 1: raccogliere informazioni sulla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="0c55d-117">Passaggio 2: preparare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="0c55d-118">Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="0c55d-119">Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="0c55d-120">Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="0c55d-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="0c55d-121">Passaggio 6: ripristinare lo stato precedente della cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="0c55d-p104">Le procedure descritte in questo articolo determinano l'eliminazione definitiva (eliminata) dei dati da una cassetta postale di Exchange Online. Questo significa che i messaggi eliminati dalla cartella elementi ripristinabili non possono essere recuperati e non saranno disponibili per la ricerca legale o per altri scopi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che viene mantenuta come parte di un blocco per controversia legale, archiviazione sul posto, blocco di eDiscovery o criteri di conservazione di Office 365 creati nel centro &amp; sicurezza e conformità di Office 365, consultare la sezione gestione dei record o legale reparti prima di rimuovere il blocco. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un evento di perdita dei dati ha la priorità.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="0c55d-126">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="0c55d-126">Before you begin</span></span>

- <span data-ttu-id="0c55d-127">È necessario essere assegnati entrambi i ruoli di gestione seguenti in Exchange Online per cercare ed eliminare i messaggi dalla cartella elementi ripristinabili nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="0c55d-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="0c55d-p105">**Ricerca cassette** postali-questo ruolo consente di effettuare ricerche nelle cassette postali dell'organizzazione. Per impostazione predefinita, gli amministratori di Exchange non sono assegnati a questo ruolo. Per assegnare manualmente questo ruolo, aggiungersi come membro del gruppo di ruoli Gestione individuazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="0c55d-p106">**Esportazione delle cassette postali** -questo ruolo consente di eliminare i messaggi dalla cassetta postale di un utente. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="0c55d-p107">La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Ciò è dovuto al fatto che non è possibile riapplicare un blocco (o un criterio di conservazione di Office 365) a una cassetta postale inattiva dopo averlo rimosso. Quando si rimuove un'esenzione da una cassetta postale inattiva, viene modificata in una normale cassetta postale eliminata temporaneamente e viene eliminata definitivamente dall'organizzazione dopo che è stata elaborata dall'Assistente cartelle gestite.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="0c55d-p108">Non è possibile eseguire questa procedura per una cassetta postale che è stata assegnata a un criterio di conservazione di Office 365 che è stato bloccato con un blocco di conservazione. Ciò è dovuto al fatto che un blocco di conservazione impedisce di rimuovere o escludere la cassetta postale dal criterio di conservazione di Office 365 e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sul blocco dei criteri di conservazione, vedere [Locking a Retention Policy](retention-policies.md#locking-a-retention-policy).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="0c55d-p109">Se non si dispone di una cassetta postale in attesa (o se non è stato abilitato il ripristino di un singolo elemento), è possibile eliminare gli elementi dalla cartella elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere [cercare ed eliminare i messaggi ](https://go.microsoft.com/fwlink/?linkid=852453).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="0c55d-142">Passaggio 1: raccogliere informazioni sulla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="0c55d-p110">Questo primo passaggio consiste nel raccogliere le proprietà selezionate dalla cassetta postale di destinazione che influenzerà questa procedura. Assicurarsi di annotare queste impostazioni o salvarle in un file di testo, perché si modificheranno alcune di queste proprietà e quindi si tornerà ai valori originali del passaggio 6, dopo aver eliminato gli elementi dalla cartella elementi ripristinabili. Ecco un elenco delle proprietà della cassetta postale che è necessario raccogliere.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="0c55d-146">*SingleItemRecoveryEnabled* e *RetainDeletedItemsFor* ; Se necessario, è possibile disabilitare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="0c55d-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="0c55d-p111">*LitigationHoldEnabled* e *InPlaceHolds* ; è necessario identificare tutti gli appigli posizionati nella cassetta postale in modo da poterli rimuovere temporaneamente nel passaggio 3. Vedere la sezione [ulteriori informazioni](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="0c55d-p112">Inoltre, è necessario ottenere le impostazioni di accesso client delle cassette postali in modo da poterle disabilitare temporaneamente in modo che il proprietario (o altri utenti) non riesca ad accedere alla cassetta postale durante questa procedura. Infine, è possibile ottenere la dimensione corrente e il numero di elementi nella cartella elementi ripristinabili. Dopo aver eliminato gli elementi nella cartella elementi ripristinabili nel passaggio 5, è possibile utilizzare queste informazioni per verificare che gli elementi siano stati effettivamente rimossi.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="0c55d-p113">[Connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e una password per un account amministratore a cui sono stati assegnati i ruoli di gestione idonei in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="0c55d-154">Eseguire il seguente comando per ottenere informazioni sul ripristino di un singolo elemento e sul periodo di conservazione degli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="0c55d-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="0c55d-p114">Se il ripristino di un singolo elemento è abilitato, è necessario disattivarlo nel passaggio 2. Se il periodo di conservazione degli elementi eliminati non è impostato per 30 giorni (il valore massimo in Exchange Online), è possibile aumentarlo nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="0c55d-157">Eseguire il seguente comando per ottenere le impostazioni di accesso alle cassette postali per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="0c55d-158">Nel passaggio 2 vengono disattivati tutti questi metodi di accesso.</span><span class="sxs-lookup"><span data-stu-id="0c55d-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="0c55d-159">Eseguire il seguente comando per ottenere informazioni sulle esenzioni e sui criteri di conservazione di Office 365 applicati alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="0c55d-160">Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="0c55d-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="0c55d-161">Eseguire il seguente comando per ottenere informazioni su tutti i criteri di conservazione di Office 365 a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="0c55d-162">Se l'organizzazione dispone di criteri di conservazione di Office 365 a livello di organizzazione, sarà necessario escludere la cassetta postale da questi criteri nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="0c55d-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="0c55d-163">Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="0c55d-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="0c55d-164">Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="0c55d-165">Se la cassetta postale di archiviazione dell'utente è abilitata, eseguire il comando riportato di seguito per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="0c55d-p115">Quando si eliminano gli elementi nel passaggio 5, è possibile scegliere di eliminare o non eliminare gli elementi nella cartella elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente. Se per la cassetta postale è abilitata l'archiviazione con espansione automatica, gli elementi in una cassetta postale di archiviazione ausiliaria non verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="0c55d-168">Passaggio 2: preparare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="0c55d-169">Dopo aver raccolto e salvato le informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c55d-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="0c55d-170">**Disabilitare l'accesso client alla cassetta postale** , in modo che il proprietario della cassetta postale non possa accedere alla propria cassetta postale e apportare le modifiche ai dati della cassetta postale durante questa procedura.</span><span class="sxs-lookup"><span data-stu-id="0c55d-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="0c55d-171">**Aumentare il periodo di conservazione degli elementi eliminati** fino a 30 giorni (il valore massimo in Exchange Online), in modo che gli elementi non vengano eliminati dalla cartella elemento ripristinabile prima di poterli eliminare nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="0c55d-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="0c55d-172">**Disabilitare il ripristino di un singolo elemento** in modo che gli elementi non vengano conservati (per la durata del periodo di conservazione degli elementi eliminati) dopo averli eliminati dalla cartella elementi ripristinabili nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="0c55d-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="0c55d-173">**Disabilitare l'Assistente cartelle gestite** in modo che non elabori la cassetta postale e mantenga gli elementi eliminati nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="0c55d-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="0c55d-174">Eseguire le operazioni seguenti in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="0c55d-p116">Eseguire il seguente comando per disabilitare tutti gli accessi client alla cassetta postale. La sintassi del comando presuppone che tutti i metodi di accesso client siano stati abilitati nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="0c55d-p117">Per disabilitare tutti i metodi di accesso client alla cassetta postale, potrebbero essere necessari fino a 60 minuti. Si noti che la disabilitazione di questi metodi di accesso non disconnetterà il proprietario della cassetta postale a cui è attualmente connesso. Se il proprietario non ha eseguito l'accesso, non sarà in grado di accedere alla propria cassetta postale dopo che questi metodi di accesso sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="0c55d-p118">Eseguire il seguente comando per aumentare il periodo di conservazione degli elementi eliminati per un massimo di 30 giorni. Si presuppone che l'impostazione corrente sia inferiore a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="0c55d-182">Per disabilitare il ripristino di un singolo elemento, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0c55d-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="0c55d-p119">Per disabilitare il ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti. Non eliminare gli elementi nella cartella elementi ripristinabili fino a quando non è trascorso questo periodo.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="0c55d-p120">Eseguire il seguente comando per evitare che l'Assistente cartelle gestite esegua l'elaborazione della cassetta postale. Come spiegato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se un criterio di conservazione di Office 365 con un blocco di conservazione non viene applicato alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="0c55d-187">Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="0c55d-p121">L'ultimo passaggio prima di poter eliminare gli elementi dalla cartella elementi ripristinabili consiste nel rimuovere tutte le esenzioni (identificate nel passaggio 1) inserite nella cassetta postale. Tutte le esenzioni devono essere rimosse in modo che gli elementi non vengano conservati dopo averli eliminati dalla cartella elementi ripristinabili. Nelle sezioni seguenti sono contenute informazioni sulla rimozione di diversi tipi di esenzioni su una cassetta postale. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale. Per ulteriori informazioni, vedere [come identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0c55d-193">Come indicato in precedenza, consultare la gestione dei record o i reparti giuridici prima di rimuovere un'esenzione da una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="0c55d-194">Conservazione in caso di dispute</span><span class="sxs-lookup"><span data-stu-id="0c55d-194">Litigation Hold</span></span>
  
<span data-ttu-id="0c55d-195">Eseguire il seguente comando in Exchange Online PowerShell per rimuovere un blocco per controversia legale dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="0c55d-p122">Analogamente alla disattivazione dei metodi di accesso client e del ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti per rimuovere il blocco per controversia legale. Non eliminare gli elementi dalla cartella elementi ripristinabili fino a quando non è trascorso questo periodo.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="0c55d-198">Blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="0c55d-198">In-Place Hold</span></span>
  
<span data-ttu-id="0c55d-p123">Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco sul posto applicato alla cassetta postale. Utilizzare il GUID per il blocco sul posto identificato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="0c55d-p124">Dopo aver identificato il blocco sul posto, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [creare o rimuovere un blocco sul posto](https://go.microsoft.com/fwlink/?linkid=852668).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="0c55d-203">Criteri di conservazione di Office 365 applicati a cassette postali specifiche</span><span class="sxs-lookup"><span data-stu-id="0c55d-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="0c55d-p125">Eseguire il seguente comando in [PowerShell per il &amp; Centro sicurezza e conformità di Office 365](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale. Utilizzare il GUID (escluso il `mbx` prefisso `skp` o) per i criteri di conservazione identificati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="0c55d-206">Dopo aver identificato il criterio di conservazione, passare alla pagina **conservazione** **Data Governance** \> nel centro &amp; sicurezza e conformità, modificare i criteri di conservazione identificati nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="0c55d-207">Criteri di conservazione di Office 365 a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="0c55d-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="0c55d-p126">I criteri di conservazione di Office 365 a livello di organizzazione e di Exchange sono applicati a tutte le cassette postali dell'organizzazione. Vengono applicati a livello di organizzazione (non a livello di cassetta postale) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Eseguire il seguente comando in [PowerShell &amp; per il Centro sicurezza e conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione di Office 365 a livello dell'organizzazione. Utilizzare il GUID (escluso il `mbx` prefisso) per i criteri di conservazione a livello dell'organizzazione identificati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="0c55d-p127">dopo aver identificato i criteri di conservazione di Office 365 a livello di organizzazione, passare alla pagina \> **conservazione** governance &amp; **data** nel centro sicurezza e conformità, modificare tutti i criteri di conservazione a livello di organizzazione identificati nell' passaggio precedente e aggiungere la cassetta postale all'elenco dei destinatari esclusi. In questo modo, la cassetta postale dell'utente verrà rimossa dal criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="0c55d-214">Etichette di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="0c55d-214">Office 365 retention labels</span></span>

<span data-ttu-id="0c55d-p128">Ogni volta che un utente applica un'etichetta configurata per mantenere il contenuto o mantenere e quindi eliminare il contenuto in una cartella o un elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* viene impostata su **true**. In questo caso, la cassetta postale viene considerata attiva, come se fosse stata inserita in una conservazione per controversia legale o assegnata a un criterio di ritenzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="0c55d-217">Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0c55d-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="0c55d-p129">Dopo aver identificato che una cassetta postale è in attesa perché viene applicata un'etichetta di conservazione a una cartella o a un elemento, è possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza & Compliance per cercare gli elementi contrassegnati utilizzando la condizione di ricerca di ComplianceTag. Per ulteriori informazioni, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="0c55d-220">Per ulteriori informazioni sulle etichette, vedere [Overview of Office 365 labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="0c55d-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="0c55d-221">blocco del caso di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0c55d-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="0c55d-p130">Eseguire i seguenti comandi in [PowerShell &amp; per il Centro sicurezza e conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare il blocco associato a un caso di eDiscovery applicato alla cassetta postale. Utilizzare il GUID (escluso il `UniH` prefisso) per il blocco eDiscovery identificato nel passaggio 1. Si noti che il secondo comando Visualizza il nome del caso di eDiscovery a cui è associato il blocco. il terzo comando Visualizza il nome dell'esenzione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="0c55d-p131">Dopo aver identificato il nome del caso eDiscovery e il blocco, passare alla pagina \> \*\*analisi ricerca &amp; \*\* **eDiscovery** nel centro sicurezza &amp; e conformità, aprire il caso e rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [gestire i casi di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](manage-ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="0c55d-227">Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="0c55d-p132">Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* è impostato su **true**. Questo problema si verifica quando l'Assistente cartelle gestite elabora la cassetta postale e rileva che è stata rimossa un'esenzione. Si tratta di un *blocco di ritardo* che indica che la rimozione effettiva del blocco viene posticipata di 30 giorni per evitare che i dati vengano eliminati definitivamente dalla cassetta postale. Lo scopo di un blocco di ritardo consiste nell'assegnare agli amministratori la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un'esenzione.  Quando viene immessa una conservazione per la cassetta postale, la cassetta postale è ancora considerata attiva per una durata illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, scade il ritardo e Office 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà *DelayHoldApplied* su **false**) in modo che il blocco venga effettivamente rimosso.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="0c55d-p133">Prima di poter eliminare gli elementi nel passaggio 5, è necessario rimuovere il blocco di ritardo dalla cassetta postale. Per prima cosa, determinare se il blocco di ritardo viene applicato alla cassetta postale eseguendo il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0c55d-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="0c55d-p134">Se il valore della proprietà *DelayHoldApplied* è impostato su **false**, nella cassetta postale non è stato applicato un blocco di ritardo. È possibile passare al passaggio 5 ed eliminare gli elementi nella cartella elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p134">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox. You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="0c55d-237">Se il valore della proprietà *DelayHoldApplied* è impostato su **true**, eseguire il comando riportato di seguito per rimuovere il blocco di ritardo:</span><span class="sxs-lookup"><span data-stu-id="0c55d-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="0c55d-238">Tenere presente che è necessario essere assegnati al ruolo di blocco legale in Exchange Online per utilizzare il parametro *RemoveDelayHoldApplied* .</span><span class="sxs-lookup"><span data-stu-id="0c55d-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="0c55d-239">Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="0c55d-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="0c55d-p135">A questo punto si è pronti per eliminare effettivamente gli elementi nella cartella elementi ripristinabili utilizzando il cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) in Exchange Online PowerShell. Quando si esegue il cmdlet **Search-Mailbox** , sono disponibili tre opzioni.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p135">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="0c55d-242">Copiare gli elementi in una cassetta postale di destinazione prima di eliminarli in modo da poter esaminare gli elementi, se necessario, prima di eliminarli.</span><span class="sxs-lookup"><span data-stu-id="0c55d-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="0c55d-243">Copiare gli elementi in una cassetta postale di destinazione ed eliminarli nello stesso comando.</span><span class="sxs-lookup"><span data-stu-id="0c55d-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="0c55d-244">Eliminare gli elementi senza copiarli in una cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="0c55d-p136">Tenere presente che gli elementi nella cartella elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente verranno eliminati anche quando si esegue il cmdlet **Search-Mailbox** . Per evitare questo, è possibile includere l'opzione *DoNotIncludeArchive* . Come indicato in precedenza, se l'archiviazione con espansione automatica è abilitata per la cassetta postale, il cmdlet \* \* Search-Mailbox \* \* non elimina gli elementi in una cassetta postale di archiviazione ausiliaria. Per ulteriori informazioni sull'espansione automatica dell'archivio, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p136">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c55d-p137">Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="0c55d-p138">Negli esempi seguenti viene illustrata la sintassi dei comandi per ognuna di queste opzioni. In questi esempi viene `-SearchQuery size>0` utilizzato il valore del parametro, che consente di eliminare tutti gli elementi da tutte le sottocartelle nella cartella elementi ripristinabili. Se è necessario eliminare solo gli elementi che soddisfano condizioni specifiche, è anche possibile utilizzare il parametro *SearchQuery* per specificare altre condizioni, ad esempio l'oggetto di un messaggio o un intervallo di date. Per ulteriori informazioni, vedere gli [altri esempi di utilizzo del parametro SearchQuery](#other-examples-of-using-the-searchquery-parameter) .</span><span class="sxs-lookup"><span data-stu-id="0c55d-p138">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="0c55d-255">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="0c55d-255">Example 1</span></span>

<span data-ttu-id="0c55d-p139">In questo esempio vengono copiati tutti gli elementi della cartella elementi ripristinabili dell'utente in una cartella della cassetta postale di individuazione dell'organizzazione. In questo modo è possibile esaminare gli elementi prima di eliminarli definitivamente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p139">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="0c55d-p140">Nell'esempio precedente, non è necessario copiare gli elementi nella cassetta postale di ricerca di individuazione. È possibile copiare i messaggi in tutte le cassette postali di destinazione. Tuttavia, per impedire l'accesso ai dati delle cassette postali potenzialmente sensibili, è consigliabile copiare i messaggi in una cassetta postale che ha accesso limitato a personale autorizzato. Per impostazione predefinita, l'accesso alla cassetta postale di ricerca di individuazione predefinita è limitato ai membri del gruppo di ruoli Gestione individuazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p140">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="0c55d-262">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="0c55d-262">Example 2</span></span>

<span data-ttu-id="0c55d-263">In questo esempio vengono copiati tutti gli elementi della cartella elementi ripristinabili dell'utente in una cartella della cassetta postale di individuazione dell'organizzazione e quindi vengono eliminati gli elementi dalla cartella elementi ripristinabili dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="0c55d-264">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="0c55d-264">Example 3</span></span>

<span data-ttu-id="0c55d-265">In questo esempio vengono eliminati tutti gli elementi nella cartella elementi ripristinabili dell'utente, senza copiarli in una cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="0c55d-266">Altri esempi di utilizzo del parametro SearchQuery</span><span class="sxs-lookup"><span data-stu-id="0c55d-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="0c55d-p141">Di seguito sono riportati alcuni esempi di utilizzo del parametro *SearchQuery* per trovare messaggi specifici. Se si utilizza il parametro *SearchQuery* per cercare elementi specifici, è consigliabile copiare i risultati della ricerca in una cassetta postale di destinazione in modo che sia possibile esaminare i risultati della ricerca e quindi rivedere la query se necessario prima di eliminare i risultati di una ricerca.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p141">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="0c55d-269">In questo esempio vengono restituiti i messaggi che contengono una frase specifica nel campo Subject.</span><span class="sxs-lookup"><span data-stu-id="0c55d-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="0c55d-270">In questo esempio vengono restituiti i messaggi che sono stati inviati entro l'intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="0c55d-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="0c55d-271">In questo esempio vengono restituiti i messaggi che sono stati inviati alla persona specificata.</span><span class="sxs-lookup"><span data-stu-id="0c55d-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="0c55d-272">Verificare che gli elementi siano stati eliminati</span><span class="sxs-lookup"><span data-stu-id="0c55d-272">Verify that items were deleted</span></span>

<span data-ttu-id="0c55d-p142">Per verificare la corretta eliminazione degli elementi dalla cartella elementi ripristinabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** in PowerShell di Exchange Online per controllare la dimensione e il numero di elementi nella cartella elementi ripristinabili. È possibile confrontare queste statistiche con quelle raccolte nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p142">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="0c55d-275">Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="0c55d-276">Eseguire il seguente comando per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="0c55d-277">Passaggio 6: ripristinare lo stato precedente della cassetta postale</span><span class="sxs-lookup"><span data-stu-id="0c55d-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="0c55d-p143">Il passaggio finale consiste nel ripristinare la configurazione precedente della cassetta postale. Questo significa reimpostare le proprietà modificate nel passaggio 2 e riapplicare le esenzioni rimosse al passaggio 3. Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c55d-p143">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="0c55d-p144">Modifica del periodo di conservazione degli elementi eliminati sul valore precedente. In alternativa, è possibile lasciare questo set a 30 giorni, ovvero il valore massimo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p144">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="0c55d-283">Riattivazione del ripristino di un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="0c55d-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="0c55d-284">Riattivare i metodi di accesso client in modo che il proprietario possa accedere alla propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="0c55d-285">Riapplicare le esenzioni e i criteri di conservazione di Office 365 rimossi.</span><span class="sxs-lookup"><span data-stu-id="0c55d-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="0c55d-286">Riattivare l'Assistente cartelle gestite per elaborare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0c55d-287">È consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione di Office 365 (e verificare che sia sul posto) prima di riabilitare l'Assistente cartelle gestite per elaborare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="0c55d-288">Eseguire i passaggi seguenti (nella sequenza specificata) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c55d-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="0c55d-p145">Eseguire il seguente comando per ripristinare il valore originale del periodo di conservazione degli elementi eliminati. Si presuppone che l'impostazione precedente sia inferiore a 30 giorni. ad esempio, 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p145">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="0c55d-291">Eseguire il seguente comando per riattivare il ripristino di un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="0c55d-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="0c55d-292">Eseguire il seguente comando per riabilitare tutti i metodi di accesso client alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="0c55d-p146">Riapplicare le esenzioni rimosse nel passaggio 3. A seconda del tipo di blocco, utilizzare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p146">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="0c55d-295">**Conservazione in caso di dispute**</span><span class="sxs-lookup"><span data-stu-id="0c55d-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="0c55d-296">Eseguire il seguente comando per riattivare un blocco per controversia legale per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="0c55d-297">**Conservazione in locale**</span><span class="sxs-lookup"><span data-stu-id="0c55d-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="0c55d-298">Utilizzare EAC (o Exchange Online PowerShell) per aggiungere di nuovo la cassetta postale all'archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="0c55d-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="0c55d-299">**Criteri di conservazione di Office 365 applicati a cassette postali specifiche**</span><span class="sxs-lookup"><span data-stu-id="0c55d-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="0c55d-p147">Utilizzare il centro &amp; sicurezza e conformità per aggiungere di nuovo la cassetta postale ai criteri di conservazione di Office 365. Passare alla pagina \*\*\*\* \> **conservazione** governance data nel centro sicurezza &amp; e conformità, modificare il criterio di conservazione e aggiungere di nuovo la cassetta postale all'elenco dei destinatari a cui è applicato il criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p147">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="0c55d-302">**Criteri di conservazione di Office 365 a livello di organizzazione**</span><span class="sxs-lookup"><span data-stu-id="0c55d-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="0c55d-p148">Se è stato rimosso un criterio di conservazione a livello di organizzazione o a livello di Exchange, escluderlo dal criterio, utilizzare &amp; il Centro sicurezza e conformità per rimuovere la cassetta postale dall'elenco degli utenti esclusi. Passare alla pagina \*\*\*\* \> **conservazione** governance data nel centro sicurezza &amp; e conformità, modificare il criterio di conservazione a livello dell'organizzazione e rimuovere la cassetta postale dall'elenco dei destinatari esclusi. In questo modo verrà applicato di nuovo il criterio di conservazione alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p148">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="0c55d-306">**blocco del caso di eDiscovery**</span><span class="sxs-lookup"><span data-stu-id="0c55d-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="0c55d-p149">Utilizzare il centro &amp; sicurezza e conformità per aggiungere la cassetta postale che è associata a un caso di eDiscovery. Passare alla pagina \*\*analisi &amp; \*\* \> di ricerca di **eDiscovery** nel centro &amp; sicurezza e conformità, aprire il caso e riaggiungere la cassetta postale all'esenzione.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p149">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="0c55d-p150">Eseguire il seguente comando per consentire all'Assistente cartelle gestite di elaborare di nuovo la cassetta postale. Come indicato in precedenza, è consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione di Office 365 (e verificare che sia sul posto) prima di abilitare di nuovo l'Assistente cartelle gestite.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p150">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="0c55d-311">Per verificare che la cassetta postale sia stata ripristinata alla configurazione precedente, è possibile eseguire i comandi seguenti e quindi confrontare le impostazioni con quelle raccolte nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0c55d-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="0c55d-312">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0c55d-312">More information</span></span>

<span data-ttu-id="0c55d-p151">Di seguito viene riportata una tabella in cui viene descritto come identificare diversi tipi di esenzioni in base ai valori della proprietà *InPlaceHolds* quando si eseguono i cmdlet **Get-Mailbox** o **Get-OrganizationConfig** . Per informazioni più dettagliate, vedere [How to identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="0c55d-p151">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="0c55d-315">Come spiegato in precedenza, è necessario rimuovere tutte le esenzioni e i criteri di conservazione di Office 365 da una cassetta postale prima di poter eliminare correttamente gli elementi nella cartella elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="0c55d-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="0c55d-316">**Tipo di blocco**</span><span class="sxs-lookup"><span data-stu-id="0c55d-316">**Hold type**</span></span>|<span data-ttu-id="0c55d-317">**Valore di esempio**</span><span class="sxs-lookup"><span data-stu-id="0c55d-317">**Example value**</span></span>|<span data-ttu-id="0c55d-318">**Come identificare il blocco**</span><span class="sxs-lookup"><span data-stu-id="0c55d-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c55d-319">Blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="0c55d-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="0c55d-320">La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.</span><span class="sxs-lookup"><span data-stu-id="0c55d-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="0c55d-321">Blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="0c55d-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="0c55d-p152">La proprietà *InPlaceHolds* contiene il GUID del blocco sul posto applicato alla cassetta postale. È possibile indicare che si tratta di un blocco sul posto poiché il GUID non inizia con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p152">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="0c55d-324">È possibile utilizzare il `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando in PowerShell di Exchange Online per ottenere informazioni sul blocco sul posto sulla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="0c55d-325">Criteri di conservazione di Office 365 nel &amp; centro conformità di sicurezza applicato a cassette postali specifiche</span><span class="sxs-lookup"><span data-stu-id="0c55d-325">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="0c55d-326">oppure</span><span class="sxs-lookup"><span data-stu-id="0c55d-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="0c55d-p153">Quando si esegue il cmdlet **Get-Mailbox** , la proprietà *InPlaceHolds* contiene anche i GUID dei criteri di conservazione di Office 365 applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia `mbx` con il prefisso. Si noti che se il GUID del criterio di conservazione inizia con `skp` il prefisso, indica che il criterio di conservazione viene applicato alle conversazioni di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p153">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="0c55d-330">Per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale, eseguire il comando seguente in PowerShell &amp; per il Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="0c55d-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="0c55d-331">Assicurarsi di rimuovere il `mbx` prefisso o `skp` quando si esegue questo comando.</span><span class="sxs-lookup"><span data-stu-id="0c55d-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="0c55d-332">Criteri di conservazione di Office 365 a livello di organizzazione &amp; nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="0c55d-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="0c55d-333">Nessun valore</span><span class="sxs-lookup"><span data-stu-id="0c55d-333">No value</span></span>  <br/> <span data-ttu-id="0c55d-334">oppure</span><span class="sxs-lookup"><span data-stu-id="0c55d-334">or</span></span>  <br/>  <span data-ttu-id="0c55d-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`(indica che la cassetta postale è esclusa da un criterio a livello di organizzazione)</span><span class="sxs-lookup"><span data-stu-id="0c55d-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="0c55d-336">Anche se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è ancora possibile che siano presenti uno o più criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c55d-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="0c55d-p154">Per verificarlo, è possibile eseguire il `Get-OrganizationConfig | FL InPlaceHolds` comando in Exchange Online PowerShell per ottenere un elenco dei GUID per i criteri di conservazione di Office 365 a livello dell'organizzazione. Il GUID per i criteri di conservazione a livello dell'organizzazione applicati alle cassette postali di Exchange inizia con il `mbx` prefisso. ad esempio `mbxa3056bb15562480fadb46ce523ff7b02`.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p154">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  </span></span><br/> <span data-ttu-id="0c55d-339">Per identificare i criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale, eseguire il comando seguente in &amp; PowerShell per il Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="0c55d-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="0c55d-340">Si noti che se una cassetta postale è stata esclusa da un criterio di conservazione di Office 365 a livello di organizzazione, il GUID per il criterio di conservazione viene visualizzato nella proprietà *InPlaceHolds* della cassetta postale dell'utente quando si esegue il cmdlet **Get-Mailbox** . è identificato dal prefisso `-mbx`; Per esempio`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="0c55d-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="0c55d-341">blocco del caso di eDiscovery nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="0c55d-341">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="0c55d-p155">La proprietà *InPlaceHolds* contiene inoltre il GUID di qualsiasi blocco associato a un caso di eDiscovery nel centro &amp; sicurezza e conformità che potrebbe essere posizionato sulla cassetta postale. Si può dire che si tratta di un caso di eDiscovery, perché il GUID `UniH` inizia con il prefisso.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p155">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="0c55d-p156">È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in PowerShell &amp; per la conformità al centro sicurezza per ottenere informazioni sul caso di eDiscovery a cui è associato il blocco della cassetta postale. Ad esempio, è possibile eseguire il comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` per visualizzare il nome del blocco del caso che si trova nella cassetta postale. Assicurarsi di rimuovere il `UniH` prefisso quando si esegue questo comando.</span><span class="sxs-lookup"><span data-stu-id="0c55d-p156">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  </span></span><br/><br/> <span data-ttu-id="0c55d-347">Per identificare il caso di eDiscovery a cui è associato il blocco della cassetta postale, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c55d-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


