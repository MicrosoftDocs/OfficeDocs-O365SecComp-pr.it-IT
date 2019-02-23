---
title: Aumentare la quota degli elementi recuperabili per le cassette postali in attesa
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: "Abilitare la cassetta postale di archiviazione e attivare l'archiviazione automatica per aumentare le dimensioni della cartella elementi ripristinabili per una cassetta postale in Office 365. "
ms.openlocfilehash: ebb052ba17ba8a84076e1e75a82713cc5cf437a1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218476"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="1a259-103">Aumentare la quota degli elementi recuperabili per le cassette postali in attesa</span><span class="sxs-lookup"><span data-stu-id="1a259-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="1a259-p101">I criteri di conservazione predefiniti, denominati criteri di gestione record di messaggistica predefinita, che vengono applicati automaticamente alle nuove cassette postali in Exchange Online, contengono un tag di conservazione denominato elementi ripristinabili 14 giorni di spostamento in archivio. Questo tag di conservazione Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente alla cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente dopo la scadenza del periodo di conservazione di 14 giorni per un elemento. Affinché ciò accada, la cassetta postale di archiviazione dell'utente deve essere abilitata. Se la cassetta postale di archiviazione non è abilitata, non viene eseguita alcuna azione, ovvero gli elementi della cartella elementi ripristinabili per una cassetta postale in attesa non vengono spostati nella cassetta postale di archiviazione dopo la scadenza del periodo di conservazione di 14 giorni. Poiché non viene eliminato nulla da una cassetta postale in attesa, è possibile che la quota di archiviazione per la cartella elementi ripristinabili venga superata, soprattutto se la cassetta postale di archiviazione dell'utente non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1a259-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="1a259-p102">Per ridurre la possibilità di superare questo limite, la quota di archiviazione per la cartella elementi ripristinabili viene automaticamente aumentata da 30 GB a 100 GB quando viene inserita una cassetta postale in Exchange Online. Se la cassetta postale di archiviazione è abilitata, è aumentata anche la quota per la cartella elementi ripristinabili nella cassetta postale di archiviazione da 30 GB a 100 GB. Se la funzionalità di archiviazione in espansione automatica in Exchange Online è abilitata, la quota di archiviazione per la cartella elementi ripristinabili nell'archivio dell'utente sarà illimitata.</span><span class="sxs-lookup"><span data-stu-id="1a259-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="1a259-112"> La tabella seguente riepiloga la quota di archiviazione per la cartella Elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="1a259-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="1a259-113">**Posizione della cartella Elementi ripristinabili**</span><span class="sxs-lookup"><span data-stu-id="1a259-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="1a259-114">**Cassette postali non in blocco**</span><span class="sxs-lookup"><span data-stu-id="1a259-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="1a259-115">**Cassette postali in blocco**</span><span class="sxs-lookup"><span data-stu-id="1a259-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a259-116">Cassetta postale principale</span><span class="sxs-lookup"><span data-stu-id="1a259-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="1a259-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="1a259-117">30 GB</span></span>  <br/> |<span data-ttu-id="1a259-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="1a259-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="1a259-119">Cassetta postale di archiviazione<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a259-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="1a259-120">Illimitata</span><span class="sxs-lookup"><span data-stu-id="1a259-120">Unlimited</span></span>  <br/> |<span data-ttu-id="1a259-121">Illimitata</span><span class="sxs-lookup"><span data-stu-id="1a259-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="1a259-122">**Quota di archiviazione totale per la cartella Elementi ripristinabili**</span><span class="sxs-lookup"><span data-stu-id="1a259-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="1a259-123">Illimitata</span><span class="sxs-lookup"><span data-stu-id="1a259-123">Unlimited</span></span>  <br/> |<span data-ttu-id="1a259-124">Illimitata</span><span class="sxs-lookup"><span data-stu-id="1a259-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1a259-p103"><sup>\*</sup>La quota di archiviazione iniziale per la cassetta postale di archivio è di 100 GB per gli utenti con una licenza di Exchange Online (piano 2). Tuttavia, quando l'archiviazione in espansione automatica è attivata per le cassette postali in blocco, la quota di archiviazione per la cassetta postale di archivio e la cartella elementi ripristinabili viene aumentata a 110 GB. Se necessario, verrà eseguito il provisioning di un ulteriore spazio di archiviazione dell'archivio, che consentirà di ottenere un numero illimitato di archiviazione. Per ulteriori informazioni sull'archiviazione automatica, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="1a259-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="1a259-129">Quando la quota di archiviazione per la cartella Elementi ripristinabili nella cassetta postale principale di una cassetta postale in blocco sta per raggiungere il limite, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a259-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="1a259-p104">**Abilitazione della cassetta postale** di archiviazione e attivazione dell'archiviazione automatica-è possibile abilitare una capacità illimitata di archiviazione per la cartella elementi ripristinabili semplicemente abilitando la cassetta postale di archiviazione e quindi attivando la caratteristica di archiviazione in espansione automatica in Exchange Online. Ciò comporta 110 GB per la cartella elementi ripristinabili nella cassetta postale principale e una quantità illimitata di capacità di archiviazione per la cartella elementi ripristinabili nell'archivio dell'utente. Vedere come: [abilitare le cassette postali di archiviazione nel &amp; Centro sicurezza e conformità di Office 365](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="1a259-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1a259-p105">Dopo aver abilitato l'archivio per una cassetta postale vicina al superamento della quota di archiviazione per la cartella elementi ripristinabili, potrebbe essere necessario eseguire l'Assistente cartelle gestite per attivare manualmente l'assistente per elaborare la cassetta postale in modo che gli elementi scaduti vengano spostati nell' Cartella elementi ripristinabili nella cassetta postale di archiviazione. Per istruzioni, vedere [passaggio 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Tenere presente che gli altri elementi della cassetta postale dell'utente possono essere spostati nella nuova cassetta postale di archiviazione. È consigliabile informare l'utente che può verificarsi dopo aver abilitato la cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1a259-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="1a259-p106">**Creare un criterio di conservazione personalizzato per le cassette postali in attesa** -oltre che per abilitare la cassetta postale di archiviazione e l'archiviazione automatica per le cassette postali in blocco per controversia legale o in blocco sul posto, potrebbe essere necessario creare un criterio di conservazione personalizzato per le cassette postali in tenere. In questo modo è possibile applicare un criterio di conservazione alle cassette postali in blocco che differiscono dal criterio di gestione record di messaggistica predefinito applicato alle cassette postali che non sono in attesa. In questo modo è possibile applicare i tag di conservazione appositamente progettati per le cassette postali in blocco. Questo include la creazione di un nuovo tag di conservazione per la cartella elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="1a259-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="1a259-141">Il resto di questo argomento descrive procedure dettagliate per creare criteri di conservazione personalizzati per le cassette postali in blocco.</span><span class="sxs-lookup"><span data-stu-id="1a259-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="1a259-142">Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="1a259-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="1a259-143">[[Passaggio 2: creare un nuovo criterio di conservazione per le cassette postali in blocco](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="1a259-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="1a259-144">Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="1a259-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="1a259-145">Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="1a259-146">Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili</span><span class="sxs-lookup"><span data-stu-id="1a259-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="1a259-p107">Il primo passaggio consiste nel creare un tag di conservazione personalizzato (denominato tag dei criteri di conservazione o RPT) per la cartella elementi ripristinabili. Come spiegato in precedenza, questo RPT sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente alla cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente. È necessario utilizzare PowerShell per creare un RPT per la cartella elementi ripristinabili. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="1a259-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="1a259-151">Connettersi a Exchange Online usando una sessione remota di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a259-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="1a259-152">Eseguire il seguente comando per creare un nuovo RPT nella cartella Elementi ripristinabili: </span><span class="sxs-lookup"><span data-stu-id="1a259-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="1a259-p108">Ad esempio, il seguente comando crea un RPT per la cartella Elementi ripristinabili denominata "Spostamento degli elementi ripristinabili dopo 30 giorni per le cassette postali in blocco", con un periodo di conservazione di 30 giorni. Ciò significa che dopo che un elemento è stato nella cartella Elementi ripristinabili per 30 giorni, viene spostato nella cartella Elementi ripristinabili nella cassetta postale di archiviazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1a259-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="1a259-p109">È consigliabile che il periodo di conservazione (definito dal parametro _AgeLimitForRetention_ ) per gli elementi ripristinabili sia lo stesso del periodo di conservazione per le cassette postali a cui verrà applicato il RPT. In questo modo un utente può recuperare il periodo di conservazione degli elementi eliminati prima che vengano spostati nella cassetta postale di archiviazione. Nell'esempio precedente, il periodo di conservazione è stato impostato su 30 giorni in base all'ipotesi che il periodo di conservazione degli elementi eliminati per le cassette postali sia anche di 30 giorni. Per impostazione predefinita, una cassetta postale di Exchange Online è configurata per mantenere gli elementi eliminati per 14 giorni. Tuttavia, è possibile modificare questa impostazione fino a un massimo di 30 giorni. Per ulteriori informazioni, vedere [modificare il periodo di conservazione degli elementi eliminati per una cassetta postale in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span><span class="sxs-lookup"><span data-stu-id="1a259-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="1a259-161">Passaggio 2: Creazione di nuovi criteri di conservazione per le cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="1a259-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="1a259-p110">Il passaggio successivo consiste nel creare nuovi criteri di conservazione e aggiungere tag di conservazione, inclusi i RPT di elementi ripristinabili creati nel Passaggio 1. I nuovi criteri verranno applicati alle cassette postali in blocco nel passaggio successivo. </span><span class="sxs-lookup"><span data-stu-id="1a259-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="1a259-p111">Prima di creare i nuovi criteri di conservazione, determinare quali tag di conservazione aggiuntivi aggiungere. Per un elenco dei tag di conservazione che vengono aggiunti ai criteri di gestione record di messaggistica predefiniti e per informazioni sulla creazione di nuovi tag di conservazione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a259-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="1a259-166">Criteri di conservazione predefiniti in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1a259-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="1a259-167">Cartelle predefinite che supportano i tag di Criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="1a259-168">La sezione "creare un tag di conservazione" nell'argomento [Create a RetentIon Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="1a259-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="1a259-169">È possibile utilizzare EAC o Exchange Online PowerShell per creare un criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1a259-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="1a259-170">Creazione di un criterio di conservazione tramite l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="1a259-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="1a259-171">Nell'interfaccia di amministrazione di Exchange, accedere a **criteri di conservazione**per la **gestione** \> della conformità](media/ITPro-EAC-AddIcon.gif)e quindi fare clic su **Aggiungi** ![icona Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1a259-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="1a259-172">Nella pagina **Nuovo criterio di conservazione**, in **Nome**, digitare un nome che descriva lo scopo del criterio di conservazione, ad esempio, **MRM Policy for Mailboxes on Hold**. </span><span class="sxs-lookup"><span data-stu-id="1a259-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="1a259-173">In **tag di conservazione**fare \*\*\*\* ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif)icona Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1a259-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="1a259-174">Nell'elenco dei tag di conservazione, selezionare l’elemento RPT di Elementi ripristinabili creato nel Passaggio 1, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1a259-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Selezionare il tag di conservazione Elementi recuperabili personalizzato](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="1a259-p112">Selezionare i tag di conservazione aggiuntivi da aggiungere ai criteri di conservazione. Ad esempio, è possibile aggiungere gli stessi tag inclusi nei criteri di gestione record di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="1a259-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="1a259-178">Dopo aver completato l'aggiunta dei tag di conservazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a259-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="1a259-179">Fare clic su **Salva** per creare i nuovi criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1a259-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="1a259-180">Tenere presente che i tag di conversazione collegati ai criteri di conservazione vengono visualizzati nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="1a259-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![I tag di conversazione collegati al criterio di conservazione vengono visualizzati nel riquadro dei dettagli](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="1a259-182">Utilizzare PowerShell di Exchange Online per creare un criterio di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="1a259-183">Per creare nuovi criteri di conservazione per le cassette postali in blocco, eseguire il seguente comando: </span><span class="sxs-lookup"><span data-stu-id="1a259-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="1a259-184">Il comando seguente, ad esempio, crea il criterio di conservazione e tag di conservazione collegati, come illustrato nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="1a259-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="1a259-185">Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco</span><span class="sxs-lookup"><span data-stu-id="1a259-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="1a259-p113">L'ultimo passaggio consiste nell'applicare i nuovi criteri di conservazione creati nel passaggio 2 alle cassette postali in attesa nell'organizzazione. È possibile utilizzare EAC o Exchange Online PowerShell per applicare il criterio di conservazione a una singola cassetta postale o a più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="1a259-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="1a259-188">Utilizzare EAC per applicare i nuovi criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="1a259-189">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="1a259-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="1a259-190">Nella visualizzazione elenco, selezionare la cassetta postale a cui si desidera applicare il criterio di conservazione, quindi fare \*\*\*\* ![clic su modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)icona modifica.</span><span class="sxs-lookup"><span data-stu-id="1a259-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="1a259-191">Nella pagina **Cassetta postale utente**, fare clic su **Funzionalità delle cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="1a259-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="1a259-192">In **Criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1a259-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="1a259-193">È anche possibile utilizzare EAC per applicare criteri di conservazione a più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="1a259-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="1a259-194">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="1a259-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="1a259-195">Nell'elenco, utilizzare il tasto Maiusc o Ctrl per selezionare più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="1a259-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="1a259-196">Nel riquadro dei dettagli, fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="1a259-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="1a259-197">In **Criterio di conservazione**, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="1a259-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="1a259-198">Nella pagina **Assegna in blocco i criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**. </span><span class="sxs-lookup"><span data-stu-id="1a259-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="1a259-199">Utilizzare PowerShell di Exchange Online per applicare i nuovi criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="1a259-p114">È possibile utilizzare PowerShell di Exchange Online per applicare un nuovo criterio di conservazione a una singola cassetta postale. Tuttavia, il vero potere di PowerShell è che è possibile utilizzarlo per identificare rapidamente tutte le cassette postali dell'organizzazione che si trovano su blocco per controversia legale o sul posto, quindi applicare il nuovo criterio di conservazione a tutte le cassette postali in attesa in un singolo comando. Di seguito sono riportati alcuni esempi di utilizzo di Exchange PowerShell per applicare un criterio di conservazione a una o più cassette postali. In tutti gli esempi viene applicato il criterio di conservazione creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="1a259-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="1a259-204">In questo esempio vengono applicati nuovi criteri di conservazione alla cassetta postale di Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="1a259-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="1a259-205">In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="1a259-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="1a259-206">In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1a259-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="1a259-207">È possibile utilizzare il cmdlet **Get-Mailbox** per verificare che siano stati applicati i nuovi criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1a259-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="1a259-208">Ecco alcuni esempi per verificare che i comandi negli esempi precedenti abbiano applicato i criteri di conservazione "Criteri di gestione record di messaggistica per le cassette postali in blocco" alle cassette postali in blocco per controversia legale e alle cassette postali in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1a259-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="1a259-209">Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione</span><span class="sxs-lookup"><span data-stu-id="1a259-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="1a259-p115">Dopo aver applicato il nuovo criterio di conservazione alle cassette postali in attesa, possono essere necessari fino a 7 giorni in Exchange Online affinché l'Assistente cartelle gestite elabori queste cassette postali utilizzando le impostazioni del nuovo criterio di conservazione. Invece di attendere l'esecuzione dell'Assistente cartelle gestite, è possibile utilizzare il cmdlet **Start-ManagedFolderAssistant** per attivare manualmente l'assistente per elaborare le cassette postali a cui è stato applicato il nuovo criterio di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1a259-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="1a259-212">Eseguire il seguente comando per avviare l'Assistente cartelle gestite per la cassetta postale di Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="1a259-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="1a259-213">Eseguire il seguente comando per avviare l'Assistente cartelle gestite per tutte le cassette postali in blocco.</span><span class="sxs-lookup"><span data-stu-id="1a259-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="1a259-214">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1a259-214">More information</span></span>

- <span data-ttu-id="1a259-p116">Dopo aver abilitato la cassetta postale di archiviazione di un utente, è consigliabile comunicare all'utente che altri elementi della cassetta postale (non solo gli elementi nella cartella elementi ripristinabili) potrebbero essere spostati nella cassetta postale di archiviazione. Ciò è dovuto al fatto che il criterio di gestione record di messaggistica predefinito assegnato alle cassette postali di Exchange Online contiene un tag di conservazione (denominati 2 anni di spostamento in Archivio) che sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento è stato recapitato alla cassetta postale o creato dal utente. Per ulteriori informazioni, vedere [criteri di conservazione predefiniti in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="1a259-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="1a259-p117">Dopo aver abilitato la cassetta postale di archiviazione di un utente, si potrebbe anche informare l'utente che è possibile recuperare gli elementi eliminati nella cartella elementi ripristinabili nella cassetta postale di archiviazione. È possibile eseguire questa operazione in Outlook selezionando la cartella **posta eliminata** nella cassetta postale di archiviazione e quindi facendo clic su **Ripristina elementi eliminati dal server** nella scheda **Home** . Per ulteriori informazioni sul ripristino degli elementi eliminati, vedere [recuperare gli elementi eliminati in Outlook per Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="1a259-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
