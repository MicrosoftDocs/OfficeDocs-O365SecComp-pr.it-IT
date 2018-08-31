---
title: Mettere an In-Place Hold in una cassetta postale eliminata in Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Informazioni su come creare un'archiviazione sul posto per una cassetta postale eliminata per rendere inattiva e mantenere il relativo contenuto. Quindi è possibile utilizzare gli strumenti di eDiscovery di Microsoft per la ricerca di cassette postali inattive.
ms.openlocfilehash: abc0aa625a5483141f25111dc1858a3d989f32d0
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003115"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="81570-104">Mettere an In-Place Hold in una cassetta postale eliminata in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81570-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="81570-p102">Informazioni su come creare un'archiviazione sul posto per una cassetta postale eliminata per rendere inattiva e mantenere il relativo contenuto. Quindi è possibile utilizzare gli strumenti di eDiscovery di Microsoft per la ricerca di cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="81570-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81570-p103">È stata posticipata la scadenza del 1 ° luglio 2017 per la creazione di nuove archiviazioni sul posto di Exchange Online (in Office 365 ed Exchange Online piani autonomi). Ma più avanti in questo anno o un anno successivo anticipati, non sarà in grado di creare nuove archiviazioni sul posto di Exchange Online. In alternativa all'utilizzo di archiviazione sul posto, è possibile utilizzare i [casi di eDiscovery](https://go.microsoft.com/fwlink/?linkid=780738) o [criteri di conservazione](https://go.microsoft.com/fwlink/?linkid=827811) in Office 365 Security &amp; centro conformità. Dopo che è nuovo rimuovere archiviazioni sul posto, ancora sarà possibile modificare archiviazioni sul posto esistente e la creazione di nuove archiviazioni sul posto di Exchange Server 2013 e le distribuzioni ibride di Exchange continueranno a essere supportate. E ancora sarà in grado di effettuare le cassette postali di conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="81570-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="81570-p104">Potrebbe essere una situazione in cui una persona ha lasciato l'organizzazione e le cassette postali e l'account utente corrispondente sono state eliminate. In un secondo momento, si nota non è presente nella cassetta postale che è necessario mantenere informazioni. Cosa potete fare? Se non è scaduto il periodo di conservazione delle cassette postali eliminate, è possibile inserire un'archiviazione sul posto nella cassetta postale eliminata (noti come una cassetta postale eliminata) e rendere una cassetta postale inattiva. Una *cassetta postale inattiva* viene utilizzato per mantenere la posta elettronica del dipendente precedente dopo potrà lascia l'organizzazione. Il contenuto di una cassetta postale inattiva viene conservato per la durata di In-Place Hold che è stato viene messa nella cassetta postale eliminata quando è stata effettuata inattivo. Dopo aver effettuata la cassetta postale inattiva, è possibile cercare la cassetta postale tramite eDiscovery In locale in Exchange Online, ricerca contenuto in Office 365 Security &amp; centro conformità o il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="81570-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="81570-p105">In Exchange Online, una cassetta postale eliminata è una cassetta postale è stata eliminata, ma è possibile ripristinare entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali eliminate in Exchange Online è 30 giorni. Questo significa che la cassetta postale può essere recuperato (o con una cassetta postale inattiva) entro 30 giorni da eliminare. Dopo 30 giorni, una cassetta postale eliminata è contrassegnata per l'eliminazione definitiva e non può essere ripristinata o rese inattiva.</span><span class="sxs-lookup"><span data-stu-id="81570-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="81570-123">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="81570-123">Before you begin</span></span>
<span data-ttu-id="81570-124"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="81570-124"></span></span>

- <span data-ttu-id="81570-p106">È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per mettere an In-Place Hold in una cassetta postale eliminata. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) oppure il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="81570-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="81570-127">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="81570-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="81570-128">Eseguire il comando seguente per ottenere informazioni sull'identità sulle cassette postali eliminate all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="81570-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="81570-129">Per ulteriori informazioni sulle cassette postali inattive, vedere [Cassette postali inattive in Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).</span><span class="sxs-lookup"><span data-stu-id="81570-129">For more information about inactive mailboxes, see [Inactive mailboxes in Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="81570-130">Mettere an In-Place Hold in una cassetta postale eliminata per effettuare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="81570-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>
<span data-ttu-id="81570-131"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="81570-131"></span></span>

<span data-ttu-id="81570-p107">Utilizzare il cmdlet **New-MailboxSearch** per effettuare una cassetta postale eliminata una cassetta postale inattiva. Per ulteriori informazioni, vedere [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="81570-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="81570-134">Creare una variabile che contiene le proprietà delle cassette postali eliminate.</span><span class="sxs-lookup"><span data-stu-id="81570-134">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
  ```
  $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
  ```

    > [!IMPORTANT]
    > <span data-ttu-id="81570-p108">Nel comando precedente, utilizzare il valore della proprietà **ExchangeGuid** o **DistinguishedName** per identificare la cassetta postale eliminata. Queste proprietà sono univoche per ciascuna cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata potrebbe essere lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="81570-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="81570-p109">Creare an In-Place Hold e inserirli nella cassetta postale eliminata. In questo esempio non viene specificato durata dell'attesa. In questo modo si terrà elementi per un tempo indefinito o fino alla rimozione di cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="81570-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
  
  ```

    <span data-ttu-id="81570-p110">È inoltre possibile specificare un intervallo di tempo di attesa quando si crea l'archiviazione sul posto. In questo esempio contiene gli elementi nella cassetta postale inattiva di circa 7 anni.</span><span class="sxs-lookup"><span data-stu-id="81570-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
  ```

3. <span data-ttu-id="81570-142">Dopo pochi secondi, eseguire uno dei seguenti comandi per verificare che la cassetta postale eliminata una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="81570-142">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly
  ```

    <span data-ttu-id="81570-143">Oppure</span><span class="sxs-lookup"><span data-stu-id="81570-143">Or</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
  ```

## <a name="more-information"></a><span data-ttu-id="81570-144">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="81570-144">More information</span></span>
<span data-ttu-id="81570-145"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="81570-145"></span></span>

<span data-ttu-id="81570-p111">Dopo aver apportato una cassetta postale eliminata una cassetta postale inattiva, esistono diversi modi per che gestire la cassetta postale. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="81570-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="81570-148">Modificare la durata del blocco per una cassetta postale inattiva in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81570-148">Change the hold duration for an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [<span data-ttu-id="81570-149">Recuperare una cassetta postale inattiva in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81570-149">Recover an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [<span data-ttu-id="81570-150">Ripristinare una cassetta postale inattiva in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81570-150">Restore an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [<span data-ttu-id="81570-151">Rimuovere un'esenzione da una cassetta postale inattiva in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81570-151">Remove a hold from an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

