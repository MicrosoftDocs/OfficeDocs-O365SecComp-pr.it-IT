---
title: Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST file scaricato nel computer quando si esportano i risultati della ricerca eDiscovery.
ms.openlocfilehash: 1479db72117729d2e5cfa6feec1d9a0d9a60ffb5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037989"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery

Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per esportare i risultati della posta elettronica di una ricerca eDiscovery diversi strumenti di Microsoft eDiscovery, la dimensione predefinita di un file PST che può essere esportato è 10 GB. Se si desidera modificare la dimensione predefinita, è possibile modificare il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Uno dei motivi per eseguire questa operazione è un file PST può contenere il rimovibile, ad esempio un DVD, un CD-ROM o un'unità USB. 
  
> [!NOTE]
>  Lo strumento di esportazione eDiscovery di Office 365 viene utilizzato per esportare i risultati della ricerca quando si utilizza ricerca contenuto in Office 365 Security &amp; centro conformità, eDiscovery In locale in Exchange Online e il centro eDiscovery in SharePoint Online. 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Creare un'impostazione del Registro di sistema per modificare le dimensioni dei file PST durante l'esportazione dei risultati della ricerca di eDiscovery

Eseguire la procedura seguente nel computer in cui verranno utilizzati per esportare i risultati di una ricerca eDiscovery.
  
1. Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto. 
    
2. Salvare il testo seguente in un file di registro di sistema finestra con il suffisso nome del file con estensione reg; ad esempio, PstExportSize.reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Nell'esempio precedente, il `PstSizeLimitInBytes` è impostata su 1.073.741.824 byte o circa 1 GB. Ecco alcuni altri valori di esempio per il `PstSizeLimitInBytes` impostazione. 
    
    |**Dimensione in GB (circa)**|**Dimensioni in byte**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Modifica la `PstSizeLimitInBytes` valore per la dimensione massima desiderata di un file PST quando si esportano i risultati della ricerca e quindi salvare il file. 
    
4. In Esplora risorse fare clic o doppio clic sul file con estensione reg creata nei passaggi precedenti.
    
5. Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche. 
    
6. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.
    
7. È possibile ripetere i passaggi da 3 a 6 per modificare il valore per il `PstSizeLimitInBytes` impostazione del Registro di sistema. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Domande frequenti su come modificare la dimensione predefinita del file PST durante l'esportazione dei risultati della ricerca di eDiscovery

 **Il valore predefinito è un'altezza di 10 GB.**
  
La dimensione predefinita di 10 GB è basata su feedback dei clienti; 10 GB rappresenta un buon compromesso tra la quantità di contenuto in un singolo file PST e con una minima possibilità di danneggiamento dei file ottimale.
  
 **È consigliabile aumentare o diminuire la dimensione predefinita del file PST?**
  
I clienti tendono a diminuire la dimensione massima, in modo che i risultati della ricerca occupi rimovibile che può consegna fisica altre posizioni all'interno dell'organizzazione. Non è consigliabile aumentare le dimensioni predefinite perché file superiori a 10 GB potrebbe essere problemi di danneggiamento dei file PST.
  
 **Il computer è necessario eseguire questa operazione?**
  
È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale che si esegue lo strumento di esportazione eDiscovery di Office 365 in.
  
 **Dopo che è possibile modificare questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Ma, se lo strumento di esportazione eDiscovery di Office 365 è in esecuzione, è necessario chiudere e il riavvio viene dopo che si modifica questa impostazione.
  
 **Ottenere modifica una chiave del Registro di sistema esistente o vengono creata una nuova chiave.**
  
Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creato in questa procedura. L'impostazione viene quindi modificata ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg.
