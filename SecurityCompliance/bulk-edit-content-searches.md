---
title: Modifica in blocco le ricerche di contenuto in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: Utilizzare l'Editor di ricerca in blocco in Office 365 Security &amp; centro conformità modificare rapidamente i percorsi di query e del contenuto per una o più ricerche di contenuto.
ms.openlocfilehash: 45c9a3fc4bcc5e5d8ce9945d3094bfb4a39d6dcf
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530685"
---
# <a name="bulk-edit-content-searches-in-the-office-365-security-amp-compliance-center"></a>Modifica in blocco le ricerche di contenuto in Office 365 Security &amp; centro conformità

È possibile utilizzare l'Editor di ricerca in blocco in Office 365 Security &amp; centro conformità modificare più ricerche contenuto contemporaneamente. Con questo strumento consente di modificare rapidamente i percorsi di query e del contenuto per una o più ricerche. È possibile eseguire di nuovo le ricerche e ottenere i risultati di ricerca stimati nuova per le ricerche revisionati. L'editor consente inoltre di copiare e incollare le query e i percorsi di contenuti da un file di Microsoft Excel o un file di testo. Ciò significa che è possibile utilizzare lo strumento statistiche ricerca per visualizzare le statistiche di uno o più ricerche, esportare le statistiche in un file CSV in cui è possibile modificare le query e i percorsi di contenuti di Excel. È quindi utilizzare l'Editor di ricerca di blocco per aggiungere le query revisionata e i percorsi di contenuti per le ricerche. Dopo aver rivisto uno o più ricerche è possibile avviarli nuovamente e ottenere i risultati di ricerca stimati nuovo.
  
Per ulteriori informazioni sull'utilizzo dello strumento di statistiche ricerca, vedere [visualizzare le statistiche delle parole chiave per i risultati di ricerca del contenuto](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Utilizzare l'Editor di ricerca di blocco per modificare le query

1. In sicurezza &amp; centro conformità, passare a **ricerca &amp; indagini** \> **ricerca del contenuto**.
    
