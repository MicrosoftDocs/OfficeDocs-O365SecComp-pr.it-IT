---
title: Abilitare l'archiviazione illimitata in Office 365 - della Guida di amministrazione
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: "Per gli amministratori: informazioni su come abilitare l'espansione automatica archiviazione in Office 365, che consente agli utenti con archiviazione illimitata per le cassette postali di Exchange Online. È possibile abilitare l'espansione automatica di archiviazione per l'intera organizzazione o semplicemente per utenti specifici."
ms.openlocfilehash: 6dd49433a1692d3a0ba23af57e7e2d9544f8a2b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530218"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="8e7d7-104">Abilitare l'archiviazione illimitata in Office 365 - della Guida di amministrazione</span><span class="sxs-lookup"><span data-stu-id="8e7d7-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="8e7d7-p102">È possibile utilizzare la funzionalità di archiviazione Exchange Online espansione automatica in Office 365 per abilitare lo spazio di archiviazione illimitata per cassette postali di archiviazione. Quando è attivata l'espansione automatica di archiviazione, ulteriore spazio di archiviazione viene automaticamente aggiunto alla cassetta postale di archivio dell'utente quando si avvicina al limite di archiviazione. Il risultato è la capacità di archiviazione delle cassette postali illimitato. È possibile attivare l'archiviazione per tutti gli utenti dell'organizzazione o solo per utenti specifici l'espansione automatica. Per ulteriori informazioni sull'espansione automatica di archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8e7d7-110">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="8e7d7-110">Before you begin</span></span>

- <span data-ttu-id="8e7d7-p103">È necessario essere un amministratore globale dell'organizzazione Office 365 o un membro del gruppo di ruoli Gestione organizzazione nell'organizzazione Exchange Online per abilitare l'espansione automatica archiviazione per l'intera organizzazione o per utenti specifici. In alternativa, è necessario essere membri del gruppo di ruoli che è assegnato il ruolo destinatari di posta elettronica per consentire l'espansione automatica di archiviazione per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="8e7d7-p104">Cassetta postale di archivio dell'utente deve essere abilitata per poter abilitare l'espansione automatica di archiviazione. Un utente deve essere assegnato una licenza di Exchange Online piano 2 per abilitare la cassetta postale di archivio. Se un utente viene assegnato una licenza di Exchange Online piano 1, è necessario assegnarli una licenza separata archiviazione Exchange Online per consentire loro cassetta postale di archivio. Vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="8e7d7-p105">È inoltre possibile utilizzare PowerShell per abilitare cassette postali di archiviazione. Vedere la sezione [informazioni](#more-information) per un esempio del comando PowerShell che è possibile utilizzare per abilitare cassette postali di archiviazione per tutti gli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="8e7d7-p106">L'espansione automatica archiviazione inoltre supporta le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="8e7d7-p107">È possibile utilizzare l'interfaccia di amministrazione di Exchange o la sicurezza &amp; centro conformità per abilitare l'espansione automatica archiviazione. È necessario utilizzare Exchange Online PowerShell. Per connettersi all'organizzazione Exchange Online tramite remote PowerShell, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="8e7d7-124">Abilitare l'espansione automatica archiviazione per l'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="8e7d7-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="8e7d7-p108">È possibile abilitare l'espansione automatica di archiviazione per l'intera organizzazione. Dopo aver attivarlo, espansione automatica archiviazione verrà abilitata per le cassette postali utente esistenti e le nuove cassette postali degli utenti creati. Quando si creano nuove cassette postali utente, è necessario abilitare cassetta postale di archivio principale dell'utente in modo che la caratteristica archiviazione espansione automatica funzionerà per la nuova cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="8e7d7-128">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e7d7-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="8e7d7-129">Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'espansione automatica archiviazione per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="8e7d7-130">Abilitare l'espansione automatica archiviazione per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="8e7d7-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="8e7d7-p109">Anziché consentire l'espansione automatica di archiviazione per tutti gli utenti nell'organizzazione, è possibile solo abilitarla per utenti specifici. È possibile utilizzare questo perché solo ad alcuni utenti potrebbero essere necessario per un archivio di archiviazione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="8e7d7-133">Quando si abilita l'espansione automatica di archiviazione per un utente specifico, vengono apportate anche le modifiche di due configurazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e7d7-133">When you enable auto-expanding archiving for a specific user, the following two configurations changes are also made:</span></span>
  
- <span data-ttu-id="8e7d7-134">La quota di archiviazione per la cassetta postale di archivio principale dell'utente viene aumentata a 10 GB (da 100 GB a 110 GB).</span><span class="sxs-lookup"><span data-stu-id="8e7d7-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span>
    
- <span data-ttu-id="8e7d7-p110">La quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale dell'utente viene aumentata a 10 GB (anche da 100 GB a 110 GB). Questa modifica è applicabile solo se la cassetta postale in attesa.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p110">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). This change is applicable only if the mailbox in on hold.</span></span>
    
