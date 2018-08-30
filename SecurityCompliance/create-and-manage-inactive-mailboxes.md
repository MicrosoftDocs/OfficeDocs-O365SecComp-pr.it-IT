---
title: Creare e gestire le cassette postali inattive in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: È possibile creare una cassetta postale inattiva in Office 365 applicando una conservazione o criteri di conservazione di Office 365 per la cassetta postale e quindi eliminare l'account utente di Office 365 corrispondente. Gli elementi in una cassetta postale inattiva vengono mantenuti per tutta la durata del criterio di conservazione o conservazione che è stato applicato prima che venga effettuata inattivo. Per eliminare definitivamente una cassetta postale inattiva, rimuove solo i criteri di conservazione o conservazione.
ms.openlocfilehash: ed0af9077222d9151dc41010bca10590769118b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530574"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a><span data-ttu-id="03a4b-105">Creare e gestire le cassette postali inattive in Office 365</span><span class="sxs-lookup"><span data-stu-id="03a4b-105">Create and manage inactive mailboxes in Office 365</span></span>

<span data-ttu-id="03a4b-p102">Office 365 consente di mantenere il contenuto delle cassette postali eliminate. Questa funzionalità è denominata [delle cassette postali inattive](inactive-mailboxes-in-office-365.md). Cassette postali inattive consentono di mantenere posta elettronica ex dipendenti una volta terminata l'organizzazione. Una cassetta postale diventa inattiva quando una conservazione per controversia legale o un criterio di conservazione di Office 365 (creato in Office 365 Security &amp; centro conformità) viene applicato alla cassetta postale prima che venga eliminato l'account utente di Office 365 corrispondente. Il contenuto di una cassetta postale inattiva viene mantenuto per la durata dell'attesa effettuata nella cassetta postale prima che venga effettuata inattivo. In questo modo gli amministratori e responsabili della conformità record Manager utilizzare la ricerca del contenuto per la protezione &amp; centro conformità per cercare ed esportare il contenuto di una cassetta postale inattiva. Cassette postali inattive non possono ricevere posta elettronica e non vengono visualizzate nella Rubrica condivisa dell'organizzazione o altri elenchi.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p102">Office 365 makes it possible for you to retain the contents of deleted mailboxes. This feature is called [inactive mailboxes](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. A mailbox becomes inactive when a Litigation Hold or an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) is applied to the mailbox before the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. This allows administrators, compliance officers, and records managers to use Content Search in the Security &amp; Compliance Center to search and export the contents of an inactive mailbox. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03a4b-p103">Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="03a4b-118">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="03a4b-118">Before you begin</span></span>

- <span data-ttu-id="03a4b-p104">Per rendere inattiva una cassetta postale, è necessario assegnare una licenza di Exchange Online piano 2 in modo che una conservazione per controversia legale o un criterio di conservazione di Office 365 è possibile applicare alla cassetta postale prima che venga eliminato. Le licenze di Exchange Online piano 2 fanno parte di un sottoscrizioni Office 365 Enterprise E3 ed E5. Se una cassetta postale viene assegnata una licenza di Exchange Online piano 1 (che fa parte di una sottoscrizione a Office 365 Enterprise E1), è necessario assegnare una licenza separata archiviazione Exchange Online in modo da un'esenzione può essere applicata alla cassetta postale prima che venga eliminato. Per ulteriori informazioni, vedere [Archiviazione Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p104">To make a mailbox inactive, it must be assigned an Exchange Online Plan 2 license so that a Litigation Hold or an Office 365 retention policy can be applied to the mailbox before it's deleted. Exchange Online Plan 2 licenses are part of an Office 365 Enterprise E3 and E5 subscriptions. If a mailbox is assigned an Exchange Online Plan 1 license (which is part of an Office 365 Enterprise E1 subscription), you would have to assign it a separate Exchange Online Archiving license so that a hold can be applied to the mailbox before it's deleted. For more information, see [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span></span>
    
- <span data-ttu-id="03a4b-p105">La licenza associata alla cassetta postale di Exchange Online eliminata saranno disponibile dopo l'eliminazione di account utente di Office 365 corrispondente. È quindi possibile [assegnare licenze agli utenti di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p105">The license associated with the deleted Exchange Online mailbox will be available after you delete the corresponding Office 365 user account. You can then [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) to another user.</span></span> 
    
