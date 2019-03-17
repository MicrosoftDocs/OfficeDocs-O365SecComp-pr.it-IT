---
title: Personalizzare una tipologia integrata di informazioni sensibili
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Quando si cercano informazioni sensibili nel contenuto, è necessario descriverle in una regola. La prevenzione della perdita dei dati (DLP) include regole per le tipologie più comuni di informazioni sensibili che è possibile utilizzare immediatamente. Per utilizzare queste regole, è necessario includerle in un criterio. Per modificare queste regole predefinite in modo che soddisfino esigenze specifiche dell'organizzazione, creare informazioni sensibili personalizzate. Questo argomento mostra come personalizzare il file XML che contiene la raccolta di regole esistenti per rilevare una gamma più ampia di potenziali informazioni sulle carte di credito.
ms.openlocfilehash: c0a3fcb86acf1eaa5df72e385b21e8dba9b0d668
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639073"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="8f0ee-107">Personalizzare una tipologia integrata di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f0ee-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="8f0ee-p102">Quando si cercano informazioni sensibili nel contenuto, è necessario descriverle in una *regola*. La prevenzione della perdita dei dati (DLP) include regole per le tipologie più comuni di informazioni sensibili che è possibile utilizzare immediatamente. Per utilizzare queste regole, è necessario includerle in un criterio. Per modificare queste regole predefinite in modo che soddisfino esigenze specifiche dell'organizzazione, creare informazioni sensibili personalizzate. Questo argomento mostra come personalizzare il file XML che contiene la raccolta di regole esistenti per rilevare una gamma più ampia di potenziali informazioni sulle carte di credito.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="8f0ee-p103">L'esempio riportato può essere applicato ad altre tipologie di informazioni sensibili predefinite. Per un elenco delle tipologie di informazioni sensibili predefinite e delle definizioni XML, vedere [Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="8f0ee-115">Esportare il file XML delle regole correnti</span><span class="sxs-lookup"><span data-stu-id="8f0ee-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="8f0ee-116">Per esportare l'XML, è necessario [connettersi al Centro sicurezza e conformità tramite una sessione remota di PowerShell](https://go.microsoft.com/fwlink/?linkid=799771).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771).</span></span>
  
1. <span data-ttu-id="8f0ee-p104">In PowerShell, digitare quanto segue per visualizzare le regole dell'organizzazione sullo schermo. Se non sono state create regole proprie, verranno visualizzate solo quelle predefinite con l'etichetta "Pacchetto di regole Microsoft".</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>
    
     `Get-DlpSensitiveInformationTypeRulePackage`
    
2. <span data-ttu-id="8f0ee-p105">Archiviare le regole dell'organizzazione in una variabile, digitando quanto segue consentirà di recuperare facilmente le regole in un secondo momento, nel formato adatto ai comandi di PowerShell remoti.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p105">Store your organization's rules in a in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>
    
     `$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage`
    