<span data-ttu-id="8e7d7-p111">In questo spazio aggiuntivo viene aggiunto per evitare problemi di archiviazione che possono verificarsi prima che viene eseguito il provisioning dell'archivio di espansione automatica. Si noti che ulteriore spazio di archiviazione spazio *non è* aggiunto quando si abilita l'espansione automatica archiviazione per l'intera organizzazione, come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p111">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="8e7d7-139">Connessione a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e7d7-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="8e7d7-p112">Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'espansione automatica archiviazione per un utente specifico. Come indicato in precedenza, è necessario abilitare cassetta postale di archivio dell'utente (archivio principale) prima che è possibile attivare l'archiviazione per tale utente l'espansione automatica.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p112">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="8e7d7-p113">In una distribuzione ibrida di Exchange, è possibile utilizzare il comando **Enable-Mailbox AutoExpandingArchive** per abilitare l'archiviazione per specifici di un utente la cui cassetta postale principale è locale l'espansione automatica e delle relative cassette postali di archiviazione sono basata su cloud. Per abilitare l'espansione automatica archiviazione delle cassette postali di archiviazione basata su cloud in una distribuzione ibrida di Exchange, è necessario eseguire il comando **Set-OrganizationConfig AutoExpandingArchive** di Exchange Online PowerShell per abilitare l'espansione automatica archiviazione l'intera organizzazione. Se un utente del principale e cassette postali di archiviazione sono basate su cloud, è possibile utilizzare il comando **Enable-Mailbox AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per l'utente specifico.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p113">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="8e7d7-145">Verificare che sia abilitata l'espansione automatica di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8e7d7-145">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="8e7d7-146">Per verificare che l'espansione automatica archiviazione sia abilitato per l'organizzazione, eseguire il seguente comando in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-146">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="8e7d7-147">Un valore pari a `True` indica che l'espansione automatica di archiviazione è abilitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-147">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="8e7d7-148">Per verificare che l'espansione automatica archiviazione sia attiva per un utente specifico, eseguire il seguente comando in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-148">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="8e7d7-149">Un valore pari a `True` indica che l'espansione automatica di archiviazione è abilitata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-149">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="8e7d7-150">Dopo aver abilitato l'espansione automatica di archiviazione, tenere presenti i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="8e7d7-150">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="8e7d7-p114">Se si esegue il comando **Set-OrganizationConfig AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per l'organizzazione, non è necessario eseguire **Enable-Mailbox AutoExpandingArchive** per singole cassette postali. Si noti che l'esecuzione del cmdlet **Set-OrganizationConfig** per abilitare l'espansione automatica archiviazione per l'organizzazione non modifica la proprietà *AutoExpandingArchiveEnabled* cassette postali degli utenti a `True`.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p114">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="8e7d7-p115">Analogamente, i valori delle proprietà della cassetta postale *ArchiveQuota* e *ArchiveWarningQuota* non vengono modificati quando si abilita l'espansione automatica archiviazione. In realtà, quando si abilita l'espansione automatica archiviazione per una cassetta postale utente e la proprietà *AutoExpandingArchiveEnabled* è impostata su `True`, le proprietà *ArchiveQuota* e *ArchiveWarningQuota* appena vengono ignorate. Di seguito è riportato un esempio di queste proprietà della cassetta postale dopo l'espansione automatica archiviazione è abilitata per la cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p115">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![ArchiveQuota e ArchiveWarningQuota vengono ignorate dopo aver abilitato l'espansione automatica di archiviazione](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="8e7d7-157">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8e7d7-157">More information</span></span>

- <span data-ttu-id="8e7d7-p116">È inoltre possibile utilizzare PowerShell per abilitare cassette postali di archiviazione. Ad esempio, è possibile eseguire il comando seguente in Exchange Online PowerShell per abilitare cassette postali di archiviazione per tutti gli utenti la cui cassetta postale di archiviazione non è già abilitato.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p116">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="8e7d7-p117">Dopo aver attivato l'espansione automatica di archiviazione per l'organizzazione o di un utente specifico, una cassetta postale di archiviazione viene convertita in un archivio per l'espansione automatica quando la cassetta postale di archiviazione (inclusi la cartella elementi ripristinabili) raggiunge 90 GB. Può richiedere fino a 30 giorni per lo spazio di archiviazione aggiuntiva effettuare il provisioning.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p117">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="8e7d7-162">Dopo aver attivato l'archiviazione l'espansione automatica, non può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-162">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="8e7d7-p118">L'espansione automatica di archiviazione è supportato per le cassette postali di archiviazione basata su cloud in una distribuzione ibrida di Exchange per gli utenti che dispongono di una cassetta postale principale in locale. Tuttavia, dopo l'espansione automatica di archiviazione è abilitata per una cassetta postale di archiviazione basata sul cloud, è non può disattivare-area tale cassetta postale di archivio back all'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p118">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="8e7d7-165">Per un elenco dei client di Outlook che gli utenti possono utilizzare per accedere agli elementi nell'area di ulteriore spazio di archiviazione nella cassetta postale di archiviazione, vedere la sezione "Requisiti di Outlook per accedere agli elementi in un archivio espanse automaticamente" in [Overview of illimitato archiviazione in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) .</span><span class="sxs-lookup"><span data-stu-id="8e7d7-165">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="8e7d7-p119">Come spiegato in precedenza, per la quota di archiviazione della cassetta postale di archivio principale dell'utente viene aggiunto 10 GB (e per la cartella elementi recuperabili se la cassetta postale è in attesa) quando si esegue il comando **AutoExpandingArchive Enable-Mailbox** . In tal modo spazio di archiviazione aggiuntivo fino a quando non lo spazio di archiviazione automatica espansa viene effettuato il provisioning (che può richiedere fino a 30 giorni). Questo ulteriore spazio di archiviazione non viene aggiunto durante l'esecuzione di **Set-OrganizationConfig AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per tutte le cassette postali nell'organizzazione. Se è abilitata l'espansione automatica di archiviazione per l'intera organizzazione, ma è necessario aggiungere altri 10 GB di spazio di archiviazione per un utente specifico, è possibile eseguire il comando **Enable-Mailbox AutoExpandingArchive** nella cassetta postale. Si noti che verrà visualizzato un errore indicante che espansione automatica è già stata abilitata l'archiviazione, ma lo spazio di archiviazione aggiuntivo verrà aggiunto alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="8e7d7-p119">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 