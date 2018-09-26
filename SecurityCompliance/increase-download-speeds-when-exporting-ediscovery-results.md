---
title: Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Informazioni su come configurare il Registro di sistema per aumentare la velocità effettiva di scaricare i risultati della ricerca e cercare i dati da Office 365 Security &amp; eDiscovery centro conformità e avanzate di Office 365.
ms.openlocfilehash: a05c2b786d1d1de7ff5014d12c708484345f908b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038119"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365

Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per scaricare i risultati di una ricerca di contenuto in Office 365 Security &amp; dati centro conformità o download di Office 365 avanzate eDiscovery, lo strumento consente di avviare un certo numero di esportazione simultanee operazioni di scaricare i dati nel computer locale. Per impostazione predefinita, il numero di operazioni simultanee è impostato a 8 volte il numero di core nel computer in uso per scaricare i dati. Ad esempio, se si dispone di un computer dual-core (vale a dire due CPU su uno chip), il numero predefinito di operazioni di esportazione simultanee è 16. Per aumentare la velocità effettiva di trasferimento dati e velocizzare il processo di download, è possibile aumentare il numero di operazioni simultanee configurando un'impostazione del Registro di sistema di Windows nel computer utilizzato per scaricare i risultati della ricerca. Per velocizzare il processo di download, è consigliabile iniziare con un'impostazione di 24 operazioni simultanee.
  
Se si scarica i risultati della ricerca in una rete di larghezza di banda ridotta, l'aumento di questa impostazione può avere un impatto negativo. In alternativa, è possibile aumentare l'impostazione per più di 24 operazioni simultanee in una rete ampia larghezza di banda (il numero massimo di operazioni simultanee è 512). Dopo aver configurato questa impostazione del Registro di sistema, potrebbe essere necessario modificarla per trovare il numero di operazioni simultanee per l'ambiente ottimale.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Creare un registro di sistema è necessario per modificare il numero di operazioni simultanee per l'esportazione dei dati

Eseguire la procedura seguente nel computer in cui verrà utilizzata per scaricare i risultati di ricerca di sicurezza &amp; centro conformità o dati provenienti da eDiscovery avanzate.
  
1. Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto. 
    
2. Salvare il testo seguente in un file di registro di sistema finestra con il suffisso nome del file con estensione reg; ad esempio, ConcurrentOperations.reg. 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Precedente come descritto, è consigliabile iniziare con 24 operazioni concorrenti e quindi modificare questa impostazione a seconda dei casi.
    
3. In Esplora risorse fare clic o doppio clic sul file con estensione reg creato nel passaggio precedente.
    
4. Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.
    
6. È possibile ripetere i passaggi 2-5 per modificare il valore per il `DownloadConcurrency` impostazione del Registro di sistema. 
    
    > [!IMPORTANT]
    > Dopo aver creato o modificare il `DownloadConcurrency` Registro di sistema impostazione, è necessario creare un nuovo processo di esportazione o riavviare un processo di esportazione esistente per i risultati di ricerca o dati che si desidera scaricare. Per ulteriori informazioni, vedere [ulteriori informazioni](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) . 
  
## <a name="more-information"></a>Ulteriori informazioni

- Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creato in questa procedura. L'oggetto `DownloadConcurrency` impostazione del Registro di sistema viene modificato ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg. 
    
- Lo strumento di esportazione eDiscovery di Office 365 utilizza l' [utilità AzCopy Azure](https://go.microsoft.com/fwlink/?linkid=849949) per scaricare i dati di ricerca di sicurezza &amp; centro conformità o da eDiscovery avanzate. Configurazione di `DownloadConcurrency` impostazione del Registro di sistema è simile all'utilizzo del parametro **/NC** quando si esegue l'utilità AzCopy. Pertanto l'impostazione del Registro di sistema di `"DownloadConcurrency=24"` avranno lo stesso effetto utilizzando il valore del parametro `/NC:24` con l'utilità AzCopy. 
    
- Se si arresta un download di esportazione che è attualmente in esecuzione e quindi riavviare (provando a scaricare nuovamente i risultati della ricerca), lo strumento di esportazione eDiscovery di Office 365 tenterà di riprendere il download stesso. Pertanto, se si avvia un download, interrotto e quindi passare la `DownloadConcurrency` Registro di sistema impostazione, i download probabilmente non riuscirà se si riavvia (facendo clic su **Download esportare i risultati**). Ciò avviene perché lo strumento di esportazione verrà eseguito un tentativo di riprendere il download precedente utilizzando le impostazioni che non sono valide perché l'impostazione del Registro di sistema è stata modificata.
    
    Pertanto, dopo aver modificato il `DownloadConcurrency` Registro di sistema impostazione, è necessario riavviare il processo di esportazione (facendo clic su **Riavvia export**) nella protezione &amp; centro conformità. È quindi possibile scaricare l'esportazione dei risultati. Per ulteriori informazioni sull'esportazione di dati e i risultati della ricerca, vedere:
    
  - [Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità](export-search-results.md)
    
  - [Esportare i risultati in Office 365 Advanced eDiscovery](export-results-in-advanced-ediscovery.md)
    
