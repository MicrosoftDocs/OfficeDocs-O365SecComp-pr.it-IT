---
title: Controllare la condivisione per identificare risorse condivise con utenti esterni
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
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
ms.openlocfilehash: 919592bff43379b552b83258c7b22b7eddb14e7a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219886"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="6cd70-104">Controllare la condivisione per identificare risorse condivise con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6cd70-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="6cd70-p102">La condivisione è un'attività chiave in SharePoint Online e OneDrive for business ed è ampiamente utilizzata nelle organizzazioni di Office 365. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo di Office 365 per determinare la modalità di utilizzo della condivisione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="6cd70-107">Lo schema di condivisione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6cd70-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="6cd70-p103">La condivisione di eventi (esclusi i criteri di condivisione e gli eventi di collegamento di condivisione) è diversa dagli eventi relativi a file e cartelle in un unico modo principale: un utente esegue un'azione che ha effetti su un altro utente. Ad esempio, l'utente A consente all'utente B di accedere a un file. In questo esempio, l'utente A rappresenta l'utente che *agisce* e l'utente B è l' *utente di destinazione*. Nello schema dei file di SharePoint, l'azione dell'utente che agisce ha effetto solo sul file stesso. Quando un utente apre un file, le uniche informazioni necessarie per l' \*\*\*\* evento fileaccessed sono gli utenti che agiscono. Per risolvere questa differenza, è disponibile uno schema distinto, denominato *schema di condivisione di SharePoint*, che acquisisce ulteriori informazioni sulla condivisione degli eventi. In questo modo gli amministratori avranno maggiori informazioni su chi ha condiviso una risorsa e l'utente con cui è stata condivisa la risorsa.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="6cd70-115">Nello schema di condivisione sono disponibili due campi aggiuntivi nel log di controllo relativi agli eventi di condivisione:</span><span class="sxs-lookup"><span data-stu-id="6cd70-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="6cd70-116">**TargetUserOrGroupName** -archivia l'UPN o il nome dell'utente o del gruppo di destinazione a cui è stata condivisa una risorsa (utente B nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="6cd70-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="6cd70-117">**TargetUserOrGroupType** -identifica se l'utente o il gruppo di destinazione è un membro, un ospite, un gruppo o un partner.</span><span class="sxs-lookup"><span data-stu-id="6cd70-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="6cd70-118">Questi due campi, oltre ad altre proprietà dallo schema del registro di controllo di Office 365, ad esempio l'utente, l'operazione e la data, possono \*\* raccontare la storia \*\* completa dell'utente che ha condiviso la risorsa con *chi* e *quando*.</span><span class="sxs-lookup"><span data-stu-id="6cd70-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="6cd70-p104">È presente un'altra proprietà dello schema che è importante per la storia della condivisione. La proprietà **EventData** archivia ulteriori informazioni sulla condivisione di eventi. Ad esempio, quando un utente condivide un sito con un altro utente, questo viene ottenuto aggiungendo l'utente di destinazione a un gruppo di SharePoint. La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire il contesto per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="6cd70-123">Il modello di condivisione di SharePoint e gli eventi di condivisione</span><span class="sxs-lookup"><span data-stu-id="6cd70-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="6cd70-p105">La condivisione è in realtà definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**. Di seguito viene illustrato il flusso di lavoro per la modalità di registrazione degli eventi di condivisione nel registro di controllo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![Diagramma di flusso di come funziona la condivisione del controllo](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="6cd70-p106">Quando un utente (l'utente che agisce) desidera condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for business) prima verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nella directory dell'organizzazione. Se l'utente di destinazione si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cd70-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="6cd70-129">Assegna immediatamente le autorizzazioni utente di destinazione per l'accesso alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="6cd70-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="6cd70-130">Invia una notifica di condivisione all'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6cd70-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="6cd70-131">Registra un evento **SharingSet** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="6cd70-132">Se un account utente per l'utente di destinazione non si trova nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cd70-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="6cd70-133">Crea un invito alla condivisione e lo invia all'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6cd70-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="6cd70-134">Registra un evento **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6cd70-135">L'evento **SharingInvitationCreated** è sempre associato alla condivisione esterna o Guest quando l'utente di destinazione non ha accesso alla risorsa condivisa.</span><span class="sxs-lookup"><span data-stu-id="6cd70-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="6cd70-p107">Quando l'utente di destinazione accetta l'invito di condivisione inviato a tali utenti (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e assegna le autorizzazioni utente di destinazione per l'accesso alla risorsa. Vengono inoltre registrate informazioni aggiuntive sull'utente di destinazione, ad esempio l'identità dell'utente a cui è stato inviato l'invito e l'utente che ha effettivamente accettato l'invito. In alcuni casi, questi utenti (o indirizzi di posta elettronica) potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="6cd70-139">Come identificare le risorse condivise con gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6cd70-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="6cd70-p108">Un requisito comune per gli amministratori consiste nella creazione di un elenco di tutte le risorse condivise con utenti esterni all'organizzazione. Utilizzando la condivisione del controllo in Office 365, gli amministratori possono ora generare questo elenco. Ecco come fare.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="6cd70-143">Passaggio 1: cercare gli eventi di condivisione ed esportare i risultati in un file CSV</span><span class="sxs-lookup"><span data-stu-id="6cd70-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="6cd70-p109">Il primo passaggio consiste nell'eseguire una ricerca nel registro di controllo di Office 365 per la condivisione degli eventi. Per ulteriori informazioni (incluse le autorizzazioni necessarie) sulla ricerca nel registro di controllo, vedere [Search the audit log in the Office 365 &amp; Security Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6cd70-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="6cd70-146">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="6cd70-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="6cd70-147">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6cd70-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="6cd70-148">Nel riquadro sinistro del Centro sicurezza &amp; e conformità fare clic su \*\*ricerca &amp; \*\*e quindi su **Ricerca log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="6cd70-149">Viene visualizzata la pagina di **ricerca del registro di controllo** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="6cd70-150">In **attività**fare clic su **Condivisione attività** per eseguire la ricerca solo per la condivisione di eventi.</span><span class="sxs-lookup"><span data-stu-id="6cd70-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![In attività selezionare Condivisione attività](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="6cd70-152">Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati entro quel periodo.</span><span class="sxs-lookup"><span data-stu-id="6cd70-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="6cd70-153">Fare clic su **Cerca** per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="6cd70-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="6cd70-154">Al termine dell'esecuzione della ricerca e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="6cd70-155">Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene richiesto di aprire o salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="6cd70-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="6cd70-156">Fare clic su **Salva** \> con **nome** e salvare il file CSV in una cartella del computer locale.</span><span class="sxs-lookup"><span data-stu-id="6cd70-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="6cd70-157">Passaggio 2: filtrare il file CSV per le risorse condivise con gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6cd70-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="6cd70-p110">Il passaggio successivo consiste nel filtrare il CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e per visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**. Per eseguire questa operazione, è possibile utilizzare la funzionalità Power query in Excel. In Excel 2016 viene eseguita la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="6cd70-161">In Excel 2016 aprire una cartella di lavoro vuota.</span><span class="sxs-lookup"><span data-stu-id="6cd70-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="6cd70-162">Fare clic sulla scheda **Dati**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="6cd70-163">Fare clic su **nuova query** \> **da file** \> **da CSV**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![Nella scheda dati selezionare nuova query, selezionare da file e quindi fare clic su da CSV.](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="6cd70-165">Aprire il file CSV scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="6cd70-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="6cd70-p111">Il file CSV viene aperto nell'editor di query. Si noti che sono presenti quattro colonne: **ora**, **utente**, **azione**e **dettaglio**. La colonna **dettaglio** è un campo con più proprietà. Il passaggio successivo consiste nel creare una nuova colonna per ognuna delle proprietà nella colonna **dettaglio** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="6cd70-170">Selezionare la colonna **dettaglio** e quindi nella scheda **Home** fare clic su **Suddividi colonna** \> **per**delimitatore.</span><span class="sxs-lookup"><span data-stu-id="6cd70-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![Nella scheda Home fare clic su Suddividi colonna e quindi su delimitatore](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="6cd70-172">Nella finestra **Suddividi in base** al delimitatore eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cd70-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="6cd70-173">In **Seleziona o immetti**delimitatore, \*\*\*\* seleziona virgola.</span><span class="sxs-lookup"><span data-stu-id="6cd70-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="6cd70-174">In **Split**selezionare **a ogni occorrenza del**delimitatore.</span><span class="sxs-lookup"><span data-stu-id="6cd70-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="6cd70-175">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-175">Click **OK**.</span></span>
    
    <span data-ttu-id="6cd70-p112">La colonna **dettaglio** è suddivisa in più colonne. Ogni nuova colonna è denominata **dettaglio. 1**, **dettaglio. 2**, **dettaglio. 3**e così via. Si noterà che i valori di ogni cella nelle colonne **detail. n** sono preceduti dal nome della proprietà. ad esempio, **Operation: SharingSet**, **Operation: SharingInvitationAccepted**e **Operation: SharingInvitationCreated**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![La colonna dettaglio è suddivisa in più colonne, una per ogni proprietà](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="6cd70-180">Nella scheda **file** fare clic su **Chiudi &amp; caricamento** per chiudere l'editor di query e aprire il file in una cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="6cd70-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="6cd70-181">Il passaggio successivo consiste nel filtrare il file in modo da visualizzare solo gli eventi **SharingSet** e **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="6cd70-182">Passare alla scheda **Home** e quindi selezionare la colonna **azione** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="6cd70-183">Nell'elenco a discesa \*\* &amp; Ordina filtro\*\* deselezionare tutte le selezioni, quindi selezionare **SharingSet** e **SharingInvitationCreated**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="6cd70-184">Excel Visualizza le righe per gli eventi **SharingSet** e **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="6cd70-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="6cd70-185">Passare alla colonna denominata **detail. 17** (o qualsiasi colonna contenente la proprietà **TargetUserOrGroupType** ) e selezionarla.</span><span class="sxs-lookup"><span data-stu-id="6cd70-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="6cd70-186">Nell'elenco a discesa **Ordina &amp; filtro** deselezionare tutte le selezioni, quindi selezionare **TargetUserOrGroupType: Guest**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="6cd70-187">Ora Excel Visualizza le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e in cui l'utente di destinazione si trova all'esterno dell'organizzazione, perché gli utenti esterni sono identificati dal valore **TargetUserOrGroupType: Guest**.</span><span class="sxs-lookup"><span data-stu-id="6cd70-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="6cd70-188">Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che hanno condiviso le risorse con un utente Guest all'interno di un intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="6cd70-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Condivisione di eventi nel registro di controllo di Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="6cd70-190">Anche se non è incluso nella tabella precedente, la colonna **detail. 10** (o qualsiasi colonna contiene la proprietà **ObjectID** ) identifica la risorsa condivisa con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span><span class="sxs-lookup"><span data-stu-id="6cd70-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="6cd70-191">Se si desidera identificare quando un utente ospite è stato effettivamente assegnato le autorizzazioni per l'accesso a una risorsa (anziché solo le risorse che condividono con essi), ripetere i passaggi 10, 11 e 12 e filtrare su **SharingInvitationAccepted** e \*\*SharingSet \*\*eventi nel passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="6cd70-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
