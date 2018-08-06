---
title: Conservazione in caso di dispute di una cassetta postale
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'Attivare un blocco per controversia legale in una cassetta postale per conservare tutto il contenuto della cassetta postale, tra cui elementi eliminati e versioni originali degli elementi modificati. '
ms.openlocfilehash: 8f440f5fc0bc7dafd639bdf8136808aa2f3bd35f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026443"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="59dda-103">Conservazione in caso di dispute di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="59dda-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="59dda-p101">Attivare un blocco per controversia legale in una cassetta postale per conservare tutto il contenuto della cassetta postale, tra cui elementi eliminati e versioni originali degli elementi modificati. Quando si attiva un blocco per controversia legale nella cassetta postale di un utente, anche il contenuto della cassetta postale di archiviazione dell'utente (se abilitata) viene messo in attesa. Gli elementi eliminati o modificati vengono conservati per un periodo specificato o fino a quando non viene rimosso il blocco per controversia legale dalla cassetta postale. Tutti questi elementi delle cassette postali vengono restituiti in una ricerca di [eDiscovery in locale](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx).</span><span class="sxs-lookup"><span data-stu-id="59dda-p101">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items. When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold. Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold. All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="59dda-p102">Il blocco per controversia legale conserva gli elementi nella cartella Elementi ripristinabili nella cassetta postale dell'utente.A seconda del numero e della dimensione degli elementi eliminati o modificati, la dimensione della cartella Elementi ripristinabili della cassetta postale potrebbe aumentare rapidamente. Per impostazione predefinita, la cartella Elementi ripristinabili è configurata con una quota elevata. In Exchange Online, questa quota viene aumentata automaticamente quando si attiva un blocco per controversia legale in una cassetta postale. In Exchange Server 2013 si consiglia di monitorare le cassette postali con blocco per controversia legale attivato ogni settimana per verificare non venga raggiunto il limite delle quote di Elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="59dda-p102">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox. Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly. The Recoverable Items folder is configured with a high quota by default. In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold. In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="59dda-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="59dda-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="59dda-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-114"></span></span>

