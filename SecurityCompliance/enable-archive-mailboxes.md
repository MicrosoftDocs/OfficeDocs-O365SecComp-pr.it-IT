---
title: Abilitare le cassette postali di archiviazione nel &amp; Centro sicurezza e conformità di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Utilizzare il Centro sicurezza &amp; e conformità di Office 365 per abilitare le cassette postali di archiviazione per supportare i requisiti di conservazione, eDiscovery e blocco dei messaggi dell'organizzazione.
ms.openlocfilehash: 39cd5fd8d7991b787d95e39e4994dc9b0786522c
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341797"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="76b5f-103">Abilitare le cassette postali di archiviazione nel &amp; Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="76b5f-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="76b5f-p101">L'archiviazione in Office 365 (detta anche archiviazione sul posto) fornisce agli utenti un ulteriore spazio di archiviazione per le cassette postali. Dopo aver attivato le cassette postali di archiviazione, gli utenti possono accedere e archiviare i messaggi nelle cassette postali di archiviazione utilizzando Microsoft Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). Gli utenti possono anche spostare o copiare i messaggi tra la cassetta postale principale e la cassetta postale di archiviazione. È inoltre possibile recuperare gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archiviazione utilizzando lo strumento Recupera elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="76b5f-p102">Office 365 fornisce una quantità illimitata di archivio di archiviazione con la funzionalità di archiviazione in espansione automatica. Quando l'archiviazione in espansione automatica è attivata e quindi viene raggiunta la quota di archiviazione iniziale in una cassetta postale di archivio dell'utente, Office 365 aggiunge automaticamente ulteriore spazio di archiviazione. Ciò significa che gli utenti non si esauriranno nello spazio di archiviazione delle cassette postali e non sarà necessario gestire nulla dopo aver inizialmente abilitato la cassetta postale di archiviazione e aver attivato l'espansione automatica dell'archiviazione per l'organizzazione. Per ulteriori informazioni, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="76b5f-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="76b5f-112">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="76b5f-112">Before you begin</span></span>

