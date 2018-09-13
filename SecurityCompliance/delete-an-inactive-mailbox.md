---
title: Eliminare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Quando non più necessaria mantenere il contenuto di una cassetta postale inattiva di Office 365, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo l'attesa. Dopo aver rimosso il blocco, cassette postali inattive sono contrassegnata per l'eliminazione e viene eliminata definitivamente dopo l'elaborazione.
ms.openlocfilehash: a7284be650d7ec6c89a6fdc43d8614603d6f1e19
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965253"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="1de95-104">Eliminare una cassetta postale inattiva in Office 365</span><span class="sxs-lookup"><span data-stu-id="1de95-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="1de95-p102">Una cassetta postale inattiva viene utilizzata per mantenere la posta elettronica del dipendente precedente dopo potrà lascia l'organizzazione. Quando non più necessaria mantenere il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo l'attesa. Inoltre, è possibile che più conservazioni possono essere messa in una cassetta postale inattiva. Ad esempio una cassetta postale inattiva può essere messa in conservazione per controversia legale e in uno o più archiviazioni sul posto. Inoltre, un criterio di conservazione di Office 365 (creato in Office 365 Security &amp; centro conformità) potrebbe essere applicato alla cassetta postale inattiva. È necessario rimuovere tutte le esenzioni e criteri di conservazione di Office 365 da una cassetta postale inattiva eliminata. Dopo aver rimosso le esenzioni e i criteri di conservazione, le cassette postali inattive sono contrassegnata per l'eliminazione e viene eliminata definitivamente dopo l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1de95-p102">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Additionally, an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) might be applied to the inactive mailbox. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1de95-p103">Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="1de95-117">Vedere la sezione [Ulteriori informazioni](delete-an-inactive-mailbox.md#moreinfo) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-117">See the [More information](delete-an-inactive-mailbox.md#moreinfo) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="1de95-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1de95-118">Before you begin</span></span>

