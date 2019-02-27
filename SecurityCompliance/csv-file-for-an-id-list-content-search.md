---
title: Preparare un file CSV per una ricerca di contenuto nell'elenco di ID in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Utilizzare il file results. csv o unindexed Items. csv da una ricerca di contenuto esistente per creare una ricerca nell'elenco di ID che restituisca messaggi di posta elettronica specifici. Le ricerche degli elenchi di ID vengono in genere utilizzate per restituire gli elementi della cassetta postale parzialmente indicizzati.
ms.openlocfilehash: 558a8512ed133995b2cc1d0d8b78fd7f08d11168
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296739"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="af1f5-104">Preparare un file CSV per una ricerca di contenuto nell'elenco di ID in Office 365</span><span class="sxs-lookup"><span data-stu-id="af1f5-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="af1f5-p102">È possibile cercare specifici messaggi di posta elettronica della cassetta postale e altri elementi della cassetta postale utilizzando un elenco di ID di Exchange. Per creare una ricerca nell'elenco di ID (denominato formalmente ricerca mirata), è necessario inviare un file CSV (comma separated value) che identifica gli elementi specifici della cassetta postale da cercare. Per questo file CSV è possibile utilizzare il file **results. csv** o il file unIndexed **Items. csv** incluso quando si esportano i risultati della ricerca di contenuto o si esporta un rapporto di ricerca contenuto e la ricerca di contenuto esistente. Successivamente, modificare uno di questi file per indicare gli elementi specifici da cercare e quindi creare un nuovo elenco di ID ricerca e inviare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="af1f5-109">Ecco una breve panoramica del processo per la creazione di una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="af1f5-110">Creare ed eseguire una ricerca di contenuto nuovo o guidato nel centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="af1f5-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="af1f5-p103">Esportare i risultati della ricerca del contenuto o esportare il rapporto di ricerca contenuto. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="af1f5-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="af1f5-113">Esportare i risultati della ricerca del contenuto dal centro &amp; sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="af1f5-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="af1f5-114">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="af1f5-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="af1f5-p104">Modificare il file **results. csv** o gli **elementi non indicizzati. csv** e identificare gli elementi specifici della cassetta postale che si desidera includere nella ricerca nell'elenco di ID. Vedere le [istruzioni](#prepare-the-csv-file-for-an-id-list-search) per la preparazione di un file CSV per la ricerca di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="af1f5-p105">Creare una nuova ricerca nell'elenco di ID (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato. La query di ricerca creata eseguirà la ricerca solo degli elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af1f5-p106">Le ricerche degli elenchi di ID sono supportate solo per gli elementi delle cassette postali. Non è possibile cercare i documenti di SharePoint e OneDrive in una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="af1f5-p107">**Perché creare una ricerca nell'elenco di ID?** Se non si è in grado di determinare se un elemento risponde a una richiesta di eDiscovery basata sui metadati nei \*\*\*\* file CSV. csv o **elementi** non indicizzati, è possibile utilizzare la ricerca di un elenco di ID per trovare, visualizzare in anteprima e quindi esportare tale elemento per determinare se è rispondere al caso in cui si sta indagando. Le ricerche degli elenchi di ID vengono in genere utilizzate per cercare e restituire un insieme specifico di elementi non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="af1f5-124">Preparare il file CSV per una ricerca nell'elenco di ID</span><span class="sxs-lookup"><span data-stu-id="af1f5-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="af1f5-p108">Dopo aver esportato i risultati della ricerca o il report per una ricerca di contenuto, è possibile eseguire la procedura seguente per preparare il file CSV per la ricerca di un elenco di ID. Questo file CSV identificherà tutti gli elementi nella ricerca dell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="af1f5-p109">Si noti che è possibile utilizzare un file CSV da una ricerca in cui sono inclusi i siti di SharePoint e gli account di OneDrive, ma è possibile selezionare *solo* gli elementi della cassetta postale per una ricerca nell'elenco di ID. Se si seleziona un documento in SharePoint o OneDrive, il file CSV avrà esito negativo quando si crea una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="af1f5-129">Aprire il file **results. csv** o unIndexed **Items. csv** in Excel.</span><span class="sxs-lookup"><span data-stu-id="af1f5-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="af1f5-p110">Inserire una nuova colonna e denominarla **selezionata**. Non importa dove si inserisce la colonna. Per praticità, è consigliabile inserirla a sinistra della prima colonna.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="af1f5-p111">Nella colonna **selezionata** digitare **Sì** nella cella corrispondente all'elemento che si desidera ricercare. Ripetere questo passaggio per ogni elemento che si desidera ricercare.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="af1f5-p112">Quando si apre il file CSV in Excel, il formato dei dati per la colonna **ID documento** viene modificato in **generale**. In questo modo viene visualizzato l'ID documento per un elemento nella notazione scientifica. Ad esempio, l'ID documento "481037338205" viene visualizzato come "4.81037 E + 11" è necessario eseguire i passaggi successivi per modificare il formato dei dati della colonna **ID documento** in **numero** per ripristinare il formato corretto per l'ID documento. Se non si esegue questa operazione, la ricerca dell'elenco di ID che utilizza il file CSV avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="af1f5-139">Fare clic con il pulsante destro del mouse sull'intera colonna **ID documento** e scegliere **Format Cells**.</span><span class="sxs-lookup"><span data-stu-id="af1f5-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="af1f5-140">Nella casella **categoria** fare clic su **numero**.</span><span class="sxs-lookup"><span data-stu-id="af1f5-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="af1f5-p113">Modificare il numero di posizioni decimali su **0**, quindi fare clic su **OK** per salvare le modifiche. Si noti che i valori nella colonna ID documento vengono modificati in numeri.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="af1f5-143">Di seguito è riportato un esempio di un file CSV che è pronto per essere inviato per la ricerca di contenuto di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![Esempio di un file CSV per una ricerca di contenuto mirata](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="af1f5-p114">Salvare il file CSV o utilizzare **Salva** con nome per salvare il file con un file diverso. In entrambi i casi, assicurarsi di salvare il file con il formato CSV.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="af1f5-147">Creare una ricerca nell'elenco di ID</span><span class="sxs-lookup"><span data-stu-id="af1f5-147">Create an ID list search</span></span>

<span data-ttu-id="af1f5-148">Il passaggio successivo consiste nel creare una nuova ricerca del contenuto dell'elenco di ID e nel inviare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="af1f5-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af1f5-p115">È consigliabile creare un elenco di ID che non superi i 2 giorni dopo l'esportazione dei risultati o del report da una ricerca di contenuto. Se i risultati della ricerca o il report in cui è stata esportata più di 2 giorni fa, è necessario riesportare i risultati della ricerca o il report per generare i file CSV aggiornati. È quindi possibile preparare uno dei file CSV aggiornati e utilizzarlo per creare una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="af1f5-152">Nel centro sicurezza &amp; e conformità, andare alla \> **Ricerca contenuto**ricerca \*\* &amp; analisi\*\* .</span><span class="sxs-lookup"><span data-stu-id="af1f5-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="af1f5-153">Nella pagina **ricerca** fare clic sulla freccia accanto a Aggiungi ![](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**icona, quindi fare clic su **Cerca in base all'elenco di ID**.</span><span class="sxs-lookup"><span data-stu-id="af1f5-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![Fare clic su Cerca in base all'elenco di ID dall'elenco a discesa nuovo ricerca](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="af1f5-155">Nel riquadro a comparsa **ricerca in base all'elenco di ID** , denominare la ricerca e, facoltativamente, descriverla, quindi fare clic su **Sfoglia** e selezionare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="af1f5-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="af1f5-p116">Office 365 tenta di convalidare il file CSV. Se la convalida non ha avuto esito positivo, verrà visualizzato un messaggio di errore che potrebbe facilitare la risoluzione dei problemi relativi agli errori di convalida. Il file CSV deve essere convalidato correttamente per creare una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="af1f5-159">Dopo aver convalidato il file CSV, fare clic su **Cerca** per creare la ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="af1f5-160">Di seguito è riportato un esempio dei risultati di ricerca stimati e della query generata per una ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![Query di ricerca per una ricerca di contenuto mirata nel riquadro dei dettagli](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="af1f5-162">Si noti che il numero di elementi stimati visualizzati nelle statistiche per la ricerca ID deve corrispondere al numero di elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="af1f5-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="af1f5-163">Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca dell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af1f5-p117">Se si sposta una cassetta postale dopo aver creato una ricerca nell'elenco di ID, la query per la ricerca non restituirà gli elementi specificati. Ciò è dovuto al fatto che la proprietà **DocumentID** per gli elementi della cassetta postale viene modificata quando una cassetta postale viene spostata. Nell'istanza rara quando una cassetta postale viene spostata dopo aver creato una ricerca nell'elenco di ID, è necessario creare una nuova ricerca contenuto (o aggiornare i risultati della ricerca per la ricerca di contenuto esistente) e quindi esportare i risultati della ricerca o il report per generare i file CSV aggiornati che possono essere utilizzati  per creare una nuova ricerca nell'elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="af1f5-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
