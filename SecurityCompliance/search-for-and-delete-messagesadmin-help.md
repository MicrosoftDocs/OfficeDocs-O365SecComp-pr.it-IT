---
title: Ricerca ed eliminazione di messaggi - Guida di Amministrazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: Gli amministratori possono utilizzare il cmdlet Search-Mailbox per cercare cassette postali utente ed eliminare messaggi da una cassetta postale.
ms.openlocfilehash: ed110c4a3e36a93970af99e9548aa293d94307fd
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026583"
---
# <a name="search-for-and-delete-messages---admin-help"></a>Ricerca ed eliminazione di messaggi - Guida di Amministrazione
  
Gli amministratori possono utilizzare il cmdlet **Search-Mailbox** per cercare cassette postali utente ed eliminare messaggi da una cassetta postale. 
  
Per cercare ed eliminare i messaggi in un solo passaggio, eseguire il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_. Tuttavia, durante questa operazione non è possibile visualizzare in anteprima i risultati di ricerca o creare un registro dei messaggi che verrà restituito dalla ricerca e si potrebbero inavvertitamente eliminare messaggi. Per visualizzare in anteprima un registro dei messaggi trovati nella ricerca prima che vengano eliminati, eseguire il cmdlet **Search-Mailbox** con l'opzione  _LogOnly_. 
  
Come ulteriore salvaguardia, è possibile prima copiare i messaggi su un'altra cassetta postale utilizzando i parametri  _TargetMailbox_ e  _TargetFolder_. Nell'effettuare questa operazione, mantenere una copia dei messaggi eliminati nel caso sia necessario accedervi di nuovo. 
  
## <a name="what-do-i-need-to-know-before-i-begin"></a>Informazioni necessarie per iniziare
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 10 minuti. Il tempo effettivo potrebbe variare in base alla dimensione della cassetta postale e della query di ricerca.
    
- Non è possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire tali procedure. È necessario utilizzare la shell.
    
- Per cercare ed eliminare messaggi nelle cassette postali degli utenti, è necessario ricoprire entrambi i seguenti ruoli di gestione:
    
  - **Ricerca di cassette postali** Questo ruolo consente di cercare i messaggi tra più cassette postali nell'organizzazione. Gli amministratori non sono assegnati al ruolo per impostazione predefinita. Per assegnare manualmente questo ruolo in modo che è possibile cercare cassette postali, aggiungere l'utente come membro del gruppo di ruoli gestione individuazione. Vedere [aggiunta di un utente al gruppo di ruoli gestione individuazione](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).
    
  - **Cassetta postale importazione/esportazione** Questo ruolo consente di eliminare i messaggi dalla cassetta postale dell'utente. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruolo. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere la sezione "Aggiungere un ruolo a un gruppo di ruoli" in [Gestire gruppi di ruoli](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) . 
    
- Se la cassetta postale dalla quale si desidera eliminare i messaggi ha la funzione di individuazione di singoli elementi, è necessario prima disabilitare la funzione. Per ulteriori informazioni, vedere [Abilitare o disabilitare il ripristino di un singolo elemento per una cassetta postale](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).
    
- Se la cassetta postale da cui si desidera eliminare i messaggi viene messa in attesa, è consigliabile controllare con la gestione dei record o il reparto legale prima della rimozione dell'esenzione e l'eliminazione del contenuto delle cassette postali. Dopo aver ottenuto l'approvazione, seguire i passaggi riportati nell'argomento [Pulita cartella the degli elementi ripristinabili](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).
    
- Una singola ricerca può essere eseguita su un massimo di 10.000 cassette postali con il cmdlet **Search-Mailbox**. Se si è un'organizzazione Exchange Online con più di 10.000 cassette postali, è possibile utilizzare la funzionalità Ricerca di conformità (o il corrispondente cmdlet **New-ComplianceSearch** ) per cercare un numero illimitato di cassette postali. È possibile utilizzare il cmdlet **New-ComplianceSearchAction** per eliminare i messaggi restituiti da una ricerca di conformità. Per ulteriori informazioni, vedere [Cercare ed eliminare messaggi dall'organizzazione di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).
    
- Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi. 
    
- Cassetta postale di archivio dell'utente verrà cercata anche quando si esegue il cmdlet **Search-Mailbox** . Allo stesso modo, verranno eliminati gli elementi nella cassetta postale di archivio principale quando si utilizza il cmdlet **Search-Mailbox** con l'opzione _DeleteContent_ . Per evitare questo problema, è possibile includere l'opzione *DoNotIncludeArchive* . Inoltre, è consigliabile non utilizzare l'opzione _DeleteContent_ per eliminare i messaggi in Exchange Online le cassette postali contenenti espansione automatica archiviazione abilitata poiché potrebbe verificarsi una perdita di dati imprevisti. 
    
## <a name="search-messages-and-log-the-search-results"></a>Ricerca di messaggi e registrazione dei risultati della ricerca
<a name="sectionSection1"> </a>

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto e il risultato viene registrato nella cartella SearchAndDeleteLog della cassetta postale dell'amministratore. I messaggi non vengono copiati né eliminati nella cassetta postale di destinazione.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Nell'esempio seguente in tutte le cassette postali dell'organizzazione si cercano i messaggi con qualsiasi tipo di file allegato contenente la parola "Trojan" nel nome file e viene inviato un messaggio del registro alla cassetta postale dell'amministratore.
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).
  
[Torna su](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="search-and-delete-messages"></a>Ricerca ed eliminazione dei messaggi
<a name="sectionSection2"> </a>

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto; tali messaggi vengono eliminati dalla cassetta postale di origine senza che vengano copiati i risultati di ricerca su un'altra cartella. Come spiegato precedentemente, è necessario avere il ruolo di gestione Esportazione/Importazione delle cassette postali per eliminare messaggi dalla cassetta postale di un utente.
  
> [!IMPORTANT]
> Quando si utilizza il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_, i messaggi vengono eliminati permanentemente dalla cassetta postale di origine. Prima di eliminare permanentemente i messaggi, si consiglia di utilizzare l'opzione  _LogOnly_ per creare un registro dei messaggi trovati nella ricerca prima che vengano eliminati oppure copiare i messaggi su un'altra cassetta postale prima di eliminarli dalla cassetta postale di origine. 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto. Il risultato viene copiato nella cartella AprilStewart-DeletedMessages nella cassetta postale BackupMailbox e i messaggi vengono eliminati dalla cassetta postale di April.
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

In questo esempio si cercano in tutte le cassette postali dell'organizzazione i messaggi con la riga di oggetto "Download this file" e quindi li si elimina in modo definitivo. 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).
  
[Torna su](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="using-the--loglevel-full-parameter"></a>Usando il parametro -LogLevel Full
<a name="sectionSection3"> </a>

In alcuni degli esempi precedenti, il parametro  _LogLevel_ con valore  `Full` viene utilizzato per registrare informazioni dettagliate sui risultati restituiti dal cmdlet **Search-Mailbox**. Quando si include questo parametro, un messaggio di posta elettronica viene creato e inviato alla cassetta postale specificata dal parametro  _TargetMailbox_. Il file di registro (che è un file in formato CSV denominato Search Results.csv) è allegato a questo messaggio di posta elettronica e si trova nella cartella specificata dal parametro  _TargetFolder_. Il file di registro contiene una riga per ogni messaggio incluso nei risultati della ricerca quando si esegue il cmdlet **Search-Mailbox**. 
  

