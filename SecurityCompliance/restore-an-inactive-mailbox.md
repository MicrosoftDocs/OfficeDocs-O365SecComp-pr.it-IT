---
title: Ripristinare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Se un nuovo dipendente o un altro utente deve accedere al contenuto di una cassetta postale inattiva in Office 365, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva per una cassetta postale esistente.
ms.openlocfilehash: e0add2b63a48edc27795143324c83153b15dcf8c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530275"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="c6576-103">Ripristinare una cassetta postale inattiva in Office 365</span><span class="sxs-lookup"><span data-stu-id="c6576-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="c6576-p101">Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se un altro dipendente assume le responsabilità del dipendente rimosso o se quest'ultimo ritorna nell'organizzazione, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente:</span><span class="sxs-lookup"><span data-stu-id="c6576-p101">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="c6576-p102">**Ripristinare una cassetta postale inattiva** Se l'altro dipendente assume le responsabilità di un dipendente rimosso o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Dopo il ripristino, la cassetta postale inattiva viene mantenuta e viene conservata come una cassetta postale inattiva. In questo argomento vengono descritte le procedure per il ripristino di una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="c6576-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="c6576-p103">**Ripristinare una cassetta postale inattiva** Se il dipendente chiusa restituisce all'organizzazione o un nuovo dipendente è stato assunto deve essere eseguita su professionali del dipendente chiusa, è possibile ripristinare il contenuto delle cassette postali inattive. Questo metodo converte le cassette postali inattive in una nuova cassetta postale che include il contenuto delle cassette postali inattive. Dopo avere recuperato, cassette postali inattive non esiste più. Per le procedure dettagliate, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="c6576-p103">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="c6576-114">Vedere la sezione **informazioni** di questo articolo per ulteriori informazioni sulle differenze tra il ripristino e ripristino di una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="c6576-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="c6576-115">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="c6576-115">Before you begin</span></span>

- <span data-ttu-id="c6576-p104">È necessario utilizzare Exchange Online PowerShell per ripristinare una cassetta postale inattiva. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="c6576-p104">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="c6576-119">Eseguire il seguente comando in Exchange Online PowerShell per ottenere informazioni sull'identità per le cassette postali inattive all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6576-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="c6576-120">Utilizzare le informazioni restituite da questo comando per ripristinare una cassetta postale inattiva specifica.</span><span class="sxs-lookup"><span data-stu-id="c6576-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="c6576-121">Per ulteriori informazioni sulle cassette postali inattive, vedere [cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c6576-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="c6576-122">Ripristinare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="c6576-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="c6576-p105">Utilizzare il cmdlet **New-MailboxRestoreRequest** con i parametri  _SourceMailbox_ e  _TargetMailbox_ per ripristinare il contenuto di una cassetta postale inattiva in una cassetta postale esistente. Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span><span class="sxs-lookup"><span data-stu-id="c6576-p105">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="c6576-125">Creare una variabile che contiene le proprietà della cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="c6576-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="c6576-p106">Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="c6576-p106">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="c6576-p107">Ripristinare il contenuto della cassetta postale inattiva in una cassetta postale esistente. Il contenuto della cassetta postale inattiva (cassetta postale di origine) viene unito nelle cartelle corrispondenti nella cassetta postale esistente (cassetta postale di destinazione).</span><span class="sxs-lookup"><span data-stu-id="c6576-p107">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="c6576-p108">In alternativa, è possibile specificare una cartella di primo livello nella cassetta postale di destinazione in cui si desidera ripristinare il contenuto dalla cassetta postale inattiva. Se la cartella di destinazione specificata o la struttura di cartelle di destinazione non esiste già nella cassetta postale di destinazione, viene creata durante il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="c6576-p108">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="c6576-132">Questo esempio consente di copiare elementi e sottocartelle da una cassetta postale inattiva a una cartella denominata "Cassetta postale inattiva" nella struttura di cartelle di primo livello della cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6576-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="c6576-133">Ripristinare l'archivio da una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="c6576-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="c6576-p109">Se una cassetta postale inattiva dispone di una cassetta postale di archiviazione, è anche possibile ripristinarla nella cassetta postale di archiviazione di una cassetta postale esistente. Per ripristinare l'archivio da una cassetta postale inattiva, è necessario aggiungere le opzioni  _SourceIsArchive_ e  _TargetIsAchive_ al comando utilizzato per ripristinare una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="c6576-p109">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="c6576-136">Creare una variabile che contiene le proprietà della cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="c6576-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="c6576-p110">Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="c6576-p110">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="c6576-p111">Ripristinare il contenuto dell'archivio dalla cassetta postale inattiva (archivio di origine) all'archivio di una cassetta postale esistente (archivio di destinazione). In questo esempio, il contenuto dell'archivio di origine viene copiato in una cartella denominata "Archivio della cassetta postale inattiva" nell'archivio della cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6576-p111">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="c6576-141">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c6576-141">More information</span></span>