3. <span data-ttu-id="8f0ee-p106">Creare un file con formattazione XML con tutti i dati, digitando quanto segue (`Set-content` è la parte del cmdlet che scrive nel file XML).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
     `Set-Content -path "C:\custompath\exportedRules.xml" -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection`
    
    > [!IMPORTANT]
    > <span data-ttu-id="8f0ee-p107">Assicurarsi di utilizzare il percorso in cui è effettivamente archiviato il pacchetto di regole. `C:\custompath\` è un segnaposto.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="8f0ee-125">Individuare la regola da modificare nel file XML</span><span class="sxs-lookup"><span data-stu-id="8f0ee-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="8f0ee-p108">Con i cmdlet precedenti è stata esportata l'intera *raccolta di regole*, che include le regole predefinite fornite. Successivamente sarà necessario cercare in modo specifico la regola relativa alla carta di credito da modificare.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p108">The cmdlets above exported the entire  *rule collection*  , which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="8f0ee-128">Usare un editor di testo per aprire il file esportato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="8f0ee-p109">Scorrere verso il basso il tag `<Rules>`, che corrisponde all'inizio della sezione che contiene le regole DLP (poiché il file XML contiene le informazioni relative all'intera raccolta di regole, quindi per accedere alle regole è necessario scorrere le altre informazioni contenute nella parte superiore).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. (Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.)</span></span> 
    
3. <span data-ttu-id="8f0ee-p110">Cercare *Func_credit_card* per trovare la definizione della regola relativa al numero della carta di credito. Nel file XML, i nomi delle regole non possono contenere spazi, pertanto gli spazi in genere vengono sostituiti con caratteri di sottolineatura e i nomi delle regole vengono a volte abbreviati. Ne è un esempio la regola relativa al numero di previdenza sociale negli Stati Uniti, abbreviata come "SSN". L'XML della regola relativa al numero della carta di credito non può essere simile all'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p110">Look for  *Func_credit_card*  to find the Credit Card Number rule definition. (In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span> 
    
  ```
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="8f0ee-p111">Una volta individuata la definizione della regola relativa al numero della carta di credito nel file XML, è possibile personalizzare l'XML della regola in base alle proprie esigenze (per un aggiornamento sulle definizioni XML, vedere il [glossario](#term-glossary) al termine dell'argomento).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. (For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.)</span></span> 
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="8f0ee-137">Modificare il file XML o creare una nuova tipologia di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f0ee-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="8f0ee-p112">Prima di tutto, è necessario creare una nuova tipologia di informazioni sensibili, poiché non è possibile modificare direttamente le regole predefinite. Con una nuova tipologia di informazioni sensibili è possibile eseguire un'ampia varietà di operazioni, descritte in [Creare una tipologia personalizzata di informazioni sensibili in PowerShell per Centro sicurezza e conformità di Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md). Nell'esempio riportato, per una immediata comprensione, verranno rimosse solo le prove corroborative e verranno aggiunte parole chiave alla regola relativa al numero della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="8f0ee-p113">Tutte le definizioni della regola XML sono basate sul seguente modello generale. È necessario copiare e incollare la definizione XML relativa al numero della carta di credito nel modello, modificare alcuni valori (vedere i segnaposto ". . ." in questo esempio), quindi caricare il codice XML modificato come nuova regola da usare nei criteri.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="8f0ee-p114">A questo punto, il risultato ha un aspetto simile all'XML seguente. Poiché i pacchetti delle regole e le regole vengono identificati in base a GUID univoci, è necessario generare due GUID: uno per il pacchetto delle regole e uno per sostituire il GUID per la regola relativa al numero della carta di credito. Il GUID per l'ID entità nel codice di esempio seguente è quello della definizione della regola predefinita da sostituire con una nuova. Esistono diversi modi per generare i GUID, ma è possibile farlo facilmente in PowerShell digitando **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. (The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.) There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="8f0ee-149">Rimuovere il requisito prove corroborative da una tipologia di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f0ee-149">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="8f0ee-p115">Una volta creata una nuova tipologia di informazioni sensibili, è possibile caricarla nel &amp;Centro sicurezza e conformità. Il passaggio successivo consiste nel rendere la regola più specifica. Modificare la regola di modo che appaia come un codice di 16 cifre, che superi il checksum e non richieda altre prove (corroborative) (ad esempio parole chiave). A questo scopo, è necessario rimuovere la parte del codice XML che verifica la presenza di prove corroborative. Queste ultime sono molto utili per ridurre i falsi positivi, in genere parole chiave o la data di scadenza accanto al numero della carta di credito. Se si rimuove tale prova, è necessario anche considerare il fattore di affidabilità quando viene individuato il numero di carta di credito abbassando il valore `confidenceLevel`, 85 nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p115">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific. Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence (for example keywords). To do this, you need to remove the part of the XML that looks for corroborative evidence. Corroborative evidence is very helpful in reducing false positives because usually there are certain keywords or an expiration date near the credit card number. If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="8f0ee-155">Cercare le parole chiave specifiche per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8f0ee-155">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="8f0ee-p116">È anche possibile avere prove corroborative, ma con parole chiave diverse o aggiuntive, così come è possibile cambiare il percorso in cui trovare tali prove. È possibile modificare il `patternsProximity` per espandere o ridurre la finestra delle prove corroborative a 16 cifre. Per aggiungere parole chiave, è necessario definire un elenco di parole chiave e farvi riferimento all'interno della regola. Il codice XML seguente consente di aggiungere le parole chiave "carta aziendale" e "carta Contoso" in modo che i messaggi che contengono queste frasi (nei 150 caratteri del numero della carta di credito) verranno identificati come numero della carta di credito.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span> 
  
