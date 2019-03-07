---
title: Creare un tipo di informazioni sensibili personalizzato
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Scoprire come creare, modificare, rimuovere e testare tipi di informazioni sensibili personalizzati per la prevenzione della perdita dei dati (DLP) nell'interfaccia utente grafica nel Centro sicurezza e conformità di Office 365.
ms.openlocfilehash: 5e20fac290a7d06c843a0043d95669d9c7f7cd05
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455138"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="85e3f-103">Creare un tipo di informazioni sensibili personalizzato</span><span class="sxs-lookup"><span data-stu-id="85e3f-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="85e3f-p101">Prevenzione della perdita dei dati (DLP) in Office 365 include molti [tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md) integrati già pronti per l'uso nei criteri di protezione della perdita dei dati. Tali tipi integrati possono aiutare a identificare e proteggere i numeri di carte di credito, di conti bancari, di passaporto e molti altri.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p101">Data loss prevention (DLP) in Office 365 includes many built-in [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="85e3f-106">Tuttavia, se è necessario identificare e proteggere un tipo diverso di informazioni sensibili (ad esempio gli ID dipendente o i numeri di progetto che usano un formato specifico dell'organizzazione), è possibile creare un tipo di informazioni sensibili personalizzato.</span><span class="sxs-lookup"><span data-stu-id="85e3f-106">But if you need to identify and protect a different type of sensitive information (for example, employee IDs or project numbers that uses a format specific to your organization) you can create a custom sensitive information type.</span></span>

