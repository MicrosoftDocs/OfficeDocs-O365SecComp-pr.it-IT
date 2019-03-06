---
title: Creare un dizionario di parole chiave
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Per identificare le informazioni riservate a volte è necessario cercare delle parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni riservate, questi elenchi hanno dimensioni limitate e richiedono la modifica di file XML per crearli o modificarli. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala molto più ampia, supportano fino a 100.000 termini per dizionario.
ms.openlocfilehash: bd13b4d522b22773fe56f93e1975f1d4decfbfe5
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410731"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="3f6a7-105">Creare un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="3f6a7-105">Create a keyword dictionary</span></span>

<span data-ttu-id="3f6a7-p102">La prevenzione della perdita dei dati in Office 365 consente di identificare, monitorare e proteggere le informazioni riservate. Per identificare le informazioni riservate a volte è necessario cercare delle parole chiave, in particolare quando si identifica un contenuto generico, ad esempio comunicazioni relative al settore sanitario, o contenuti con linguaggio inappropriato o esplicito. Anche se è possibile creare elenchi di parole chiave nei tipi di informazioni riservate, questi elenchi hanno dimensioni limitate e richiedono la modifica di file XML per crearli o modificarli. I dizionari di parole chiave offrono una gestione semplificata delle parole chiave e, su scala molto più ampia, supportano fino a 100.000 termini per dizionario.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p102">Data loss prevention (DLP) in Office 365 can identify, monitor, and protect your sensitive information. Identifying sensitive information sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication) or inappropriate or explicit language. While you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them. Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="3f6a7-110">Procedura di base per la creazione di un dizionario di parole chiave</span><span class="sxs-lookup"><span data-stu-id="3f6a7-110">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="3f6a7-p103">Le parole chiave per il dizionario possono provenire da diverse origini, in genere da un file (ad esempio, un elenco con estensione csv o txt), da un elenco che viene immesso direttamente nel cmdlet o da un dizionario esistente. Quando si crea un dizionario di parole chiave, seguire gli stessi passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list), from a list you enter directly in the cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="3f6a7-113">**Connettersi a PowerShell nel Centro sicurezza e conformità**: vedere [questo argomento](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3f6a7-113">**Connect to Security &amp; Compliance Center PowerShell** - see [this topic](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="3f6a7-114">**Definire o caricare le parole chiave dell'origine prevista**: il cmdlet per creare un dizionario di parole chiave accetta un elenco di parole chiave separate da virgole, quindi questo passaggio può variare leggermente a seconda dell'origine delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-114">**Define or load your keywords from your intended source** - the cmdlet to create a keyword dictionary accepts a comma-separated list of keywords, so this step will vary slightly depending on where your keywords come from.</span></span> 
    
3. <span data-ttu-id="3f6a7-115">**Codificare le parole chiave**: una volta caricate, le parole chiave vengono convertite in una matrice di byte prima di essere importate.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-115">**Encode your keywords** - once loaded, they're converted to a byte array before they're imported.</span></span> 
    
4. <span data-ttu-id="3f6a7-116">**Creare il dizionario**: scegliere un nome e una descrizione e creare il dizionario.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-116">**Create your dictionary** - choose a name and description and create your dictionary.</span></span> 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a><span data-ttu-id="3f6a7-117">Creare un dizionario di parole chiave da un file</span><span class="sxs-lookup"><span data-stu-id="3f6a7-117">Create a keyword dictionary from a file</span></span>

<span data-ttu-id="3f6a7-p104">Spesso quando si deve creare un dizionario di grandi dimensioni, è necessario utilizzare parole chiave da un file o un elenco esportato da un'altra origine. In questo caso, viene creato un dizionario di parole chiave contenente un elenco di termini offensivi da evitare nella posta elettronica esterna. È necessario prima [connettersi al PowerShell del Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p104">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You need to first [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/it-IT/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="3f6a7-121">Copiare le parole chiave in un file di testo e verificare che ogni parola chiave sia su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-121">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="3f6a7-p105">Salvare il file di testo con codifica Unicode. In Blocco note, \> **Salva con nome** \> **codifica** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p105">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="3f6a7-124">Leggere il file in una variabile eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-124">Read the file into a variable by running this cmdlet:</span></span>
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. <span data-ttu-id="3f6a7-125">Creare il dizionario eseguendo questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-125">Create the dictionary by running this cmdlet:</span></span>
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="3f6a7-126">Modifica di un dizionario di parole chiave esistente</span><span class="sxs-lookup"><span data-stu-id="3f6a7-126">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="3f6a7-p106">Potrebbe essere necessario modificare le parole chiave in uno dei dizionari di parole chiave o modificare uno dei dizionari predefiniti. In questo esempio alcuni termini vengono modificati in PowerShell, salvati in locale, dove è possibile modificarli in un editor, e quindi inseriti al posto dei termini esistenti. Prima di tutto, recuperare l'oggetto dizionario:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p106">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries. In this example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place. First, retrieve the dictionary object:</span></span>
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="3f6a7-p107">Durante la stampa di `$dict` vengono visualizzate le diverse variabili. Le stesse parole chiave vengono archiviate in un oggetto nel back-end, ma `$dict.KeywordDictionary` contiene una rappresentazione di queste parole in formato stringa, che verrà usata per modificare il dizionario. Prima di modificare il dizionario, è necessario riconvertire la stringa di termini in una matrice usando il metodo `.split(',')`. È quindi necessario eliminare gli spazi indesiderati tra le parole chiave con il metodo `.trim()`, lasciando solo le parole chiave da usare.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p107">Printing  `$dict` will show the various variables. The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary. Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method. Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="3f6a7-p108">A questo punto si rimuovono alcuni termini dal dizionario. Il dizionario di esempio include solo alcune parole chiave, quindi è possibile evitare l'esportazione modificando il dizionario direttamente nel Blocco note. In genere, però, i dizionari contengono una grande quantità di testo, quindi è utile conoscere la procedura per modificarli facilmente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p108">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="3f6a7-p109">Nell'ultimo passaggio le parole chiave sono state salvate in una matrice. Ci sono diversi modi per [rimuovere elementi da una matrice](https://go.microsoft.com/fwlink/p/?linkid=852620), ma l'approccio più diretto consiste nel creare una matrice di termini da rimuovere dal dizionario e quindi copiare solo i termini del dizionario che non si trovano nell'elenco di termini da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p109">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://go.microsoft.com/fwlink/p/?linkid=852620), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="3f6a7-p110">Eseguire il comando `$terms` per visualizzare l'elenco attuale di termini. L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p110">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="3f6a7-140">Eseguire questo comando per specificare i termini da rimuovere:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-140">Run this command to specify the terms that you want to remove:</span></span>
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="3f6a7-141">Eseguire questo comando per rimuovere effettivamente i termini dall'elenco:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-141">Run this command to actually remove the terms from the list:</span></span>
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="3f6a7-p111">Eseguire il comando `$updatedTerms` per visualizzare l'elenco aggiornato di termini. L'output del comando è simile al seguente (i termini specificati sono stati rimossi):</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p111">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="3f6a7-p112">A questo punto, salvare il dizionario in locale e aggiungere qualche altro termine. È possibile aggiungere i termini qui in PowerShell, ma sarà comunque necessario esportare il file in locale per assicurarsi che sia stato salvato con la codifica Unicode e che contenga BOM.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p112">Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.</span></span>
  
<span data-ttu-id="3f6a7-146">Salvare il dizionario in locale eseguendo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-146">Save the dictionary locally by running the following:</span></span>
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="3f6a7-p113">Ora basta aprire il file, aggiungere gli altri termini e salvare il file con la codifica Unicode (UTF-16). A questo punto, è possibile caricare i termini aggiornati e aggiornare il dizionario esistente.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p113">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="3f6a7-p114">Ora il dizionario esistente è aggiornato. Il campo `Identity` prende il nome del dizionario. Se si vuole modificare anche il nome del dizionario con il cmdlet `set-`, basta aggiungere il parametro con il nuovo nome del dizionario `-Name` al comando precedente.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p114">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="3f6a7-152">Uso dei dizionari di parole chiave nei tipi di informazioni riservate personalizzati e nei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="3f6a7-152">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="3f6a7-p115">I dizionari di parole chiave possono essere usati nell'ambito dei requisiti di corrispondenza per un tipo di informazioni sensibili personalizzato oppure proprio come tipo di informazioni sensibili. Entrambi richiedono la [creazione di un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità di Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md). Seguire le istruzioni nell'articolo collegato per creare un tipo di informazioni sensibili. Una volta disponibile il file XML, per usare il dizionario è necessario l'identificatore GUID.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p115">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves. Both require [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). Follow the instructions in the linked article to create a sensitive information type. Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="3f6a7-157">Per ottenere l'identità del dizionario, eseguire questo comando e copiare il valore della proprietà **Identity**:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-157">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="3f6a7-158">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="3f6a7-158">The output of the command looks like this:</span></span>
  
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

<span data-ttu-id="3f6a7-p116">Incollare l'identità nel file XML del tipo di informazioni riservate personalizzato e caricarlo. Il dizionario verrà visualizzato nell'elenco dei tipi di informazioni riservate e potrà essere usato direttamente nei criteri, specificando il numero di parole chiave che devono avere una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="3f6a7-p116">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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


