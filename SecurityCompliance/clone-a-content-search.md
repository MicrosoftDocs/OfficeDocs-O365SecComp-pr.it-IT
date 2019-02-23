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
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>Clonare una ricerca di contenuto nel centro sicurezza &amp; e conformità di Office 365

Creazione di una ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365 che consente di eseguire ricerche in molte cassette postali o siti di SharePoint e OneDrive for business può richiedere un po' di tempo. La specifica dei siti da cercare può anche essere soggetta a errori se si digita un URL in modo improprio. Per evitare questi problemi, è possibile utilizzare lo script di Windows PowerShell in questo articolo per clonare rapidamente una ricerca di contenuto esistente. Quando si clona una ricerca, viene creata una nuova ricerca, con un nome diverso, che contiene le stesse proprietà, ad esempio i percorsi di contenuto e la query di ricerca, come la ricerca originale. È quindi possibile modificare la nuova ricerca (modificando la query di parole chiave o l'intervallo di date) ed eseguirla.
  
Perché clonare le ricerche di contenuto?
  
- Per confrontare i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto.
    
- Per evitare di dover immettere nuovamente un numero elevato di posizioni di contenuto quando si crea una nuova ricerca.
    
- Per ridurre le dimensioni dei risultati della ricerca; Se ad esempio si dispone di una ricerca che restituisce troppi risultati da esportare, è possibile clonare la ricerca e quindi aggiungere una condizione di ricerca in base a un intervallo di date per ridurre il numero di risultati della ricerca.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire lo script descritto in questo argomento, è necessario essere membri del gruppo &amp; di ruoli eDiscovery Manager nel centro sicurezza e conformità.
    
- Lo script include la gestione degli errori minima. Lo scopo principale dello script è di clonare velocemente una ricerca di contenuto.
    
- Lo script crea una nuova ricerca del contenuto, ma non la avvia.
    
- Questo script tiene conto del fatto che la ricerca di contenuto che si sta clonando è associata a un caso di eDiscovery. Se la ricerca è associata a un caso, la nuova ricerca verrà associata anche allo stesso caso. Se la ricerca esistente non è associata a un caso, la nuova ricerca verrà elencata nella pagina **Ricerca contenuto** nel centro sicurezza &amp; e conformità. 
    
- Lo script di esempio fornito in questo argomento non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo script di esempio viene fornito come senza garanzie di alcun tipo. Microsoft nega inoltre tutte le garanzie implicite, incluse, senza limitazioni, le garanzie implicite di commerciabilità o di idoneità per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello script di esempio e della documentazione resta all'interno dell'utente. In nessun caso Microsoft, i suoi autori o chiunque altro coinvolto nella creazione, produzione o consegna degli script sarà responsabile per eventuali danni (compresi, senza limitazione, i danni per perdita degli utili aziendali, interruzioni aziendali, perdita di informazioni aziendali o altre perdite pecuniarie) derivanti dall'utilizzo o dall'impossibilità di utilizzare gli script di esempio o la documentazione, anche se Microsoft è stata avvisata della possibilità di tali danni.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Passaggio 1: eseguire lo script per clonare una ricerca

Nello script di questo passaggio viene creata una nuova ricerca di contenuto clonando un'altra esistente. Quando si esegue questo script, vengono richieste le informazioni seguenti:
  
- **Credenziali utente** : lo script utilizzerà le credenziali per connettersi al centro sicurezza &amp; e conformità per l'organizzazione di Office 365 con Windows PowerShell. Come indicato in precedenza, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza &amp; e conformità per eseguire lo script. 
    
- **Il nome della ricerca esistente** , ovvero la ricerca di contenuto che si desidera clonare. 
    
- **Nome della nuova ricerca che verrà creata** : se si lascia vuoto questo valore, lo script creerà un nome per la nuova ricerca basata sul nome della ricerca che si sta clonando. 
    
Per clonare una ricerca:
  
1. Salvare il testo seguente in un file di script di Windows PowerShell utilizzando un suffisso FileName di. ps1. ad esempio, `CloneSearch.ps1`.
    
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
    
3. Eseguire lo script; Per esempio:
    
    ```
    .\CloneSearch.ps1
    ```

4. Quando vengono richieste le credenziali, immettere l'indirizzo di posta elettronica e la password, quindi fare clic su **OK**.
    
5. Immettere le informazioni seguenti quando richiesto dallo script. Digitare ogni informazione e quindi premere **invio**.
    
    - Nome della ricerca esistente.
    
    - Nome della nuova ricerca.
    
    Lo script crea la nuova ricerca del contenuto, ma non la avvia. In questo modo è possibile modificare ed eseguire la ricerca nel passaggio successivo. Per visualizzare le proprietà della nuova ricerca, è possibile eseguire il cmdlet **Get-ComplianceSearch** o andare alla pagina **Ricerca contenuto** o **eDiscovery** nel centro sicurezza &amp; e conformità, a seconda che la nuova ricerca sia o meno associato a un caso. 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>Passaggio 2: modificare ed eseguire la ricerca clonata nel centro sicurezza &amp; e conformità

Dopo aver eseguito lo script per clonare una ricerca di contenuto esistente, il passaggio successivo consiste nel passare al centro sicurezza &amp; e conformità per modificare ed eseguire la nuova ricerca. Come indicato in precedenza, è possibile modificare una ricerca modificando la query di ricerca con parole chiave e aggiungendo o rimuovendo le condizioni di ricerca. Per ulteriori informazioni, vedere:
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
    
- [casi di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](ediscovery-cases.md)