```
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="8f0ee-160">Caricare una regola</span><span class="sxs-lookup"><span data-stu-id="8f0ee-160">Upload your rule</span></span>

<span data-ttu-id="8f0ee-161">Per caricare una regola, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-161">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="8f0ee-p117">Salvarla come file XML con codifica Unicode. Questo passaggio è fondamentale perché la regola non funziona se il file viene salvato con una codifica diversa.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="8f0ee-164">Connettersi al Centro sicurezza e conformità tramite una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-164">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="8f0ee-165">In PowerShell digitare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-165">In the PowerShell, type the following.</span></span>
    
     <span data-ttu-id="8f0ee-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8f0ee-p118">Assicurarsi di utilizzare il percorso in cui è effettivamente archiviato il pacchetto di regole. `C:\custompath\` è un segnaposto.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="8f0ee-169">Per confermare, digitare Y, quindi premere **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-169">To confirm, type Y, and then press **Enter**.</span></span>
    
5. <span data-ttu-id="8f0ee-170">Verificare che la nuova regola sia stata caricata digitando `Get-DlpSensitiveInformationType`, che ora visualizza il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-170">Verify that your new rule was uploaded by typing  `Get-DlpSensitiveInformationType`, which now displays the name of your rule.</span></span>
    
<span data-ttu-id="8f0ee-p119">Per iniziare a usare la nuova regola per rilevare informazioni sensibili, è necessario aggiungere una regola a un criterio DLP. Per informazioni su come aggiungere una regola a un criterio, vedere [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="8f0ee-173">Glossario</span><span class="sxs-lookup"><span data-stu-id="8f0ee-173">Term glossary</span></span>

<span data-ttu-id="8f0ee-174">Di seguito sono riportati i termini incontrati durante la procedura.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-174">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="8f0ee-175">**Termine**</span><span class="sxs-lookup"><span data-stu-id="8f0ee-175">**Term**</span></span>|<span data-ttu-id="8f0ee-176">**Definizione**</span><span class="sxs-lookup"><span data-stu-id="8f0ee-176">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f0ee-177">Entità</span><span class="sxs-lookup"><span data-stu-id="8f0ee-177">Entity</span></span>|<span data-ttu-id="8f0ee-p120">Le entità sono le tipologie di informazioni sensibili, come i numeri della carta di credito. Ciascuna entità ha un GUID univoco come ID. Copiando un GUID e cercandolo nell'XML, si troverà la definizione della regola XML e tutte le traduzioni localizzate di tale regola XML. Inoltre, la definizione può essere trovata individuando il GUID per la traduzione ed effettuando una ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="8f0ee-182">Funzioni</span><span class="sxs-lookup"><span data-stu-id="8f0ee-182">Functions</span></span>|<span data-ttu-id="8f0ee-p121">Il file XML fa riferimento a `Func_credit_card`, una funzione nel codice compilato. Le funzioni vengono utilizzate per eseguire regex complessi e verificare la corrispondenza del checksum alle regole predefinite. Poiché è ciò che accade nel codice, alcune variabili non vengono visualizzate nel file XML.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="8f0ee-185">IdMatch</span><span class="sxs-lookup"><span data-stu-id="8f0ee-185">IdMatch</span></span>|<span data-ttu-id="8f0ee-p122">L'identificatore cui il modello cerca corrispondenza, ad esempio, un numero di carta di credito. Sono disponibili altre informazioni a riguardo e relativamente ai tag `Match` nelle [Entità regole](https://support.office.com/article/c4ab8707-0839-4855-9390-3dbcb43475a7.aspx#dlp-entity).</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p122">This is the identifier that the pattern is to trying to match—for example, a credit card number. You can read more about this and about the  `Match` tags in [Entity rules](https://support.office.com/article/c4ab8707-0839-4855-9390-3dbcb43475a7.aspx#dlp-entity).</span></span>|
|<span data-ttu-id="8f0ee-188">Elenchi di parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f0ee-188">Keyword lists</span></span>|<span data-ttu-id="8f0ee-p123">Il file XML fa anche riferimento a `keyword_cc_verification` e `keyword_cc_name`, elenchi di parole chiave, in cui si ricercano corrispondenze per l'entità all'interno di `patternsProximity`. Questi attualmente non vengono visualizzati nell'XML.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p123">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="8f0ee-191">Modello</span><span class="sxs-lookup"><span data-stu-id="8f0ee-191">Pattern</span></span>|<span data-ttu-id="8f0ee-p124">Il modello contiene l'elenco di ciò che il tipo di informazione sensibile sta cercando. Ciò include parole chiave, regex e funzioni interne (che eseguono attività come la verifica checksum). Le tipologie di informazioni sensibili possono avere più modelli con affidabilità univoche. Ciò è utile quando si crea una tipologia di informazioni sensibili che restituisce affidabilità elevata se sono disponibili prove corroborative e affidabilità minore se sono disponibili prove corroborative minime o nulle.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p124">The pattern contains the list of what the sensitive type is looking for. This includes keywords, regexes, and internal functions (that perform tasks like verifying checksums). Sensitive information types can have multiple patterns with unique confidences. This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="8f0ee-196">Modello confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="8f0ee-196">Pattern confidenceLevel</span></span>|<span data-ttu-id="8f0ee-p125">Il livello di affidabilità che il motore DLP individui una corrispondenza. Tale livello di affidabilità è associato a una corrispondenza con i modelli se vengono soddisfatti i requisiti del modello. Questa misura di affidabilità è da prendere in considerazione quando si usano regole di flusso di posta (note anche come regole di trasporto) di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p125">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="8f0ee-200">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="8f0ee-200">patternsProximity</span></span>|<span data-ttu-id="8f0ee-201">Quando viene individuato qualcosa di simile al modello di un numero di carta di credito, `patternsProximity` è la prossimità al numero in cui verranno ricercate prove corroborative.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-201">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="8f0ee-202">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="8f0ee-202">recommendedConfidence</span></span>|<span data-ttu-id="8f0ee-p126">Il livello di affidabilità consigliato per la regola. Si applica a entità e affinità. Per le entità, il numero non viene mai valutato rispetto al valore `confidenceLevel` dei modelli. È semplicemente un suggerimento che consente di scegliere un livello di affidabilità se si desidera applicarne uno. Per le affinità, il valore `confidenceLevel` del modello deve essere maggiore del numero `recommendedConfidence` per richiamare un'azione di regola di flusso di posta. Il valore `recommendedConfidence` è il livello di affidabilità predefinito usato nella regola di flusso di posta che richiama un'azione. Se si desidera, è anche possibile modificare manualmente la regola di flusso di posta da richiamare in base al livello di affidabilità del modello.</span><span class="sxs-lookup"><span data-stu-id="8f0ee-p126">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="8f0ee-210">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8f0ee-210">For more information</span></span>

- [<span data-ttu-id="8f0ee-211">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f0ee-211">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="8f0ee-212">Creare una tipologia personalizzata di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f0ee-212">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="8f0ee-213">Panoramica relativa ai criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="8f0ee-213">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    

