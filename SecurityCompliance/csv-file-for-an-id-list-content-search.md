---
title: Preparare un file CSV per un elenco degli ID di ricerca del contenuto in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Utilizzare il file Results.csv o Items.csv indicizzati da una ricerca di contenuto esistente per creare una ricerca di ID elenco che restituisce i messaggi di posta elettronica specifico. ID elenco ricerche vengono in genere utilizzate per restituire elementi delle cassette postali parzialmente indicizzati.
ms.openlocfilehash: 9a7583c8f83626afb8dc0452bf72d834c8a28275
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038279"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="d2b6b-104">Preparare un file CSV per un elenco degli ID di ricerca del contenuto in Office 365</span><span class="sxs-lookup"><span data-stu-id="d2b6b-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="d2b6b-p102">È possibile cercare i messaggi di posta elettronica della cassetta postale specifica e altri elementi delle cassette postali utilizzando un elenco di ID di Exchange. Per creare una ricerca di elenco di ID (denominata formalmente una ricerca di destinazione), è inviare un file virgole (CSV) virgola che identifica gli elementi della cassetta postale specifica da cercare. Il file CSV si utilizza il file **Results.csv** o il file **Non indicizzate Items.csv** che vengono incluse quando si esportano i risultati di ricerca del contenuto o esportare un report di ricerca del contenuto da e ricerca del contenuto esistente. Quindi si modifica uno di questi file per indicare gli elementi specifici per la ricerca e quindi creare una nuovo ID elenco di ricerca e inviare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="d2b6b-109">Ecco una rapida panoramica del processo per la creazione di una ricerca di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="d2b6b-110">Creare ed eseguire una ricerca di contenuto nuovo o guidate in sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="d2b6b-p103">Esportare i risultati di ricerca del contenuto o esportare il report di ricerca del contenuto. Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="d2b6b-113">Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="d2b6b-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="d2b6b-114">Esportare il rapporto della Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="d2b6b-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="d2b6b-p104">Modificare il file **Results.csv** o **Items.csv non indicizzate** e identificare gli elementi della cassetta postale specifica che si desidera includere nella ricerca elenco ID. Vedere le [istruzioni](#prepare-the-csv-file-for-an-id-list-search) per la preparazione di un file CSV per la ricerca di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="d2b6b-p105">Creare un nuovo elenco di ID di ricerca (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato. Query di ricerca creato esegue la ricerca solo per gli elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d2b6b-p106">ID elenco ricerche sono supportate solo per gli elementi della cassetta postale. È possibile eseguire la ricerca di SharePoint e un elenco di documenti di OneDrive in un ID di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="d2b6b-p107">**Informazioni sulla creazione di una ricerca di elenco di ID?** Se si riesce a determinare che se un elemento risponde a una richiesta di eDiscovery in base ai metadati nei file **Results.csv** o **Items.csv non indicizzate** , è possibile utilizzare una ricerca di elenco di ID per trovare, visualizzare in anteprima e quindi Esporta che l'elemento per determinare se dispone risponde al caso sta esaminando. ID elenco ricerche vengono in genere utilizzate per cercare e restituire un insieme specifico di elementi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="d2b6b-124">Preparare il file CSV per la ricerca di un elenco di ID</span><span class="sxs-lookup"><span data-stu-id="d2b6b-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="d2b6b-p108">Dopo aver esportato i risultati della ricerca o un report per una ricerca di contenuto, è possibile eseguire la procedura seguente per preparare il file CSV per la ricerca di un elenco di ID. Tutti gli elementi nella ricerca elenco ID identifica il file CSV.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="d2b6b-p109">Si noti che è possibile utilizzare un file CSV da una ricerca inclusi account OneDrive e siti di SharePoint, ma è possibile selezionare *solo* gli elementi della cassetta postale per la ricerca di un elenco di ID. Se si seleziona un documento in SharePoint o OneDrive, il file CSV avrà esito negativo di convalida quando si crea una ricerca di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="d2b6b-129">Aprire il file **Results.csv** o **Items.csv non indicizzate** in Excel.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="d2b6b-p110">Inserire una nuova colonna e il nome **selezionato**. Non è importante dove si inserisce nella colonna. Per comodità, prendere in considerazione inserimento a sinistra della prima colonna.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="d2b6b-p111">Nella colonna **selezionato** digitare **Sì** nella cella che corrisponde all'elemento che si desidera cercare. Ripetere questo passaggio per ogni elemento che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d2b6b-p112">Quando si apre il file CSV in Excel, il formato di dati per la colonna **ID documento** viene modificato in **Generale**. Di conseguenza, visualizzando l'ID documento per un elemento scientifiche utilizzando una notazione in. Ad esempio il documento che ID di "481037338205" viene visualizzato come "4.81037E + 11" è necessario eseguire la procedura seguente per modificare il formato di dati della colonna **ID documento** al **numero di** ripristinare il formato corretto per l'ID del documento. Se non si esegue questa operazione, la ricerca di elenco di ID che utilizza il file CSV avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="d2b6b-139">L'intera colonna **ID documento** di mouse e scegliere **Formato celle**.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="d2b6b-140">Nel riquadro **categoria** , fare clic **sul numero**.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="d2b6b-p113">Modificare il numero di posizioni decimali su **0**e quindi fare clic su **OK** per salvare le modifiche. Si noti che i valori nella colonna ID documento convertiti in numeri.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="d2b6b-143">Di seguito è riportato un esempio di un file CSV è pronto per essere inviato per una ricerca di contenuto di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![Esempio di un file CSV per una ricerca di contenuto assegnato](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="d2b6b-p114">Salvare il file CSV oppure utilizzare **Salva con nome** per il salvataggio del file con nome diverso. In entrambi i casi, assicurarsi di salvare il file con formato CSV.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="d2b6b-147">Creazione di una ricerca di ID elenco</span><span class="sxs-lookup"><span data-stu-id="d2b6b-147">Create an ID list search</span></span>

<span data-ttu-id="d2b6b-148">Il passaggio successivo consiste nel creare un nuovo elenco di ID ricerca contenuto e inviare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d2b6b-p115">È consigliabile creare una ricerca di elenco di ID non più di 2 giorni dopo aver esportato i risultati da una ricerca di contenuto. Se la ricerca dei risultati o un report in cui esportare più di 2 giorni fa, è necessario esportare nuovamente i risultati della ricerca o il report per generare il file CSV aggiornati. È possibile quindi preparare un file CSV aggiornati e utilizzarlo per creare una ricerca di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="d2b6b-152">In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca del contenuto**.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="d2b6b-153">Nella pagina di **ricerca** , fare clic sulla freccia accanto a ![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**e quindi fare clic su **ricerca dall'elenco degli ID**.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![Fare clic su ricerca dall'elenco degli ID di nuovo nell'elenco a discesa ricerca](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="d2b6b-155">Nel riquadro a comparsa **dall'elenco degli ID di ricerca** , denominare la ricerca (e facoltativamente descrivono) e quindi fare clic su **Sfoglia** e selezionare il file CSV preparato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="d2b6b-p116">Office 365 tenta di convalidare il file CSV. Se la convalida ha esito negativo, verrà visualizzato un messaggio di errore che possono essere utili per risolvere gli errori di convalida. Il file CSV deve essere convalidato per creare una ricerca di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="d2b6b-159">Dopo il file CSV file è stato convalidato, quindi scegliere **Cerca** per creare la ricerca di elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="d2b6b-160">Di seguito è riportato un esempio dei risultati di ricerca stimati e la query che viene generata per la ricerca di un elenco di ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![Query di ricerca per una ricerca di contenuto personalizzata nel riquadro dei dettagli](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="d2b6b-162">Si noti che il numero delle voci stimate visualizzate le statistiche per la ricerca di ID deve corrispondere al numero di elementi selezionati nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="d2b6b-163">Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca elenco ID.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d2b6b-p117">Se si sposta una cassetta postale dopo la creazione di una ricerca di elenco di ID, la query per la ricerca non restituisca gli elementi specificati. Ciò avviene perché la proprietà **DocumentId** per gli elementi della cassetta postale vengono modificate quando una cassetta postale viene spostata. In rara istanza quando una cassetta postale viene spostata dopo aver creato una ricerca di elenco di ID, è necessario creare una nuova ricerca contenuta (o aggiornare i risultati della ricerca per la ricerca di contenuto esistente) e quindi Esporta la ricerca dei risultati o il report per la generazione di file CSV aggiornati che possono essere utilizzati  Per creare una nuovo ID elenco di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2b6b-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 
