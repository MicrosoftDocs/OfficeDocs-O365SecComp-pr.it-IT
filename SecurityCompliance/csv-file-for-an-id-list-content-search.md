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
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Utilizzare il file Results.csv o Items.csv indicizzati da una ricerca di contenuto esistente per creare una ricerca di ID elenco che restituisce i messaggi di posta elettronica specifico. ID elenco ricerche vengono in genere utilizzate per restituire elementi delle cassette postali parzialmente indicizzati.
ms.openlocfilehash: 28e4a66e5c9be1817881004b1e4b3a3e6d4bfdb9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531195"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a>Preparare un file CSV per un elenco degli ID di ricerca del contenuto in Office 365

È possibile cercare i messaggi di posta elettronica della cassetta postale specifica e altri elementi delle cassette postali utilizzando un elenco di ID di Exchange. Per creare una ricerca di elenco di ID (denominata formalmente una ricerca di destinazione), è inviare un file virgole (CSV) virgola che identifica gli elementi della cassetta postale specifica da cercare. Il file CSV si utilizza il file **Results.csv** o il file **Non indicizzate Items.csv** che vengono incluse quando si esportano i risultati di ricerca del contenuto o esportare un report di ricerca del contenuto da e ricerca del contenuto esistente. Quindi si modifica uno di questi file per indicare gli elementi specifici per la ricerca e quindi creare una nuovo ID elenco di ricerca e inviare il file CSV. 
  
Ecco una rapida panoramica del processo per la creazione di una ricerca di elenco di ID.
  
1. Creare ed eseguire una ricerca di contenuto nuovo o guidate in sicurezza &amp; centro conformità.
    
2. Esportare i risultati di ricerca del contenuto o esportare il report di ricerca del contenuto. Per ulteriori informazioni, vedere:
    
    - [Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità](export-search-results.md)
    
    - [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)
    
