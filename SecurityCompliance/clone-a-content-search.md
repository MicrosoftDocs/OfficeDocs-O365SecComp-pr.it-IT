---
title: Clonare una ricerca di contenuto in Office 365 protezione &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente nella protezione &amp; ricerca Compliane Center. Quando si clona una ricerca, viene creata una nuova ricerca (con un nuovo nome) che contiene le stesse proprietà di ricerca originale. È possibile modificare la nuova ricerca (modificando la query con parole chiave o l'intervallo di date) e quindi eseguire.
ms.openlocfilehash: a4f801e3de281e8caf8aeb7d1c2bd48f0facb77c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530672"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="b063b-105">Clonare una ricerca di contenuto in Office 365 protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="b063b-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="b063b-p102">Creazione di una ricerca di contenuto in Office 365 Security &amp; centro conformità per la ricerca di una quantità elevata di cassette postali o SharePoint e OneDrive per i siti possono richiedere qualche minuto. Specificare i siti di ricerca può inoltre essere soggetto a errori se si digita un URL. Per evitare tali problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca (con un nome diverso) che contiene le proprietà stesse, quali i percorsi di contenuti e la query di ricerca, ricerca originale di. È quindi possibile modificare la nuova ricerca (modificando la query con parole chiave o l'intervallo di date) ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="b063b-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="b063b-111">Clonare perché ricerche di contenuto?</span><span class="sxs-lookup"><span data-stu-id="b063b-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="b063b-112">Per confrontare i risultati di diversa parole chiave delle query di ricerca eseguito sui percorsi di contenuti stessi.</span><span class="sxs-lookup"><span data-stu-id="b063b-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="b063b-113">Per evitare di dover immettere di nuovo un numero elevato di percorsi di contenuti quando si crea una nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="b063b-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="b063b-114">Ridurre le dimensioni dei risultati di ricerca; ad esempio, se si dispone di una ricerca restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca basata su un intervallo di date per ridurre il numero di risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b063b-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b063b-115">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b063b-115">Before you begin</span></span>

- <span data-ttu-id="b063b-116">È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b063b-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="b063b-p103">Lo script include la gestione degli errori o molto ridotto. Lo scopo principale dello script deve rapidamente clonare una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b063b-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="b063b-119">Lo script consente di creare una nuova ricerca contenuto, ma non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="b063b-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="b063b-p104">Questo script prende in considerazione se la ricerca del contenuto da clonare è associata a un caso eDiscovery. Se la ricerca è associata a un caso, la nuova ricerca anche sarà associata lo stesso caso. Se la ricerca non è associata a un caso, la nuova ricerca verrà elencata la pagina di **ricerca del contenuto** per la protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="b063b-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="b063b-p105">Lo script di esempio fornito in questo argomento non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="b063b-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="b063b-128">Passaggio 1: Eseguire lo script per clonare una ricerca</span><span class="sxs-lookup"><span data-stu-id="b063b-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="b063b-p106">Lo script in questo passaggio verrà creato una nuova ricerca del contenuto mediante la clonazione di una esistente. Quando si esegue questo script, verrà richiesto di immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b063b-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="b063b-p107">**Le credenziali dell'utente** - lo script utilizzeranno le credenziali per connettersi alla protezione di &amp; centro conformità per l'organizzazione Office 365 con Windows PowerShell. Come affermato in precedenza, è necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="b063b-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="b063b-133">**Il nome di ricerca esistente** - contenuto di ricerca che si desidera clonare.</span><span class="sxs-lookup"><span data-stu-id="b063b-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="b063b-134">**Il nome della nuova ricerca che verrà creata** - se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca che si basa sul nome della ricerca da clonare.</span><span class="sxs-lookup"><span data-stu-id="b063b-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="b063b-135">Per clonare una ricerca:</span><span class="sxs-lookup"><span data-stu-id="b063b-135">To clone a search:</span></span>
  
1. <span data-ttu-id="b063b-136">Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b063b-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="b063b-137">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="b063b-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="b063b-138">Eseguire lo script. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b063b-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="b063b-139">Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b063b-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="b063b-p108">Immettere il seguente informazioni quando viene richiesto dallo script. Digitare ogni informazione e quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="b063b-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="b063b-142">Il nome di ricerca esistente.</span><span class="sxs-lookup"><span data-stu-id="b063b-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="b063b-143">Il nome della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="b063b-143">The name of the new search.</span></span>
    
    <span data-ttu-id="b063b-p109">Lo script consente di creare la nuova ricerca contenuto, ma non viene avviato. Offre la possibilità di modificare ed eseguire la ricerca nel passaggio successivo. È possibile visualizzare le proprietà della nuova ricerca eseguendo il cmdlet **Get-ComplianceSearch** o passando alla pagina di **ricerca del contenuto** o **eDiscovery** in sicurezza &amp; centro conformità, a seconda che sia o meno la nuova ricerca associati a un caso.</span><span class="sxs-lookup"><span data-stu-id="b063b-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="b063b-147">Passaggio 2: Modificare ed eseguire la ricerca clonata nella protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="b063b-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="b063b-p110">Dopo di aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare a sicurezza &amp; centro conformità modificare ed eseguire la ricerca di nuova. Come affermato in precedenza, è possibile modificare una ricerca modificando la query di ricerca e aggiunta o rimozione di criteri di ricerca. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b063b-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="b063b-151">Ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="b063b-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="b063b-152">Query delle parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="b063b-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="b063b-153">casi di eDiscovery in Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="b063b-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