- <span data-ttu-id="1de95-p104">È necessario utilizzare Exchange Online PowerShell per rimuovere una conservazione per controversia legale di una cassetta postale inattiva. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). È possibile utilizzare Exchange Online PowerShell o EAC per rimuovere un'archiviazione sul posto da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-p104">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="1de95-p105">Prima di rimuovere la conservazione e di eliminare una cassetta postale inattiva, è possibile copiare il contenuto di una cassetta postale inattiva a un'altra cassetta postale. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1de95-p105">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox. For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="1de95-p106">Se si rimuove l'esenzione o criteri di conservazione di Office 365 da una cassetta postale inattiva e il periodo di conservazione delle cassette postali eliminate per la cassetta postale è scaduto, verrà eliminata definitivamente la cassetta postale. Dopo l'eliminazione, non può essere annullata. Prima di rimuovere la conservazione, assicurarsi che non è più necessario il contenuto nella cassetta postale. Se si desidera riattivare una cassetta postale inattiva, è possibile recuperarla. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1de95-p106">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted. After it's deleted, it can't be recovered. Before you remove the hold, be sure that you no longer need the contents in the mailbox. If you want to re-activate an inactive mailbox, you can recover it. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="1de95-130">Per ulteriori informazioni sulle cassette postali inattive, vedere [cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1de95-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="1de95-131">Passaggio 1: identificare i blocchi su una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="1de95-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="1de95-p107">Come affermato in precedenza, potrebbe essere applicato un blocco per controversia legale, un blocco sul posto o un criterio di conservazione di Office 365 su una cassetta postale inattiva. Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="1de95-134">Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1de95-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="1de95-p108">Il valore di **True** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva ha un blocco per controversia legale. Se in una cassetta postale inattiva è abilitato un blocco sul posto, il GUID del blocco viene visualizzato come il valore per la proprietà **InPlaceHolds**. Ad esempio, i risultati seguenti per due cassette postali inattive mostrano che un blocco per controversia legale è applicato ad Ann Beebe e che due blocchi sul posto sono applicati a Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="1de95-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="1de95-p109">Se una quantità elevata di archiviazione sul posto è incluso in una cassetta postale inattiva, verrà visualizzati non tutti i GUID di conservazione In locale. È possibile eseguire il comando seguente per visualizzare tutti i GUID di conservazione In locale:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="1de95-p109">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed. You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="1de95-140">Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="1de95-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="1de95-p110">Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel rimuovere i blocchi sulla cassetta postale. Come descritto in precedenza, è necessario rimuovere tutti i blocchi per eliminare definitivamente una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="1de95-143">Rimozione di un blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="1de95-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="1de95-p111">Come descritto in precedenza, è necessario utilizzare Windows PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando riportato di seguito per rimuovere un blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="1de95-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="1de95-p112">Il modo migliore per identificare una cassetta postale inattiva è utilizzando il valore del relativo nome distinto o del GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata.</span><span class="sxs-lookup"><span data-stu-id="1de95-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="1de95-149">Rimozione dei blocchi sul posto</span><span class="sxs-lookup"><span data-stu-id="1de95-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="1de95-150">Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva:</span><span class="sxs-lookup"><span data-stu-id="1de95-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="1de95-151">**Eliminare l'oggetto di tipo In-Place Hold** Se la cassetta postale inattiva che si desidera eliminare in modo permanente è l'unica cassetta postale di origine per an In-Place Hold, è possibile eliminare l'oggetto di tipo In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="1de95-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1de95-p113">È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1de95-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="1de95-154">**Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="1de95-155">Utilizzare EAC per eliminare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="1de95-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="1de95-p114">Se si conosce il nome del blocco sul posto che si desidera eliminare, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva che si desidera eliminare definitivamente. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="1de95-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="1de95-159">In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="1de95-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="1de95-160">Selezionare l'archiviazione sul posto da eliminare e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="1de95-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="1de95-161">Nella **In-Place eDiscovery &amp; attesa** le proprietà di pagina, fare clic su **Archiviazione sul posto**, deselezionare la casella di controllo **contenuto locale che corrispondono alla query di ricerca di cassette postali selezionate in attesa** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1de95-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="1de95-162">Nel **In-Place eDiscovery &amp; attesa** di pagina, selezionare In-Place Hold e quindi fare clic su **Elimina**![sull'icona cestino](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="1de95-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="1de95-163">Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="1de95-164">Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="1de95-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="1de95-p115">Creare una variabile che contiene le proprietà del blocco sul posto che si desidera eliminare. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="1de95-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="1de95-167">Disattivare il blocco in Blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="1de95-168">Eliminare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="1de95-169">Usare EAC per rimuovere una cassetta postale inattiva da un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="1de95-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="1de95-p116">Se si conosce il nome del blocco sul posto che si desidera applicare alla cassetta postale inattiva, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="1de95-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="1de95-173">In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="1de95-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="1de95-174">Selezionare l'archiviazione sul posto che viene inserito nella cassetta postale inattiva e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span><span class="sxs-lookup"><span data-stu-id="1de95-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="1de95-175">Nella **In-Place eDiscovery &amp; attesa** proprietà pagina fare clic su **origini**.</span><span class="sxs-lookup"><span data-stu-id="1de95-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="1de95-176">Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="1de95-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="1de95-p117">Fare clic su **Salva** per salvare la modifica. Verrà visualizzato un messaggio che indica che l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1de95-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="1de95-179">Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="1de95-180">Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="1de95-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="1de95-p118">Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="1de95-p119">Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).</span><span class="sxs-lookup"><span data-stu-id="1de95-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="1de95-186">Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="1de95-p120">**Nota:** La proprietà *origini* dell'archiviazione sul posto identifica le cassette postali di origine per le relative proprietà *LegacyExchangeDN* . Poiché questa proprietà identifica in modo univoco cassette postali inattive, tramite la proprietà *origini* da In-Place Hold aiuta a prevenire rimozione della cassetta postale di un problema. In questo modo per evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP.</span><span class="sxs-lookup"><span data-stu-id="1de95-p120">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="1de95-p121">Rimuovere la cassetta postale inattiva dall'elenco delle cassette postali di origine nella variabile. Assicurarsi di usare il **LegacyExchangeDN** della cassetta postale inattiva restituito dal comando nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1de95-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="1de95-192">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine nella variabile.</span><span class="sxs-lookup"><span data-stu-id="1de95-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="1de95-193">Modificare il blocco sul posto con l'elenco aggiornato delle cassette postali di origine, che non include la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="1de95-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="1de95-194">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="1de95-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="1de95-195">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1de95-195">More information</span></span>

- <span data-ttu-id="1de95-p122">**Una cassetta postale inattiva è un tipo di cassetta postale con eliminazione temporanea.** In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, una cassetta postale con eliminazione temporanea viene contrassegnata per l'eliminazione definitiva e non può essere ripristinata.</span><span class="sxs-lookup"><span data-stu-id="1de95-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="1de95-p123">**Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?** La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni. Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva. Questa è nota come data di eliminazione temporanea, che è la data in cui l'account utente di Office 365 corrispondente è stato eliminato o in cui la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox**. La data di eliminazione temporanea non è la data in cui si rimuove il blocco.</span><span class="sxs-lookup"><span data-stu-id="1de95-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="1de95-p124">**Una cassetta postale inattiva viene eliminata definitivamente subito dopo la rimozione del blocco?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima, la cassetta postale non viene eliminata definitivamente non appena si rimuove il blocco. La cassetta postale viene contrassegnata per l'eliminazione definitiva e viene eliminata la volta successiva che viene elaborata.</span><span class="sxs-lookup"><span data-stu-id="1de95-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="1de95-p125">**In che modo il periodo di conservazione della cassetta postale eliminata influisce delle cassette postali inattive?** Se la data di eliminazione reversibile per una cassetta postale inattiva è più di 30 giorni prima della data che dell'esenzione è stato rimosso, la cassetta postale è contrassegnata per l'eliminazione definitiva. Ma se una cassetta postale inattiva è una data eliminate negli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione della cassetta postale eliminata. Per ulteriori informazioni, vedere [eliminazione o ripristino cassette postali degli utenti di Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Dopo la scadenza del periodo di conservazione cassetta postale eliminata, si dispone seguire le procedure per recuperare una cassetta postale inattiva. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1de95-p125">**How does the soft-deleted mailbox retention period affect inactive mailboxes?** If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion. But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires. For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="1de95-p126">**Come procedere per visualizzare informazioni su una cassetta postale inattiva dopo la rimozione?** Dopo che è stata rimossa un'esenzione e cassette postali inattive viene ripristinata in una cassetta postale eliminata, non viene restituito utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox** . Ma è possibile visualizzare informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox SoftDeletedMailbox** . Per esempio:</span><span class="sxs-lookup"><span data-stu-id="1de95-p126">**How do you display information about an inactive mailbox after the hold is removed?** After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet. But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command. For example:</span></span> 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
<span data-ttu-id="1de95-p127">Nell'esempio precedente, la proprietà *WhenSoftDeleted* identifica la data di eliminazione reversibile, ovvero in questo esempio il 30 ottobre 2014. Se questa cassetta postale eliminata in precedenza era una cassetta postale inattiva per il quale è stata rimossa la conservazione, sarà eliminati definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted* . In questo caso, la cassetta postale viene eliminata definitivamente dopo 30 novembre 2014.</span><span class="sxs-lookup"><span data-stu-id="1de95-p127">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014. If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property. In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

