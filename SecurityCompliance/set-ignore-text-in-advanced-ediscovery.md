---
title: Impostare l’opzione Ignora messaggio per Analizza in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Informazioni su come definire la regola per ignorare il testo specificato quando si utilizzano i moduli di processo e analisi di Office 365 avanzate eDiscovery.  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530843"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="bd5fe-103">Impostare l’opzione Ignora messaggio per Analizza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bd5fe-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="bd5fe-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="bd5fe-p102">La caratteristica Ignora testo può essere applicata a tutto o uno dei seguenti moduli avanzati eDiscovery: analizzare (quasi duplicati thread di posta elettronica, temi) e la pertinenza. Testo ignorato non verrà visualizzato nel file visualizzati in pertinenza e analisi/calcoli eliminerà il testo ignorato.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="bd5fe-p103">Se la caratteristica di ignorare il testo è stata definita in precedenza per i moduli che sono già stato eseguito, l'impostazione Ignora testo ora essere protetto dalle modifiche apportate. La caratteristica di ignorare il testo per il modulo di pertinenza può comunque essere modificata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="bd5fe-110">Modalità di applicazione di filtri Ignora testo</span><span class="sxs-lookup"><span data-stu-id="bd5fe-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="bd5fe-p104">Più filtri Ignora testo vengono applicati nell'ordine che sono stati immessi. Per modificare l'ordine in cui vengono applicati, devono essere eliminati e rientrati nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="bd5fe-113">Se il contenuto del testo è ad esempio: "DAVE BOB ALICE CAROL Giudici", esempi di voci di Ignora testo e i risultati vengono riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="bd5fe-114">**Ignora le voci di testo**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="bd5fe-115">**Risultati**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-115">**Results**</span></span> <br/> |
|<span data-ttu-id="bd5fe-116">"ALICE", "BOB ADRIANA"</span><span class="sxs-lookup"><span data-stu-id="bd5fe-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="bd5fe-117">"DAVE GIUDICI"</span><span class="sxs-lookup"><span data-stu-id="bd5fe-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="bd5fe-118">"ALICE", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="bd5fe-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="bd5fe-119">"DAVE BOB CAROL GIUDICI"</span><span class="sxs-lookup"><span data-stu-id="bd5fe-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="bd5fe-120">La seconda voce Ignora testo non è implementata perché la stringa non viene trovata in quanto tale dopo il testo di ignorare la prima applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="bd5fe-121">Utilizzare le espressioni regolari durante la definizione Ignora testo</span><span class="sxs-lookup"><span data-stu-id="bd5fe-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="bd5fe-p105">Espressioni regolari sono supportate per l'utilizzo durante la definizione Ignora testo. Di seguito sono riportati esempi di utilizzo e la sintassi di espressione regolare:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="bd5fe-124">Per rimuovere (ignorare) testo iniziale fino alla fine di una riga:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="bd5fe-125">dove "Begin" è l'occorrenza iniziale di questa stringa nella riga.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="bd5fe-126">Ad esempio, per il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="bd5fe-127">**"This is prima frase e prima riga**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="bd5fe-128">**Si tratta seconda frase e seconda riga"**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="bd5fe-129">l'espressione regolare first(.\*) $ determinerà:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="bd5fe-130">**"Questa è**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-130">**"This is**</span></span>
    
    <span data-ttu-id="bd5fe-131">**Si tratta seconda frase e seconda riga"**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="bd5fe-132">Per rimuovere automaticamente inseriti alla fine di thread di posta elettronica informazioni legali e dichiarazioni di non responsabilità:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="bd5fe-133">dove "Begin" e "End" sono stringhe univoche all'inizio e fine di un paragrafo di ritorno a capo automatico.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="bd5fe-134">Ad esempio, l'espressione regolare rimuoverà dichiarazioni di non responsabilità e informazioni legali che sono stati in thread di posta elettronica tra le stringhe Begin ed End:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="bd5fe-135">**Il messaggio contiene informazioni riservate (. | \s)\*verifica è necessaria richiedere una versione cartacei**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="bd5fe-136">Per rimuovere una dichiarazione di non responsabilità (inclusi i caratteri speciali):</span><span class="sxs-lookup"><span data-stu-id="bd5fe-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="bd5fe-137">Ad esempio, per il testo seguente (con la dichiarazione di non responsabilità rappresentata da x):</span><span class="sxs-lookup"><span data-stu-id="bd5fe-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="bd5fe-138">**/\*\ Il messaggio contiene informazioni riservate. xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="bd5fe-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="bd5fe-140">\**xxxx xxxx se è necessario, la verifica Richiedi una versione di stampato. /\*\**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="bd5fe-141">l'espressione regolare per rimuovere la dichiarazione di non responsabilità precedente deve essere:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="bd5fe-142">**\/\\*\\Il messaggio contiene informazioni riservate\.(. | \s)\* verifica è necessaria richiedere una versione cartacei\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="bd5fe-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="bd5fe-143">Regole di espressione regolare:</span><span class="sxs-lookup"><span data-stu-id="bd5fe-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="bd5fe-144">Tutti i caratteri che non fanno parte dell'alfabeto ad eccezione di spazi da parte, "_" e "-" deve essere preceduto da "\".</span><span class="sxs-lookup"><span data-stu-id="bd5fe-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="bd5fe-145">Il campo eExpression regolare può essere un numero illimitato di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="bd5fe-146">Per una spiegazione e informazioni dettagliate sulla sintassi delle espressioni regolari, vedere: [Linguaggio di espressioni regolari - Guida di riferimento rapido](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd5fe-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="bd5fe-147">Definire la regola ignora testo</span><span class="sxs-lookup"><span data-stu-id="bd5fe-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="bd5fe-148">Nella **Gestisci \> Analizza \> analizzare le opzioni** fare clic su scheda, nella sezione **Ignora testo** il **+** icona per aggiungere una regola.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="bd5fe-149">Nella finestra di dialogo **Aggiungi Ignora testo** nel campo **nome** digitare un nome per la regola ignora testo.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![Aggiungi testo ignorato](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="bd5fe-p106">Nella casella di **testo** , digitare il testo verrà ignorato. Il campo testo consente a un numero illimitato di caratteri.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="bd5fe-153">Come indicato nella precedente finestra, fare clic su **lampadina** per visualizzare le linee guida sintassi comuni per la regola ignora testo.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="bd5fe-154">Se lo si desidera, selezionare la casella di controllo **maiuscole/minuscole** .</span><span class="sxs-lookup"><span data-stu-id="bd5fe-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="bd5fe-155">Nell'elenco **Applica a** selezionare moduli avanzati eDiscovery in cui si desidera applicare la definizione.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="bd5fe-p107">Se si desidera che un'esecuzione di test in testo di esempio, digitare il testo di esempio nella casella di testo **Input** e fare clic su **Test**. I risultati vengono visualizzati nella casella di testo **Output** .</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="bd5fe-p108">Fare clic su **OK** per salvare la regola ignora testo. Viene visualizzata la regola ignora testo definita.</span><span class="sxs-lookup"><span data-stu-id="bd5fe-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![Impostare nome del testo ignorato](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="bd5fe-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd5fe-161">See also</span></span>

[<span data-ttu-id="bd5fe-162">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bd5fe-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="bd5fe-163">Informazioni sui similarità documento</span><span class="sxs-lookup"><span data-stu-id="bd5fe-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bd5fe-164">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="bd5fe-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bd5fe-165">Impostazioni avanzate di analisi di impostazione</span><span class="sxs-lookup"><span data-stu-id="bd5fe-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="bd5fe-166">Visualizzazione dei risultati di analisi</span><span class="sxs-lookup"><span data-stu-id="bd5fe-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

