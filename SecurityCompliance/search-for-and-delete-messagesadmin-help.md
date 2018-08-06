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
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="e42d4-103">Ricerca ed eliminazione di messaggi - Guida di Amministrazione</span><span class="sxs-lookup"><span data-stu-id="e42d4-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="e42d4-104">Gli amministratori possono utilizzare il cmdlet **Search-Mailbox** per cercare cassette postali utente ed eliminare messaggi da una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e42d4-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="e42d4-p101">Per cercare ed eliminare i messaggi in un solo passaggio, eseguire il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_. Tuttavia, durante questa operazione non è possibile visualizzare in anteprima i risultati di ricerca o creare un registro dei messaggi che verrà restituito dalla ricerca e si potrebbero inavvertitamente eliminare messaggi. Per visualizzare in anteprima un registro dei messaggi trovati nella ricerca prima che vengano eliminati, eseguire il cmdlet **Search-Mailbox** con l'opzione  _LogOnly_.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="e42d4-p102">Come ulteriore salvaguardia, è possibile prima copiare i messaggi su un'altra cassetta postale utilizzando i parametri  _TargetMailbox_ e  _TargetFolder_. Nell'effettuare questa operazione, mantenere una copia dei messaggi eliminati nel caso sia necessario accedervi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="what-do-i-need-to-know-before-i-begin"></a><span data-ttu-id="e42d4-110">Informazioni necessarie per iniziare</span><span class="sxs-lookup"><span data-stu-id="e42d4-110">What do I need to know before I begin?</span></span>
<span data-ttu-id="e42d4-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e42d4-111"></span></span>

