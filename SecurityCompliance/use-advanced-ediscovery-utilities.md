---
title: Usare le utilità di Office 365 Advanced eDiscovery
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Per conoscere le utilità di eDiscovery Office 365 avanzate, tra cui registro casi, cancellare i dati, gli errori del processo, modificare pertinenza e la trasparenza analisi.  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530283"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="da944-103">Usare le utilità di Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="da944-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="da944-p101">EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="da944-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="da944-106">Utilità che verranno visualizzati e disponibili in eDiscovery avanzate dipendono dal ruoli utente e di contesto.</span><span class="sxs-lookup"><span data-stu-id="da944-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="da944-107">Registro casi</span><span class="sxs-lookup"><span data-stu-id="da944-107">Case log</span></span>

<span data-ttu-id="da944-p102">Il registro del caso contiene un elenco dettagliato delle attività di elaborazione dell'applicazione, che può essere utilizzato per la tracciabilità, risoluzione dei problemi e per la risoluzione di errori e avvisi. Nel registro può essere generato e memorizzato localmente nel computer host o server o inviato direttamente a un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="da944-p102">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings. The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="da944-p103">Il file di registro può inoltre essere scaricato per il computer client. L'opzione di download del client può essere attivata o disattivata in base al ruolo utente e di configurazione.</span><span class="sxs-lookup"><span data-stu-id="da944-p103">The log file can also be downloaded to the client's computer. The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="da944-112">Nella barra dei menu, fare clic sull'icona **Cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="da944-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="da944-113">Nella **impostazioni e le utilità \> utilità** , selezionare **registro casi \> il programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="da944-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="da944-114">Selezionare il **livello di registrazione** nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="da944-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="da944-p104">**Standard**: include i dati dei registri di base. Questa opzione è in genere necessaria per il monitoraggio e deve essere utilizzata a meno che non consigliato in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="da944-p104">**Standard**: Includes the basic log data. This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="da944-117">**Minimo**: utilizzato per i casi di grandi dimensioni e restituisce solo i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="da944-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="da944-p105">Fare clic su **Registro Case eseguito**. Il registro generato e percorso viene visualizzato. Le informazioni sull'avanzamento delle attività per l'attività corrente e il cognome è visualizzati nel riquadro di stato attività.</span><span class="sxs-lookup"><span data-stu-id="da944-p105">Click **Run Case log**. The log is generated and path is displayed. The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="da944-121">Cancella dati</span><span class="sxs-lookup"><span data-stu-id="da944-121">Clear data</span></span>

<span data-ttu-id="da944-p106">Se è necessario eliminare o reinizializzare dati sui casi, l'istanza del database deve inizializzato. L'utilità Cancella dati Elimina specificate tutte le voci dal database maiuscole, file di testo, cartella sociale e risultati accumulati. La funzione può essere eseguita solo da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="da944-p106">If it is necessary to delete or reinitialize case data, the database instance must be initialized. The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results. The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da944-p107">Questa azione non è reversibile eliminerà tutti pertinenza tagging e analisi eseguita da un esperto. Salvare una copia di backup dei dati, se necessario. Utilizzare questa opzione con prestare particolare attenzione. Eliminazione dei file di tag e classificati può influire sui risultati della pertinenza.</span><span class="sxs-lookup"><span data-stu-id="da944-p107">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert. Save a backup of data, if necessary. Use this option with extreme care. Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="da944-129">Nella barra dei menu, fare clic sull'icona **Cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="da944-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="da944-130">Nella **impostazioni e le utilità \> utilità** , selezionare **cancellare i dati \> il programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="da944-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="da944-131">Selezionare un'opzione per le informazioni necessarie per inizializzare:</span><span class="sxs-lookup"><span data-stu-id="da944-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="da944-p108">**Pertinenza**: consente di eliminare tutte le operazioni eseguite in pertinenza, tra cui definizione dei carichi e associazione dei file e carichi. Elimina tutti gli esempi e tagging.</span><span class="sxs-lookup"><span data-stu-id="da944-p108">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads. It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="da944-134">**Quasi duplicati e thread di posta elettronica**: consente di eliminare tutte le informazioni di analisi dei quasi duplicati e thread di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="da944-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="da944-135">**Temi**: consente di eliminare i dati relativi ai temi.</span><span class="sxs-lookup"><span data-stu-id="da944-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="da944-136">**Esporta la cronologia**: consente di eliminare le informazioni della cronologia del batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="da944-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="da944-p109">Fare clic su **Cancella dati**. I dati maiuscole sia deselezionati. Le informazioni sull'avanzamento delle attività per l'attività corrente e il cognome è visualizzati nel riquadro di **stato dell'attività** .</span><span class="sxs-lookup"><span data-stu-id="da944-p109">Click **Clear data**. The case data is cleared. The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="da944-140">Modificare pertinenza</span><span class="sxs-lookup"><span data-stu-id="da944-140">Modify Relevance</span></span>

