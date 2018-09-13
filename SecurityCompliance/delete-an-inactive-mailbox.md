---
title: Eliminare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Quando non più necessaria mantenere il contenuto di una cassetta postale inattiva di Office 365, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo l'attesa. Dopo aver rimosso il blocco, cassette postali inattive sono contrassegnata per l'eliminazione e viene eliminata definitivamente dopo l'elaborazione.
ms.openlocfilehash: a7284be650d7ec6c89a6fdc43d8614603d6f1e19
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965253"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>Eliminare una cassetta postale inattiva in Office 365

Una cassetta postale inattiva viene utilizzata per mantenere la posta elettronica del dipendente precedente dopo potrà lascia l'organizzazione. Quando non più necessaria mantenere il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo l'attesa. Inoltre, è possibile che più conservazioni possono essere messa in una cassetta postale inattiva. Ad esempio una cassetta postale inattiva può essere messa in conservazione per controversia legale e in uno o più archiviazioni sul posto. Inoltre, un criterio di conservazione di Office 365 (creato in Office 365 Security &amp; centro conformità) potrebbe essere applicato alla cassetta postale inattiva. È necessario rimuovere tutte le esenzioni e criteri di conservazione di Office 365 da una cassetta postale inattiva eliminata. Dopo aver rimosso le esenzioni e i criteri di conservazione, le cassette postali inattive sono contrassegnata per l'eliminazione e viene eliminata definitivamente dopo l'elaborazione.
  
> [!IMPORTANT]
> Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
  
Vedere la sezione [Ulteriori informazioni](delete-an-inactive-mailbox.md#moreinfo) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario utilizzare Exchange Online PowerShell per rimuovere una conservazione per controversia legale di una cassetta postale inattiva. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). È possibile utilizzare Exchange Online PowerShell o EAC per rimuovere un'archiviazione sul posto da una cassetta postale inattiva. 
    
- Prima di rimuovere la conservazione e di eliminare una cassetta postale inattiva, è possibile copiare il contenuto di una cassetta postale inattiva a un'altra cassetta postale. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
- Se si rimuove l'esenzione o criteri di conservazione di Office 365 da una cassetta postale inattiva e il periodo di conservazione delle cassette postali eliminate per la cassetta postale è scaduto, verrà eliminata definitivamente la cassetta postale. Dopo l'eliminazione, non può essere annullata. Prima di rimuovere la conservazione, assicurarsi che non è più necessario il contenuto nella cassetta postale. Se si desidera riattivare una cassetta postale inattiva, è possibile recuperarla. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).
    
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
> Se una quantità elevata di archiviazione sul posto è incluso in una cassetta postale inattiva, verrà visualizzati non tutti i GUID di conservazione In locale. È possibile eseguire il comando seguente per visualizzare tutti i GUID di conservazione In locale:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
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
  
- **Eliminare l'oggetto di tipo In-Place Hold** Se la cassetta postale inattiva che si desidera eliminare in modo permanente è l'unica cassetta postale di origine per an In-Place Hold, è possibile eliminare l'oggetto di tipo In-Place Hold. 
    
    > [!NOTE]
    > È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore. 
  
- **Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Utilizzare EAC per eliminare un blocco sul posto

1. Se si conosce il nome del blocco sul posto che si desidera eliminare, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva che si desidera eliminare definitivamente. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
3. Selezionare l'archiviazione sul posto da eliminare e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
4. Nella **In-Place eDiscovery &amp; attesa** le proprietà di pagina, fare clic su **Archiviazione sul posto**, deselezionare la casella di controllo **contenuto locale che corrispondono alla query di ricerca di cassette postali selezionate in attesa** e quindi fare clic su **Salva**.
    
5. Nel **In-Place eDiscovery &amp; attesa** di pagina, selezionare In-Place Hold e quindi fare clic su **Elimina**![sull'icona cestino](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto

1. Creare una variabile che contiene le proprietà del blocco sul posto che si desidera eliminare. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).
    
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

1. Se si conosce il nome del blocco sul posto che si desidera applicare alla cassetta postale inattiva, è possibile passare al passaggio successivo. In caso contrario, eseguire il seguente comando per ottenere il nome del blocco sul posto applicato alla cassetta postale. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. In EAC, andare a **Gestione conformità** \> **In-Place eDiscovery &amp; attesa**.
    
3. Selezionare l'archiviazione sul posto che viene inserito nella cassetta postale inattiva e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
4. Nella **In-Place eDiscovery &amp; attesa** proprietà pagina fare clic su **origini**.
    
5. Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Fare clic su **Salva** per salvare la modifica. Verrà visualizzato un messaggio che indica che l'operazione è stata completata. 
    
7. Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto

Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto. 
  
1. Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](delete-an-inactive-mailbox.md#step1).
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto. 
    
```
  $InPlaceHold.Sources
```

   **Nota:** La proprietà *origini* dell'archiviazione sul posto identifica le cassette postali di origine per le relative proprietà *LegacyExchangeDN* . Poiché questa proprietà identifica in modo univoco cassette postali inattive, tramite la proprietà *origini* da In-Place Hold aiuta a prevenire rimozione della cassetta postale di un problema. In questo modo per evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP. 
   
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
    
- **In che modo il periodo di conservazione della cassetta postale eliminata influisce delle cassette postali inattive?** Se la data di eliminazione reversibile per una cassetta postale inattiva è più di 30 giorni prima della data che dell'esenzione è stato rimosso, la cassetta postale è contrassegnata per l'eliminazione definitiva. Ma se una cassetta postale inattiva è una data eliminate negli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione della cassetta postale eliminata. Per ulteriori informazioni, vedere [eliminazione o ripristino cassette postali degli utenti di Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Dopo la scadenza del periodo di conservazione cassetta postale eliminata, si dispone seguire le procedure per recuperare una cassetta postale inattiva. Per ulteriori informazioni, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
- **Come procedere per visualizzare informazioni su una cassetta postale inattiva dopo la rimozione?** Dopo che è stata rimossa un'esenzione e cassette postali inattive viene ripristinata in una cassetta postale eliminata, non viene restituito utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox** . Ma è possibile visualizzare informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox SoftDeletedMailbox** . Per esempio: 
    
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
  
Nell'esempio precedente, la proprietà *WhenSoftDeleted* identifica la data di eliminazione reversibile, ovvero in questo esempio il 30 ottobre 2014. Se questa cassetta postale eliminata in precedenza era una cassetta postale inattiva per il quale è stata rimossa la conservazione, sarà eliminati definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted* . In questo caso, la cassetta postale viene eliminata definitivamente dopo 30 novembre 2014.

