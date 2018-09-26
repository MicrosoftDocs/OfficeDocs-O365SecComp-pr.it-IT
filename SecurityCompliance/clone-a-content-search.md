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
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente nella protezione &amp; ricerca Compliane Center. Quando si clona una ricerca, viene creata una nuova ricerca (con un nuovo nome) che contiene le stesse proprietà di ricerca originale. È possibile modificare la nuova ricerca (modificando la query con parole chiave o l'intervallo di date) e quindi eseguire.
ms.openlocfilehash: fd2ea0d8fa812d23e7479b664b13c786a62d5a38
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038049"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Clonare una ricerca di contenuto in Office 365 protezione &amp; centro conformità

Creazione di una ricerca di contenuto in Office 365 Security &amp; centro conformità per la ricerca di una quantità elevata di cassette postali o SharePoint e OneDrive per i siti possono richiedere qualche minuto. Specificare i siti di ricerca può inoltre essere soggetto a errori se si digita un URL. Per evitare tali problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca (con un nome diverso) che contiene le proprietà stesse, quali i percorsi di contenuti e la query di ricerca, ricerca originale di. È quindi possibile modificare la nuova ricerca (modificando la query con parole chiave o l'intervallo di date) ed eseguirlo.
  
Clonare perché ricerche di contenuto?
  
- Per confrontare i risultati di diversa parole chiave delle query di ricerca eseguito sui percorsi di contenuti stessi.
    
- Per evitare di dover immettere di nuovo un numero elevato di percorsi di contenuti quando si crea una nuova ricerca.
    
- Ridurre le dimensioni dei risultati di ricerca; ad esempio, se si dispone di una ricerca restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca basata su un intervallo di date per ridurre il numero di risultati di ricerca.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script descritto in questo argomento.
    
- Lo script include la gestione degli errori o molto ridotto. Lo scopo principale dello script deve rapidamente clonare una ricerca di contenuto.
    
- Lo script consente di creare una nuova ricerca contenuto, ma non viene avviato.
    
- Questo script prende in considerazione se la ricerca del contenuto da clonare è associata a un caso eDiscovery. Se la ricerca è associata a un caso, la nuova ricerca anche sarà associata lo stesso caso. Se la ricerca non è associata a un caso, la nuova ricerca verrà elencata la pagina di **ricerca del contenuto** per la protezione &amp; centro conformità. 
    
- Lo script di esempio fornito in questo argomento non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito degli script di tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Passaggio 1: Eseguire lo script per clonare una ricerca

Lo script in questo passaggio verrà creato una nuova ricerca del contenuto mediante la clonazione di una esistente. Quando si esegue questo script, verrà richiesto di immettere le informazioni seguenti:
  
- **Le credenziali dell'utente** - lo script utilizzeranno le credenziali per connettersi alla protezione di &amp; centro conformità per l'organizzazione Office 365 con Windows PowerShell. Come affermato in precedenza, è necessario essere membri del gruppo di ruoli gestione eDiscovery in sicurezza &amp; centro conformità per eseguire lo script. 
    
- **Il nome di ricerca esistente** - contenuto di ricerca che si desidera clonare. 
    
- **Il nome della nuova ricerca che verrà creata** - se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca che si basa sul nome della ricerca da clonare. 
    
Per clonare una ricerca:
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `CloneSearch.ps1`.
    
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

2. Aprire Windows PowerShell e passare alla cartella in cui è stato salvato lo script.
    
3. Eseguire lo script. Per esempio:
    
    ```
    .\CloneSearch.ps1
    ```

4. Quando richiesto per le proprie credenziali, immettere l'indirizzo di posta elettronica e la password e quindi fare clic su **OK**.
    
5. Immettere il seguente informazioni quando viene richiesto dallo script. Digitare ogni informazione e quindi premere **INVIO**.
    
    - Il nome di ricerca esistente.
    
    - Il nome della nuova ricerca.
    
    Lo script consente di creare la nuova ricerca contenuto, ma non viene avviato. Offre la possibilità di modificare ed eseguire la ricerca nel passaggio successivo. È possibile visualizzare le proprietà della nuova ricerca eseguendo il cmdlet **Get-ComplianceSearch** o passando alla pagina di **ricerca del contenuto** o **eDiscovery** in sicurezza &amp; centro conformità, a seconda che sia o meno la nuova ricerca associati a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>Passaggio 2: Modificare ed eseguire la ricerca clonata nella protezione &amp; centro conformità

Dopo di aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare a sicurezza &amp; centro conformità modificare ed eseguire la ricerca di nuova. Come affermato in precedenza, è possibile modificare una ricerca modificando la query di ricerca e aggiunta o rimozione di criteri di ricerca. Per ulteriori informazioni, vedere:
  
- [Ricerca del contenuto in Office 365](content-search.md)
    
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
    
- [casi di eDiscovery in Office 365 Security &amp; centro conformità](ediscovery-cases.md)