2. Nell'elenco delle ricerche, selezionare uno o più ricerche e quindi fare clic su **Editor di ricerca di massa** ![pulsante Editor ricerca blocco](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png).
    
    ![Selezionare uno o più ricerche e quindi fare clic su editor di ricerca in blocco](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    Le informazioni seguenti vengono visualizzate nella pagina **query** di blocco ricerca Editor. 
    
    ![Le query per le ricerche selezionati viene visualizzata la pagina di editor di ricerca in blocco](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    r. la colonna di **ricerca** viene visualizzato il nome di ricerca del contenuto. Come descritto in precedenza, è possibile modificare la query per le ricerche più. 
    
    b. colonna di **Query** viene visualizzata la query per la ricerca di contenuto elencati nella colonna di **ricerca** . Se la query è stata creata utilizzando la caratteristica di elenco di parole chiave, le parole chiave sono separate da testo * * `(c:s)` **. Indica che le parole chiave sono connessi tramite l'operatore **OR** . Inoltre, se la query include le condizioni, le parole chiave e le condizioni sono separate da testo * * `(c:c)` **. Indica che le parole chiave (o le fasi di parola chiave) siano connessi alle condizioni per l'operatore **AND** . Ad esempio, nella schermata precedente il per la ricerca ContosoSearch1, la query KQL che corrisponde al `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` sarà `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.
    
3. Per modificare una query, fare clic sulla cella della query che si desidera modificare ed effettuare una delle operazioni seguenti. Si noti che la cella è bordata da un riquadro blu quando si fa clic sopra.
    
   - Digitare la nuova query nella cella. Si noti che non è possibile modificare una parte della query. È necessario digitare l'intera query.
    
      Oppure
    
    - Incolla una nuova query nella cella. L'esempio presuppone che è stato copiato il testo della query da un file, ad esempio un file di testo o un file di Excel.
    
4. Dopo aver modificato una o più query nella pagina **delle query** , fare clic su **Salva**.
    
    La query modificata viene visualizzata nella colonna di **Query** per la ricerca selezionata. 
    
5. Fare clic su **Chiudi** per chiudere l'Editor di ricerca in blocco. 
    
6. Nella pagina di **ricerca del contenuto** selezionare la ricerca è stato modificato e fare clic su **Avvia** ricerca per riavviare la ricerca tramite query modificata. 
    
Di seguito sono riportati alcuni suggerimenti per la modifica delle query utilizzando la finestra di ricerca globali:
  
- Copiare la query esistente (utilizzando **Ctrl C** ) in un file di testo. Modificare la query nel file di testo e quindi copiare la query modificata e incollarlo (utilizzando **Ctrl V** ) alla cella nella pagina **delle query** . 
    
- È inoltre possibile copiare le query da altre applicazioni (ad esempio Microsoft Word o Microsoft Excel). Tuttavia, tenere presente che è possibile aggiungere inavvertitamente caratteri non supportati a una query utilizzando l'Editor di ricerca in blocco. Il modo migliore per evitare che caratteri non supportati consiste nel digitare solo la query in una cella nella pagina **delle query** . In alternativa, è possibile copiare una query da Word o Excel e incollarlo in un file in un editor di testo, ad esempio Microsoft Notepad. Quindi salvare il file di testo e selezionare nell'elenco a discesa **codifica** **ANSI** . Questo comando rimuoverà tutti i caratteri non supportati e formattazione. È quindi possibile copiare e incollare la query dal file di testo alla pagina di **query** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Utilizzare l'Editor di ricerca di blocco per modificare i percorsi di contenuti

1. Blocco ricerca Nell'Editor per uno o più ricerche selezionate, fare clic su **Abilita editor percorso blocco**e fare clic sul collegamento di **percorsi** che viene visualizzato la pagina. 
    
    Le informazioni seguenti vengono visualizzate nella pagina **posizioni** dell'Editor di ricerca del blocco. 
    
    ![Fare clic su Enable collettive percorso editor e quindi fare clic su percorsi per aggiungere o rimuovere i percorsi di contenuti](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    r. **le cassette postali per la ricerca**in questa sezione viene visualizzata una colonna per ogni ricerca di contenuto selezionato e riga per ogni cassetta postale inclusa nella ricerca. Un segno di spunta indica che la cassetta postale è inclusa nella ricerca. È possibile aggiungere ulteriori cassette postali per una ricerca digitando l'indirizzo di posta elettronica della cassetta postale in una riga vuota e quindi scegliendo la casella di controllo per la ricerca di contenuto che si desidera aggiungere a. Oppure è possibile rimuovere una cassetta postale da una ricerca deselezionando la casella di controllo.
    
    b. **siti di SharePoint per la ricerca**in questa sezione viene visualizzata una riga per ogni sito di SharePoint e OneDrive disponibili in ogni selezionata ricerca del contenuto. Un segno di spunta indica che il sito è inclusa nella ricerca. È possibile aggiungere altri siti per la ricerca digitando l'URL del sito in una riga vuota e quindi e facendo clic sulla casella di controllo per la ricerca di contenuto che si desidera aggiungere a. Oppure è possibile rimuovere un sito da una ricerca deselezionando la casella di controllo.
    
    c. **altre opzioni di ricerca**in questa sezione indica se gli elementi indicizzati e le cartelle pubbliche sono incluse nella ricerca. Per includere tali, verificare che sia selezionata la casella di controllo. Per effettuare questa operazione, deselezionare la casella di controllo.
    
2. Dopo aver modificato uno o più delle sezioni nella pagina **percorsi** , fare clic su **Salva**.
    
    Nella sezione appropriata per le ricerche selezionati vengono visualizzati i percorsi di contenuti revisionati.
    
3. Fare clic su **Chiudi** per chiudere l'Editor di ricerca in blocco. 
    
4. Nella pagina **di ricerca del contenuto** selezionare la ricerca è stato modificato e fare clic su **Avvia** ricerca per riavviare la ricerca utilizzando i percorsi di contenuti revisionati. 
    
Di seguito sono riportati alcuni suggerimenti per la modifica i percorsi di contenuti nell'editor di ricerca globali:
  
- È possibile modificare le ricerche di contenuto per eseguire la ricerca tutte le cassette postali o siti nell'organizzazione digitando **tutte** in una riga vuota nella sezione **cassette postali per la ricerca** o **siti di SharePoint per la ricerca** e quindi facendo clic sulla casella di controllo. 
    
- È possibile aggiungere più percorsi di contenuti per una o più ricerche copiando più righe da un file di testo o un file di Excel e quindi incollarle in una sezione nella pagina **posizioni** . Dopo aver aggiunto nuovi percorsi, assicurarsi di selezionare la casella di controllo per ogni ricerca che si desidera aggiungere il percorso in cui. 
    
    > [!TIP]
    > Per generare un elenco di indirizzi di posta elettronica per tutti gli utenti nell'organizzazione, eseguire il comando PowerShell nel passaggio 2 di [Utilizzare la ricerca del contenuto per eseguire una ricerca cassetta postale e OneDrive per sito Business per un elenco di utenti](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2). Utilizzare lo script in [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a) per generare un elenco di tutti i OneDrive per i siti all'interno dell'organizzazione. Si noti che è necessario aggiungere l'URL per del dominio sito personale dell'organizzazione (ad esempio, https://contoso-my.sharepoint.com) a OneDrive per i siti creati dallo script. Dopo aver ottenuto l'elenco di indirizzi di posta elettronica o OneDrive per i siti, è possibile copiare e incollare li alla pagina **percorsi** nell'Editor di ricerca del blocco. 
  
- Fare clic su **Salva** per salvare le modifiche nell'Editor di ricerca di blocco, sarà convalidato l'indirizzo di posta elettronica per le cassette postali che è stato aggiunto a una ricerca. Se l'indirizzo di posta elettronica non esiste, viene visualizzato un messaggio di errore che indica che non è possibile individuare la cassetta postale. Si noti che non vengono convalidati gli URL dei siti. 
  

