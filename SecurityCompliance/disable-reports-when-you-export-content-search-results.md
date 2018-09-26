---
title: Disabilitare report quando si esportano i risultati di ricerca del contenuto in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Modificare il Registro di sistema nel computer locale per disabilitare il report quando si esportano i risultati di ricerca di contenuto da Office 365 Security &amp; Comliance Center. Disabilitare questi rapporti consente di ridurre il tempo di download e di risparmiare spazio su disco.
ms.openlocfilehash: 62782c472adca892e1dcf239a45fe80f0fa7251b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037979"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>Disabilitare report quando si esportano i risultati di ricerca del contenuto in Office 365 Security &amp; centro conformità

Quando si utilizza lo strumento di esportazione eDiscovery di Office 365 per esportare i risultati di una ricerca di contenuto per la protezione &amp; centro conformità, lo strumento verrà creato automaticamente ed Esporta due rapporti che contengono ulteriori informazioni sul contenuto esportato. Questi rapporti sono file Results.csv e il file manifest (vedere la sezione [domande frequenti sulla disattivazione del report di esportazione](#frequently-asked-questions-about-disabling-export-reports) in questo argomento per una descrizione dettagliata di questi rapporti). Poiché questi file possono essere molto grandi, è possibile ridurre il tempo di download e salvare lo spazio su disco per impedire che questi file da esportare. È possibile eseguire questo modificando il Registro di sistema nel computer utilizzato per esportare i risultati della ricerca. Se si desidera includere i risultati in un secondo momento, è possibile modificare l'impostazione del Registro di sistema. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Creare le impostazioni del Registro di sistema per disabilitare l'esportazione dei rapporti

Eseguire la procedura seguente nel computer in cui verranno utilizzati per esportare i risultati della ricerca di contenuto.
  
1. Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.
    
2. Eseguire uno o entrambi i passaggi seguenti, in base al quale report esportazione da disattivare.
    
    - **Results.csv**
    
      Salvare il testo seguente in un file di registro di sistema di Windows utilizzando il suffisso nome del file con estensione reg; ad esempio, DisableResultsCsv.reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **File manifest. Xml**
    
      Salvare il testo seguente in un file di registro di sistema di Windows utilizzando il suffisso nome del file con estensione reg; ad esempio, DisableManifestXml.reg.
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. In Esplora risorse fare clic o doppio clic sul file con estensione reg creata nei passaggi precedenti.
    
4. Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Modificare le impostazioni del Registro di sistema per abilitare di nuovo l'esportazione dei rapporti

Se è disabilitata per i rapporti Results.csv e manifest creando i file con estensione reg nella procedura precedente, è possibile modificare tali file per riattivare un report in modo che l'esportazione dei risultati della ricerca. Nel computer in cui verranno utilizzati per esportare i risultati della ricerca di contenuto, eseguire la procedura seguente.
  
1. Chiudere lo strumento di esportazione eDiscovery di Office 365 se è aperto.
    
2. Modificare uno o entrambi i file con estensione reg modifica creata nella procedura precedente.
    
    - **Results.csv**
    
        Aprire il file DisableResultsCsv.reg nel blocco note, modificare il valore `False` a `True`e quindi salvare il file. Ad esempio, dopo aver modificato il file, simile al seguente:
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **File manifest. Xml**
    
        Aprire il file DisableManifestXml.reg nel blocco note, modificare il valore `False` a `True`e quindi salvare il file. Ad esempio, dopo aver modificato il file, simile al seguente:
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. In Esplora risorse fare clic su o fare doppio clic su un file con estensione reg che è stato modificato nel passaggio precedente.
    
4. Nella finestra controllo di accesso utente, fare clic su **Sì** per consentire l'Editor del Registro di sistema di apportare le modifiche. 
    
5. Quando viene richiesto di continuare, fare clic su **Sì**.
    
    L'Editor del Registro di sistema viene visualizzato un messaggio che informa che l'impostazione è stato aggiunto al Registro di sistema.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Domande frequenti sulla disabilitazione di esportazione dei rapporti
<a name="faqs"> </a>

 **Che cosa sono i rapporti Results.csv e file manifest. Xml?**
  
I file manifest. XML e Results.csv contengono ulteriori informazioni sul contenuto che è stata esportata.
  
- Documento di Excel **Results.csv** che contiene informazioni su ogni elemento è disponibile come download come risultato di ricerca. Per la posta elettronica, il registro risultato contiene informazioni su ogni messaggio, tra cui: 
    
  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).
    
  - La data in cui è stato inviato o ricevuto il messaggio.
    
  - La riga dell'oggetto del messaggio.
    
  - Il mittente e i destinatari del messaggio.
    
  - Indica se il messaggio è un messaggio duplicato se è abilitata la deduplicazione per l'esportazione dei risultati della ricerca. I messaggi duplicati dispone di un valore nella colonna **ID articolo padre** che identifica il messaggio come duplicato. Il valore nella colonna **ID articolo padre** è uguale al valore nella colonna **DocumentId elemento** del messaggio è stato esportato. 
    
    Per i documenti di SharePoint e OneDrive per i siti di Business, registro risultato contiene informazioni su tutti i documenti, tra cui:
    
  - L'URL per il documento.
    
  - L’URL per la raccolta di siti in cui si trova il documento.
    
  - La data dell'ultima modifica al documento.
    
  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).
    
- **Manifest** un file manifesto (in formato XML) che contiene informazioni su ogni elemento incluso nei risultati della ricerca. Le informazioni contenute in questo report corrisponde al rapporto Results.csv, ma è nel formato specificato dal modello di riferimento Electronic Discovery (EDRM). Per ulteriori informazioni su EDRM, vedere [https://www.edrm.net](https://www.edrm.net).
    
 **Se opportuno disabilitare esportazione questi rapporti?**
  
Dipende dalle esigenze specifiche. Molte organizzazioni non sono necessarie ulteriori informazioni sui risultati di ricerca e non è necessario questi rapporti.
  
 **Il computer è necessario eseguire questa operazione?**
  
 È necessario modificare l'impostazione del Registro di sistema in qualsiasi computer locale che si esegue lo strumento di esportazione eDiscovery di Office 365 in. 
  
 **Dopo che è possibile modificare questa impostazione, è necessario riavviare il computer?**
  
No, non è necessario riavviare il computer. Tuttavia, se lo strumento di esportazione eDiscovery di Office 365 è in esecuzione, è necessario chiuderlo e quindi riavviarlo dopo aver modificato l'impostazione del Registro di sistema.
  
 **Ottenere modifica una chiave del Registro di sistema esistente o vengono creata una nuova chiave.**
  
Una nuova chiave del Registro di sistema viene creata la prima volta che viene eseguito il file con estensione reg creata nella procedura in questo argomento. L'impostazione viene quindi modificata ogni volta che si modifica ed eseguita di nuovo il file di modifica con estensione reg.
