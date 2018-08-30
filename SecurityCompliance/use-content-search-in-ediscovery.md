---
title: Utilizzare la ricerca di contenuto nel flusso di lavoro di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Utilizzare uno script di PowerShell per creare una ricerca eDiscovery In locale in Exchange Online basato su una ricerca creata in Office 365 Security &amp; centro conformità. '
ms.openlocfilehash: d2f4f845e8c819eed67c3a234bff208a11fb571c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530862"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="015c8-103">Utilizzare la ricerca di contenuto nel flusso di lavoro di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="015c8-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="015c8-p101">La funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità consente di cercare tutte le cassette postali nell'organizzazione. A differenza di eDiscovery In locale in Exchange Online (in cui è possibile cercare fino a 10.000 cassette postali), non esistono limiti per il numero di cassette postali di destinazione in una singola ricerca. Per gli scenari che richiedono è possibile eseguire ricerche a livello di organizzazione, è possibile utilizzare ricerca contenuto per la ricerca di tutte le cassette postali. Quindi è possibile utilizzare le funzionalità del flusso di lavoro di eDiscovery In locale per eseguire altre attività relative a eDiscovery, quali cassette postali di posizionamento in attesa e risultati della ricerca di esportazione. Si supponga, ad esempio, che è necessario cercare tutte le cassette postali per identificare depositari specifici che sono rispondono a una controversia legale. È possibile utilizzare ricerca contenuto nella protezione &amp; centro conformità per la ricerca di tutte le cassette postali nell'organizzazione per identificare quelle risponde al caso. È quindi possibile utilizzare tale elenco delle cassette postali depositaria come cassette postali di origine per una ricerca eDiscovery In locale in Exchange Online. Utilizzo di eDiscovery In locale consente inoltre di creare un'esenzione su tali cassette postali di origine, copiare i risultati della ricerca in una cassetta postale di individuazione ed esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-p101">The Content Search feature in the Office 365 Security &amp; Compliance Center allows you to search all mailboxes in your organization. Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search. For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes. Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results. For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case. You can use Content Search in the Security &amp; Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case. Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online. Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="015c8-p102">In questo argomento include uno script che è possibile eseguire per creare una ricerca eDiscovery In locale in Exchange Online mediante l'elenco delle cassette postali di origine e di query di ricerca da una ricerca nella sicurezza &amp; centro conformità. Di seguito viene fornita una panoramica del processo:</span><span class="sxs-lookup"><span data-stu-id="015c8-p102">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security &amp; Compliance Center. Here's an overview of the process:</span></span>
  
