---
title: Creare un dizionario di parole chiave
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c8a95d1b-c3b6-4613-98ab-0331d1872cf3
description: Per identificare le informazioni riservate a volte è necessario cercare delle parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni riservate, questi elenchi hanno dimensioni limitate e richiedono la modifica di file XML per crearli o modificarli. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala molto più ampia, supportano fino a 100.000 termini per dizionario.
ms.openlocfilehash: 1cf41df5475af7ac5018cd34ea26e66ad5d668ee
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857234"
---
# <a name="create-a-keyword-dictionary"></a>Creare un dizionario di parole chiave

La prevenzione della perdita dei dati in Office 365 consente di identificare, monitorare e proteggere le informazioni riservate. Per identificare le informazioni riservate a volte è necessario cercare delle parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni riservate, questi elenchi hanno dimensioni limitate e richiedono la modifica di file XML per crearli o modificarli. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala molto più ampia, supportano fino a 100.000 termini per dizionario.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Procedura di base per la creazione di un dizionario di parole chiave

Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt), da un elenco che viene immesso direttamente nel cmdlet o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:
  
1. **Connettersi a PowerShell nel Centro sicurezza e conformità**: vedere [questo argomento](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. **Definire o caricare le parole chiave dell'origine prevista**: il cmdlet per creare un dizionario di parole chiave accetta un elenco di parole chiave separate da virgole, quindi questo passaggio può variare leggermente a seconda dell'origine delle parole chiave. 
    
3. **Codificare le parole chiave**: una volta caricate, le parole chiave vengono convertite in una matrice di byte prima di essere importate. 
    
4. **Creare il dizionario**: scegliere un nome e una descrizione e creare il dizionario. 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a>Creare un dizionario di parole chiave da un file

Spesso quando si deve creare un dizionario di grandi dimensioni, è necessario utilizzare parole chiave da un file o un elenco esportato da un'altra origine. In questo caso, viene creato un dizionario di parole chiave contenente un elenco di termini offensivi da evitare nella posta elettronica esterna. È necessario prima [connettersi al PowerShell del Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.
    
2. Salvare il file di testo con codifica Unicode. In Blocco note, \> **Salva con nome** \> **codifica** \> **Unicode**.
    
3. Leggere il file in una variabile eseguendo questo cmdlet:
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. Creare il dizionario eseguendo questo cmdlet:
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Modifica di un dizionario di parole chiave esistente

Potrebbe essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti. In questo esempio alcuni termini vengono modificati in PowerShell, salvati in locale, dove è possibile modificarli in un editor, e quindi inseriti al posto dei termini esistenti. Prima di tutto, recuperare l'oggetto dizionario:
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Durante la stampa di `$dict` vengono visualizzate le diverse variabili. Le stesse parole chiave vengono archiviate in un oggetto nel back-end, ma `$dict.KeywordDictionary` contiene una rappresentazione di queste parole in formato stringa, che verrà usata per modificare il dizionario. Prima di modificare il dizionario, è necessario riconvertire la stringa di termini in una matrice usando il metodo `.split(',')`. È quindi necessario eliminare gli spazi indesiderati tra le parole chiave con il metodo `.trim()`, lasciando solo le parole chiave da usare. 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

A questo punto si rimuovono alcuni termini dal dizionario. Il dizionario di esempio include solo alcune parole chiave, quindi è possibile evitare l'esportazione modificando il dizionario direttamente nel Blocco note. In genere, però, i dizionari contengono una grande quantità di testo, quindi è utile conoscere la procedura per modificarli facilmente in PowerShell.
  
Nell'ultimo passaggio le parole chiave sono state salvate in una matrice. Ci sono diversi modi per [rimuovere elementi da una matrice](https://go.microsoft.com/fwlink/p/?linkid=852620), ma l'approccio più diretto consiste nel creare una matrice di termini da rimuovere dal dizionario e quindi copiare solo i termini del dizionario che non si trovano nell'elenco di termini da rimuovere.
  
Eseguire il comando `$terms` per visualizzare l'elenco attuale di termini. L'output del comando avrà questo aspetto: 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

Eseguire questo comando per specificare i termini da rimuovere:
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Eseguire il comando `$updatedTerms` per visualizzare l'elenco aggiornato di termini. L'output del comando è simile al seguente (i termini specificati sono stati rimossi): 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

A questo punto, salvare il dizionario in locale e aggiungere qualche altro termine. È possibile aggiungere i termini qui in PowerShell, ma sarà comunque necessario esportare il file in locale per assicurarsi che sia stato salvato con la codifica Unicode e che contenga BOM.
  
Salvare il dizionario in locale eseguendo quanto segue:
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Ora basta aprire il file, aggiungere gli altri termini e salvare il file con la codifica Unicode (UTF-16). A questo punto, è possibile caricare i termini aggiornati e aggiornare il dizionario esistente.
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Ora il dizionario esistente è aggiornato. Il campo `Identity` prende il nome del dizionario. Se si vuole modificare anche il nome del dizionario con il cmdlet `set-`, basta aggiungere il parametro con il nuovo nome del dizionario `-Name` al comando precedente. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati

I dizionari di parole chiave possono essere usati nell'ambito dei requisiti di corrispondenza per un tipo di informazioni sensibili personalizzato oppure proprio come tipo di informazioni sensibili. Entrambi richiedono la [creazione di un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità di Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md). Seguire le istruzioni nell'articolo collegato per creare un tipo di informazioni sensibili. Una volta disponibile il file XML, per usare il dizionario è necessario l'identificatore GUID.
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**: 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

L'output del comando avrà questo aspetto:
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

Incollare l'identità nel file XML del tipo di informazioni riservate personalizzato e caricarlo. Il dizionario verrà visualizzato nell'elenco dei tipi di informazioni riservate e potrà essere usato direttamente nei criteri, specificando il numero di parole chiave che devono avere una corrispondenza.
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