3. Modificare il file **Results.csv** o **Items.csv non indicizzate** e identificare gli elementi della cassetta postale specifica che si desidera includere nella ricerca elenco ID. Vedere le [istruzioni](#prepare-the-csv-file-for-an-id-list-search) per la preparazione di un file CSV per la ricerca di un elenco di ID. 
    
4. Creare un nuovo elenco di ID di ricerca (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato. Query di ricerca creato esegue la ricerca solo per gli elementi selezionati nel file CSV.
    
> [!NOTE]
> ID elenco ricerche sono supportate solo per gli elementi della cassetta postale. È possibile eseguire la ricerca di SharePoint e un elenco di documenti di OneDrive in un ID di ricerca. 
  
 **Informazioni sulla creazione di una ricerca di elenco di ID?** Se si riesce a determinare che se un elemento risponde a una richiesta di eDiscovery in base ai metadati nei file **Results.csv** o **Items.csv non indicizzate** , è possibile utilizzare una ricerca di elenco di ID per trovare, visualizzare in anteprima e quindi Esporta che l'elemento per determinare se dispone risponde al caso sta esaminando. ID elenco ricerche vengono in genere utilizzate per cercare e restituire un insieme specifico di elementi indicizzati. 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparare il file CSV per la ricerca di un elenco di ID

Dopo aver esportato i risultati della ricerca o un report per una ricerca di contenuto, è possibile eseguire la procedura seguente per preparare il file CSV per la ricerca di un elenco di ID. Tutti gli elementi nella ricerca elenco ID identifica il file CSV.
  
Si noti che è possibile utilizzare un file CSV da una ricerca inclusi account OneDrive e siti di SharePoint, ma è possibile selezionare *solo* gli elementi della cassetta postale per la ricerca di un elenco di ID. Se si seleziona un documento in SharePoint o OneDrive, il file CSV avrà esito negativo di convalida quando si crea una ricerca di elenco di ID. 
  
1. Aprire il file **Results.csv** o **Items.csv non indicizzate** in Excel. 
    
2. Inserire una nuova colonna e il nome **selezionato**. Non è importante dove si inserisce nella colonna. Per comodità, prendere in considerazione inserimento a sinistra della prima colonna.
    
3. Nella colonna **selezionato** digitare **Sì** nella cella che corrisponde all'elemento che si desidera cercare. Ripetere questo passaggio per ogni elemento che si desidera cercare. 
    
    > [!IMPORTANT]
    > Quando si apre il file CSV in Excel, il formato di dati per la colonna **ID documento** viene modificato in **Generale**. Di conseguenza, visualizzando l'ID documento per un elemento scientifiche utilizzando una notazione in. Ad esempio il documento che ID di "481037338205" viene visualizzato come "4.81037E + 11" è necessario eseguire la procedura seguente per modificare il formato di dati della colonna **ID documento** al **numero di** ripristinare il formato corretto per l'ID del documento. Se non si esegue questa operazione, la ricerca di elenco di ID che utilizza il file CSV avrà esito negativo. 
  
4. L'intera colonna **ID documento** di mouse e scegliere **Formato celle**.
    
5. Nel riquadro **categoria** , fare clic **sul numero**.
    
6. Modificare il numero di posizioni decimali su **0**e quindi fare clic su **OK** per salvare le modifiche. Si noti che i valori nella colonna ID documento convertiti in numeri. 
    
    Di seguito è riportato un esempio di un file CSV è pronto per essere inviato per una ricerca di contenuto di elenco di ID.
    
    ![Esempio di un file CSV per una ricerca di contenuto assegnato](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. Salvare il file CSV oppure utilizzare **Salva con nome** per il salvataggio del file con nome diverso. In entrambi i casi, assicurarsi di salvare il file con formato CSV. 
  
## <a name="create-an-id-list-search"></a>Creazione di una ricerca di ID elenco

Il passaggio successivo consiste nel creare un nuovo elenco di ID ricerca contenuto e inviare il file CSV preparato nel passaggio precedente.
  
> [!IMPORTANT]
> È consigliabile creare una ricerca di elenco di ID non più di 2 giorni dopo aver esportato i risultati da una ricerca di contenuto. Se la ricerca dei risultati o un report in cui esportare più di 2 giorni fa, è necessario esportare nuovamente i risultati della ricerca o il report per generare il file CSV aggiornati. È possibile quindi preparare un file CSV aggiornati e utilizzarlo per creare una ricerca di elenco di ID. 
  
1. In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca del contenuto**.
    
2. Nella pagina di **ricerca** , fare clic sulla freccia accanto a ![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**e quindi fare clic su **ricerca dall'elenco degli ID**.
    
    ![Fare clic su ricerca dall'elenco degli ID di nuovo nell'elenco a discesa ricerca](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. Nel riquadro a comparsa **dall'elenco degli ID di ricerca** , denominare la ricerca (e facoltativamente descrivono) e quindi fare clic su **Sfoglia** e selezionare il file CSV preparato nel passaggio precedente. 
    
    Office 365 tenta di convalidare il file CSV. Se la convalida ha esito negativo, verrà visualizzato un messaggio di errore che possono essere utili per risolvere gli errori di convalida. Il file CSV deve essere convalidato per creare una ricerca di elenco di ID.
    
4. Dopo il file CSV file è stato convalidato, quindi scegliere **Cerca** per creare la ricerca di elenco di ID. 
    
    Di seguito è riportato un esempio dei risultati di ricerca stimati e la query che viene generata per la ricerca di un elenco di ID.
    
    ![Query di ricerca per una ricerca di contenuto personalizzata nel riquadro dei dettagli](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    Si noti che il numero delle voci stimate visualizzate le statistiche per la ricerca di ID deve corrispondere al numero di elementi selezionati nel file CSV.
    
5. Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca elenco ID.
    
> [!NOTE]
> Se si sposta una cassetta postale dopo la creazione di una ricerca di elenco di ID, la query per la ricerca non restituisca gli elementi specificati. Ciò avviene perché la proprietà **DocumentId** per gli elementi della cassetta postale vengono modificate quando una cassetta postale viene spostata. In rara istanza quando una cassetta postale viene spostata dopo aver creato una ricerca di elenco di ID, è necessario creare una nuova ricerca contenuta (o aggiornare i risultati della ricerca per la ricerca di contenuto esistente) e quindi Esporta la ricerca dei risultati o il report per la generazione di file CSV aggiornati che possono essere utilizzati  Per creare una nuovo ID elenco di ricerca. 