[<span data-ttu-id="015c8-114">Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="015c8-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="015c8-115">Passaggio 2: Connessione per la protezione &amp; centro conformità ed Exchange Online in una singola sessione di PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="015c8-115">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="015c8-116">Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="015c8-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="015c8-117">Passaggio 4: avviare la ricerca eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="015c8-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="015c8-118">Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="015c8-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="015c8-p103">Il primo passaggio consiste nell'utilizzare la sicurezza &amp; centro conformità (o sicurezza e conformità centro PowerShell) per creare una ricerca di contenuto per la ricerca di tutte le cassette postali nell'organizzazione. Non esiste alcun limite per il numero di cassette postali per una singola ricerca contenuto. Consente di specificare una query con parole chiave appropriato (o una query per i tipi di informazioni riservate) in modo che la ricerca restituisce solo le cassette postali di origine rilevanti per le indagini. Se necessario, ridefinire la query di ricerca per restringere l'ambito dei risultati di ricerca e cassette postali di origine che vengono restituite.</span><span class="sxs-lookup"><span data-stu-id="015c8-p103">The first step is to use the Security &amp; Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization. There's no limit for the number of mailboxes for a single Content Search. Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation. If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="015c8-p104">Se la ricerca di contenuto di origine non restituisce risultati, non viene creata una ricerca eDiscovery sul posto quando si esegue lo script indicato al passaggio 3. Potrebbe essere necessario rivedere la query di ricerca ed eseguire di nuovo la ricerca di contenuto per ottenere dei risultati.</span><span class="sxs-lookup"><span data-stu-id="015c8-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="015c8-125">Utilizzare la protezione &amp; centro conformità per la ricerca di tutte le cassette postali</span><span class="sxs-lookup"><span data-stu-id="015c8-125">Use the Security &amp; Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="015c8-126">[Passare alla protezione di Office 365 &amp; centro conformità](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="015c8-126">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="015c8-127">Fare clic su **ricerca &amp; indagini**, fare clic su **ricerca contenuto**e quindi fare clic su **Nuovo** ![sull'icona Aggiungi](media/O365-MDM-CreatePolicy-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="015c8-127">Click **Search &amp; investigation**, click **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="015c8-128">Nella pagina **Nuova ricerca**, digitare un nome per la ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="015c8-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="015c8-129">In **Dove si vuole effettuare la ricerca?**, fare clic su **Cerca in tutte le cassette postali**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="015c8-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="015c8-p105">Nella casella in **scegliere un'opzione di cercare?**, digitare una query di ricerca nella casella. È possibile specificare le parole chiave, messaggio proprietà come inviati e ricevuti, date o proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È possibile utilizzare una query più complesse che utilizzano un operatore booleano, ad esempio AND, OR non o vicino o è inoltre possibile cercare informazioni sensibili (ad esempio numeri di previdenza sociale) nei messaggi. Per ulteriori informazioni sulla creazione delle query di ricerca, vedere [query con parole chiave per la ricerca del contenuto](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="015c8-p105">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages. For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="015c8-134">Fare clic su **Ricerca** per salvare le impostazioni e avviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="015c8-p106">Dopo un po' di tempo, una stima dei risultati della ricerca visualizzati nel riquadro dei dettagli. La stima include le dimensioni totali e il numero di elementi per i risultati della ricerca. Al termine della ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario, fare clic su **Aggiorna**![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="015c8-p106">After a while, an estimate of the search results displayed in the details pane. The estimate includes the total size and number of items for the search results. After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="015c8-139">Se necessario, perfezionare la query di ricerca per limitare l'ambito dei risultati della ricerca, quindi riavviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="015c8-140">Utilizzare PowerShell centro conformità e sicurezza per la ricerca di tutte le cassette postali</span><span class="sxs-lookup"><span data-stu-id="015c8-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="015c8-p107">È anche possibile utilizzare il cmdlet **New-ComplianceSearch** per la ricerca di tutte le cassette postali nell'organizzazione. Il primo passaggio consiste nel [Connetti a Office 365 Security &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span><span class="sxs-lookup"><span data-stu-id="015c8-p107">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization. The first step is to [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="015c8-p108">Di seguito è riportato un esempio dell'utilizzo di PowerShell per la ricerca di tutte le cassette postali nell'organizzazione. Query di ricerca restituisce tutti i messaggi inviati tra il 1 ° gennaio 2015 e 30 giugno 2015 e che contengono la frase "report finanziari" nella riga dell'oggetto. Il primo comando crea la ricerca e il secondo comando viene eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-p108">Here's an example of using PowerShell to search all mailboxes in your organization. The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line. The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="015c8-146">Per ulteriori informazioni, vedere [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span><span class="sxs-lookup"><span data-stu-id="015c8-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="015c8-147">Verificare il numero di cassette postali di origine nella ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="015c8-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="015c8-p109">Una ricerca contenuto restituisce al massimo 1.000 cassette postali di origine che contengono i risultati della ricerca. Se sono presenti più di 1.000 cassette postali che includono contenuto corrispondente alla query di ricerca, solo le prime 1000 le cassette postali con la maggior parte dei risultati della ricerca sono inclusi nella ricerca contenuto creato nel passaggio precedente. Pertanto se più di 1.000 cassette postali contengono i risultati della ricerca, alcune delle cassette postali non vengono inclusi nell'elenco delle cassette postali di origine copiati nella nuova ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="015c8-p109">A Content Search returns a maximum of 1,000 source mailboxes that contain search results. If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step. So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="015c8-151">Per creare una ricerca di contenuto con non più cassette postali di origine 1.000, eseguire la procedura seguente per eseguire uno script che viene visualizzato il numero di cassette postali di origine (che contengono i risultati della ricerca) restituito dalla ricerca contenuto creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="015c8-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="015c8-p110">Salvare il testo seguente in un file di script PowerShell utilizzando il suffisso filename. ps1. Ad esempio possibile salvare in un file denominato `SourceMailboxes.ps1`.</span><span class="sxs-lookup"><span data-stu-id="015c8-p110">Save the following text to a PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. <span data-ttu-id="015c8-154">In sicurezza e conformità centro PowerShell, passare alla cartella in cui si trova lo script che è stato creato nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="015c8-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="015c8-155">Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="015c8-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="015c8-156">Lo script consente di visualizzare il numero di cassette postali di origine che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="015c8-p111">Se sono presenti più di 1.000 cassette postali di origine, provare a creare ricerche di contenuto due (o più). Ad esempio, cercare la metà di cassette postali dell'organizzazione in una ricerca di contenuto e per metà in un'altra ricerca contenuto. È inoltre possibile modificare i criteri di ricerca per ridurre il numero di cassette postali che contengono i risultati della ricerca. Ad esempio, si potrebbe includere un intervallo di date o ridefinire le query con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="015c8-p111">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches. For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search. You could also change the search criteria to reduce the number of mailboxes that contain search results. For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="015c8-161">Passaggio 2: Connessione per la protezione &amp; centro conformità ed Exchange Online in una singola sessione di PowerShell remota</span><span class="sxs-lookup"><span data-stu-id="015c8-161">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="015c8-p112">Il passaggio successivo consiste nel connettere Windows PowerShell per la protezione sia &amp; centro conformità e l'organizzazione di Exchange Online. Questa operazione è necessaria poiché lo script che viene eseguita nel passaggio 3 richiede l'accesso ai cmdlet ricerca contenuto nella protezione &amp; centro conformità e i cmdlet di eDiscovery In locale in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="015c8-p112">The next step is to connect Windows PowerShell to both the Security &amp; Compliance Center and to your Exchange Online organization. This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security &amp; Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="015c8-p113">Salvare il testo seguente in un file di script di Windows PowerShell, utilizzando il suffisso filename. ps1. Ad esempio possibile salvare in un file denominato `ConnectEXO-CC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="015c8-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="015c8-166">Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente e quindi eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="015c8-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="015c8-p114">Come fai a sapere se si ha avuto esito positivo? Dopo aver eseguito lo script, i cmdlet di sicurezza &amp; centro conformità ed Exchange Online vengono importati nella sessione PowerShell locale. Se non di errori, l'utente connesso correttamente. Una prova veloce consiste nell'eseguire una protezione &amp; cmdlet centro conformità, ad esempio, **Install-UnifiedCompliancePrerequisite** e un cmdlet di Exchange Online, ad esempio **Get-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="015c8-p114">How do you know if this worked? After you run the script, cmdlets from the Security &amp; Compliance Center and Exchange Online are imported into your local PowerShell session. If you don't receive any errors, you connected successfully. A quick test is to run a Security &amp; Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="015c8-171">Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="015c8-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="015c8-p115">Dopo aver creato la sessione PowerShell doppia nel passaggio 2, il passaggio successivo consiste nell'eseguire uno script che converte una ricerca di contenuto esistente in una ricerca eDiscovery In locale. Ecco che cosa lo script:</span><span class="sxs-lookup"><span data-stu-id="015c8-p115">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search. Here's what the script does:</span></span>
  
- <span data-ttu-id="015c8-174">Richiede il nome della ricerca di contenuto da convertire.</span><span class="sxs-lookup"><span data-stu-id="015c8-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="015c8-p116">Verifica che la ricerca di contenuto abbia completato l'esecuzione. Se la ricerca di contenuto non restituisce risultati, non viene creata una ricerca eDiscovery sul posto.</span><span class="sxs-lookup"><span data-stu-id="015c8-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="015c8-177">Salva un elenco di cassette postali di origine dalla ricerca di contenuto che contengono i risultati della ricerca per una variabile.</span><span class="sxs-lookup"><span data-stu-id="015c8-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="015c8-p117">Crea una nuova ricerca eDiscovery sul posto, con le proprietà riportate di seguito. La nuova ricerca non è stata avviata. È possibile avviarla nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="015c8-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="015c8-p118">**Nome** - il nome della nuova ricerca viene utilizzato il seguente formato: \<nome di ricerca del contenuto\>_MBSearch1. Se si esegue nuovamente lo script e utilizzare la stessa origine contenuto di ricerca, la ricerca verrà denominata \<nome di ricerca del contenuto\>_MBSearch2.</span><span class="sxs-lookup"><span data-stu-id="015c8-p118">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1. If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="015c8-183">**Cassette postali di origine** - tutte le cassette postali di ricerca del contenuto che contengono i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="015c8-p119">**Query di ricerca** - nuova ricerca utilizza la query di ricerca di ricerca del contenuto. Se la ricerca di contenuto include tutto il contenuto (dove la query di ricerca è vuota) nuova ricerca disporrà inoltre di una query di ricerca vuoto e sarà incluso tutto il contenuto di cassette postali di origine.</span><span class="sxs-lookup"><span data-stu-id="015c8-p119">**Search query** - The new search uses the search query from the Content Search. If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="015c8-p120">**Stimare solo ricerca** - nuova ricerca è contrassegnato come una ricerca solo stima. È non una copia dei risultati di ricerca per una cassetta postale di individuazione dopo aver avviato.</span><span class="sxs-lookup"><span data-stu-id="015c8-p120">**Estimate only search** - The new search is marked as an estimate-only search. It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="015c8-p121">Salvare il testo seguente in un file di script di Windows PowerShell, utilizzando il suffisso nome di file ps1. Ad esempio possibile salvare in un file denominato `CreateMBSearchFromComplianceSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="015c8-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1. For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. <span data-ttu-id="015c8-190">Nella sessione di Windows PowerShell che è stato creato nel passaggio 2, passare alla cartella in cui si trova lo script creato nel passaggio precedente ed eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="015c8-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="015c8-191">Quando richiesto dallo script, digitare il nome della ricerca contenuto che si desidera convertire per una ricerca eDiscovery In locale (ad esempio, la ricerca creato nel passaggio 1) e quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="015c8-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="015c8-p122">Se lo script ha esito positivo, viene creata una nuova ricerca eDiscovery sul posto con lo stato **NotStarted**. Eseguire il comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` per visualizzare le proprietà della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="015c8-194">Passaggio 4: avviare la ricerca eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="015c8-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="015c8-p123">Lo script eseguito nel passaggio 3 crea una nuova ricerca eDiscovery sul posto, ma non la avvia. Il passaggio successivo consiste nell'avviare la ricerca, affinché sia possibile ottenere una stima dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="015c8-197">Nell'interfaccia di amministrazione di Exchange (EAC) accedere a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="015c8-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="015c8-198">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="015c8-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="015c8-199">Fare clic su **Cerca** ![sull'icona di ricerca](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **stima dei risultati di ricerca** per avviare la ricerca e ottenere una stima delle dimensioni totali e numero di elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="015c8-p124">Le stime vengono visualizzate nel riquadro dei dettagli. Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni visualizzate nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="015c8-p124">The estimates are displayed in the details pane. Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="015c8-202">Per visualizzare in anteprima i risultati dopo il completamento della ricerca, fare clic su **Anteprima risultati della ricerca** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="015c8-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="015c8-203">Passaggi successivi alla creazione e all'esecuzione della ricerca eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="015c8-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="015c8-204">Dopo aver avviato la ricerca eDiscovery sul posto creata dallo script nel passaggio 3, è possibile utilizzare il normale flusso di lavoro della ricerca eDiscovery sul posto per eseguire varie operazioni relative alla ricerca eDiscovery sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="015c8-205">Creare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="015c8-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="015c8-206">In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="015c8-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="015c8-207">Nella visualizzazione elenco, selezionare la ricerca di eDiscovery In locale creata nel passaggio 3 e quindi fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="015c8-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="015c8-208">Nella pagina **Blocco sul posto**, selezionare la casella di controllo **Blocca il contenuto delle cassette postali selezionate che corrisponde alla query di ricerca** e scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="015c8-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="015c8-p125">**Tenere premuto per un tempo indefinito** - scegliere questa opzione per inserire gli elementi restituiti dalla ricerca una conservazione indefinita. Verranno mantenuti gli elementi in attesa finché non rimuovere la cassetta postale dalla ricerca o rimuovere la ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-p125">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold. Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="015c8-p126">**Specificare il numero di giorni di conservazione degli elementi rispetto al loro data di ricezione** : selezionare questa opzione per conservare gli elementi per un determinato periodo. La durata viene calcolata dalla data di ricezione o creato un elemento della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="015c8-p126">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period. The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="015c8-213">Fare clic su **Salva** per creare il blocco sul posto e riavviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="015c8-214">Inizio pagina</span><span class="sxs-lookup"><span data-stu-id="015c8-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="015c8-215">Copiare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="015c8-215">Copy the search results</span></span>

1. <span data-ttu-id="015c8-216">In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="015c8-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="015c8-217">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="015c8-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="015c8-218">Fare clic su **Cerca** ![sull'icona di ricerca](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), quindi fare clic su **copiare i risultati della ricerca** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="015c8-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="015c8-219">In **Copia risultati della ricerca**, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="015c8-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="015c8-220">**Includi elementi non ricercabili** : selezionare questa casella di controllo per includere gli elementi delle cassette postali che non eseguire la ricerca (ad esempio, i messaggi con allegati di tipi di file non è stati indicizzati dalla ricerca di Exchange).</span><span class="sxs-lookup"><span data-stu-id="015c8-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="015c8-p127">**Abilita deduplicazione** - selezionare questa casella di controllo per escludere i messaggi duplicati. Una sola istanza di un messaggio verrà copiata nella cassetta postale di individuazione.</span><span class="sxs-lookup"><span data-stu-id="015c8-p127">**Enable de-duplication** - Select this check box to exclude duplicate messages. Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="015c8-223">**Attivare la registrazione dei completa** - selezionare questa casella di controllo per includere un registro full nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="015c8-224">**Invio di posta elettronica al termine della copia** - selezionare questa casella di controllo per ottenere una notifica tramite posta elettronica al termine della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="015c8-225">**Copiare i risultati a questa cassetta postale di individuazione** - fare clic su **Sfoglia** per selezionare la cassetta postale di individuazione in cui si desidera i risultati della ricerca copiati.</span><span class="sxs-lookup"><span data-stu-id="015c8-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="015c8-226">Fare clic su **Copia** per avviare il processo per copiare i risultati della ricerca nella cassetta postale di individuazione specificata.</span><span class="sxs-lookup"><span data-stu-id="015c8-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="015c8-227">Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni sullo stato copia che viene visualizzata nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="015c8-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="015c8-228">Al termine della copia, fare clic su **Apri** per aprire la cassetta postale di individuazione e visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="015c8-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="015c8-229">Esportare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="015c8-229">Export the search results</span></span>

1. <span data-ttu-id="015c8-230">In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.</span><span class="sxs-lookup"><span data-stu-id="015c8-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="015c8-231">Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **Esporta in un file PST**.</span><span class="sxs-lookup"><span data-stu-id="015c8-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="015c8-232">Nella finestra **Strumento eDiscovery per esportazione PST** effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="015c8-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="015c8-233">Fare clic su **Sfoglia** per specificare la posizione in cui si desidera scaricare il file PST.</span><span class="sxs-lookup"><span data-stu-id="015c8-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="015c8-p128">Selezionare la casella di controllo **Abilita deduplicazione** per escludere i messaggi duplicati. Il file PST conterrà una sola istanza di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="015c8-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="015c8-p129">Selezionare la casella di controllo **Includi elementi senza funzioni di ricerca** per includere elementi non ricercabili, ad esempio messaggi con allegati di tipi di file non indicizzabili da parte di Ricerca di Exchange. Gli elementi non ricercabili vengono esportati in un file PST separato.</span><span class="sxs-lookup"><span data-stu-id="015c8-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="015c8-238">Fare clic su **Start** per esportare i risultati della ricerca in un file PST.</span><span class="sxs-lookup"><span data-stu-id="015c8-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="015c8-239">Viene visualizzata una finestra contenente informazioni relative allo stato del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="015c8-239">A window is displayed that contains status information about the export process.</span></span>