- <span data-ttu-id="59dda-115">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="59dda-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="59dda-116">L'impostazione Blocco per controversia legale potrebbe richiedere fino a 60 minuti per essere effettivo.</span><span class="sxs-lookup"><span data-stu-id="59dda-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="59dda-p103">È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "In-Place Hold" nell'argomento [Messaging policy e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) .</span><span class="sxs-lookup"><span data-stu-id="59dda-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="59dda-p104">Per attivare il blocco per controversia legale in una cassetta postale di Exchange Online, è necessario disporre di una licenza di Exchange Online (Piano 2). Se una cassetta postale dispone di una licenza di Exchange Online (Piano 1), occorre assegnarle una licenza di Exchange Online Archiving distinta per attivare il blocco.</span><span class="sxs-lookup"><span data-stu-id="59dda-p104">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license. If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="59dda-p105">Come descritto in precedenza, quando si esegue un blocco per controversia legale nella cassetta postale dell'utente, anche il contenuto nella cassetta postale di archiviazione dell'utente viene bloccato. Se si attiva un blocco per controversia legale in una cassetta postale principale locale in una distribuzione ibrida di Exchange, viene conservata anche la cassetta postale di archiviazione basata sul cloud (se abilitata).</span><span class="sxs-lookup"><span data-stu-id="59dda-p105">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold. If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="59dda-p106">In Exchange Online, la quota per la cartella Elementi ripristinabili viene automaticamente aumentata a 100 GB quando per una cassetta postale si attiva il blocco per controversia legale. La dimensione predefinita della cartella è 30 GB.</span><span class="sxs-lookup"><span data-stu-id="59dda-p106">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="59dda-p107">Conservazione per controversia legale consente di mantenere gli elementi eliminati e inoltre di mantenere le versioni originali degli elementi modificati fino a quando non viene rimosso l'attesa. È possibile specificare una durata di attesa, che consente di mantenere un elemento della cassetta postale per il periodo di durata specificato. Se si specifica una periodo di durata della conservazione, viene calcolata dalla data di ricezione di un messaggio o viene creato un elemento della cassetta postale. Per conservare gli elementi che soddisfano i criteri specificati, utilizzare an In-Place Hold per creare un'esenzione basata su query. Per ulteriori informazioni, vedere [creare o rimuovere un'archiviazione sul posto](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span><span class="sxs-lookup"><span data-stu-id="59dda-p107">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed. You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period. If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold. For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="59dda-p108">Per attivare un blocco in una cassetta postale di Exchange Online tramite la shell, è necessario utilizzare Exchange Online PowerShell. Per ulteriori informazioni, vedere [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span><span class="sxs-lookup"><span data-stu-id="59dda-p108">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell. For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="59dda-p109">L'impostazione di un blocco per controversia legale su una cassetta postale per le cartelle pubbliche non è supportata. Per applicare un blocco alle cartelle pubbliche, è necessario utilizzare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="59dda-p109">Placing a Litigation Hold on a public folder mailbox isn't supported. You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="59dda-134">Utilizzo dell'interfaccia di amministrazione di Exchange per attivare un blocco per controversia legale in una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="59dda-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="59dda-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-135"></span></span>

1. <span data-ttu-id="59dda-136">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="59dda-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="59dda-137">Nell'elenco delle cassette postali utente, fare clic sulla cassetta postale per cui si desidera attivare il blocco per controversia legale, quindi fare clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="59dda-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="59dda-138">Dalla pagina delle proprietà della cassetta postale, fare clic su **Funzionalità cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="59dda-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="59dda-139">In **Blocco per controversia legale: disabilitato**, fare clic su **Abilita** per attivare il blocco per controversia legale nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="59dda-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="59dda-140">Nella pagina **Blocco per controversia legale**, inserire le seguenti informazioni opzionali:</span><span class="sxs-lookup"><span data-stu-id="59dda-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="59dda-p110">**Durata del blocco per controversia legale (giorni)** Utilizzare questa casella per specificare la durata di conservazione degli elementi della cassetta postale quando viene attivato il blocco per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale. Se si lascia la casella vuota, gli elementi vengono conservati a tempo indeterminato o fino a quando non viene rimossa la conservazione. Usare un numero di giorni per specificare la durata.</span><span class="sxs-lookup"><span data-stu-id="59dda-p110">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="59dda-p111">**Nota** Utilizzare questa casella per informare l'utente che nella sua cassetta postale è attivo il blocco per controversia legale. La nota viene visualizzata nella cassetta postale dell'utente se quest'ultimo utilizza Outlook 2010 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="59dda-p111">**Note** Use this box to inform the user their mailbox is on Litigation Hold. The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="59dda-p112">**URL** Utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sul blocco per controversia legale. Questo URL viene visualizzato nella cassetta postale dell'utente se quest'ultimo utilizza Outlook 2010 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="59dda-p112">**URL** Use this box to direct the user to a website for more information about Litigation Hold. This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="59dda-149">Fare clic su **Salva** nella pagina **Blocco per controversia legale**, quindi fare clic su **Save** nella pagina proprietà della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="59dda-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="59dda-150">Attivare un blocco per controversia legale a tempo indeterminato nella cassetta postale tramite la shell</span><span class="sxs-lookup"><span data-stu-id="59dda-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="59dda-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-151"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="59dda-p113">In questo esempio viene attivato il blocco per controversia legale nella cassetta postale bsuneja@contoso.com. Gli elementi nella cassetta postale vengono conservati a tempo indeterminato o finché non viene rimosso il blocco.</span><span class="sxs-lookup"><span data-stu-id="59dda-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="59dda-154">Quando si attiva un blocco per controversia legale per un tempo indefinito (senza specificarne la durata), il valore della proprietà  _LitigationHoldDuration_ è impostato su  `Unlimited`.</span><span class="sxs-lookup"><span data-stu-id="59dda-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="59dda-155">Utilizzo della shell per attivare il blocco per controversia legale nella cassetta postale e conservare gli elementi per una durata specifica</span><span class="sxs-lookup"><span data-stu-id="59dda-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="59dda-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-156"><a name="sectionSection3"> </a></span></span>

<span data-ttu-id="59dda-157">In questo esempio viene attivato il blocco per controversia legale nella cassetta postale bsuneja@contoso.com e gli elementi vengono conservati per 2555 giorni (circa 7 anni):</span><span class="sxs-lookup"><span data-stu-id="59dda-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="59dda-158">Utilizzo della shell per attivare il blocco per controversia legale in tutte le cassette postali per una durata specifica</span><span class="sxs-lookup"><span data-stu-id="59dda-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="59dda-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-159"><a name="sectionSection4"> </a></span></span>

<span data-ttu-id="59dda-p114">L'organizzazione può richiedere che tutti i dati delle cassette postali siano conservati per un periodo di tempo specifico. Prima di attivare il blocco per controversia legale per tutte le cassette postali nell'organizzazione, considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="59dda-p114">Your organization may require that all mailbox data be preserved for a specific period of time. Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="59dda-162">In questo esempio viene attivato il blocco per controversia legale in tutte le cassette postali utente di un anno (365 giorni).</span><span class="sxs-lookup"><span data-stu-id="59dda-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="59dda-163">In questo esempio viene utilizzato il cmdlet [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) per recuperare tutte le cassette postali nell'organizzazione, si specifica un filtro destinatari per includere tutte le cassette postali utente e viene trasmesso un elenco di cassette postali al cmdlet [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) per attivare il blocco per controversia legale e impostarne la durata.</span><span class="sxs-lookup"><span data-stu-id="59dda-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="59dda-164">Per impostare un blocco indefinito in tutte le cassette postali utente, eseguire il comando precedente senza includere il parametro  _LitigationHoldDuration_.</span><span class="sxs-lookup"><span data-stu-id="59dda-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="59dda-165">Vedere la sezione [Ulteriori informazioni](#moreinfo.md) per esempi relativi all'utilizzo di altre proprietà del destinatario in un filtro per includere o escludere una o più cassette postali.</span><span class="sxs-lookup"><span data-stu-id="59dda-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="59dda-166">Rimozione dalla conservazione in caso di dispute di una cassetta postale tramite shell</span><span class="sxs-lookup"><span data-stu-id="59dda-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="59dda-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-167"><a name="sectionSection5"> </a></span></span>

<span data-ttu-id="59dda-168">In questo esempio, viene rimosso un blocco per controversia legale dalla cassetta postale bsuneja@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="59dda-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="59dda-169">P</span><span class="sxs-lookup"><span data-stu-id="59dda-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="59dda-170">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="59dda-170">How do you know this worked?</span></span>
<span data-ttu-id="59dda-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-171"><a name="sectionSection6"> </a></span></span>

<span data-ttu-id="59dda-172">Per verificare la corretta attivazione di un blocco per controversia legale in una cassetta postale, effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="59dda-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="59dda-173">Nell'interfaccia di amministrazione di Exchange:</span><span class="sxs-lookup"><span data-stu-id="59dda-173">In the EAC:</span></span>
    
1. <span data-ttu-id="59dda-174">Andare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="59dda-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="59dda-175">Nell'elenco delle cassette postali utente, fare clic sulla cassetta postale di cui si desidera verificare le impostazioni del blocco per controversia legale, quindi fare clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="59dda-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="59dda-176">Dalla pagina delle proprietà della cassetta postale, fare clic su **Funzionalità cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="59dda-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="59dda-177">In **Blocco per controversia legale**, verificare che il blocco sia attivato.</span><span class="sxs-lookup"><span data-stu-id="59dda-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="59dda-p115">Fare clic su **Visualizza dettagli** per verificare quando è stato attivato il blocco per controversia legale e da chi. È inoltre possibile verificare o modificare i valori nelle caselle facoltative **Durata del blocco per controversia legale (giorni)**, **Nota** e **URL**.</span><span class="sxs-lookup"><span data-stu-id="59dda-p115">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom. You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="59dda-180">In Shell, utilizzare uno dei seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="59dda-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="59dda-181">oppure</span><span class="sxs-lookup"><span data-stu-id="59dda-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="59dda-182">Se si attiva un blocco per controversia legale per un tempo indefinito, il valore della proprietà  _LitigationHoldDuration_ è impostato su  `Unlimited`.</span><span class="sxs-lookup"><span data-stu-id="59dda-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="59dda-183">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="59dda-183">More information</span></span>
<span data-ttu-id="59dda-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="59dda-184"><a name="moreinfo"> </a></span></span>

- <span data-ttu-id="59dda-185">Se l'organizzazione richiede che tutti i dati delle cassette postali siano conservati per un periodo di tempo specifico, considerare quanto segue prima di attivare il blocco per controversia legale per tutte le cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59dda-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="59dda-p116">Quando si utilizza il comando precedente per attivare un blocco in tutte le cassette postali nell'organizzazione (oppure un set secondario di cassette postali corrispondenti a un filtro destinatario specificato), il blocco viene attivato solo per le cassette postali che esistono al momento dell'esecuzione del comando. Se si creano nuove cassette postali in un secondo momento, sarà necessario eseguire di nuovo il comando per attivare il blocco per le nuove cassette postali. Se si creano spesso nuove cassette postali, è possibile eseguire il comando come attività pianificata secondo la frequenza necessaria.</span><span class="sxs-lookup"><span data-stu-id="59dda-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="59dda-p117">Attivare il blocco per controversia legale in tutte le cassette postali può influire notevolmente sulle dimensioni delle cassette postali. In un'organizzazione Exchange Server 2013, pianificare lo spazio di archiviazione adeguato per soddisfare i requisiti di conservazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59dda-p117">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes. In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="59dda-p118">La cartella Elementi ripristinabili presenta un proprio limite di archiviazione, quindi gli elementi nella cartella non pesano sul limite di archiviazione della cassetta postale. Come spiegato in precedenza, la conservazione dei dati delle cassette postali per un lungo periodo di tempo causa la crescita della cartella Elementi ripristinabili in una cassetta postale e nell'archivio di un utente. Per rendere possibile questo aumento in Exchange Online, la quota per la cartella Elementi ripristinabili viene automaticamente aumentata da 30 GB a 100 GB quando per una cassetta postale si attiva il blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="59dda-p118">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="59dda-p119">In Exchange Server 2013, il limite di archiviazione predefinito per la cartella elementi ripristinabili è anche 30 GB. È consigliabile monitorare periodicamente le dimensioni della cartella per assicurarsi che non raggiunge il limite previsto. Per ulteriori informazioni, vedere [Cartella elementi ripristinabili](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span><span class="sxs-lookup"><span data-stu-id="59dda-p119">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB. We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit. For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="59dda-p120">Il comando precedente per attivare un blocco in tutte e cassette postali utilizza un filtro destinatario che restituisce tutte le cassette postali utente. È possibile utilizzare altre proprietà dei destinatari per un elenco delle cassette postali specifiche che è quindi possibile restituire al cmdlet **Set-Mailbox** per attivare un blocco per controversia legale in tali cassette postali.</span><span class="sxs-lookup"><span data-stu-id="59dda-p120">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes. You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="59dda-p121">Ecco alcuni esempi sull'utilizzo dei cmdlet **Get-Mailbox** e **Get-Recipient** per restituire un set secondario di cassette postali in base alle proprietà comuni di utenti o cassette postali. Tali esempi presumono che le proprietà della cassetta postale rilevante (ad esempio,  _CustomAttributeN_ o  _Department_) siano state popolate.</span><span class="sxs-lookup"><span data-stu-id="59dda-p121">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties. These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    <span data-ttu-id="59dda-p122">È possibile utilizzare altre proprietà della cassetta postale utente in un filtro per escludere o includere le cassette postali. Per ulteriori dettagli, vedere [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span><span class="sxs-lookup"><span data-stu-id="59dda-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

