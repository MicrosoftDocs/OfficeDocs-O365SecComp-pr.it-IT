---
title: Eliminare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Quando non è più necessario conservare il contenuto di una cassetta postale inattiva di Office 365, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo l'esenzione. Dopo aver rimosso il blocco, la cassetta postale inattiva viene contrassegnata per l'eliminazione e viene eliminata definitivamente dopo l'elaborazione.
ms.openlocfilehash: f1aa29b0e40d02e4b6450202c0b2a34ae3075677
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001069"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>Eliminare una cassetta postale inattiva in Office 365

An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Inoltre, è possibile applicare un criterio di conservazione di Office 365 (creato nel centro sicurezza e conformità di Office 365 o Microsoft 365) alla cassetta postale inattiva. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
  
Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). È possibile utilizzare Exchange Online PowerShell o l'interfaccia di amministrazione di Exchange (EAC) per rimuovere un blocco sul posto da una cassetta postale inattiva. 
    
- È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva. Per ulteriori informazioni, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- Se si rimuove il blocco o i criteri di conservazione di Office 365 da una cassetta postale inattiva e il periodo di conservazione della cassetta postale con eliminazione temporanea è scaduto, la cassetta postale viene eliminata definitivamente. Una volta eliminata, non è possibile recuperarla. Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario. Se si desidera attivare nuovamente una cassetta postale inattiva, è possibile recuperarla. Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Passaggio 1: identificare i blocchi su una cassetta postale inattiva

Come affermato in precedenza, potrebbe essere applicato un blocco per controversia legale, un blocco sul posto o un criterio di conservazione di Office 365 su una cassetta postale inattiva. Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.
  
Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

Il valore di **True** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva ha un blocco per controversia legale. Se in una cassetta postale inattiva è abilitato un blocco sul posto, il GUID del blocco viene visualizzato come il valore per la proprietà **InPlaceHolds**. Ad esempio, i risultati seguenti per due cassette postali inattive mostrano che un blocco per controversia legale è applicato ad Ann Beebe e che due blocchi sul posto sono applicati a Pilar Pinilla. 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Se sono abilitati numerosi blocchi sul posto per una cassetta postale inattiva, non vengono visualizzati tutti i GUID dei blocchi sul posto. È possibile eseguire il comando seguente per visualizzare tutti i GUID del blocco sul posto:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva

Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel rimuovere i blocchi sulla cassetta postale. Come descritto in precedenza, è necessario rimuovere tutti i blocchi per eliminare definitivamente una cassetta postale inattiva. 
  
### <a name="remove-a-litigation-hold"></a>Rimozione di un blocco per controversia legale

Come descritto in precedenza, è necessario utilizzare Windows PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando riportato di seguito per rimuovere un blocco per controversia legale.
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> Il modo migliore per identificare una cassetta postale inattiva è utilizzando il valore del relativo nome distinto o del GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 
  
### <a name="remove-in-place-holds"></a>Rimozione dei blocchi sul posto

 Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva: 
  
- **Eliminare l'oggetto blocco sul posto** Se la cassetta postale inattiva che si desidera eliminare in modo definitivo è l'unica cassetta postale di origine per un blocco sul posto, è possibile eliminare l'oggetto blocco sul posto. 
    
    > [!NOTE]
    > È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore. 
  
- **Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Utilizzare EAC per eliminare un blocco sul posto

1. Se si conosce il nome del blocco sul posto che si desidera eliminare, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva che si desidera eliminare definitivamente. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il blocco sul posto che si desidera eliminare, quindi fare clic su **modifica** ![icona](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto

1. Creare una variabile che contiene le proprietà del blocco sul posto che si desidera eliminare. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. Disattivare il blocco in Blocco sul posto.
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. Eliminare il blocco sul posto.
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usare EAC per rimuovere una cassetta postale inattiva da un blocco sul posto

1. Se si conosce il nome del blocco sul posto che si desidera applicare alla cassetta postale inattiva, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Selezionare il blocco sul posto applicato alla cassetta postale inattiva, quindi fare clic su **modifica** ![icona](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Fare clic su **Salva** per salvare la modifica. Verrà visualizzato un messaggio che indica che l'operazione è stata completata. 
    
7. Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto

Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto. 
  
1. Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto. 
    
```
  $InPlaceHold.Sources
```

   **Nota:** La ** proprietà sources del blocco sul posto identifica le cassette postali di origine in base alle rispettive proprietà *legacyExchangeDN* . Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata. Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP. 
   
3. Rimuovere la cassetta postale inattiva dall'elenco delle cassette postali di origine nella variabile. Assicurarsi di usare il **LegacyExchangeDN** della cassetta postale inattiva restituito dal comando nel passaggio precedente. 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine nella variabile.
    
```
  $InPlaceHold.Sources
```

5. Modificare il blocco sul posto con l'elenco aggiornato delle cassette postali di origine, che non include la cassetta postale inattiva.
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine per il blocco sul posto.
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>Ulteriori informazioni

- **Una cassetta postale inattiva è un tipo di cassetta postale con eliminazione temporanea.** In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, una cassetta postale con eliminazione temporanea viene contrassegnata per l'eliminazione definitiva e non può essere ripristinata. 
    
- **Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?** La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni. Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva. Questa è nota come data di eliminazione temporanea, che è la data in cui l'account utente di Office 365 corrispondente è stato eliminato o in cui la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox**. La data di eliminazione temporanea non è la data in cui si rimuove il blocco. 
    
- **Una cassetta postale inattiva viene eliminata definitivamente subito dopo la rimozione del blocco?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima, la cassetta postale non viene eliminata definitivamente non appena si rimuove il blocco. La cassetta postale viene contrassegnata per l'eliminazione definitiva e viene eliminata la volta successiva che viene elaborata. 
    
- **In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva. Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea. Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Alla scadenza del periodo di conservazione delle cassette postali con eliminazione temporanea, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva. Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?** Dopo la rimozione di un'esenzione e la cassetta postale inattiva viene ripristinata a una cassetta postale eliminata temporaneamente, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox** . Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**. Ad esempio: 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
Nell'esempio precedente, la proprietà *WhenSoftDeleted* identifica la data di eliminazione temporanea, che in questo esempio è il 30 ottobre 2014. Se questa cassetta postale eliminata temporaneamente è stata precedentemente una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminato definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted* . In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.

