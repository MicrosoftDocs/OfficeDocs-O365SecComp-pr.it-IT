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
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: 'Utilizzare uno script di PowerShell per creare una ricerca eDiscovery In locale in Exchange Online basato su una ricerca creata in Office 365 Security &amp; centro conformità. '
ms.openlocfilehash: 42af94ce850736dede52e619c240bb9e0a6f7031
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038069"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>Utilizzare la ricerca di contenuto nel flusso di lavoro di eDiscovery

La funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità consente di cercare tutte le cassette postali nell'organizzazione. A differenza di eDiscovery In locale in Exchange Online (in cui è possibile cercare fino a 10.000 cassette postali), non esistono limiti per il numero di cassette postali di destinazione in una singola ricerca. Per gli scenari che richiedono è possibile eseguire ricerche a livello di organizzazione, è possibile utilizzare ricerca contenuto per la ricerca di tutte le cassette postali. Quindi è possibile utilizzare le funzionalità del flusso di lavoro di eDiscovery In locale per eseguire altre attività relative a eDiscovery, quali cassette postali di posizionamento in attesa e risultati della ricerca di esportazione. Si supponga, ad esempio, che è necessario cercare tutte le cassette postali per identificare depositari specifici che sono rispondono a una controversia legale. È possibile utilizzare ricerca contenuto nella protezione &amp; centro conformità per la ricerca di tutte le cassette postali nell'organizzazione per identificare quelle risponde al caso. È quindi possibile utilizzare tale elenco delle cassette postali depositaria come cassette postali di origine per una ricerca eDiscovery In locale in Exchange Online. Utilizzo di eDiscovery In locale consente inoltre di creare un'esenzione su tali cassette postali di origine, copiare i risultati della ricerca in una cassetta postale di individuazione ed esportare i risultati della ricerca.
  
In questo argomento include uno script che è possibile eseguire per creare una ricerca eDiscovery In locale in Exchange Online mediante l'elenco delle cassette postali di origine e di query di ricerca da una ricerca nella sicurezza &amp; centro conformità. Di seguito viene fornita una panoramica del processo:
  
[Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[Passaggio 2: Connessione per la protezione &amp; centro conformità ed Exchange Online in una singola sessione di PowerShell remota](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Passaggio 4: avviare la ricerca eDiscovery sul posto](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>Passaggio 1: creare una ricerca di contenuto per effettuare una ricerca in tutte le cassette postali dell'organizzazione

Il primo passaggio consiste nell'utilizzare la sicurezza &amp; centro conformità (o sicurezza e conformità centro PowerShell) per creare una ricerca di contenuto per la ricerca di tutte le cassette postali nell'organizzazione. Non esiste alcun limite per il numero di cassette postali per una singola ricerca contenuto. Consente di specificare una query con parole chiave appropriato (o una query per i tipi di informazioni riservate) in modo che la ricerca restituisce solo le cassette postali di origine rilevanti per le indagini. Se necessario, ridefinire la query di ricerca per restringere l'ambito dei risultati di ricerca e cassette postali di origine che vengono restituite.
  
> [!NOTE]
> Se la ricerca di contenuto di origine non restituisce risultati, non viene creata una ricerca eDiscovery sul posto quando si esegue lo script indicato al passaggio 3. Potrebbe essere necessario rivedere la query di ricerca ed eseguire di nuovo la ricerca di contenuto per ottenere dei risultati. 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a>Utilizzare la protezione &amp; centro conformità per la ricerca di tutte le cassette postali

1. [Passare alla protezione di Office 365 &amp; centro conformità](go-to-the-securitycompliance-center.md). 
    
2. Fare clic su **ricerca &amp; indagini**, fare clic su **ricerca contenuto**e quindi fare clic su **Nuovo** ![sull'icona Aggiungi](media/O365-MDM-CreatePolicy-AddIcon.gif).
    
3. Nella pagina **Nuova ricerca**, digitare un nome per la ricerca di contenuto. 
    
4. In **Dove si vuole effettuare la ricerca?**, fare clic su **Cerca in tutte le cassette postali**, quindi su **Avanti**.
    
5. Nella casella in **scegliere un'opzione di cercare?**, digitare una query di ricerca nella casella. È possibile specificare le parole chiave, messaggio proprietà come inviati e ricevuti, date o proprietà del documento, ad esempio i nomi di file o la data dell'ultima modifica di un documento. È possibile utilizzare una query più complesse che utilizzano un operatore booleano, ad esempio AND, OR non o vicino o è inoltre possibile cercare informazioni sensibili (ad esempio numeri di previdenza sociale) nei messaggi. Per ulteriori informazioni sulla creazione delle query di ricerca, vedere [query con parole chiave per la ricerca del contenuto](keyword-queries-and-search-conditions.md).
    
6. Fare clic su **Ricerca** per salvare le impostazioni e avviare la ricerca. 
    
    Dopo un po' di tempo, una stima dei risultati della ricerca visualizzati nel riquadro dei dettagli. La stima include le dimensioni totali e il numero di elementi per i risultati della ricerca. Al termine della ricerca, è possibile visualizzare in anteprima i risultati della ricerca. Se necessario, fare clic su **Aggiorna**![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli. 
    
7.  Se necessario, perfezionare la query di ricerca per limitare l'ambito dei risultati della ricerca, quindi riavviare la ricerca. 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>Utilizzare PowerShell centro conformità e sicurezza per la ricerca di tutte le cassette postali

È anche possibile utilizzare il cmdlet **New-ComplianceSearch** per la ricerca di tutte le cassette postali nell'organizzazione. Il primo passaggio consiste nel [Connetti a Office 365 Security &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/p/?LinkID=627084).
  
Di seguito è riportato un esempio dell'utilizzo di PowerShell per la ricerca di tutte le cassette postali nell'organizzazione. Query di ricerca restituisce tutti i messaggi inviati tra il 1 ° gennaio 2015 e 30 giugno 2015 e che contengono la frase "report finanziari" nella riga dell'oggetto. Il primo comando crea la ricerca e il secondo comando viene eseguita la ricerca. 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

Per ulteriori informazioni, vedere [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>Verificare il numero di cassette postali di origine nella ricerca di contenuto

Una ricerca contenuto restituisce al massimo 1.000 cassette postali di origine che contengono i risultati della ricerca. Se sono presenti più di 1.000 cassette postali che includono contenuto corrispondente alla query di ricerca, solo le prime 1000 le cassette postali con la maggior parte dei risultati della ricerca sono inclusi nella ricerca contenuto creato nel passaggio precedente. Pertanto se più di 1.000 cassette postali contengono i risultati della ricerca, alcune delle cassette postali non vengono inclusi nell'elenco delle cassette postali di origine copiati nella nuova ricerca eDiscovery sul posto creata nel passaggio 3. 
  
Per creare una ricerca di contenuto con non più cassette postali di origine 1.000, eseguire la procedura seguente per eseguire uno script che viene visualizzato il numero di cassette postali di origine (che contengono i risultati della ricerca) restituito dalla ricerca contenuto creato nel passaggio 1. 
  
1. Salvare il testo seguente in un file di script PowerShell utilizzando il suffisso filename. ps1. Ad esempio possibile salvare in un file denominato `SourceMailboxes.ps1`.
    
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

2. In sicurezza e conformità centro PowerShell, passare alla cartella in cui si trova lo script che è stato creato nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. Quando viene richiesto dallo script, digitare il nome della ricerca di contenuto creata nel passaggio 1.
    
    Lo script consente di visualizzare il numero di cassette postali di origine che contengono i risultati della ricerca.
    
Se sono presenti più di 1.000 cassette postali di origine, provare a creare ricerche di contenuto due (o più). Ad esempio, cercare la metà di cassette postali dell'organizzazione in una ricerca di contenuto e per metà in un'altra ricerca contenuto. È inoltre possibile modificare i criteri di ricerca per ridurre il numero di cassette postali che contengono i risultati della ricerca. Ad esempio, si potrebbe includere un intervallo di date o ridefinire le query con parole chiave.
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Passaggio 2: Connessione per la protezione &amp; centro conformità ed Exchange Online in una singola sessione di PowerShell remota

Il passaggio successivo consiste nel connettere Windows PowerShell per la protezione sia &amp; centro conformità e l'organizzazione di Exchange Online. Questa operazione è necessaria poiché lo script che viene eseguita nel passaggio 3 richiede l'accesso ai cmdlet ricerca contenuto nella protezione &amp; centro conformità e i cmdlet di eDiscovery In locale in Exchange Online.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell, utilizzando il suffisso filename. ps1. Ad esempio possibile salvare in un file denominato `ConnectEXO-CC.ps1`.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

Come fai a sapere se si ha avuto esito positivo? Dopo aver eseguito lo script, i cmdlet di sicurezza &amp; centro conformità ed Exchange Online vengono importati nella sessione PowerShell locale. Se non di errori, l'utente connesso correttamente. Una prova veloce consiste nell'eseguire una protezione &amp; cmdlet centro conformità, ad esempio, **Install-UnifiedCompliancePrerequisite** e un cmdlet di Exchange Online, ad esempio **Get-Mailbox**. 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>Passaggio 3: eseguire lo script per creare una ricerca eDiscovery sul posto dalla ricerca di contenuto

Dopo aver creato la sessione PowerShell doppia nel passaggio 2, il passaggio successivo consiste nell'eseguire uno script che converte una ricerca di contenuto esistente in una ricerca eDiscovery In locale. Ecco che cosa lo script:
  
- Richiede il nome della ricerca di contenuto da convertire.
    
- Verifica che la ricerca di contenuto abbia completato l'esecuzione. Se la ricerca di contenuto non restituisce risultati, non viene creata una ricerca eDiscovery sul posto.
    
- Salva un elenco di cassette postali di origine dalla ricerca di contenuto che contengono i risultati della ricerca per una variabile.
    
- Crea una nuova ricerca eDiscovery sul posto, con le proprietà riportate di seguito. La nuova ricerca non è stata avviata. È possibile avviarla nel passaggio 4.
    
  - **Nome** - il nome della nuova ricerca viene utilizzato il seguente formato: \<nome di ricerca del contenuto\>_MBSearch1. Se si esegue nuovamente lo script e utilizzare la stessa origine contenuto di ricerca, la ricerca verrà denominata \<nome di ricerca del contenuto\>_MBSearch2.
    
  - **Cassette postali di origine** - tutte le cassette postali di ricerca del contenuto che contengono i risultati della ricerca. 
    
  - **Query di ricerca** - nuova ricerca utilizza la query di ricerca di ricerca del contenuto. Se la ricerca di contenuto include tutto il contenuto (dove la query di ricerca è vuota) nuova ricerca disporrà inoltre di una query di ricerca vuoto e sarà incluso tutto il contenuto di cassette postali di origine. 
    
  - **Stimare solo ricerca** - nuova ricerca è contrassegnato come una ricerca solo stima. È non una copia dei risultati di ricerca per una cassetta postale di individuazione dopo aver avviato. 
    
1. Salvare il testo seguente in un file di script di Windows PowerShell, utilizzando il suffisso nome di file ps1. Ad esempio possibile salvare in un file denominato `CreateMBSearchFromComplianceSearch.ps1`.
    
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

2. Nella sessione di Windows PowerShell che è stato creato nel passaggio 2, passare alla cartella in cui si trova lo script creato nel passaggio precedente ed eseguire lo script. Per esempio:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. Quando richiesto dallo script, digitare il nome della ricerca contenuto che si desidera convertire per una ricerca eDiscovery In locale (ad esempio, la ricerca creato nel passaggio 1) e quindi premere **INVIO**.
    
    Se lo script ha esito positivo, viene creata una nuova ricerca eDiscovery sul posto con lo stato **NotStarted**. Eseguire il comando  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` per visualizzare le proprietà della nuova ricerca. 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>Passaggio 4: avviare la ricerca eDiscovery sul posto

Lo script eseguito nel passaggio 3 crea una nuova ricerca eDiscovery sul posto, ma non la avvia. Il passaggio successivo consiste nell'avviare la ricerca, affinché sia possibile ottenere una stima dei risultati della ricerca.
  
1. Nell'interfaccia di amministrazione di Exchange (EAC) accedere a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.
    
3. Fare clic su **Cerca** ![sull'icona di ricerca](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **stima dei risultati di ricerca** per avviare la ricerca e ottenere una stima delle dimensioni totali e numero di elementi restituiti dalla ricerca. 
    
    Le stime vengono visualizzate nel riquadro dei dettagli. Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni visualizzate nel riquadro dei dettagli. 
    
4. Per visualizzare in anteprima i risultati dopo il completamento della ricerca, fare clic su **Anteprima risultati della ricerca** nel riquadro dei dettagli.
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>Passaggi successivi alla creazione e all'esecuzione della ricerca eDiscovery sul posto

Dopo aver avviato la ricerca eDiscovery sul posto creata dallo script nel passaggio 3, è possibile utilizzare il normale flusso di lavoro della ricerca eDiscovery sul posto per eseguire varie operazioni relative alla ricerca eDiscovery sui risultati della ricerca.
  
### <a name="create-an-in-place-hold"></a>Creare un blocco sul posto

1. In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
2. Nella visualizzazione elenco, selezionare la ricerca di eDiscovery In locale creata nel passaggio 3 e quindi fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif).
    
3. Nella pagina **Blocco sul posto**, selezionare la casella di controllo **Blocca il contenuto delle cassette postali selezionate che corrisponde alla query di ricerca** e scegliere una delle seguenti opzioni: 
    
  - **Tenere premuto per un tempo indefinito** - scegliere questa opzione per inserire gli elementi restituiti dalla ricerca una conservazione indefinita. Verranno mantenuti gli elementi in attesa finché non rimuovere la cassetta postale dalla ricerca o rimuovere la ricerca. 
    
  - **Specificare il numero di giorni di conservazione degli elementi rispetto al loro data di ricezione** : selezionare questa opzione per conservare gli elementi per un determinato periodo. La durata viene calcolata dalla data di ricezione o creato un elemento della cassetta postale. 
    
4. Fare clic su **Salva** per creare il blocco sul posto e riavviare la ricerca. 
    
[Inizio pagina](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>Copiare i risultati della ricerca

1. In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3.
    
3. Fare clic su **Cerca** ![sull'icona di ricerca](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), quindi fare clic su **copiare i risultati della ricerca** dall'elenco a discesa. 
    
4. In **Copia risultati della ricerca**, scegliere una delle seguenti opzioni:
    
    - **Includi elementi non ricercabili** : selezionare questa casella di controllo per includere gli elementi delle cassette postali che non eseguire la ricerca (ad esempio, i messaggi con allegati di tipi di file non è stati indicizzati dalla ricerca di Exchange). 
    
    - **Abilita deduplicazione** - selezionare questa casella di controllo per escludere i messaggi duplicati. Una sola istanza di un messaggio verrà copiata nella cassetta postale di individuazione. 
    
    - **Attivare la registrazione dei completa** - selezionare questa casella di controllo per includere un registro full nei risultati della ricerca. 
    
    - **Invio di posta elettronica al termine della copia** - selezionare questa casella di controllo per ottenere una notifica tramite posta elettronica al termine della ricerca. 
    
    - **Copiare i risultati a questa cassetta postale di individuazione** - fare clic su **Sfoglia** per selezionare la cassetta postale di individuazione in cui si desidera i risultati della ricerca copiati. 
    
5. Fare clic su **Copia** per avviare il processo per copiare i risultati della ricerca nella cassetta postale di individuazione specificata. 
    
6. Fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni sullo stato copia che viene visualizzata nel riquadro dei dettagli. 
    
7. Al termine della copia, fare clic su **Apri** per aprire la cassetta postale di individuazione e visualizzare i risultati della ricerca. 
  
### <a name="export-the-search-results"></a>Esportare i risultati della ricerca

1. In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
2. Nella visualizzazione elenco, selezionare la ricerca eDiscovery sul posto creata nel passaggio 3, quindi fare clic su **Esporta in un file PST**.
    
3. Nella finestra **Strumento eDiscovery per esportazione PST** effettuare le seguenti operazioni: 
    
    - Fare clic su **Sfoglia** per specificare la posizione in cui si desidera scaricare il file PST. 
    
    - Selezionare la casella di controllo **Abilita deduplicazione** per escludere i messaggi duplicati. Il file PST conterrà una sola istanza di un messaggio. 
    
    - Selezionare la casella di controllo **Includi elementi senza funzioni di ricerca** per includere elementi non ricercabili, ad esempio messaggi con allegati di tipi di file non indicizzabili da parte di Ricerca di Exchange. Gli elementi non ricercabili vengono esportati in un file PST separato. 
    
4. Fare clic su **Start** per esportare i risultati della ricerca in un file PST. 
    
    Viene visualizzata una finestra contenente informazioni relative allo stato del processo di esportazione.
