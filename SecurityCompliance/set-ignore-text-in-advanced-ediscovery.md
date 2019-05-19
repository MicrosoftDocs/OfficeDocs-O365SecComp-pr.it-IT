---
title: Impostare l'opzione Ignora testo per ANALYZE in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Informazioni su come definire la regola per ignorare il testo specifico quando si utilizzano i moduli Analyze and process in Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: 70d9879f1cb6b3def06ff978fc2f7fa8f20a92f0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156678"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7829c-103">Impostare l'opzione Ignora testo per ANALYZE in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7829c-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="7829c-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7829c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7829c-106">La funzionalità Ignora testo può essere applicata a tutti o a uno dei seguenti moduli avanzati di eDiscovery: Analyze (near-Duplicates, email Threads, Themes) e pertinenza.</span><span class="sxs-lookup"><span data-stu-id="7829c-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="7829c-107">Il testo ignorato non verrà visualizzato nei file visualizzati in pertinenza e l'analisi/calcoli ignorerà il testo ignorato.</span><span class="sxs-lookup"><span data-stu-id="7829c-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="7829c-108">Se la caratteristica Ignora testo era stata definita in precedenza per i moduli già in esecuzione, l'impostazione Ignora testo sarà ora protetta dalla modifica.</span><span class="sxs-lookup"><span data-stu-id="7829c-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="7829c-109">Tuttavia, la caratteristica Ignora testo per il modulo pertinenza può comunque essere modificata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="7829c-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="7829c-110">Modalità di applicazione dei filtri di testo Ignora</span><span class="sxs-lookup"><span data-stu-id="7829c-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="7829c-111">Più filtri di testo Ignora vengono applicati nell'ordine in cui sono stati immessi.</span><span class="sxs-lookup"><span data-stu-id="7829c-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="7829c-112">Per modificare l'ordine in cui vengono applicati, è necessario eliminarlo e riimmetterlo nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="7829c-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="7829c-113">Ad esempio, se il contenuto del testo è: "DAVE BOB ALICE CAROL EVE", di seguito sono riportati alcuni esempi di voci di testo Ignora e i risultati:</span><span class="sxs-lookup"><span data-stu-id="7829c-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7829c-114">**Ignora voci di testo**</span><span class="sxs-lookup"><span data-stu-id="7829c-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="7829c-115">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="7829c-115">**Results**</span></span> <br/> |
|<span data-ttu-id="7829c-116">"ALICE", "BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="7829c-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="7829c-117">"DAVE EVE"</span><span class="sxs-lookup"><span data-stu-id="7829c-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="7829c-118">"ALICE", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="7829c-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="7829c-119">"DAVE BOB CAROL EVE"</span><span class="sxs-lookup"><span data-stu-id="7829c-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="7829c-120">La seconda voce Ignora testo non viene implementata perché la stringa non viene trovata come tale dopo l'applicazione del primo testo Ignora.</span><span class="sxs-lookup"><span data-stu-id="7829c-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="7829c-121">Utilizzo di espressioni regolari quando si definisce Ignora testo</span><span class="sxs-lookup"><span data-stu-id="7829c-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="7829c-122">Le espressioni regolari sono supportate per l'utilizzo quando si definisce Ignora testo.</span><span class="sxs-lookup"><span data-stu-id="7829c-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="7829c-123">Di seguito sono riportati alcuni esempi di sintassi e utilizzo di espressioni regolari:</span><span class="sxs-lookup"><span data-stu-id="7829c-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="7829c-124">Per rimuovere (ignorare) il testo da inizio fino alla fine di una riga:</span><span class="sxs-lookup"><span data-stu-id="7829c-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="7829c-125">dove "Begin" è l'occorrenza iniziale di questa stringa nella riga.</span><span class="sxs-lookup"><span data-stu-id="7829c-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="7829c-126">Ad esempio, per il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="7829c-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="7829c-127">**"Questa è la prima frase e la prima riga**</span><span class="sxs-lookup"><span data-stu-id="7829c-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="7829c-128">**Questa è la seconda frase e la seconda riga "**</span><span class="sxs-lookup"><span data-stu-id="7829c-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="7829c-129">prima espressione regolare (.\*) $ provocherà:</span><span class="sxs-lookup"><span data-stu-id="7829c-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="7829c-130">**"Questo è**</span><span class="sxs-lookup"><span data-stu-id="7829c-130">**"This is**</span></span>
    
    <span data-ttu-id="7829c-131">**Questa è la seconda frase e la seconda riga "**</span><span class="sxs-lookup"><span data-stu-id="7829c-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="7829c-132">Per rimuovere le dichiarazioni di non responsabilità e le istruzioni legali inserite automaticamente alla fine dei thread di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="7829c-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="7829c-133">dove "Begin" e "end" sono stringhe univoche all'inizio e alla fine di un paragrafo di testo avvolto.</span><span class="sxs-lookup"><span data-stu-id="7829c-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="7829c-134">Ad esempio, l'espressione regolare seguente eliminerà le dichiarazioni di non responsabilità e le istruzioni legali che si trovavano nel thread di posta elettronica tra le stringhe Begin e end:</span><span class="sxs-lookup"><span data-stu-id="7829c-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="7829c-135">**Questo messaggio contiene informazioni riservate (. | \s)\*se è richiesta la verifica, richiedere una versione cartacea**</span><span class="sxs-lookup"><span data-stu-id="7829c-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="7829c-136">Per rimuovere una dichiarazione di non responsabilità (compresi i caratteri speciali):</span><span class="sxs-lookup"><span data-stu-id="7829c-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="7829c-137">Ad esempio, per il testo seguente (con la dichiarazione di non responsabilità rappresentata qui da x):</span><span class="sxs-lookup"><span data-stu-id="7829c-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="7829c-138">**/\*\ Questo messaggio contiene informazioni riservate. xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="7829c-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="7829c-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="7829c-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="7829c-140">\**xxxx xxxx se è richiesta la verifica, richiedere una versione cartacea. /\*\**</span><span class="sxs-lookup"><span data-stu-id="7829c-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="7829c-141">l'espressione regolare per rimuovere la dichiarazione di non responsabilità di cui sopra dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="7829c-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="7829c-142">**\/\\*\\Questo messaggio contiene informazioni\.riservate (. | \s)\* se è richiesta la verifica, richiedere una versione\. cartacea\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="7829c-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="7829c-143">Regole di espressione regolare:</span><span class="sxs-lookup"><span data-stu-id="7829c-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="7829c-144">Tutti i caratteri che non fanno parte dell'alfabeto eccetto per gli spazi, "_" e "-" devono essere preceduti da "\".</span><span class="sxs-lookup"><span data-stu-id="7829c-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="7829c-145">Il campo eExpression regolare può essere di lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="7829c-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="7829c-146">Per una spiegazione e una sintassi dettagliata delle espressioni regolari, vedere: [Regular Expression Language-Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7829c-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="7829c-147">Definire la regola ignora testo</span><span class="sxs-lookup"><span data-stu-id="7829c-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="7829c-148">Nella sezione **Ignora testo** della scheda **Gestisci \> opzioni di \> analisi Analyze** fare clic sull' **+** icona per aggiungere una regola.</span><span class="sxs-lookup"><span data-stu-id="7829c-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="7829c-149">Nella finestra di dialogo **Aggiungi testo Ignora** , nel campo **nome** , digitare un nome per la regola di testo Ignora.</span><span class="sxs-lookup"><span data-stu-id="7829c-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Aggiungi testo ignorato](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="7829c-151">Nella casella di **testo** Digitare il testo da ignorare.</span><span class="sxs-lookup"><span data-stu-id="7829c-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="7829c-152">Il campo di testo consente un numero illimitato di caratteri.</span><span class="sxs-lookup"><span data-stu-id="7829c-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7829c-153">Come mostrato nella finestra sopra, fare clic su **lampadina** per visualizzare le linee guida per la sintassi comune per la regola di testo Ignora.</span><span class="sxs-lookup"><span data-stu-id="7829c-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="7829c-154">Selezionare la casella di controllo **distinzione** tra maiuscole e minuscole, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7829c-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="7829c-155">Nell'elenco **applica a** selezionare i moduli avanzati di eDiscovery in cui applicare la definizione.</span><span class="sxs-lookup"><span data-stu-id="7829c-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="7829c-156">Se si desidera eseguire l'esecuzione di un test nel testo di esempio, digitare il testo di esempio nella casella di testo **input** e fare clic su **test**.</span><span class="sxs-lookup"><span data-stu-id="7829c-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="7829c-157">I risultati vengono visualizzati nella casella di testo **output** .</span><span class="sxs-lookup"><span data-stu-id="7829c-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="7829c-158">Fare clic su **OK** per salvare la regola di testo Ignora.</span><span class="sxs-lookup"><span data-stu-id="7829c-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="7829c-159">Viene visualizzata la regola di testo Ignora definita.</span><span class="sxs-lookup"><span data-stu-id="7829c-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![Impostare nome del testo ignorato](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="7829c-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7829c-161">See also</span></span>

[<span data-ttu-id="7829c-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7829c-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7829c-163">Informazioni sulla somiglianza del documento</span><span class="sxs-lookup"><span data-stu-id="7829c-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7829c-164">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="7829c-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7829c-165">Impostazione analisi impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="7829c-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7829c-166">Visualizzazione dei risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="7829c-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