- <span data-ttu-id="c6576-p112">**Che cos'è la differenza principale tra ripristino e ripristino di una cassetta postale inattiva?** Quando si ripristina una cassetta postale inattiva, la cassetta postale fondamentalmente viene convertita in una nuova cassetta postale, vengono mantenuti il contenuto e struttura di cartelle delle cassette postali inattive e la cassetta postale è collegata a un nuovo account utente. Dopo lo si recupera, cassette postali inattive non esiste più e le modifiche apportate al contenuto nella nuova cassetta postale influirà il contenuto che è stato originariamente in attesa nella cassetta postale inattiva. Al contrario, quando si ripristina una cassetta postale inattiva, semplicemente il contenuto viene copiato in un'altra cassetta postale. Cassette postali inattive sono protetta e rimangono una cassetta postale inattiva. Eventuali modifiche apportate al contenuto nella cassetta postale di destinazione non influisce sul contenuti originali tenuti in cassette postali inattive. Cassette postali inattive possono eseguire la ricerca utilizzando lo [strumento di ricerca del contenuto](run-a-content-search-in-the-security-and-compliance-center.md) in Office 365 Security &amp; centro conformità, è possibile ripristinare il contenuto a un'altra cassetta postale o può essere recuperato o eliminato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="c6576-p112">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Office 365 Security &amp; Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="c6576-p113">**Come si trovano le cassette postali inattive?** Per ottenere un elenco delle cassette postali inattive nell'organizzazione e visualizzare le informazioni utili per il ripristino di una cassetta postale inattiva, è possibile eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="c6576-p113">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="c6576-p114">**Utilizzare un blocco per controversia legale o un criterio di conservazione di Office 365 per mantenere il contenuto della cassetta postale inattiva.** Se si desidera mantenere lo stato di una cassetta postale inattiva dopo averla ripristinata, è possibile applicare alla cassetta postale di destinazione un [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) o un [criterio di conservazione di Office 365](retention-policies.md) prima di ripristinare la cassetta postale inattiva. Ciò impedirà l'eliminazione definitiva degli elementi della cassetta postale inattiva dopo averli ripristinati nella cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6576-p114">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.** If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox. This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="c6576-p115">**Abilita mantenimento nella cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva.** Perché gli elementi della cassetta postale di una cassetta postale inattiva potrebbero essere precedenti, è possibile abilitare mantenimento nella cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva. Quando si inserisce una cassetta postale su conservazione attesa, il criterio di conservazione viene assegnato a tale non elaborato fino a quando non viene rimosso il mantenimento o fino a quando il mantenimento scadere del periodo. In questo modo il proprietario del tempo di cassetta postale di destinazione per gestire i vecchi messaggi dalla cassetta postale inattiva. In caso contrario, il criterio di conservazione potrebbe Elimina i vecchi elementi (o spostare gli elementi di cassetta postale di archiviazione, se abilitato) scaduti in base alle impostazioni di conservazione configurate per la cassetta postale di destinazione. Per ulteriori informazioni, vedere [archiviazione sul posto una cassetta postale su conservazione in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span><span class="sxs-lookup"><span data-stu-id="c6576-p115">**Enable retention hold on the target mailbox before you restore an inactive mailbox.** Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox. When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires. This gives the owner of the target mailbox time to manage old messages from the inactive mailbox. Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox. For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="c6576-p116">**Cosa consente di fare l'opzione AllowLegacyDNMismatch?** Negli esempi precedenti sul ripristino di una cassetta postale inattiva, l'opzione **AllowLegacyDNMismatch** viene utilizzata per consentire il ripristino della cassetta postale inattiva in una cassetta postale di destinazione diversa. In un comune scenario di ripristino, l'obiettivo è quello di ripristinare il contenuto in cui le cassette postali di origine e di destinazione sono la stessa cassetta postale. In questo caso, per impostazione predefinita, il cmdlet **New-MailboxRestoreRequest** consente di verificare che il valore della proprietà **LegacyExchangeDN** per le cassette postali di origine e di destinazione sia lo stesso. Ciò impedisce di ripristinare accidentalmente una cassetta postale di origine nella cassetta postale di destinazione errata. Se si tenta di ripristinare una cassetta postale inattiva senza l'utilizzo dell'opzione **AllowLegacyDNMismatch**, il comando potrebbe avere esito negativo se le cassette postali di origine e di destinazione presentano valori diversi per la proprietà **LegacyExchangeDN**.</span><span class="sxs-lookup"><span data-stu-id="c6576-p116">**What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="c6576-p117">**È possibile utilizzare altri parametri con il cmdlet New-MailboxRestoreRequest per implementare scenari di ripristino diversi per le cassette postali inattive.** Ad esempio, è possibile eseguire questo comando per ripristinare l'archivio dalla cassetta postale inattiva nella cassetta postale principale della cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6576-p117">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="c6576-168">È inoltre possibile ripristinare la cassetta postale principale inattiva nell'archivio della cassetta postale di destinazione eseguendo questo comando.</span><span class="sxs-lookup"><span data-stu-id="c6576-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="c6576-p118">**Cosa consente di fare il parametro TargetRootFolder?** Come descritto in precedenza, è possibile utilizzare il parametro **TargetRootFolder** per specificare una cartella nel livello superiore della struttura della cartella (denominato anche radice) nella cassetta postale di destinazione in cui ripristinare il contenuto della cassetta postale inattiva. Se non si utilizza questo parametro, gli elementi della cassetta postale inattiva vengono uniti in cartelle predefinite corrispondenti della cassetta postale di destinazione e le cartelle personalizzate vengono ricreate nella radice della cassetta postale di destinazione. Le seguenti illustrazioni evidenziano le differenze nell'utilizzo o meno del parametro **TargetRootFolder**.</span><span class="sxs-lookup"><span data-stu-id="c6576-p118">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="c6576-173">**Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder non viene utilizzato**</span><span class="sxs-lookup"><span data-stu-id="c6576-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![Schermata visualizzata quando non viene utilizzato il parametro TargetRootFolder](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="c6576-175">**Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder viene utilizzato**</span><span class="sxs-lookup"><span data-stu-id="c6576-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![Schermata visualizzata quando viene utilizzato il parametro TargetRootFolder](media/300da592-7323-48db-b8a4-07012259d113.png)

  