- <span data-ttu-id="e42d4-p103">Tempo stimato per il completamento: 10 minuti. Il tempo effettivo potrebbe variare in base alla dimensione della cassetta postale e della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="e42d4-p104">Non è possibile utilizzare l'interfaccia di amministrazione di Exchange per eseguire tali procedure. È necessario utilizzare la shell.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="e42d4-116">Per cercare ed eliminare messaggi nelle cassette postali degli utenti, è necessario ricoprire entrambi i seguenti ruoli di gestione:</span><span class="sxs-lookup"><span data-stu-id="e42d4-116">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="e42d4-p105">**Ricerca di cassette postali** Questo ruolo consente di cercare i messaggi tra più cassette postali nell'organizzazione. Gli amministratori non sono assegnati al ruolo per impostazione predefinita. Per assegnare manualmente questo ruolo in modo che è possibile cercare cassette postali, aggiungere l'utente come membro del gruppo di ruoli gestione individuazione. Vedere [aggiunta di un utente al gruppo di ruoli gestione individuazione](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span><span class="sxs-lookup"><span data-stu-id="e42d4-p105">**Mailbox Search** This role allows you to search for messages across multiple mailboxes in your organization. Administrators aren't assigned this role by default. To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group. See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="e42d4-p106">**Cassetta postale importazione/esportazione** Questo ruolo consente di eliminare i messaggi dalla cassetta postale dell'utente. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruolo. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Per ulteriori informazioni, vedere la sezione "Aggiungere un ruolo a un gruppo di ruoli" in [Gestire gruppi di ruoli](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span><span class="sxs-lookup"><span data-stu-id="e42d4-p106">**Mailbox Import Export** This role allows you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group. For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="e42d4-p107">Se la cassetta postale dalla quale si desidera eliminare i messaggi ha la funzione di individuazione di singoli elementi, è necessario prima disabilitare la funzione. Per ulteriori informazioni, vedere [Abilitare o disabilitare il ripristino di un singolo elemento per una cassetta postale](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span><span class="sxs-lookup"><span data-stu-id="e42d4-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="e42d4-p108">Se la cassetta postale da cui si desidera eliminare i messaggi viene messa in attesa, è consigliabile controllare con la gestione dei record o il reparto legale prima della rimozione dell'esenzione e l'eliminazione del contenuto delle cassette postali. Dopo aver ottenuto l'approvazione, seguire i passaggi riportati nell'argomento [Pulita cartella the degli elementi ripristinabili](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span><span class="sxs-lookup"><span data-stu-id="e42d4-p108">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content. After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="e42d4-p109">Una singola ricerca può essere eseguita su un massimo di 10.000 cassette postali con il cmdlet **Search-Mailbox**. Se si è un'organizzazione Exchange Online con più di 10.000 cassette postali, è possibile utilizzare la funzionalità Ricerca di conformità (o il corrispondente cmdlet **New-ComplianceSearch** ) per cercare un numero illimitato di cassette postali. È possibile utilizzare il cmdlet **New-ComplianceSearchAction** per eliminare i messaggi restituiti da una ricerca di conformità. Per ulteriori informazioni, vedere [Cercare ed eliminare messaggi dall'organizzazione di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span><span class="sxs-lookup"><span data-stu-id="e42d4-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="e42d4-p110">Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="e42d4-p111">Cassetta postale di archivio dell'utente verrà cercata anche quando si esegue il cmdlet **Search-Mailbox** . Allo stesso modo, verranno eliminati gli elementi nella cassetta postale di archivio principale quando si utilizza il cmdlet **Search-Mailbox** con l'opzione _DeleteContent_ . Per evitare questo problema, è possibile includere l'opzione *DoNotIncludeArchive* . Inoltre, è consigliabile non utilizzare l'opzione _DeleteContent_ per eliminare i messaggi in Exchange Online le cassette postali contenenti espansione automatica archiviazione abilitata poiché potrebbe verificarsi una perdita di dati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p111">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet. Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. To prevent this, you can include the  *DoNotIncludeArchive*  switch. Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="e42d4-139">Ricerca di messaggi e registrazione dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="e42d4-139">Search messages and log the search results</span></span>
<span data-ttu-id="e42d4-140"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e42d4-140"></span></span>

<span data-ttu-id="e42d4-p112">Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto e il risultato viene registrato nella cartella SearchAndDeleteLog della cassetta postale dell'amministratore. I messaggi non vengono copiati né eliminati nella cassetta postale di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="e42d4-143">Nell'esempio seguente in tutte le cassette postali dell'organizzazione si cercano i messaggi con qualsiasi tipo di file allegato contenente la parola "Trojan" nel nome file e viene inviato un messaggio del registro alla cassetta postale dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e42d4-143">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="e42d4-144">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="e42d4-144">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
[<span data-ttu-id="e42d4-145">Torna su</span><span class="sxs-lookup"><span data-stu-id="e42d4-145">Return to top</span></span>](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="search-and-delete-messages"></a><span data-ttu-id="e42d4-146">Ricerca ed eliminazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e42d4-146">Search and delete messages</span></span>
<span data-ttu-id="e42d4-147"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e42d4-147"></span></span>

<span data-ttu-id="e42d4-p113">Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto; tali messaggi vengono eliminati dalla cassetta postale di origine senza che vengano copiati i risultati di ricerca su un'altra cartella. Come spiegato precedentemente, è necessario avere il ruolo di gestione Esportazione/Importazione delle cassette postali per eliminare messaggi dalla cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e42d4-p114">Quando si utilizza il cmdlet **Search-Mailbox** con l'opzione  _DeleteContent_, i messaggi vengono eliminati permanentemente dalla cassetta postale di origine. Prima di eliminare permanentemente i messaggi, si consiglia di utilizzare l'opzione  _LogOnly_ per creare un registro dei messaggi trovati nella ricerca prima che vengano eliminati oppure copiare i messaggi su un'altra cassetta postale prima di eliminarli dalla cassetta postale di origine.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="e42d4-152">Con questo esempio viene effettuata una ricerca nella cassetta postale di April Stewart per individuare i messaggi contenenti la frase "Your bank statement" nell'oggetto. Il risultato viene copiato nella cartella AprilStewart-DeletedMessages nella cassetta postale BackupMailbox e i messaggi vengono eliminati dalla cassetta postale di April.</span><span class="sxs-lookup"><span data-stu-id="e42d4-152">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="e42d4-153">In questo esempio si cercano in tutte le cassette postali dell'organizzazione i messaggi con la riga di oggetto "Download this file" e quindi li si elimina in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="e42d4-153">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="e42d4-154">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span><span class="sxs-lookup"><span data-stu-id="e42d4-154">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
[<span data-ttu-id="e42d4-155">Torna su</span><span class="sxs-lookup"><span data-stu-id="e42d4-155">Return to top</span></span>](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="e42d4-156">Usando il parametro -LogLevel Full</span><span class="sxs-lookup"><span data-stu-id="e42d4-156">Using the -LogLevel Full parameter</span></span>
<span data-ttu-id="e42d4-157"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="e42d4-157"></span></span>

<span data-ttu-id="e42d4-p115">In alcuni degli esempi precedenti, il parametro  _LogLevel_ con valore  `Full` viene utilizzato per registrare informazioni dettagliate sui risultati restituiti dal cmdlet **Search-Mailbox**. Quando si include questo parametro, un messaggio di posta elettronica viene creato e inviato alla cassetta postale specificata dal parametro  _TargetMailbox_. Il file di registro (che è un file in formato CSV denominato Search Results.csv) è allegato a questo messaggio di posta elettronica e si trova nella cartella specificata dal parametro  _TargetFolder_. Il file di registro contiene una riga per ogni messaggio incluso nei risultati della ricerca quando si esegue il cmdlet **Search-Mailbox**.</span><span class="sxs-lookup"><span data-stu-id="e42d4-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
  

