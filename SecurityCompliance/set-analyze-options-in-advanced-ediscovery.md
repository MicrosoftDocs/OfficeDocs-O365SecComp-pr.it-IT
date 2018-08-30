---
title: Visualizzare le opzioni di Analizza in Office 365 Advanced eDiscovery
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Rivedere i passaggi per impostare le opzioni per il processo di analisi di eDiscovery Office 365 avanzate, tra cui quasi duplicati, thread di posta elettronica e temi.  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530791"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="e3c73-103">Visualizzare le opzioni di Analizza in Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e3c73-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="e3c73-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="e3c73-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e3c73-106">Nella scheda Avanzate eDiscovery, impostare le opzioni di analisi prima dell'esecuzione di analisi.</span><span class="sxs-lookup"><span data-stu-id="e3c73-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="e3c73-107">Impostare le opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="e3c73-107">Set Analyze options</span></span>

<span data-ttu-id="e3c73-p102">Apri **preparare \> analizzare** \> **il programma di installazione**. Verrà visualizzata la finestra seguente.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p102">Open **Prepare \> Analyze** \> **Setup**. The following window is displayed.</span></span>
  
![Impostare opzioni di analisi](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="e3c73-p103">**Quasi duplicati e thread di posta elettronica** Selezionare questa casella se si desidera eseguire l'analisi. È selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p103">**Near-duplicates and email threads** Check this box if you want to run the analysis. It is selected by default.</span></span> 
  
 <span data-ttu-id="e3c73-113">**Similarità documento** Immettere il valore di soglia Near duplicati o accettare il valore predefinito è 65%.</span><span class="sxs-lookup"><span data-stu-id="e3c73-113">**Document similarity**Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="e3c73-p104">**Temi** Selezionare questa casella per elaborare tutti i file e assegnare loro temi. Per impostazione predefinita, questa casella di controllo non è selezionata. Se si desidera eseguire temi di elaborazione, immettere le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p104">**Themes**Check this box to process all files and assign themes to them. By default, this check box is not selected. Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="e3c73-p105">**Numero massimo di temi** Immettere o selezionare un valore per il numero di temi per creare. Il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p105">**Max number of themes**Enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e3c73-p106">L'aumento del numero di temi influisce sulle prestazioni, nonché la possibilità di un tema per generalizzare. Maggiore è il numero di temi, più granulare sono. Se, ad esempio, un insieme di 50 temi includa un tema, ad esempio "Pallacanestro, tramite il, elettrico, Lakers"; 300 temi possono includere i temi separati: "Tramite il", "E", "Lakers". Se si non consapevolezza del tema "Pallacanestro" e utilizzare questa caratteristica per ECA, visualizzando il tema "Pallacanestro" può essere utile. Tuttavia, se l'elaborazione hanno un numero eccessivo di temi, che non venga visualizzato la parola "Pallacanestro" e non possono essere noti che tramite il ed elettrico è buone temi pallacanestro per esaminare, anziché gli elementi da inserire nel viene avviato e utilizzato per fini.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p106">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="e3c73-p107">**Temi suggeriti** È inoltre possibile indicare parole tema per controllare l'elaborazione di temi. EDiscovery avanzate verrà occuparsi di queste parole suggerite e tenta di creare uno o più temi rilevanti, in base alle impostazioni "Max numero di temi".</span><span class="sxs-lookup"><span data-stu-id="e3c73-p107">**Suggested themes**You can suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="e3c73-p108">Ad esempio, se la parola consigliata è "computer" e specificato "2" come "numero massimo di temi", eDiscovery avanzate tenterà di generare due temi correlate alla parola "computer". Due temi potrebbero essere "computer" hardware e "software", ad esempio.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p108">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="e3c73-129">Per visualizzare, aggiungere o modificare i temi consigliati, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e3c73-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="e3c73-p109">Nel Pannello di **temi suggeriti** , fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icona per aggiungere un tema. Nel Pannello di **tema suggerita Add** , aggiungere le parole, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p109">In the **Suggested themes** panel, click the **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme. In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="e3c73-132">Nella casella **numero di temi**di selezionare un valore per determinare il numero di temi avanzate eDiscovery cercherà di generare per queste parole (valore predefinito è 1 tema).</span><span class="sxs-lookup"><span data-stu-id="e3c73-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="e3c73-133">Fare clic su **Salva** e quindi chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e3c73-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e3c73-p110">Il numero totale di temi include temi suggerito. I temi suggerito totale non può superare i temi totali. Se sono presenti molti temi suggerito rispetto al totali temi, solo alcuni temi "quesiti nuovi" vengono rilevati dal sistema in quanto la maggior parte dei temi dovrà essere dedicata ai temi suggerito.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p110">The total number of themes includes Suggested Themes. The total Suggested Themes cannot exceed the total themes. If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="e3c73-137">**Modalità** Dall'elenco a discesa selezionare un'opzione di **temi** :</span><span class="sxs-lookup"><span data-stu-id="e3c73-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="e3c73-138">**Creare e applicare modelli**: calcola temi dai modelli da un segmento dei file e quindi distribuisce i file tra loro.</span><span class="sxs-lookup"><span data-stu-id="e3c73-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="e3c73-p111">**Crea modello**: calcola un modello di temi di un segmento dei file. Il processo di applica della divisione di file è terminato separatamente in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p111">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="e3c73-p112">**Applica modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non ancora applicato. Ciò consente di dividere il file in base ai temi.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p112">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="e3c73-143">È inoltre possibile [set Ignora testo](set-ignore-text-in-advanced-ediscovery.md) e [impostare analizza le impostazioni avanzata](set-analyze-advanced-settings-in-advanced-ediscovery.md) di analisi.</span><span class="sxs-lookup"><span data-stu-id="e3c73-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="e3c73-p113">Dopo aver impostato queste opzioni, fare clic su **analisi** per l'esecuzione. [Visualizzazione analizzare i risultati](view-analyze-results-in-advanced-ediscovery.md) vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e3c73-p113">After you've set these options, click **Analyze** to run. [View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e3c73-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3c73-146">See also</span></span>

[<span data-ttu-id="e3c73-147">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e3c73-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c73-148">Informazioni sui similarità documento</span><span class="sxs-lookup"><span data-stu-id="e3c73-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c73-149">Impostare Ignora testo</span><span class="sxs-lookup"><span data-stu-id="e3c73-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c73-150">Impostazioni avanzate per l'analisi</span><span class="sxs-lookup"><span data-stu-id="e3c73-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e3c73-151">Visualizzare i risultati di analisi</span><span class="sxs-lookup"><span data-stu-id="e3c73-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