<span data-ttu-id="85e3f-107">Le parti fondamentali di un tipo di informazioni sensibili personalizzato sono:</span><span class="sxs-lookup"><span data-stu-id="85e3f-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="85e3f-108">**Criterio principale**: ID dipendente, numeri di progetto e così via. In genere è identificato da un'espressione regolare (RegEx), ma può anche essere un elenco di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="85e3f-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="85e3f-p102">**Evidenza aggiuntiva**: si supponga di cercare un numero ID dipendente di nove cifre. Non tutti i numeri di nove cifre sono numeri ID dipendente, quindi è possibile cercare testo aggiuntivo: parole chiave come "dipendente", "badge", "ID" o altri criteri di testo basati su ulteriori espressioni regolari. Questa evidenza di supporto (denominata anche evidenza__ _corroborativa_) consente di aumentare la probabilità che il numero di nove cifre individuato nel contenuto sia davvero un numero ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="85e3f-p103">**Prossimità dei caratteri**: è logico che più il criterio principale e l'evidenza di supporto sono vicini tra loro, più è probabile che il contenuto rilevato sia quello che si sta cercando. È possibile specificare la distanza dei caratteri tra il criterio principale e l'evidenza di supporto (nota anche come _finestra di prossimità_) come mostrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="85e3f-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagramma dell'evidenza corroborativa e della finestra di prossimità](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="85e3f-p104">**Livello di probabilità**: più evidenze di supporto si hanno, più alta è la probabilità che una corrispondenza contenga le informazioni sensibili che si stanno cercando. È possibile assegnare livelli di probabilità più elevati per le corrispondenze rilevate con altre evidenze.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="85e3f-p105">Quando viene soddisfatto, un criterio restituisce un numero e un livello di probabilità che è possibile utilizzare nelle condizioni nei criteri DLP. Quando si aggiunge una condizione per il rilevamento di un tipo di informazione riservata a un criterio DLP, è possibile modificare il numero e il livello di probabilità, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="85e3f-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Numero di istanze e opzioni di precisione di corrispondenza](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="85e3f-120">Per creare tipi di informazioni riservate personalizzati nel Centro sicurezza e conformità di Office 365, si hanno le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-120">To create custom sensitive information types in the Office 365 Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="85e3f-p106">**Usare l'interfaccia utente**: questo metodo è più facile e veloce, ma fornisce meno opzioni di configurazione rispetto a PowerShell. Il resto di questo argomento descrive tali procedure.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="85e3f-p107">**Usare PowerShell**: questo metodo richiede di creare prima un file XML (denominato _pacchetto di regole_) che contiene uno o più tipi di informazioni sensibili, quindi usare PowerShell per importare il pacchetto di regole (l'importazione del pacchetto di regole è semplicissima rispetto alla creazione del pacchetto di regole). Questo metodo è molto più complesso dell'interfaccia utente, ma fornisce un maggior numero di opzioni di configurazione. Per istruzioni in merito, vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità di Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="85e3f-126">Le differenze principali vengono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="85e3f-126">The key differences are described in the following table:</span></span>

|<span data-ttu-id="85e3f-127">**Tipi di informazioni sensibili personalizzati nell'interfaccia utente**</span><span class="sxs-lookup"><span data-stu-id="85e3f-127">**Custom sensitive information types in the UI**</span></span>|<span data-ttu-id="85e3f-128">**Tipi di informazioni sensibili personalizzati in PowerShell**</span><span class="sxs-lookup"><span data-stu-id="85e3f-128">**Custom sensitive information types in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85e3f-129">Nome e descrizione sono in una lingua.</span><span class="sxs-lookup"><span data-stu-id="85e3f-129">Name and Description are in one language.</span></span>|<span data-ttu-id="85e3f-130">Supporta più lingue per nome e descrizione.</span><span class="sxs-lookup"><span data-stu-id="85e3f-130">Supports multiple languages for Name and Description.</span></span>|
|<span data-ttu-id="85e3f-131">Supporta un criterio.</span><span class="sxs-lookup"><span data-stu-id="85e3f-131">Supports one pattern.</span></span>|<span data-ttu-id="85e3f-132">Supporta più criteri.</span><span class="sxs-lookup"><span data-stu-id="85e3f-132">Supports multiple patterns.</span></span>|
|<span data-ttu-id="85e3f-133">Le evidenze di supporto possono essere:</span><span class="sxs-lookup"><span data-stu-id="85e3f-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="85e3f-134">• Espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="85e3f-134">• Regular expressions</span></span> <br/><span data-ttu-id="85e3f-135">• Parole chiave</span><span class="sxs-lookup"><span data-stu-id="85e3f-135">• Keywords</span></span> <br/><span data-ttu-id="85e3f-136">• Parole chiave personalizzate</span><span class="sxs-lookup"><span data-stu-id="85e3f-136">• Keyword dictionaries</span></span>|<span data-ttu-id="85e3f-137">Le evidenze di supporto possono essere:</span><span class="sxs-lookup"><span data-stu-id="85e3f-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="85e3f-138">• Espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="85e3f-138">• Regular expressions</span></span> <br/><span data-ttu-id="85e3f-139">• Parole chiave</span><span class="sxs-lookup"><span data-stu-id="85e3f-139">• Keywords</span></span> <br/><span data-ttu-id="85e3f-140">• Parole chiave personalizzate</span><span class="sxs-lookup"><span data-stu-id="85e3f-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="85e3f-141">• [Funzioni di prevenzione della perdita dei dati incorporate](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="85e3f-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="85e3f-142">I tipi di informazioni sensibili personalizzati vengono aggiunti al pacchetto di regole denominato Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="85e3f-142">Custom sensitive information types are added to the rule package named Microsoft.SCCManaged.CustomRulePack</span></span>|<span data-ttu-id="85e3f-143">È possibile creare fino a 10 pacchetti di regole che contengono tipi di informazioni sensibili personalizzati.</span><span class="sxs-lookup"><span data-stu-id="85e3f-143">You can create up to 10 rule packages that contain custom sensitive information types.</span></span>|
|<span data-ttu-id="85e3f-144">La corrispondenza al criterio richiede il rilevamento del criterio principale e di tutte le evidenze di supporto (viene usato l'operatore AND implicito).</span><span class="sxs-lookup"><span data-stu-id="85e3f-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="85e3f-145">La corrispondenza al criterio richiede il rilevamento del criterio principale e di una quantità configurabile di evidenze di supporto (vengono usati gli operatori AND e OR impliciti).</span><span class="sxs-lookup"><span data-stu-id="85e3f-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85e3f-146">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="85e3f-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85e3f-147">Per aprire il Centro sicurezza e conformità, vedere [Accedere al Centro sicurezza e conformità di Office 365](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85e3f-147">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="85e3f-p108">I tipi di informazioni sensibili personalizzati richiedono una certa familiarità con le espressioni regolari (RegEx). Per ulteriori informazioni sul motore Boost.RegEx (in precedenza noto come RegEx++) utilizzato per l'elaborazione del testo, vedere [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="85e3f-p109">Il Supporto tecnico Microsoft non può dare assistenza nella fornitura di definizioni di corrispondenza del contenuto personalizzate (definizione di classificazioni personalizzate o criteri di espressioni regolari). I tecnici del supporto possono fornire supporto limitato per la funzionalità, ma non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente. Come esempio del tipo di supporto che può essere fornito, è possibile fornire esempi di modelli di espressioni regolari a scopo di test. In alternativa, il supporto può aiutare nella risoluzione dei problemi di un criterio RegEx esistente che non si attiva come previsto.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="85e3f-p110">DLP usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business. Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario che venga effettuata una nuova ricerca per indicizzazione. Il contenuto viene sottoposto nuovamente alla ricerca in base a una programmazione, ma è possibile effettuare manualmente la ricerca per indicizzazione per una raccolta siti, un elenco o una raccolta. Per ulteriori informazioni, vedere [Richiedere manualmente l'esecuzione di una nuova ricerca per indicizzazione e la reindicizzazione di un sito, una raccolta o un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="85e3f-156">Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="85e3f-156">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="85e3f-157">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-157">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="85e3f-158">Le impostazioni sono abbastanza chiare e vengono spiegate nella pagina della procedura guidata associata:</span><span class="sxs-lookup"><span data-stu-id="85e3f-158">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="85e3f-159">**Nome**</span><span class="sxs-lookup"><span data-stu-id="85e3f-159">**Name**</span></span>

- <span data-ttu-id="85e3f-160">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85e3f-160">**Description**</span></span>

- <span data-ttu-id="85e3f-161">**Prossimità**</span><span class="sxs-lookup"><span data-stu-id="85e3f-161">**Proximity**</span></span>

- <span data-ttu-id="85e3f-162">**Livello di probabilità**</span><span class="sxs-lookup"><span data-stu-id="85e3f-162">**Confidence level**</span></span>

- <span data-ttu-id="85e3f-163">**Elemento pattern principale** (parole chiave, espressione regolare o dizionario)</span><span class="sxs-lookup"><span data-stu-id="85e3f-163">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="85e3f-164">Facoltativo **Elementi pattern di supporto** (parole chiave, espressione regolare o dizionario) e un valore di **costo minimo** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="85e3f-164">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="85e3f-p111">Ecco uno scenario: si desidera un tipo di informazioni sensibili personalizzato che rilevi i numeri dipendente di 9 cifre nel contenuto, con le parole chiave "dipendente", "ID" e "badge". Per creare un tipo di informazioni sensibili personalizzato, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="85e3f-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="85e3f-167">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-167">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Crea](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="85e3f-169">Nella pagina **Scegliere un nome e una descrizione** che viene visualizzata, immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-169">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="85e3f-170">**Nome**: ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="85e3f-170">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="85e3f-171">**Descrizione**: Rilevare i numeri ID dipendente di Contoso di 9 cifre.</span><span class="sxs-lookup"><span data-stu-id="85e3f-171">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Pagina con nome e descrizione](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="85e3f-173">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-173">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="85e3f-174">Nella pagina **Requisiti per la corrispondenza** che viene visualizzata, fare clic su **Aggiungi un elemento** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-174">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="85e3f-175">**Rilevare il contenuto che contiene**:</span><span class="sxs-lookup"><span data-stu-id="85e3f-175">**Detect content containing**:</span></span>
 
      <span data-ttu-id="85e3f-p112">a. Fare clic su **Una qualsiasi di queste condizioni** e selezionare **Espressione regolare**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="85e3f-p113">b. Nella casella di espressione regolare, immettere `(\s)(\d{9})(\s)` (numeri di 9 cifre racchiusi da spazi).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="85e3f-180">**Elementi di supporto**: fare clic su **Aggiungi gli elementi di supporto** e selezionare **Contiene questo elenco di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-180">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="85e3f-181">Nell'area **Contiene questo elenco di parole chiave** che viene visualizzata, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-181">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="85e3f-182">**Elenco di parole chiave**: immettere il valore seguente: dipendente,ID,badge.</span><span class="sxs-lookup"><span data-stu-id="85e3f-182">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="85e3f-183">**Numero minimo**: lasciare il valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="85e3f-183">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="85e3f-184">Lasciare il valore 60 del **Livello di probabilità** predefinito.</span><span class="sxs-lookup"><span data-stu-id="85e3f-184">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="85e3f-185">Lasciare il valore 300 della **Prossimità dei caratteri** predefinito.</span><span class="sxs-lookup"><span data-stu-id="85e3f-185">Leave the default **Character proximity** value 300.</span></span>

    ![Pagina Requisiti per la corrispondenza](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="85e3f-187">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="85e3f-188">Nella pagina **Verifica e completamento** che viene visualizzata, controllare le impostazioni e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-188">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Pagina Verifica e completamento](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="85e3f-p114">La pagina successiva invita a testare il nuovo tipo di informazioni sensibili personalizzato facendo clic su **Sì**. Per ulteriori informazioni, vedere **Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità**. Per testare la regola in un secondo momento, fare clic su [No](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p114">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Pagina Suggerimenti per il test](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="85e3f-194">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="85e3f-194">How do you know this worked?</span></span>

<span data-ttu-id="85e3f-195">Per verificare che sia stato creato correttamente un nuovo tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-195">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="85e3f-196">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e verificare che sia presente il nuovo tipo di informazioni sensibili personalizzato.</span><span class="sxs-lookup"><span data-stu-id="85e3f-196">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="85e3f-p115">Testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="85e3f-199">Modificare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="85e3f-199">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="85e3f-200">**Note**:</span><span class="sxs-lookup"><span data-stu-id="85e3f-200">**Notes**:</span></span>

- <span data-ttu-id="85e3f-p116">È possibile modificare solo i tipi di informazioni sensibili personalizzati; non è possibile modificare quelli predefiniti. Tuttavia, è possibile usare PowerShell per esportare i tipi di informazioni sensibili personalizzati predefiniti, personalizzarli e importarli come tipi di informazioni sensibili personalizzati. Per ulteriori informazioni, vedere [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p116">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="85e3f-p117">È possibile modificare solo i tipi di informazioni riservate personalizzati creati nell'interfaccia utente. Se è stata usata la [procedura di PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per importare un pacchetto di regole di tipo di informazioni riservate personalizzato, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="85e3f-p117">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="85e3f-206">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**, selezionare il tipo di informazioni sensibili personalizzato da modificare e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-206">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Posizione dei tipi di informazioni riservate e pulsante Modifica](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="85e3f-p118">Le stesse opzioni sono disponibili qui come quando è stato creato il tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p118">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="85e3f-210">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="85e3f-210">How do you know this worked?</span></span>

<span data-ttu-id="85e3f-211">Per verificare che sia stato modificato correttamente un tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85e3f-211">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="85e3f-212">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare le proprietà del tipo di informazioni sensibili personalizzato modificato.</span><span class="sxs-lookup"><span data-stu-id="85e3f-212">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="85e3f-p119">Testare il tipo di informazioni sensibili personalizzato modificato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p119">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="85e3f-215">Rimuovere tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="85e3f-215">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="85e3f-216">**Note**:</span><span class="sxs-lookup"><span data-stu-id="85e3f-216">**Notes**:</span></span>

- <span data-ttu-id="85e3f-217">È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="85e3f-217">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="85e3f-218">Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="85e3f-218">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="85e3f-219">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare uno o più tipi di informazioni sensibili personalizzati da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="85e3f-219">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="85e3f-220">Nel menu a comparsa che viene visualizzato, fare clic su **Elimina** (o **Eliminare i tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="85e3f-220">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Elimina](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="85e3f-222">Nel messaggio di avviso che viene visualizzato, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-222">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="85e3f-223">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="85e3f-223">How do you know this worked?</span></span>

<span data-ttu-id="85e3f-224">Per accertarsi di aver rimosso correttamente un tipo di informazioni sensibili personalizzato, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare che il tipo di informazioni sensibili personalizzato non sia più presente.</span><span class="sxs-lookup"><span data-stu-id="85e3f-224">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="85e3f-225">Testare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="85e3f-225">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="85e3f-226">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-226">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="85e3f-p120">Selezionare uno o più tipi di informazioni sensibili personalizzati da testare. Nel menu a comparsa che viene visualizzato, fare clic su **Tipo di test** (o **Test dei tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="85e3f-p120">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Tipo di test](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="85e3f-230">Nella pagina **Carica file da testare** che viene visualizzata, caricare un documento per il test trascinando e rilasciando un file o facendo clic su **Sfoglia** e selezionando un file.</span><span class="sxs-lookup"><span data-stu-id="85e3f-230">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Pagina Carica file da testare](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="85e3f-232">Fare clic sul pulsante **Test** per testare il documento per individuare le corrispondenze al criterio nel file.</span><span class="sxs-lookup"><span data-stu-id="85e3f-232">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="85e3f-233">Nella pagina **Risultati corrispondenza** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="85e3f-233">On the **Match results** page, click **Finish**.</span></span>

    ![Risultati corrispondenza](media/scc-cust-sens-info-type-test-results.png)