<span data-ttu-id="da944-141">In questa sezione viene descritto come ignorare o eseguire il rollback di un campione di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="da944-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="da944-142">Nella barra dei menu, fare clic sull'icona **Cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="da944-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="da944-143">Nella **impostazioni e le utilità \> utilità** selezionare **la pertinenza di modifica**.</span><span class="sxs-lookup"><span data-stu-id="da944-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="da944-144">Selezionare una delle opzioni:</span><span class="sxs-lookup"><span data-stu-id="da944-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="da944-p110">**Esempio corrente di elementi da ignorare - per l'utente corrente**: questo verrà contrassegnato, come **elementi da ignorare**tutti i file senza tag nell'esempio di maiuscole open dell'utente che esegue l'utilità. Elaborazione di pertinenza non verrà eseguito nel file contrassegnati come **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="da944-p110">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility. Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="da944-p111">**Sample corrente di elementi da ignorare - all aprire esempi**: come **elementi da ignorare**questo verrà contrassegnare tutti i file senza tag negli esempi di tutte le finestra per tutti gli utenti. Questa opzione non è consigliata se gli utenti sono attualmente tagging esempi.</span><span class="sxs-lookup"><span data-stu-id="da944-p111">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users. This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="da944-p112">**Eseguire il rollback di esempio ultimo**: l'ultimo completato pertinenza campione per verrà annullata, indipendentemente dal fatto che sia prima o dopo il processo di "Calcolo". Rollback di un campione di aggiornamento non è consentito.</span><span class="sxs-lookup"><span data-stu-id="da944-p112">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process. Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="da944-151">Fare clic su **Esegui** per eseguire.</span><span class="sxs-lookup"><span data-stu-id="da944-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="da944-152">Analisi di trasparenza</span><span class="sxs-lookup"><span data-stu-id="da944-152">Transparency analysis</span></span>

<span data-ttu-id="da944-p113">L'utilità di analisi trasparenza consente una visualizzazione dettagliata dei file e loro assegnato punteggio di pertinenza. Il report può essere utilizzato come una verifica dell'integrità o per confrontare la pertinenza di un file definito da un revisore alla pertinenza assegnato da eDiscovery avanzate.</span><span class="sxs-lookup"><span data-stu-id="da944-p113">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score. The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="da944-p114">Oltre a punteggio di pertinenza, eDiscovery avanzate calcola e assegna spessori parola chiave che considerare il contesto di parola chiave. La stessa parola in un file può essere assegnata diversi fattori, in base al contesto e il percorso. Ogni parola chiave è contrassegnato con una scala l'aumento di intensità del colore compreso giallo e arancione scuro e varying sfumature di grigio. La codifica dei colori viene utilizzata per indicare visivamente la parola parente contributo positivo o negativo per il punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="da944-p114">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context. The same word in a file can be assigned different weights, depending on context and location. Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray. Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="da944-159">In uno scenario di maiuscole più problema, un report di analisi trasparenza può essere generato per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="da944-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="da944-160">Nella barra dei menu, fare clic sull'icona **Cogwheel** .</span><span class="sxs-lookup"><span data-stu-id="da944-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="da944-161">Nella **impostazioni e le utilità \> utilità** , selezionare **analysis trasparenza \> il programma di installazione**.</span><span class="sxs-lookup"><span data-stu-id="da944-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="da944-162">In * * File ID * *, immettere l'ID di file del file per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="da944-162">In ** File ID **, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="da944-163">Nell'elenco **problema** , selezionare il problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="da944-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="da944-p115">Fare clic su **analisi trasparenza**. Al termine, viene visualizzato il report di analisi di trasparenza del file di cui viene illustrato come i colori delle parole chiave contrassegnate essere correlato al punteggio di pertinenza globale.</span><span class="sxs-lookup"><span data-stu-id="da944-p115">Click **Transparency analysis**. Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da944-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da944-166">See also</span></span>

[<span data-ttu-id="da944-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="da944-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="da944-168">Definizione delle impostazioni di maiuscole e minuscole e tenant</span><span class="sxs-lookup"><span data-stu-id="da944-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

