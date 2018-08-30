---
title: Utilizzo della condivisione controllo nel Registro di controllo di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: "La condivisione è un'attività chiave in SharePoint Online e OneDrive for Business. Gli amministratori ora possono utilizzare Condivisione controllo nel Registro di controllo di Office 365 per determinare la modalità di condivisione utilizzata all'interno dell'organizzazione. "
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530910"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="988a7-104">Utilizzo della condivisione controllo nel Registro di controllo di Office 365</span><span class="sxs-lookup"><span data-stu-id="988a7-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="988a7-p102">La condivisione è un'attività chiave in SharePoint Online e OneDrive for Business e viene ampiamente utilizzata nelle organizzazioni di Office 365. Gli amministratori ora possono utilizzare Condivisione controllo nel Registro di controllo di Office 365 per determinare la modalità di condivisione utilizzata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="988a7-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="988a7-107">Lo schema di condivisione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="988a7-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="988a7-p103">Condivisione (escluso condivisione dei criteri e collegare gli eventi) sono diversi da eventi relativi a file e cartelle in un modo principale: un utente richiede un'azione che ha alcune effetto su un altro utente. Ad esempio, l'utente consente l'accesso utente B in un file. In questo esempio, l'utente è *che agiscono utente* e utente B è l' *utente di destinazione*. Nello schema di File di SharePoint, azione dell'utente operativo interessa solo il file stesso. Quando l'utente apre un file, l'unica informazione necessaria nell'evento **FileAccessed** è l'utente operativo. Per risolvere questo differenza, c'è uno schema separato, denominato *SharePoint condivisione dello schema*, per l'acquisizione di ulteriori informazioni sulla condivisione degli eventi. In questo modo che gli amministratori dispongono di un'analisi più approfondita in cui una risorsa condivisa e l'utente la risorsa deve essere stato condiviso con.</span><span class="sxs-lookup"><span data-stu-id="988a7-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="988a7-115">Lo schema di condivisione sono disponibili due campi aggiuntivi nel Registro di controllo relative alla condivisione degli eventi:</span><span class="sxs-lookup"><span data-stu-id="988a7-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="988a7-116">**TargetUserOrGroupName** - archivia l'UPN o il nome dell'utente di destinazione o del gruppo che una risorsa è stato condiviso con (utente B nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="988a7-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="988a7-117">**TargetUserOrGroupType** - indica se l'utente di destinazione o il gruppo è un membro, Guest, gruppo o Partner.</span><span class="sxs-lookup"><span data-stu-id="988a7-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="988a7-118">Questi due campi, oltre alle altre proprietà di Office 365 schema del Registro di controllo come utente, l'operazione e data poter distinguere brano completo su *quali* condivisi *quali* risorsa utente con *cui* e *quando*.</span><span class="sxs-lookup"><span data-stu-id="988a7-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="988a7-p104">Non esiste un'altra proprietà dello schema che è importante brano della condivisione. La proprietà **EventData** archivia informazioni aggiuntive sulla condivisione degli eventi. Ad esempio, quando un utente condivide un sito con un altro utente, questa operazione viene eseguita aggiungendo l'utente di destinazione a un gruppo di SharePoint. La proprietà **EventData** acquisisce queste informazioni aggiuntive per fornire un contesto per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="988a7-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="988a7-123">Il modello di condivisione e gli eventi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="988a7-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="988a7-p105">La condivisione viene effettivamente definita da tre eventi distinti: **SharingSet**, **SharingInvitationCreated**e **SharingInvitaitonAccepted**. Ecco il flusso di lavoro per gli eventi come condivisione vengono registrati nel Registro di controllo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="988a7-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![Diagramma di flusso del funzionamento di condivisione controllo](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="988a7-p106">Quando un utente (user operativo) può condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for Business) innanzitutto verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nell'elenco dell'organizzazione. Se l'utente di destinazione nella directory dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="988a7-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="988a7-129">Immediatamente consente di assegnare le autorizzazioni utente di destinazione per accedere alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="988a7-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="988a7-130">Invia una notifica di condivisione per l'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="988a7-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="988a7-131">Registra un evento **SharingSet** .</span><span class="sxs-lookup"><span data-stu-id="988a7-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="988a7-132">Se non è un account utente per l'utente di destinazione nell'elenco dell'organizzazione, SharePoint esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="988a7-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="988a7-133">Crea un invito alla condivisione e invia per l'indirizzo di posta elettronica dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="988a7-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="988a7-134">Registra un evento **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="988a7-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="988a7-135">L'evento **SharingInvitationCreated** è sempre più associato esterno o guest condivisione quando l'utente di destinazione non dispone dell'accesso alle risorse che deve essere stato condiviso.</span><span class="sxs-lookup"><span data-stu-id="988a7-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="988a7-p107">Quando l'utente di destinazione accetta l'invito alla condivisione che ha inviato a tali (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e consente di assegnare le autorizzazioni utente di destinazione per accedere alla risorsa. Viene registrate anche informazioni aggiuntive relative all'utente di destinazione, ad esempio l'identità dell'utente che è stato inviato l'invito e l'utente che ha effettivamente accettato l'invito. In alcuni casi, questi utenti (o gli indirizzi di posta elettronica) potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="988a7-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="988a7-139">Come identificare le risorse condivise con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="988a7-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="988a7-p108">Un requisito comune per gli amministratori sta creando un elenco di tutte le risorse condivise con gli utenti all'esterno dell'organizzazione. Utilizzando la condivisione controllo in Office 365, gli amministratori possono ora generare questo elenco. Ecco come.</span><span class="sxs-lookup"><span data-stu-id="988a7-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="988a7-143">Passaggio 1: Ricerca per la condivisione di eventi ed esportare i risultati in un file CSV</span><span class="sxs-lookup"><span data-stu-id="988a7-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="988a7-p109">Il primo passaggio consiste nel cercare nel Registro di controllo di Office 365 per gli eventi di condivisione. Per ulteriori informazioni (tra cui le autorizzazioni necessarie) sulla ricerca nel Registro di controllo, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="988a7-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="988a7-146">Accedere a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="988a7-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="988a7-147">Accedere a Office 365 utilizzando l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="988a7-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="988a7-148">Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini**e quindi fare clic su **ricerca dei registri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="988a7-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="988a7-149">Verrà visualizzata la pagina di **ricerca dei registri di controllo** .</span><span class="sxs-lookup"><span data-stu-id="988a7-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="988a7-150">In **attività**, fare clic su **attività di condivisione** per la ricerca solo per gli eventi di condivisione.</span><span class="sxs-lookup"><span data-stu-id="988a7-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![Tra le attività, selezionare le attività di condivisione](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="988a7-152">Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="988a7-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="988a7-153">Fare clic su **ricerca** per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="988a7-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="988a7-154">Al termine della ricerca in esecuzione e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.</span><span class="sxs-lookup"><span data-stu-id="988a7-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="988a7-155">Dopo aver selezionato l'opzione di esportazione, viene visualizzato un messaggio nella parte inferiore della finestra in cui viene chiesto se aprire o salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="988a7-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="988a7-156">Fare clic su **Salva** \> **Salva** e salvare il file CSV in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="988a7-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="988a7-157">Passaggio 2: Filtrare il file CSV per le risorse condivise con utenti esterni</span><span class="sxs-lookup"><span data-stu-id="988a7-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="988a7-p110">Il passaggio successivo è per filtrare il file CSV per gli eventi **SharingSet** e **SharingInvitationCreated** e visualizzare gli eventi in cui la proprietà **TargetUserOrGroupType** è **Guest**. Si utilizzerà la funzionalità Power Query in Excel per eseguire questa operazione. La procedura seguente viene eseguita in Excel 2016.</span><span class="sxs-lookup"><span data-stu-id="988a7-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="988a7-161">In Excel 2016, aprire una cartella di lavoro vuota.</span><span class="sxs-lookup"><span data-stu-id="988a7-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="988a7-162">Fare clic sulla scheda **Dati**.</span><span class="sxs-lookup"><span data-stu-id="988a7-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="988a7-163">Fare clic su **Nuova Query** \> **dal file** \> **Da CSV**.</span><span class="sxs-lookup"><span data-stu-id="988a7-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![Nella scheda dati selezionare Nuova Query, selezionare file e quindi selezionare da CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="988a7-165">Aprire il file CSV che è stato scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="988a7-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="988a7-p111">Il file CSV viene aperto nell'Editor di Query. Si noti che esistono quattro colonne: **ora**, **utente**, **Azioni**e **tutti i dettagli**. Nella colonna **dei dettagli** è un campo a più proprietà. Il passaggio successivo consiste nel creare una nuova colonna per ogni proprietà della colonna di **tutti i dettagli** .</span><span class="sxs-lookup"><span data-stu-id="988a7-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="988a7-170">Selezionare la colonna di **tutti i dettagli** e quindi nella scheda **Home** fare clic su **Colonna divisa** \> **Da delimitatore**.</span><span class="sxs-lookup"><span data-stu-id="988a7-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![Nella scheda Home fare clic su colonna divisa e quindi fare clic su da delimitatore](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="988a7-172">Nella finestra della **Colonna divisa da delimitatore** , procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="988a7-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="988a7-173">In **Selezionare o immettere delimitatore**, selezionare **virgola**.</span><span class="sxs-lookup"><span data-stu-id="988a7-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="988a7-174">In **divisa**, selezionare **ogni occorrenza della delimitatore**.</span><span class="sxs-lookup"><span data-stu-id="988a7-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="988a7-175">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="988a7-175">Click **OK**.</span></span>
    
    <span data-ttu-id="988a7-p112">Nella colonna **dei dettagli** è suddivisa in più colonne. Ogni nuova colonna è denominato **Detail.1**, **Detail.2**, **Detail.3**e così via. Si noterà che includono il prefisso i valori in ciascuna cella nelle colonne **Detail.n** con il nome della proprietà. ad esempio **Operazione: SharingSet**, **Operazione: SharingInvitationAccepted**e **Operazione: SharingInvitationCreated**.</span><span class="sxs-lookup"><span data-stu-id="988a7-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![La colonna dettagli viene suddiviso in più colonne, uno per ogni proprietà](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="988a7-180">Nella scheda **File** fare clic su **chiudere &amp; carico** per chiudere l'Editor di Query e aprire il file in una cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="988a7-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="988a7-181">Il passaggio successivo consiste nel filtrare il file da visualizzare solo gli eventi **SharingSet** e **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="988a7-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="988a7-182">Passare alla scheda **Home** e quindi selezionare nella colonna **azione** .</span><span class="sxs-lookup"><span data-stu-id="988a7-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="988a7-183">Nella **ordinamento &amp; filtro** elenco a discesa, deselezionare tutte le selezioni effettuate, quindi selezionare **SharingSet** e **SharingInvitationCreated**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="988a7-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="988a7-184">Verranno visualizzate le righe per gli eventi **SharingSet** e **SharingInvitationCreated** .</span><span class="sxs-lookup"><span data-stu-id="988a7-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="988a7-185">Passare alla colonna denominata **Detail.17** (o qualsiasi colonna contiene la proprietà **TargetUserOrGroupType** ) e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="988a7-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="988a7-186">Nella **ordinamento &amp; filtro** elenco a discesa, deselezionare tutte le selezioni effettuate, quindi selezionare **TargetUserOrGroupType:Guest**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="988a7-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="988a7-187">Ora Excel vengono visualizzate le righe per gli eventi **SharingInvitationCreated** e **SharingSet** e dove l'utente di destinazione è esterno all'organizzazione, perché gli utenti esterni vengono identificati dal valore **TargetUserOrGroupType:Guest**.</span><span class="sxs-lookup"><span data-stu-id="988a7-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="988a7-188">Nella tabella seguente vengono illustrati tutti gli utenti dell'organizzazione che le risorse condivise con un utente guest all'interno di un intervallo di date specificato.</span><span class="sxs-lookup"><span data-stu-id="988a7-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![Registro di controllo di condivisione degli eventi in Office 365](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="988a7-190">Anche se non è incluso nella tabella precedente, la colonna **Detail.10** (o qualsiasi colonna contiene la proprietà **ObjectId** ) identifica la risorsa che deve essere stato condiviso con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span><span class="sxs-lookup"><span data-stu-id="988a7-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="988a7-191">Se si desidera identificare quando un utente guest è stato assegnato le autorizzazioni per accedere a una risorsa (in contrapposizione a quelli solo le risorse quello in condivise con loro), ripetere i passaggi 10, 11 e 12 e filtrare i **SharingInvitationAccepted** e **SharingSet **eventi nel passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="988a7-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 
