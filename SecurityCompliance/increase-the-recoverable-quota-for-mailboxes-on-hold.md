---
title: Aumentare la quota degli elementi recuperabili per le cassette postali in attesa
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: "Abilitare la cassetta postale di archiviazione e attivare l'archiviazione per aumentare le dimensioni della cartella elementi recuperabili per una cassetta postale in Office 365 l'espansione automatica. "
ms.openlocfilehash: cd2d07e6ef1637343798ccb71870c8d436f10574
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782093"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="7c8b9-103">Aumentare la quota degli elementi recuperabili per le cassette postali in attesa</span><span class="sxs-lookup"><span data-stu-id="7c8b9-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="7c8b9-p101">Il criterio di conservazione predefinito, ovvero denominato criterio di gestione record di messaggistica predefinito, vale a dire automaticamente applicata a nuove cassette postali in Exchange Online contiene un tag di conservazione denominate giorni 14 elementi recuperabili spostamento nell'archivio. Tag di conservazione Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente nella cartella elementi recuperabili di cassetta postale di archivio dell'utente dopo il periodo di conservazione 14 giorni per un elemento. A tale scopo, è necessario attivare cassetta postale di archivio dell'utente. Se la cassetta postale di archiviazione non è abilitata, viene eseguita alcuna azione, il che significa che non vengono spostati gli elementi nella cartella per una cassetta postale in attesa agli elementi ripristinabili la cassetta postale di archiviazione dopo il periodo di conservazione 14 giorni. Poiché non viene eliminato da una cassetta postale in attesa, è possibile che potrebbe essere superata la quota di archiviazione per la cartella elementi ripristinabili, soprattutto se non è abilitata cassetta postale di archivio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="7c8b9-p102">Per ridurre le possibilità che superano questo limite, la quota di archiviazione per la cartella elementi recuperabili viene automaticamente aumentata da 30 GB a 100 GB quando un'esenzione viene messa in una cassetta postale di Exchange Online. Se la cassetta postale di archiviazione è abilitata, la quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale di archiviazione viene inoltre aumentata da 30 GB a 100 GB. Se l'archiviazione di espansione automatica delle funzionalità di Exchange Online è abilitata, la quota di archiviazione per la cartella elementi recuperabili nell'archivio dell'utente è un numero illimitata.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="7c8b9-112"> La tabella seguente riepiloga la quota di archiviazione per la cartella Elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="7c8b9-113">**Posizione della cartella Elementi ripristinabili**</span><span class="sxs-lookup"><span data-stu-id="7c8b9-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="7c8b9-114">**Cassette postali non in blocco**</span><span class="sxs-lookup"><span data-stu-id="7c8b9-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="7c8b9-115">**Cassette postali in blocco**</span><span class="sxs-lookup"><span data-stu-id="7c8b9-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c8b9-116">Cassetta postale principale</span><span class="sxs-lookup"><span data-stu-id="7c8b9-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="7c8b9-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="7c8b9-117">30 GB</span></span>  <br/> |<span data-ttu-id="7c8b9-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="7c8b9-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="7c8b9-119">Cassetta postale di archiviazione<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7c8b9-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="7c8b9-120">Illimitata</span><span class="sxs-lookup"><span data-stu-id="7c8b9-120">Unlimited</span></span>  <br/> |<span data-ttu-id="7c8b9-121">Illimitata</span><span class="sxs-lookup"><span data-stu-id="7c8b9-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="7c8b9-122">**Quota di archiviazione totale per la cartella Elementi ripristinabili**</span><span class="sxs-lookup"><span data-stu-id="7c8b9-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="7c8b9-123">Illimitata</span><span class="sxs-lookup"><span data-stu-id="7c8b9-123">Unlimited</span></span>  <br/> |<span data-ttu-id="7c8b9-124">Illimitata</span><span class="sxs-lookup"><span data-stu-id="7c8b9-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="7c8b9-p103"><sup>\*</sup>La quota di archiviazione iniziali per la cassetta postale di archiviazione è pari a 100 GB per gli utenti con una licenza di Exchange Online (piano 2). Tuttavia, quando l'espansione automatica di archiviazione viene attivato per cassette postali in attesa, la quota di archiviazione sia per la cassetta postale di archiviazione e la cartella elementi recuperabili viene aumentata a 110 GB. Verrà eseguito il provisioning lo spazio di archiviazione di archiviazione aggiuntivo quando è necessario che i risultati in una quantità di spazio di archiviazione di archiviazione illimitata. Per ulteriori informazioni sull'espansione automatica di archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="7c8b9-129">Quando la quota di archiviazione per la cartella Elementi ripristinabili nella cassetta postale principale di una cassetta postale in blocco sta per raggiungere il limite, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c8b9-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="7c8b9-p104">**Abilitare la cassetta postale di archiviazione e attivare l'archiviazione l'espansione automatica** - è possibile attivare una capacità di archiviazione illimitato per la cartella elementi ripristinabili semplicemente dall'abilitazione della cassetta postale di archiviazione e quindi riattivare la caratteristica archiviazione espansione automatica di Exchange In linea. Di conseguenza 110 GB per la cartella elementi ripristinabili nella cassetta postale principale e una numero illimitata quantità di capacità di archiviazione per la cartella elementi recuperabili nell'archivio dell'utente. Vedere Procedura: [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c8b9-p105">Dopo aver abilitato l'archivio per una cassetta postale che si avvicina al superamento della quota di archiviazione per la cartella elementi ripristinabili, è possibile eseguire l'Assistente cartelle gestite per attivare manualmente l'Assistente per elaborare la cassetta postale in modo che gli elementi scaduti vengono spostati i Cartella degli elementi ripristinabili nella cassetta postale di archivio. Per istruzioni, vedere [il passaggio 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Si noti che la nuova cassetta postale di archiviazione possono quindi essere spostati altri elementi nella cassetta postale dell'utente. È consigliabile che indica all'utente che questa situazione può verificarsi dopo aver attivato la cassetta postale di archivio.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="7c8b9-p106">**Crea un criterio di conservazione personalizzata per le cassette postali in attesa** - oltre abilitazione della cassetta postale di archiviazione e l'archiviazione delle cassette postali su conservazione per controversia legale o archiviazione sul posto, l'espansione automatica è inoltre possibile creare un criterio di conservazione personalizzata per le cassette postali su in attesa. Ciò si è applicare un criterio di conservazione alle cassette postali in attesa è diverso dal criterio Gestione record di messaggistica predefinito viene applicato alle cassette postali che non sono in attesa. In tal modo si per applicare i tag di conservazione sono progettati per le cassette postali in attesa. Esse comprendono la creazione di un nuovo tag di conservazione per la cartella elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="7c8b9-141">Il resto di questo argomento descrive procedure dettagliate per creare criteri di conservazione personalizzati per le cassette postali in blocco.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="7c8b9-142">Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="7c8b9-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="7c8b9-143">[[Passaggio 2: creare un nuovo criterio di conservazione per le cassette postali in attesa](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="7c8b9-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="7c8b9-144">Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="7c8b9-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="7c8b9-145">Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="7c8b9-146">Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="7c8b9-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="7c8b9-p107">Il primo passaggio consiste nel creare un tag di conservazione personalizzata (detta tag criterio di conservazione o tag) per la cartella elementi recuperabili. Come indicato in precedenza, questo RPT Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente nella cartella elementi recuperabili di cassetta postale di archivio dell'utente. È necessario utilizzare PowerShell per creare un tag per la cartella elementi recuperabili. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="7c8b9-151">Connessione a Exchange Online tramite remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c8b9-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="7c8b9-152">Eseguire il seguente comando per creare un nuovo RPT nella cartella Elementi ripristinabili: </span><span class="sxs-lookup"><span data-stu-id="7c8b9-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="7c8b9-p108">Ad esempio, il seguente comando crea un RPT per la cartella Elementi ripristinabili denominata "Spostamento degli elementi ripristinabili dopo 30 giorni per le cassette postali in blocco", con un periodo di conservazione di 30 giorni. Ciò significa che dopo che un elemento è stato nella cartella Elementi ripristinabili per 30 giorni, viene spostato nella cartella Elementi ripristinabili nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="7c8b9-p109">È consigliabile che il periodo di conservazione (definito dal parametro _AgeLimitForRetention_ ) per il tag degli elementi ripristinabili è lo stesso del periodo di mantenimento elementi eliminati per le cassette postali che verrà applicato il tag. Ciò consente l'intero periodo di mantenimento per ripristinare gli elementi eliminati prima che venga vengono spostati nella cassetta postale di archivio. Nell'esempio precedente, il periodo di conservazione è stato impostato su 30 giorni partendo dal presupposto che il periodo di mantenimento elementi eliminati per le cassette postali è anche 30 giorni. Una cassetta postale di Exchange Online è configurata per conservare gli elementi eliminati 14 giorni, per impostazione predefinita. Ma è possibile modificare questa impostazione per un massimo di 30 giorni. Per ulteriori informazioni, vedere [modificare il periodo di mantenimento elementi eliminati per una cassetta postale di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="7c8b9-161">Passaggio 2: Creazione di nuovi criteri di conservazione per le cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="7c8b9-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="7c8b9-p110">Il passaggio successivo consiste nel creare nuovi criteri di conservazione e aggiungere tag di conservazione, inclusi i RPT di elementi ripristinabili creati nel Passaggio 1. I nuovi criteri verranno applicati alle cassette postali in blocco nel passaggio successivo. </span><span class="sxs-lookup"><span data-stu-id="7c8b9-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="7c8b9-p111">Prima di creare i nuovi criteri di conservazione, determinare quali tag di conservazione aggiuntivi aggiungere. Per un elenco dei tag di conservazione che vengono aggiunti ai criteri di gestione record di messaggistica predefiniti e per informazioni sulla creazione di nuovi tag di conservazione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="7c8b9-166">Default criterio di conservazione in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7c8b9-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="7c8b9-167">Cartelle predefinite che supportano i tag del criterio di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="7c8b9-168">La sezione "Creare un tag di conservazione" nell'argomento [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="7c8b9-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="7c8b9-169">È possibile utilizzare EAC o Exchange Online PowerShell per creare un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="7c8b9-170">Creazione di un criterio di conservazione tramite l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="7c8b9-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="7c8b9-171">In EAC, andare a **Gestione conformità** \> **i criteri di conservazione**e quindi fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="7c8b9-172">Nella pagina **Nuovo criterio di conservazione**, in **Nome**, digitare un nome che descriva lo scopo del criterio di conservazione, ad esempio, **MRM Policy for Mailboxes on Hold**. </span><span class="sxs-lookup"><span data-stu-id="7c8b9-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="7c8b9-173">**I tag di conservazione**, fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="7c8b9-174">Nell'elenco dei tag di conservazione, selezionare l’elemento RPT di Elementi ripristinabili creato nel Passaggio 1, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Selezionare il tag di conservazione Elementi recuperabili personalizzato](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="7c8b9-p112">Selezionare i tag di conservazione aggiuntivi da aggiungere ai criteri di conservazione. Ad esempio, è possibile aggiungere gli stessi tag inclusi nei criteri di gestione record di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="7c8b9-178">Dopo aver completato l'aggiunta dei tag di conservazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="7c8b9-179">Fare clic su **Salva** per creare i nuovi criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="7c8b9-180">Tenere presente che i tag di conversazione collegati ai criteri di conservazione vengono visualizzati nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![I tag di conversazione collegati al criterio di conservazione vengono visualizzati nel riquadro dei dettagli](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="7c8b9-182">Utilizzare Exchange Online PowerShell per creare un criterio di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="7c8b9-183">Per creare nuovi criteri di conservazione per le cassette postali in blocco, eseguire il seguente comando: </span><span class="sxs-lookup"><span data-stu-id="7c8b9-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="7c8b9-184">Il comando seguente, ad esempio, crea il criterio di conservazione e tag di conservazione collegati, come illustrato nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="7c8b9-185">Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="7c8b9-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="7c8b9-p113">L'ultimo passaggio è per applicare il nuovo criterio di conservazione creata nel passaggio 2 per le cassette postali in attesa nell'organizzazione. È possibile utilizzare EAC o Exchange Online PowerShell per applicare il criterio di conservazione a una singola cassetta postale o a più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="7c8b9-188">Utilizzare EAC per applicare i nuovi criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="7c8b9-189">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="7c8b9-190">Nella visualizzazione elenco, selezionare la cassetta postale che si desidera applicare il criterio di conservazione per e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="7c8b9-191">Nella pagina **Cassetta postale utente**, fare clic su **Funzionalità delle cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="7c8b9-192">In **Criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="7c8b9-193">È anche possibile utilizzare EAC per applicare criteri di conservazione a più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="7c8b9-194">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="7c8b9-195">Nell'elenco, utilizzare il tasto Maiusc o Ctrl per selezionare più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="7c8b9-196">Nel riquadro dei dettagli, fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="7c8b9-197">In **Criterio di conservazione**, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="7c8b9-198">Nella pagina **Assegna in blocco i criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**. </span><span class="sxs-lookup"><span data-stu-id="7c8b9-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="7c8b9-199">Utilizzare Exchange Online PowerShell per applicare il nuovo criterio di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="7c8b9-p114">È possibile utilizzare Exchange Online PowerShell per applicare un nuovo criterio di conservazione a una singola cassetta postale. Ma l'efficacia di PowerShell che è possibile utilizzare per identificare rapidamente tutte le cassette postali nell'organizzazione su conservazione per controversia legale o archiviazione sul posto e quindi applicano il nuovo criterio di conservazione per tutte le cassette postali in attesa in un unico comando. Di seguito sono riportati alcuni esempi dell'utilizzo di PowerShell di Exchange per applicare un criterio di conservazione a una o più cassette postali. Tutti gli esempi di applicare il criterio di conservazione creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="7c8b9-204">In questo esempio vengono applicati nuovi criteri di conservazione alla cassetta postale di Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="7c8b9-205">In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="7c8b9-206">In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="7c8b9-207">È possibile utilizzare il cmdlet **Get-Mailbox** per verificare che siano stati applicati i nuovi criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="7c8b9-208">Ecco alcuni esempi per verificare che i comandi negli esempi precedenti abbiano applicato i criteri di conservazione "Criteri di gestione record di messaggistica per le cassette postali in blocco" alle cassette postali in blocco per controversia legale e alle cassette postali in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="7c8b9-209">Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione</span><span class="sxs-lookup"><span data-stu-id="7c8b9-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="7c8b9-p115">Dopo aver applicato il nuovo criterio di conservazione alle cassette postali in attesa, potrebbero essere necessari fino a 7 giorni di Exchange Online per l'Assistente cartelle gestite elaborare le cassette postali utilizzando le impostazioni nel nuovo criterio di conservazione. Anziché attendere l'Assistente cartelle gestite per l'esecuzione, è possibile utilizzare il cmdlet **Start-ManagedFolderAssistant** per attivare manualmente l'Assistente per elaborare le cassette postali che è stato applicato il nuovo criterio di conservazione a.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="7c8b9-212">Eseguire il seguente comando per avviare l'Assistente cartelle gestite per la cassetta postale di Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="7c8b9-213">Eseguire il seguente comando per avviare l'Assistente cartelle gestite per tutte le cassette postali in blocco.</span><span class="sxs-lookup"><span data-stu-id="7c8b9-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="7c8b9-214">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7c8b9-214">More information</span></span>

- <span data-ttu-id="7c8b9-p116">Dopo aver abilitato cassetta postale di archivio dell'utente, è consigliabile che indica all'utente che altri elementi nella cassetta postale (non solo gli elementi nella cartella elementi ripristinabili) potrebbe essere spostati la cassetta postale di archiviazione. Perché il criterio di gestione record di messaggistica predefinito assegnato alle cassette postali di Exchange Online contiene un tag di conservazione (denominato Default 2 anni spostamento nell'archivio) che sposta gli elementi nella cassetta postale di archivio di due anni dopo la data, l'elemento è stato recapitato alla cassetta postale o creato con il utente. Per ulteriori informazioni, vedere [Criteri di conservazione predefiniti in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="7c8b9-p117">Dopo aver abilitato cassetta postale di archivio dell'utente, potrebbe anche informare l'utente che è possibile recuperare elementi eliminati in cartella elementi ripristinabili nella cassetta postale di archivio. È possibile ottenere questo risultato in Outlook selezionare la cartella **Posta eliminata** nella cassetta postale di archiviazione e quindi fare clic su **Recupera elementi eliminati dal Server** nella scheda **Home** . Per ulteriori informazioni sugli elementi eliminati il ripristino, vedere [che recupera elementi eliminati in Outlook per Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="7c8b9-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 