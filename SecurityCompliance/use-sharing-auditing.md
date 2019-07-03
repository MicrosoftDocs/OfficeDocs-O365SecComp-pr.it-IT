---
title: Controllare la condivisione per identificare risorse condivise con utenti esterni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: "La condivisione è un'attività chiave in SharePoint Online e OneDrive for business. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione. "
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435241"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="999b5-104">Controllare la condivisione per identificare risorse condivise con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="999b5-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="999b5-105">La condivisione è un'attività chiave in SharePoint Online e OneDrive for business ed è ampiamente utilizzata nelle organizzazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="999b5-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="999b5-106">Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="999b5-107">Lo schema di condivisione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="999b5-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="999b5-108">La condivisione di eventi (esclusi i criteri di condivisione e gli eventi di collegamento di condivisione) è diversa dagli eventi relativi a file e cartelle in un unico modo principale: un utente esegue un'azione che ha effetti su un altro utente.</span><span class="sxs-lookup"><span data-stu-id="999b5-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="999b5-109">Ad esempio, l'utente A consente all'utente B di accedere a un file.</span><span class="sxs-lookup"><span data-stu-id="999b5-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="999b5-110">In questo esempio, l'utente A rappresenta l'utente che *agisce* e l'utente B è l' *utente di destinazione*.</span><span class="sxs-lookup"><span data-stu-id="999b5-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="999b5-111">Nello schema dei file di SharePoint, l'azione dell'utente che agisce ha effetto solo sul file stesso.</span><span class="sxs-lookup"><span data-stu-id="999b5-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="999b5-112">Quando un utente apre un file, le uniche informazioni necessarie per l' \*\*\*\* evento fileaccessed sono gli utenti che agiscono.</span><span class="sxs-lookup"><span data-stu-id="999b5-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="999b5-113">Per risolvere questa differenza, è disponibile uno schema distinto, denominato *schema di condivisione di SharePoint*, che acquisisce ulteriori informazioni sulla condivisione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="999b5-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="999b5-114">In questo modo gli amministratori avranno maggiori informazioni su chi ha condiviso una risorsa e l'utente con cui è stata condivisa la risorsa.</span><span class="sxs-lookup"><span data-stu-id="999b5-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="999b5-115">Nello schema di condivisione sono disponibili due campi aggiuntivi nel log di controllo relativi agli eventi di condivisione:</span><span class="sxs-lookup"><span data-stu-id="999b5-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="999b5-116">**TargetUserOrGroupName** – archivia l'UPN o il nome dell'utente o del gruppo di destinazione a cui è stata condivisa una risorsa (utente B nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="999b5-116">**TargetUserOrGroupName** – Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="999b5-117">**TargetUserOrGroupType** – identifica se l'utente o il gruppo di destinazione è un membro, un ospite, un gruppo o un partner.</span><span class="sxs-lookup"><span data-stu-id="999b5-117">**TargetUserOrGroupType** – Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="999b5-118">Questi due campi, oltre ad altre proprietà dallo schema del registro di controllo di Office 365, ad esempio l'utente, l'operazione e la data, possono \*\* raccontare la storia \*\* completa dell'utente che ha condiviso la risorsa con *chi* e *quando*.</span><span class="sxs-lookup"><span data-stu-id="999b5-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="999b5-119">È presente un'altra proprietà dello schema che è importante per la storia della condivisione.</span><span class="sxs-lookup"><span data-stu-id="999b5-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="999b5-120">La proprietà **EventData** archivia ulteriori informazioni sulla condivisione di eventi.</span><span class="sxs-lookup"><span data-stu-id="999b5-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="999b5-121">Ad esempio, quando un utente condivide un sito con un altro utente, questo viene ottenuto aggiungendo l'utente di destinazione a un gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="999b5-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="999b5-122">La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire il contesto per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="999b5-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="999b5-123">Il modello di condivisione di SharePoint e gli eventi di condivisione</span><span class="sxs-lookup"><span data-stu-id="999b5-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="999b5-124">La condivisione è definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**.</span><span class="sxs-lookup"><span data-stu-id="999b5-124">Sharing is defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="999b5-125">Di seguito viene illustrato il flusso di lavoro per la modalità di registrazione degli eventi di condivisione nel registro di controllo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="999b5-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![Diagramma di flusso di come funziona la condivisione del controllo](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="999b5-127">Quando un utente (l'utente che agisce) desidera condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for business) prima verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nella directory dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="999b5-128">Se l'utente di destinazione si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="999b5-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="999b5-129">Assegna immediatamente le autorizzazioni utente di destinazione per l'accesso alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="999b5-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="999b5-130">Invia una notifica di condivisione all'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="999b5-131">Registra un evento **SharingSet** .</span><span class="sxs-lookup"><span data-stu-id="999b5-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="999b5-132">Se un account utente per l'utente di destinazione non si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="999b5-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="999b5-133">Crea un invito alla condivisione e lo invia all'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="999b5-134">Registra un evento **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="999b5-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="999b5-135">L'evento **SharingInvitationCreated** è sempre associato alla condivisione esterna o Guest quando l'utente di destinazione non ha accesso alla risorsa condivisa.</span><span class="sxs-lookup"><span data-stu-id="999b5-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="999b5-136">Quando l'utente di destinazione accetta l'invito di condivisione inviato a tali utenti (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e assegna le autorizzazioni utente di destinazione per l'accesso alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="999b5-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="999b5-137">Vengono inoltre registrate informazioni aggiuntive sull'utente di destinazione, ad esempio l'identità dell'utente a cui è stato inviato l'invito e l'utente che ha effettivamente accettato l'invito.</span><span class="sxs-lookup"><span data-stu-id="999b5-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="999b5-138">In alcuni casi, questi utenti (o indirizzi di posta elettronica) potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="999b5-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="999b5-139">Come identificare le risorse condivise con gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="999b5-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="999b5-140">Un requisito comune per gli amministratori consiste nella creazione di un elenco di tutte le risorse condivise con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="999b5-141">Utilizzando la condivisione del controllo in Office 365, gli amministratori possono ora generare questo elenco.</span><span class="sxs-lookup"><span data-stu-id="999b5-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="999b5-142">Ecco come fare.</span><span class="sxs-lookup"><span data-stu-id="999b5-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="999b5-143">Passaggio 1: cercare gli eventi di condivisione ed esportare i risultati in un file CSV</span><span class="sxs-lookup"><span data-stu-id="999b5-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="999b5-144">Il primo passaggio consiste nell'eseguire una ricerca nel registro di controllo di Office 365 per la condivisione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="999b5-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="999b5-145">Per ulteriori informazioni (incluse le autorizzazioni necessarie) per la ricerca nel registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="999b5-145">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="999b5-146">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="999b5-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="999b5-147">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="999b5-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="999b5-148">Nel riquadro sinistro del Centro sicurezza & conformità fare clic su ricerca \*\*\*\*  > **log di controllo**di ricerca.</span><span class="sxs-lookup"><span data-stu-id="999b5-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="999b5-149">Viene visualizzata la pagina di **ricerca del registro di controllo** .</span><span class="sxs-lookup"><span data-stu-id="999b5-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="999b5-150">In **attività**fare clic su **condivisione e accesso alle attività richieste** per cercare gli eventi relativi alla condivisione.</span><span class="sxs-lookup"><span data-stu-id="999b5-150">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![In attività selezionare condivisione e accesso alle attività richieste](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="999b5-152">Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati entro quel periodo.</span><span class="sxs-lookup"><span data-stu-id="999b5-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="999b5-153">Fare clic su **Cerca** per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="999b5-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="999b5-154">Al termine dell'esecuzione della ricerca e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.</span><span class="sxs-lookup"><span data-stu-id="999b5-154">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="999b5-155">Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene richiesto di aprire o salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="999b5-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="999b5-156">Fare clic su **Salva** \> con **nome** e salvare il file CSV in una cartella del computer locale.</span><span class="sxs-lookup"><span data-stu-id="999b5-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="999b5-157">Passaggio 2: filtrare il file CSV per le risorse condivise con gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="999b5-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="999b5-158">Il passaggio successivo consiste nel filtrare il CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e per visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**.</span><span class="sxs-lookup"><span data-stu-id="999b5-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="999b5-159">Per eseguire questa operazione, è possibile utilizzare lo strumento Power query editor in Excel.</span><span class="sxs-lookup"><span data-stu-id="999b5-159">You use the Power Query Editor tool in Excel to do this.</span></span> <span data-ttu-id="999b5-160">Per istruzioni dettagliate, vedere [esportazione, configurazione e visualizzazione dei record del registro di controllo](export-view-audit-log-records.md).</span><span class="sxs-lookup"><span data-stu-id="999b5-160">For step-by-step instructions, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span> 

<span data-ttu-id="999b5-161">Dopo aver seguito le istruzioni riportate nell'argomento precedente per preparare il file CSV, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="999b5-161">After you've followed the instructions in the previous topic to prepare the CSV file, do the following:</span></span>
    
1. <span data-ttu-id="999b5-162">Aprire il file CSV preparato con l'editor di query di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="999b5-162">Open the CSV file that you prepared with the Power Query Editor.</span></span> 

2. <span data-ttu-id="999b5-163">Nella scheda **Home** fare clic su **Ordina & filtro**, quindi fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="999b5-163">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="999b5-164">Nell'elenco a discesa **ordina & filtro** nella colonna **operazioni** deselezionare tutte le selezioni, quindi selezionare **SharingSet** e **SharingInvitationCreated**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="999b5-164">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="999b5-165">Excel Visualizza le righe per gli eventi **SharingSet** e **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="999b5-165">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
4. <span data-ttu-id="999b5-166">Passare alla colonna denominata **TargetUserOrGroupType** e selezionarla.</span><span class="sxs-lookup"><span data-stu-id="999b5-166">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="999b5-167">Nell'elenco a discesa **ordina & filtro** , deselezionare tutte le selezioni, quindi selezionare **TargetUserOrGroupType: Guest**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="999b5-167">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="999b5-168">Ora Excel Visualizza le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e in cui l'utente di destinazione si trova all'esterno dell'organizzazione, perché gli utenti esterni sono identificati dal valore **TargetUserOrGroupType: Guest**.</span><span class="sxs-lookup"><span data-stu-id="999b5-168">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="999b5-169">Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che hanno condiviso le risorse con un utente Guest all'interno di un intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="999b5-169">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Condivisione di eventi nel registro di controllo di Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="999b5-171">Anche se non è incluso nella tabella precedente, la proprietà **ObjectID** identifica la risorsa condivisa con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span><span class="sxs-lookup"><span data-stu-id="999b5-171">Although it's not included in the previous table, the **ObjectId** property identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="999b5-172">Se si desidera identificare quando un utente ospite è stato effettivamente assegnato le autorizzazioni per l'accesso a una risorsa (anziché solo le risorse che condividono con essi), ripetere i passaggi 2, 3 e 4 e filtrare su **SharingInvitationAccepted** e **SharingSet** eventi nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="999b5-172">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 2, 3, and 4, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 5.</span></span> 
