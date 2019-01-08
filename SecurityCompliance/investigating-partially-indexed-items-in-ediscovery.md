---
title: Investigating partially indexed items in Office 365 eDiscovery (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Parzialmente voci indicizzate (anche gli elementi di chiamata non indicizzata) sono elementi della cassetta postale di Exchange e i documenti in SharePoint e ai siti OneDrive per qualche motivo non sono stati completamente indicizzato per la ricerca del contenuto. In questo articolo per informazioni sui motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi indicizzati parzialmente, identificare gli errori di ricerca di elementi indicizzati parzialmente e utilizzare uno script di PowerShell per determinare l'esposizione dell'organizzazione per la posta elettronica parzialmente indicizzato elementi.
ms.openlocfilehash: c1003f9907fffa37042ba62d01e4d938250cf570
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749340"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>Investigating partially indexed items in Office 365 eDiscovery (Analisi di elementi parzialmente indicizzati in eDiscovery di Office 365)

Una ricerca di contenuto che viene eseguita da Office 365 Security &amp; centro conformità include automaticamente elementi indicizzati parzialmente nei risultati della ricerca stimati quando si esegue una ricerca. Elementi indicizzati parzialmente sono elementi della cassetta postale di Exchange e documenti in SharePoint e OneDrive per i siti che, per qualche motivo, non sono stati completamente indicizzati per la ricerca. La maggior parte dei messaggi di posta elettronica e documenti del sito vengono indicizzati correttamente perché sono inclusi entro il [limite per il servizio di indicizzazione di messaggi di posta elettronica](limits-for-content-search.md#indexing-limits-for-email-messages). Tuttavia, alcuni elementi possono superare i limiti di indicizzazione e sarà possibile indicizzare parzialmente. Di seguito sono altri motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi indicizzati parzialmente quando si esegue una ricerca di contenuto:
  
- Messaggi di posta elettronica dispongono di un file allegato di un tipo di file che non possono essere indicizzato; Nella maggior parte dei casi, il tipo di file è [sconosciuta o non è supportato per l'indicizzazione](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- Messaggi di posta elettronica sono un file allegato senza un gestore valido, ad esempio file di immagine. Questa è la causa più comune di elementi di posta elettronica parzialmente indicizzati
    
- Troppi file allegati al messaggio di posta elettronica
    
- Un file allegato al messaggio di posta elettronica è troppo grande
    
- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per uno specifico file
    
Sebbene varino, per dimensioni parzialmente indicizzato maggior parte dei clienti di organizzazioni di Office 365 hanno meno dell'1% del contenuto dal volume e inferiore a 12% del contenuto. Il motivo per la differenza tra il volume rispetto alla dimensione è che i file di dimensioni maggiori probabilità di che include contenuto che non possono essere indicizzato completamente.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Perché il conteggio di elementi indicizzati parzialmente viene modificati per una ricerca?

Dopo l'esecuzione di una ricerca di contenuto in Office 365 Security &amp; centro conformità, il numero totale e le dimensioni di elementi indicizzati parzialmente nelle posizioni in cui sono stati ricercati sono elencate nelle statistiche di risultati di ricerca che vengono visualizzate nelle statistiche dettagliate per la ricerca. Si noti che detti *elementi indicizzati* nelle statistiche di ricerca. Ecco alcuni aspetti che incideranno il numero di elementi indicizzati parzialmente restituite nei risultati della ricerca: 
  
- Se un elemento è parzialmente indicizzato e genera una corrispondenza per la query di ricerca, viene incluso il conteggio (e dimensioni) di elementi indicizzati parzialmente e gli elementi dei risultati di ricerca. Tuttavia, quando vengono esportati i risultati della ricerca stessa, l'elemento è incluso solo con set di risultati di ricerca; non è incluso come elemento parzialmente indicizzato.
    
- Se si specifica un intervallo di date per una query di ricerca (per includerla nella query con parole chiave) o utilizzando una condizione, qualsiasi elemento parzialmente indicizzata che non soddisfano l'intervallo di date non include il numero di elementi indicizzati parzialmente. Solo gli elementi indicizzati parzialmente compresi nell'intervallo di date sono inclusi nel conteggio degli elementi parzialmente indicizzati.
    
 **Nota:** Parzialmente indicizzato elementi disponibili in SharePoint e OneDrive siti *non* inclusi nella stima di elementi indicizzati parzialmente visualizzate nelle statistiche dettagliate per la ricerca. Tuttavia, è possono esportare elementi indicizzati parzialmente quando si esportano i risultati di ricerca di contenuto. Ad esempio, se la ricerca solo i siti in una ricerca di contenuto, il numero stimato parzialmente elementi indicizzati sarà zero. 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Calcolare il rapporto di elementi indicizzati parzialmente all'interno dell'organizzazione

Per comprendere i propri sistemi dell'organizzazione a elementi indicizzati parzialmente, è possibile eseguire una ricerca per tutto il contenuto in tutte le cassette postali (tramite una query con parole chiave vuota). Nell'esempio seguente riportata di seguito, esistono 56,208 (4,830 MB) completamente indicizzato elementi e 470 (316 MB) parzialmente voci indicizzate.
  
![Ad esempio che mostra le statistiche ricerca parzialmente voci indicizzate](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
È possibile determinare la percentuale di elementi indicizzati parzialmente utilizzando i calcoli seguenti.
  
 **Per calcolare il rapporto di elementi indicizzati parzialmente all'interno dell'organizzazione:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
Utilizzando i risultati della ricerca dell'esempio precedente,. 84% di tutti gli elementi delle cassette postali parzialmente vengono indicizzati.
  
 **Per calcolare la percentuale delle dimensioni di elementi indicizzati parzialmente all'interno dell'organizzazione:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Nell'esempio precedente, in modo 6.54% della dimensione totale di elementi delle cassette postali sono di elementi indicizzati parzialmente. Come affermato in precedenza, la maggior parte delle organizzazioni di Office 365 per dimensioni parzialmente indicizzato i clienti hanno meno dell'1% del contenuto volume e inferiore a 12% del contenuto.

## <a name="working-with-partially-indexed-items"></a>Utilizzo di parzialmente voci indicizzate

In casi quando è necessario esaminare parzialmente gli elementi per verificare che non contengono informazioni necessarie, è possibile [esportare un report di ricerca del contenuto](export-a-content-search-report.md) che contiene informazioni sugli elementi parzialmente indicizzati. Quando si esporta un report di ricerca del contenuto, assicurarsi di selezionare una delle opzioni di esportazione che include gli elementi parzialmente indicizzati. 
  
![Scegliere l'opzione secondo o terzo per esportare elementi parzialmente indicizzati](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Quando si esporta i risultati di ricerca del contenuto o un report di ricerca del contenuto mediante una delle opzioni seguenti, Esporta include un report denominato Items.csv non indicizzate. In questo report include la maggior parte delle stesse informazioni come file ResultsLog.csv. Tuttavia, il file non indicizzate Items.csv include due campi relativi agli elementi indicizzati parzialmente: **Errore tag** e **Le proprietà di errore**. Questi campi contenenti informazioni sull'errore di indicizzazione per ogni elemento parzialmente indicizzato. Utilizzando le informazioni contenute in questi due campi consentono di determinare se l'errore di indicizzazione per un determinato un impatto significativo sull'analisi. In caso affermativo, è possibile eseguire una ricerca di contenuto mirata e recuperare ed esportare documenti di SharePoint o OneDrive e messaggi di posta elettronica specifici in modo da poter esaminare in modo da determinare se è rilevanti per le indagini. Per istruzioni dettagliate, vedere [Preparazione di un file CSV per una ricerca di contenuto personalizzati in Office 365](csv-file-for-an-id-list-content-search.md).
  
 **Nota:** Il file non indicizzate Items.csv contiene inoltre campi denominati **Tipo di errore** e il **Messaggio di errore**. Si tratta di campi legacy che contengono informazioni simili a quelle contenute nei campi **I tag di errore** e **Le proprietà di errore** , ma con informazioni meno dettagliate. È possibile ignorare questi campi legacy. 
  
## <a name="errors-related-to-partially-indexed-items"></a>Errori correlati agli elementi parzialmente indicizzati

I tag di errore è costituiti da due tipi di informazioni, l'errore e il tipo di file. Ad esempio, in questa coppia di errori/filetype:

```
 parseroutputsize_xls
```

   
 `parseroutputsize`è l'errore e `xls` corrisponde al tipo di file del file di cui si è verificato l'errore. In casi sono stati il tipo di file non è stato il tipo di file è stato riconosciuto o non si applica all'errore che verrà visualizzato il valore `noformat` al posto del tipo di file. 
  
Di seguito è un elenco di indicizzazione errori e una descrizione per la possibile causa dell'errore.
  
|**Tag di errore**|**Descrizione**|
|:-----|:-----|
| `attachmentcount` <br/> |Messaggio di posta elettronica con un numero eccessivo di allegati e alcune di questi allegati non sono stati elaborati.  <br/> |
| `attachmentdepth` <br/> |Il parser fact e documenti contenuto trovato troppi livelli di allegati annidati all'interno degli altri allegati. Alcuni di questi allegati non sono stati elaborati.  <br/> |
| `attachmentrms` <br/> |Un allegato non riuscito decodifica perché non è stato protetti con RMS.  <br/> |
| `attachmentsize` <br/> |Un file allegato al messaggio di posta elettronica è troppo grande e non può essere elaborato.  <br/> |
| `indexingtruncated` <br/> |Quando si scrive il messaggio di posta elettronica elaborato nell'indice, una delle proprietà indicizzabili troppo grande ed è stata troncata. Le proprietà troncate sono elencate nel campo proprietà errori.  <br/> |
| `invalidunicode` <br/> |Messaggio di posta elettronica contenuto testo che non è stato elaborato come Unicode valido. Indicizzazione di questo elemento può essere incompleta.  <br/> |
| `parserencrypted` <br/> |Il contenuto dell'allegato o messaggio di posta elettronica è crittografato e Office 365 non decodificare il contenuto.  <br/> |
| `parsererror` <br/> |Si è verificato un errore sconosciuto durante l'analisi. Ciò è dovuto in genere a un bug software o un arresto anomalo del servizio.  <br/> |
| `parserinputsize` <br/> |Un allegato è troppo grande per il parser per la gestione e l'analisi di tale allegato non avvenire o non è stato completato.  <br/> |
| `parsermalformed` <br/> |Un allegato non valido e non gestito dal parser. Il risultato dal file precedente can formati, file creati da software incompatibile o virus FALSO qualcosa di diverso da quello richiesto.  <br/> |
| `parseroutputsize` <br/> |L'output dell'analisi di un allegato è troppo grande e hanno dovuto essere troncato.  <br/> |
| `parserunknowntype` <br/> |Un allegato con un tipo di file che non è stato rilevato Office 365.  <br/> |
| `parserunsupportedtype` <br/> |Un allegato con un tipo di file Office 365could rileva, ma l'analisi di tale tipo di file non è supportata.  <br/> |
| `propertytoobig` <br/> |Il valore di una proprietà di un messaggio di posta elettronica di Exchange archivio è troppo grande per essere recuperati e il messaggio non è stato elaborato. Ciò accade di solito alla proprietà del corpo del messaggio di posta elettronica.  <br/> |
| `retrieverrms` <br/> |La funzione di recupero del contenuto non riuscito decodificare un messaggio protetto con RMS.  <br/> |
| `wordbreakertruncated` <br/> |Sono state identificate troppe parole del documento durante l'indicizzazione. Elaborazione della proprietà interrotta quando sta per raggiungere il limite e la proprietà viene troncata.  <br/> |
   
Campi di errore vengono descritti i campi che sono interessati dall'errore elaborazione elencato nel campo tag di errore. Se si esegue la ricerca una proprietà come `subject` o `participants`, errori nel corpo del messaggio non influiscono su risultati della ricerca. Può essere utile per determinare esattamente quali elementi indicizzati parzialmente potrebbe essere necessario ulteriori analisi.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Utilizzo di uno script di PowerShell per determinare l'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati

La procedura seguente è illustrato come eseguire uno script di PowerShell che esegue la ricerca per tutti gli elementi in tutte le cassette postali di Exchange, quindi genera un report su rapporto dell'organizzazione di elementi di posta elettronica parzialmente indicizzati (numero e dimensioni) e viene visualizzato il numero di elementi (e il tipo di file) per ogni errore di indicizzazione che si verifica. Utilizzare le descrizioni dei tag di errore nella sezione precedente per identificare l'errore di indicizzazione.
  
1. Salvare il testo seguente in un file di script di Windows PowerShell con il suffisso filename. ps1; ad esempio `PartiallyIndexedItems.ps1`.

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. [Connettersi a Office 365 protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/p/?linkid=627084).
    
3. In sicurezza &amp; PowerShell centro conformità, passare alla cartella a cui è stato salvato lo script nel passaggio 1 e quindi eseguire lo script. Per esempio:

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
Di seguito è riportato un esempio fo l'output restituito dallo script.
  
![Esempio di output di uno script che genera un report sull'esposizione dell'organizzazione agli elementi di posta elettronica parzialmente indicizzati](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
Tenere presente quanto segue:
  
1. Il numero totale e le dimensioni degli elementi di posta elettronica e rapporto dell'organizzazione indicizzati parzialmente degli elementi di posta (numero e dimensioni)
    
2. Un tag di errore di elenco e i corrispondenti tipi di file per cui si è verificato l'errore.
  
## <a name="see-also"></a>Vedere anche

[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)
