---
title: Clonare una ricerca di contenuto nel centro sicurezza &amp; e conformità di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente &amp; nella ricerca di Compliane Center di sicurezza. Quando si clona una ricerca, viene creata una nuova ricerca (con un nuovo nome) che contiene le stesse proprietà della ricerca originale. È quindi possibile modificare la nuova ricerca modificando la query di parole chiave o l'intervallo di date e quindi eseguirlo.
ms.openlocfilehash: 15f1ca5d00f03f510745fef7ae8418192a9eb448
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213546"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="b4f55-105">Clonare una ricerca di contenuto nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="b4f55-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="b4f55-p102">Creazione di una ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 che consente di eseguire ricerche in molte cassette postali o siti di SharePoint e OneDrive for business può richiedere un po' di tempo. La specifica dei siti da cercare può anche essere soggetta a errori se si digita un URL in modo improprio. Per evitare questi problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca, con un nome diverso, che contiene le stesse proprietà, ad esempio i percorsi di contenuto e la query di ricerca, come la ricerca originale. È quindi possibile modificare la nuova ricerca (modificando la query di parole chiave o l'intervallo di date) ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="b4f55-111">Perché clonare le ricerche di contenuto?</span><span class="sxs-lookup"><span data-stu-id="b4f55-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="b4f55-112">Per confrontare i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4f55-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="b4f55-113">Per evitare di dover immettere nuovamente un numero elevato di posizioni di contenuto quando si crea una nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="b4f55-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="b4f55-114">Per ridurre le dimensioni dei risultati della ricerca; Se ad esempio si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca in base a un intervallo di date per ridurre il numero di risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b4f55-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b4f55-115">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b4f55-115">Before you begin</span></span>

- <span data-ttu-id="b4f55-116">Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo &amp; di ruoli eDiscovery Manager nel centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="b4f55-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="b4f55-p103">Lo script include la gestione degli errori minima. Lo scopo principale dello script è di clonare velocemente una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="b4f55-119">Lo script crea una nuova ricerca del contenuto, ma non la avvia.</span><span class="sxs-lookup"><span data-stu-id="b4f55-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="b4f55-p104">Questo script tiene conto del fatto che la ricerca di contenuto che si sta clonando è associata a un caso di eDiscovery. Se la ricerca è associata a un caso, la nuova ricerca verrà associata anche allo stesso caso. Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca contenuto** nel centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="b4f55-p105">Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft nega inoltre tutte le garanzie implicite, incluse, senza limitazioni, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script sarà responsabile per eventuali danni (compresi, senza limitazione, i danni per perdita degli utili aziendali, interruzioni aziendali, perdita di informazioni aziendali o altre perdite pecuniarie) derivanti dall'utilizzo o dall'impossibilità di utilizzare gli script di esempio o la documentazione, anche se Microsoft è stata avvisata della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="b4f55-128">Passaggio 1: eseguire lo script per clonare una ricerca</span><span class="sxs-lookup"><span data-stu-id="b4f55-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="b4f55-p106">Nello script di questo passaggio viene creata una nuova ricerca di contenuto clonando un'altra esistente. Quando si esegue questo script, vengono richieste le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4f55-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="b4f55-p107">**Credenziali utente** : lo script utilizzerà le credenziali per connettersi al centro sicurezza &amp; e conformità per l'organizzazione di Office 365 con Windows PowerShell. Come indicato in precedenza, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza &amp; e conformità per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="b4f55-133">**Il nome della ricerca esistente** , ovvero la ricerca di contenuto che si desidera clonare.</span><span class="sxs-lookup"><span data-stu-id="b4f55-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="b4f55-134">**Nome della nuova ricerca che verrà creata** : se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca basata sul nome della ricerca che si sta clonando.</span><span class="sxs-lookup"><span data-stu-id="b4f55-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="b4f55-135">Per clonare una ricerca:</span><span class="sxs-lookup"><span data-stu-id="b4f55-135">To clone a search:</span></span>
  
1. <span data-ttu-id="b4f55-136">Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b4f55-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="b4f55-137">Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.</span><span class="sxs-lookup"><span data-stu-id="b4f55-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="b4f55-138">Eseguire lo script; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b4f55-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="b4f55-139">Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4f55-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="b4f55-p108">Immettere le informazioni seguenti quando richiesto dallo script. Digitare ogni informazione e quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="b4f55-142">Nome della ricerca esistente.</span><span class="sxs-lookup"><span data-stu-id="b4f55-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="b4f55-143">Nome della nuova ricerca.</span><span class="sxs-lookup"><span data-stu-id="b4f55-143">The name of the new search.</span></span>
    
    <span data-ttu-id="b4f55-p109">Lo script crea la nuova ricerca del contenuto, ma non la avvia. In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo. Per visualizzare le proprietà della nuova ricerca, è possibile eseguire il cmdlet **Get-ComplianceSearch** o andare alla pagina **Ricerca contenuto** o **eDiscovery** nel centro sicurezza &amp; e conformità, a seconda che la nuova ricerca sia o meno associato a un caso.</span><span class="sxs-lookup"><span data-stu-id="b4f55-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="b4f55-147">Passaggio 2: modificare ed eseguire la ricerca clonata nel centro sicurezza &amp; e conformità</span><span class="sxs-lookup"><span data-stu-id="b4f55-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="b4f55-p110">Dopo aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare al centro sicurezza &amp; e conformità per modificare ed eseguire la nuova ricerca. Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="b4f55-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="b4f55-151">Ricerca contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="b4f55-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="b4f55-152">Query con parole chiave e condizioni di ricerca per la Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="b4f55-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="b4f55-153">casi di eDiscovery nel centro sicurezza &amp; e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="b4f55-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