- <span data-ttu-id="03a4b-p106">Se non si applica un blocco per controversia legale o un criterio di conservazione di Office 365 a una cassetta postale prima della sua eliminazione, il contenuto non verrà conservato e non potrà essere trovato. Tuttavia, è possibile recuperare la cassetta postale eliminata entro 30 giorni dall'eliminazione; se non viene recuperata entro 30 giorni, la cassetta postale e il suo contenuto vengono eliminati definitivamente.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p106">If a Litigation Hold or an Office 365 retention policy isn't applied to a mailbox before it's deleted, the contents of the mailbox won't be retained or discoverable. However, the deleted mailbox can be recovered within 30 days of deletion, but the mailbox and its contents will be permanently deleted after 30 days if it isn't recovered.</span></span>
    
- <span data-ttu-id="03a4b-p107">Per ulteriori informazioni sulla conservazione per controversia legale, vedere [archiviazione sul posto e conservazione per controversia legale](https://go.microsoft.com/fwlink/p/?LinkId=846124). Per ulteriori informazioni sui criteri di conservazione di Office 365 in sicurezza &amp; centro conformità, vedere [Panoramica di criteri di conservazione in Office 365](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p107">For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). For more information about Office 365 retention policies in the Security &amp; Compliance Center, see [Overview of retention policies in Office 365](retention-policies.md).</span></span>
  
## <a name="create-an-inactive-mailbox"></a><span data-ttu-id="03a4b-129">Creare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-129">Create an inactive mailbox</span></span>

<span data-ttu-id="03a4b-p108">Esecuzione di una cassetta postale inattiva prevede due fasi: 1) effettuare la cassetta postale su conservazione per controversia legale o applicare un criterio di conservazione di Office 365 e 2) eliminazione della cassetta postale o account utente di Office 365 corrispondente. Dopo che la cassetta postale è inattiva, il relativo contenuto viene mantenuto fino a quando non viene rimosso il criterio di conservazione o conservazione.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p108">Making a mailbox inactive involves two steps: 1) placing the mailbox on Litigation Hold or applying an Office 365 retention policy to it, and 2) deleting the mailbox or corresponding Office 365 user account. After the mailbox is inactive, its contents are retained until the hold or retention policy is removed.</span></span>
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a><span data-ttu-id="03a4b-132">Passaggio 1: applicare il blocco per controversia legale a una cassetta postale o applicare un criterio di conservazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="03a4b-132">Step 1: Place a mailbox on Litigation Hold or apply an Office 365 retention policy</span></span>

<span data-ttu-id="03a4b-p109">Applicando a una cassetta postale il blocco per controversia legale o un criterio di conservazione di Office 365, il contenuto viene mantenuto nella cassetta postale prima che venga eliminata. Con entrambi i tipi di blocchi viene conservato tutto il contenuto della cassetta postale, compresi gli elementi eliminati e le versioni originali degli elementi modificati. Gli elementi eliminati e modificati vengono conservati nella cassetta postale inattiva per un determinato periodo oppure finché non viene eliminata definitivamente la cassetta postale inattiva rimuovendo il blocco o i criteri di conservazione applicati alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p109">Placing a mailbox on Litigation Hold or applying an Office 365 retention policy retains the contents in the mailbox before it's deleted. Both types of holds will retain all mailbox content, including deleted items and original versions of modified items. Deleted and modified items are retained in the inactive mailbox for a specified period, or until you permanently delete the inactive mailbox by removing the hold or retention policy that's applied to the inactive mailbox.</span></span>
  
<span data-ttu-id="03a4b-136">Se un blocco è già attivo in una cassetta postale o se un criterio di conservazione di Office 365 è già applicato a una cassetta postale, allora sarà semplicemente necessario eliminare l'account utente di Office 365 corrispondente come descritto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="03a4b-136">If a hold is already placed on a mailbox, or if an Office 365 retention policy is already applied to a mailbox, then all you have to do is delete the corresponding Office 365 user account as explained in Step 2.</span></span>
  
<span data-ttu-id="03a4b-137">Per le procedure dettagliate sull'applicazione del blocco per controversia legale per una cassetta postale o sull'applicazione di un criterio di conservazione di Office 365, vedere:</span><span class="sxs-lookup"><span data-stu-id="03a4b-137">For step-by-step procedures for placing a mailbox on Litigation Hold or applying an Office 365 retention policy, see:</span></span>
  