<span data-ttu-id="76b5f-p103">Per abilitare o disabilitare le cassette postali di archiviazione, è necessario che venga assegnato il ruolo Mail Recipients in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione destinatari e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Se non si visualizza la pagina di **archiviazione** nel centro &amp; sicurezza e conformità, chiedere all'amministratore di assegnare le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="76b5f-116">Abilitazione di una cassetta postale di archiviazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="76b5f-117">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="76b5f-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="76b5f-118">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="76b5f-119">&amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **Archivio**sulla governance \*\*\*\* \> dei dati.</span><span class="sxs-lookup"><span data-stu-id="76b5f-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="76b5f-p104">Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="76b5f-122">Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera abilitare la cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![Fare clic su Abilita nel riquadro dei dettagli dell'utente selezionato per abilitare la cassetta postale di archiviazione](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="76b5f-124">Nel riquadro dei dettagli per l'utente selezionato, fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="76b5f-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="76b5f-p105">Viene visualizzato un messaggio di avviso che indica che se si Abilita la cassetta postale di archiviazione, gli elementi nella cassetta postale dell'utente precedenti al criterio di archiviazione assegnato alla cassetta postale verranno spostati nella nuova cassetta postale di archiviazione. Il criterio di archiviazione predefinito che fa parte del criterio di conservazione assegnato alle cassette postali di Exchange Online sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento è stato recapitato alla cassetta postale o è stato creato dall'utente. Per ulteriori informazioni, vedere la sezione **altre informazioni** in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="76b5f-128">Fare clic su **Sì** per abilitare la cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="76b5f-p106">Potrebbe essere necessario qualche minuto per creare la cassetta postale di archiviazione. Quando viene creata, la **cassetta postale di archiviazione: abilitata** viene visualizzata nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic \*\*\*\* ![su Aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="76b5f-p107">È anche possibile abilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione disabilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Abilita** nel riquadro dei dettagli. </span><span class="sxs-lookup"><span data-stu-id="76b5f-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="76b5f-134">Disabilitazione di una cassetta postale di archiviazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="76b5f-p108">È inoltre possibile utilizzare la pagina di **archiviazione** nel centro &amp; sicurezza e conformità per disabilitare la cassetta postale di archiviazione di un utente. Dopo la disattivazione di una cassetta postale di archiviazione, è possibile riconnetterla alla cassetta postale principale dell'utente entro 30 giorni dalla disattivazione. In questo caso, il contenuto originale della cassetta postale di archiviazione viene ripristinato. Dopo 30 giorni, i contenuti della cassetta postale di archiviazione originale vengono eliminati definitivamente e non possono essere recuperati. Pertanto, se si riabilita l'archivio più di 30 giorni dopo averlo disabilitato, viene creata una nuova cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="76b5f-p109">Si noti che il criterio di archiviazione predefinito assegnato alle cassette postali degli utenti sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento viene recapitato. Se si disattiva la cassetta postale di archiviazione di un utente, non verrà eseguita alcuna azione sugli elementi della cassetta postale e rimarranno nella cassetta postale principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="76b5f-142">Per disabilitare una cassetta postale di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="76b5f-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="76b5f-143">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="76b5f-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="76b5f-144">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="76b5f-145">&amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **Archivio**sulla governance \*\*\*\* \> dei dati.</span><span class="sxs-lookup"><span data-stu-id="76b5f-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="76b5f-p110">Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="76b5f-148">Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera disabilitare la cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="76b5f-149">Nel riquadro dei dettagli, fare clic su **Disabilita**. </span><span class="sxs-lookup"><span data-stu-id="76b5f-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="76b5f-150">Viene visualizzato un messaggio di avviso che indica che avrai 30 giorni per riattivare la cassetta postale di archiviazione e che dopo 30 giorni tutte le informazioni nell'archivio verranno eliminate definitivamente.</span><span class="sxs-lookup"><span data-stu-id="76b5f-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="76b5f-151">Scegliere **Sì** per disabilitare la cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="76b5f-p111">La disattivazione della cassetta postale di archiviazione potrebbe richiedere alcuni istanti. Quando è disabilitata, la **cassetta postale di archiviazione:** disattivata viene visualizzata nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic \*\*\*\* ![su Aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="76b5f-p112">È anche possibile disabilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione abilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Disabilita** nel riquadro dei dettagli. </span><span class="sxs-lookup"><span data-stu-id="76b5f-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="76b5f-157">Utilizzo di PowerShell di Exchange Online per abilitare o disabilitare le cassette postali di archiviazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="76b5f-p113">È inoltre possibile utilizzare PowerShell di Exchange Online per abilitare le cassette postali di archiviazione. Il motivo principale dell'utilizzo di PowerShell è la possibilità di abilitare rapidamente la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="76b5f-p114">Il primo passaggio consiste nel connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="76b5f-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="76b5f-162">Dopo aver effettuato la connessione a Exchange Online, è possibile eseguire i comandi nelle sezioni seguenti per abilitare o disabilitare le cassette postali di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="76b5f-163">Abilitare le cassette postali di archiviazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-163">Enable archive mailboxes</span></span>

<span data-ttu-id="76b5f-164">Per abilitare la cassetta postale di archiviazione per un singolo utente, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="76b5f-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="76b5f-165">Eseguire il seguente comando per abilitare la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione (la cui cassetta postale di archiviazione non è attualmente abilitata).</span><span class="sxs-lookup"><span data-stu-id="76b5f-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="76b5f-166">Disabilitare le cassette postali di archiviazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-166">Disable archive mailboxes</span></span>

<span data-ttu-id="76b5f-167">Per disabilitare la cassetta postale di archiviazione per un singolo utente, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="76b5f-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="76b5f-168">Eseguire il seguente comando per disabilitare la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione (la cui cassetta postale di archiviazione è attualmente abilitata).</span><span class="sxs-lookup"><span data-stu-id="76b5f-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="76b5f-169">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="76b5f-169">More information</span></span>
  
- <span data-ttu-id="76b5f-p115">Le cassette postali di archiviazione consentono a tutti gli utenti di soddisfare i requisiti di conservazione, eDiscovery e mantenimento dell'organizzazione. Ad esempio, è possibile utilizzare i criteri di conservazione di Exchange dell'organizzazione per spostare il contenuto delle cassette postali nella cassetta postale di archiviazione degli utenti. Quando si utilizza lo strumento di ricerca contenuto nel centro &amp; sicurezza e conformità per cercare contenuto specifico in una cassetta postale di un utente, verrà eseguita la ricerca anche nella cassetta postale di archiviazione dell'utente. Inoltre, quando si attiva un blocco per controversia legale o si applica un criterio di conservazione di Office 365 alla cassetta postale di un utente, vengono conservati anche gli elementi della cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="76b5f-p116">Quando una cassetta postale di archiviazione è abilitata, gli utenti possono archiviare i messaggi nella loro cassetta postale di archiviazione. Gli utenti possono accedere alle proprie cassette postali di archiviazione utilizzando Microsoft Outlook e Outlook sul Web. Se si utilizza una di queste applicazioni client, gli utenti possono visualizzare i messaggi nella cassetta postale di archiviazione e spostare o copiare i messaggi tra la cassetta postale principale e la cassetta postale di archiviazione. Gli utenti possono anche recuperare gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archiviazione utilizzando lo strumento Recupera elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="76b5f-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="76b5f-p117">Dopo che le cassette postali di archiviazione sono abilitate, l'organizzazione può usufruire dei criteri di conservazione di Exchange predefiniti (denominati anche criteri di gestione dei record di messaggistica) assegnati automaticamente a tutte le cassette postali. Quando una cassetta postale di archiviazione è abilitata, il criterio di conservazione di Exchange predefinito esegue automaticamente le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76b5f-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="76b5f-180">Sposta gli elementi di almeno due anni dalla cassetta postale principale dell'utente alla cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="76b5f-181">Sposta gli elementi di almeno 14 giorni dalla cartella Elementi ripristinabili nella cassetta postale principale dell'utente alla cartella Elementi ripristinabili nella cassetta postale di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76b5f-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="76b5f-182">Per ulteriori informazioni sulle cassette postali di archiviazione e sui criteri di conservazione di Exchange, vedere:</span><span class="sxs-lookup"><span data-stu-id="76b5f-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="76b5f-183">Tag di conservazione e criteri di conservazione</span><span class="sxs-lookup"><span data-stu-id="76b5f-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="76b5f-184">Criteri di conservazione predefiniti in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76b5f-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="76b5f-185">Configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="76b5f-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