- [<span data-ttu-id="03a4b-138">Place a mailbox on Litigation Hold</span><span class="sxs-lookup"><span data-stu-id="03a4b-138">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [<span data-ttu-id="03a4b-139">Panoramica dei criteri di conservazione in Office 365</span><span class="sxs-lookup"><span data-stu-id="03a4b-139">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
> [!NOTE]
> <span data-ttu-id="03a4b-p110">Per i blocchi per controversia legale e i criteri di conservazione di Office 365, è possibile creare un blocco indefinito o un blocco con scadenza. In caso di un blocco indefinito, il contenuto della cassetta postale inattiva viene conservato per sempre, finché il blocco non viene rimosso o finché la durata del blocco non viene modificata. Una volta rimosso il blocco o il criterio di conservazione (presumendo che la cassetta postale sia stata eliminata più di 30 giorni prima), la cassetta postale inattiva verrà contrassegnata per l'eliminazione definitiva e il suo contenuto non sarà conservato e non potrà essere trovato. In caso di un criterio di conservazione di Office 365 o di un blocco con scadenza, è necessario specificare la durata del blocco. La durata si applica ai singoli elementi e viene calcolata a partire dalla data in cui ciascun elemento è stato ricevuto o creato. Dopo che il blocco per un elemento della cassetta postale scade e che tale elemento viene spostato o si trova nella cartella Elementi ripristinabili nella cassetta postale inattiva, l'elemento viene definitivamente eliminato (cancellato) dalla cassetta postale inattiva dopo la scadenza del periodo di conservazione dell'elemento eliminato.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p110">For Litigation Holds and Office 365 retention policies, you can create an indefinite hold or on a time-based hold. In an indefinite hold, the contents of the inactive mailbox will be retained forever, or until the hold is removed or until the hold duration is changed. After the hold or retention policy is removed (assuming that the mailbox was deleted more than 30 days ago), the inactive mailbox will be marked for permanent deletion and the contents of the mailbox will no longer be retained or discoverable. In a time-based hold or Office 365 retention policy, you specify the duration of the hold. This duration is on a per-item basis and is calculated from the date a mailbox item was received or created. After the hold expires for a mailbox item, and that item moved to or is located in the Recoverable Items folder in the inactive mailbox, the item is permanently deleted (purged) from the inactive mailbox after the deleted item retention period expires.</span></span> 
  
### <a name="step-2-delete-the-mailbox"></a><span data-ttu-id="03a4b-146">Passaggio 2: Eliminare la cassetta postale</span><span class="sxs-lookup"><span data-stu-id="03a4b-146">Step 2: Delete the mailbox</span></span>

<span data-ttu-id="03a4b-p111">Dopo la cassetta postale viene messa in attesa o viene applicato un criterio di conservazione di Office 365, il passaggio successivo consiste nell'eliminare la cassetta postale. Il modo migliore per eliminare una cassetta postale consiste nell'eliminare l'account utente di Office 365 corrispondente nell'interfaccia di amministrazione di Office 365. Per informazioni sull'eliminazione di account utente di Office 365, vedere [eliminazione di un utente dall'organizzazione](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p111">After the mailbox is placed on hold or an Office 365 retention policy is applied to it, the next step is to delete the mailbox. The best way to delete a mailbox is to delete the corresponding Office 365 user account in the Office 365 admin center. For information about deleting Office 365 user accounts, see [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span></span>
  
> [!NOTE]
> <span data-ttu-id="03a4b-p112">È inoltre possibile eliminare la cassetta postale utilizzando il cmdlet **Remove-Mailbox** in PowerShell di Exchange Online. Per ulteriori informazioni, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p112">You can also delete the mailbox by using the **Remove-Mailbox** cmdlet in Exchange Online PowerShell. For more information, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span></span> 
  

## <a name="view-a-list-of-inactive-mailboxes"></a><span data-ttu-id="03a4b-152">Visualizzare un elenco delle cassette postali inattive</span><span class="sxs-lookup"><span data-stu-id="03a4b-152">View a list of inactive mailboxes</span></span>


<span data-ttu-id="03a4b-153">Per visualizzare un elenco delle cassette postali inattive all'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="03a4b-153">To view a list of the inactive mailboxes in your organization:</span></span>
  
1. <span data-ttu-id="03a4b-154">Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="03a4b-154">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="03a4b-155">Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> * * conservazione * *.</span><span class="sxs-lookup"><span data-stu-id="03a4b-155">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> ** Retention **.</span></span>
    
3. <span data-ttu-id="03a4b-156">Nella pagina **conservazione** fare clic su **altro**![puntini di sospensione barra di spostamento](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), quindi fare clic su **cassette postali inattive**.</span><span class="sxs-lookup"><span data-stu-id="03a4b-156">On the **Retention** page, click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), and then click **Inactive mailboxes**.</span></span>
    
    ![Nella pagina conservazione fare clic su altro e quindi fare clic su cassette postali inattive per visualizzare un elenco di cassette postali inattive](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    <span data-ttu-id="03a4b-p113">Verrà visualizzata la pagina **delle cassette postali inattive** . Nota che viene visualizzato il numero totale di cassette postali inattive all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p113">The **Inactive mailboxes** page is displayed. Note the total number of inactive mailboxes in your organization is displayed.</span></span> 
    
    ![Viene visualizzato un elenco di tutte le cassette postali inattive all'interno dell'organizzazione](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
<span data-ttu-id="03a4b-161">In alternativa, è possibile eseguire il seguente comando in Exchange Online PowerShell per visualizzare l'elenco delle cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="03a4b-161">Alternatively, you can run the following command in Exchange Online PowerShell to display the list of inactive mailboxes.</span></span>

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

<span data-ttu-id="03a4b-162">È possibile fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **esportare** per visualizzare o scaricare un file CSV che contiene informazioni aggiuntive sulle cassette postali inattive all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03a4b-162">You can click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization.</span></span> 
  
<span data-ttu-id="03a4b-p114">È inoltre possibile eseguire il comando seguente per esportare l'elenco delle cassette postali inattive e altre informazioni su un file CSV. In questo esempio viene creato il file CSV nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p114">You can also run the following command to export the list of inactive mailboxes and other information to a CSV file. In this example, the CSV file is created in the current directory.</span></span>

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> <span data-ttu-id="03a4b-p115">È possibile che una cassetta postale inattiva può avere lo stesso indirizzo SMTP come una cassetta postale utente attivo. In questo caso, il valore della proprietà **ExchangeGuid** o **DistinguishedName** utilizzabile per identificare in modo univoco una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p115">It's possible that an inactive mailbox may have the same SMTP address as an active user mailbox. In this case, the value of the **DistinguishedName** or **ExchangeGuid** property can be used to uniquely identify an inactive mailbox.</span></span> 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a><span data-ttu-id="03a4b-167">Ricerca ed esportazione del contenuto di una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-167">Search and export the contents of an inactive mailbox</span></span>

<span data-ttu-id="03a4b-p116">È possibile accedere il contenuto delle cassette postali inattive mediante lo strumento di ricerca del contenuto per la protezione &amp; centro conformità. Quando si esegue la ricerca di una cassetta postale inattiva, è possibile creare la query di ricerca per cercare gli elementi specifici oppure è possibile restituire l'intero contenuto della cassetta postale inattiva. È possibile visualizzare in anteprima i risultati della ricerca o esportare i risultati della ricerca in un file di dati di Outlook (PST) o come messaggi di posta elettronica singolo. Per le procedure dettagliate per la ricerca di cassette postali e l'esportazione dei risultati della ricerca, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="03a4b-p116">You can access the contents of the inactive mailbox by using the Content Search tool in the Security &amp; Compliance Center. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:</span></span>
  
- [<span data-ttu-id="03a4b-172">Ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="03a4b-172">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="03a4b-173">Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="03a4b-173">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
<span data-ttu-id="03a4b-174">Ecco alcuni aspetti da tenere presenti durante la ricerca delle cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="03a4b-174">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="03a4b-175">Se una ricerca di contenuto include una cassetta postale utente e cassetta postale viene quindi rese inattive, ricerca contenuto continua per la ricerca di cassette postali inattive quando si esegue nuovamente la ricerca dopo diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="03a4b-175">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="03a4b-p117">In alcuni casi, un utente può disporre di una cassetta postale attiva e una cassetta postale inattiva che hanno lo stesso indirizzo SMTP. In questo caso, verrà cercata solo la cassetta postale specifica che si seleziona un percorso per una ricerca di contenuto. In altre parole, se si aggiunge una ricerca cassetta postale dell'utente, non è possibile presupporre che verranno eseguita la ricerca cassette postali attive e inattive, solo la cassetta postale aggiunto in modo esplicito per la ricerca verrà eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p117">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="03a4b-p118">È consigliabile evitare di dover delle cassette postali attivi e inattive cassette postali con lo stesso indirizzo SMTP. Se si desidera riutilizzare l'indirizzo SMTP attualmente assegnato a una cassetta postale inattiva, è consigliabile ripristinare la cassetta postale inattiva o ripristinare il contenuto di una cassetta postale inattiva a una cassetta postale attiva (o l'archivio di una cassetta postale attiva) e quindi eliminare il cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="03a4b-p118">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span>
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="03a4b-181">Modificare la durata del blocco per una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-181">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="03a4b-p119">Dopo aver effettuata una cassetta postale inattiva, è possibile modificare la durata della conservazione o il criterio di conservazione di Office 365 applicate a cassette postali inattive. Per le procedure dettagliate, vedere [modificare la durata della conservazione per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p119">After a mailbox is made inactive, you can change the duration of the hold or the Office 365 retention policy applied to the inactive mailbox. For step-by-step procedures, see [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span></span>
  
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="03a4b-184">Recuperare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-184">Recover an inactive mailbox</span></span>

<span data-ttu-id="03a4b-p120">Se un dipendente precedente restituisce all'organizzazione o un nuovo dipendente è stato assunto deve essere eseguita su professionali del dipendente chiusa, è possibile ripristinare il contenuto delle cassette postali inattive. Quando si ripristina una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, vengono mantenuti il contenuto e struttura di cartelle delle cassette postali inattive e la cassetta postale è collegata a un nuovo account utente. Dopo avere recuperato, cassette postali inattive non esiste più. Per ulteriori informazioni e procedure dettagliate avviene quando si ripristina una cassetta postale inattiva, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p120">If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists. For step-by-step procedures and more information about happens when you recover an inactive mailbox, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
  
[<span data-ttu-id="03a4b-189">Gestione di una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-189">Managing inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md#manageinactivemailboxes)
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a><span data-ttu-id="03a4b-190">Ripristinare il contenuto di una cassetta postale inattiva in un'altra cassetta postale</span><span class="sxs-lookup"><span data-stu-id="03a4b-190">Restore the contents of an inactive mailbox to another mailbox</span></span>

<span data-ttu-id="03a4b-p121">Se l'altro impiegato assume la responsabilità di un dipendente precedente o un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva per una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. Cassette postali inattive viene mantenuta e manterrà una cassetta postale inattiva. Cassette postali inattive possono comunque essere ricerca quando si utilizza eDiscovery, è possibile ripristinare il contenuto a un'altra cassetta postale o può essere recuperato o eliminato in un secondo momento. Per le procedure dettagliate, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p121">If another employee takes on the job responsibilities of a former employee, or if another person needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. When you restore an inactive mailbox, the contents are copied to another mailbox. The inactive mailbox is retained and remains an inactive mailbox. The inactive mailbox can still be searched using eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. For step-by-step procedures, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
  
## <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="03a4b-196">Eliminare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="03a4b-196">Delete an inactive mailbox</span></span>

<span data-ttu-id="03a4b-p122">Se non più necessaria mantenere il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente la cassetta postale inattiva la rimozione dell'esenzione o rimuovendo il criterio di conservazione di Office 365 applicato a cassette postali inattive. Se la cassetta postale è stata eliminata più di 30 giorni, la cassetta postale verrà contrassegnata per l'eliminazione definitiva dopo si rimuove il blocco e la cassetta postale diventeranno non ripristinabile. Se è stata eliminata la cassetta postale negli ultimi 30 giorni, è comunque possibile ripristinare la cassetta postale dopo aver rimosso il criterio di conservazione o conservazione. Per le procedure dettagliate per la rimozione di un'esenzione o un criterio di conservazione di Office 365 per eliminare definitivamente una cassetta postale inattiva, vedere [eliminazione di una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="03a4b-p122">If you no longer need to retain the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold or removing the Office 365 retention policy applied to the inactive mailbox. If the mailbox was deleted more than 30 days ago, the mailbox will be marked for permanent deletion after you remove the hold, and the mailbox will become non-recoverable. If the mailbox was deleted within the last 30 days, you can still recover the mailbox after removing the hold or retention policy. For step-by-step procedures for removing a hold or a Office 365 retention policy to permanently delete an inactive mailbox, see [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md).</span></span>