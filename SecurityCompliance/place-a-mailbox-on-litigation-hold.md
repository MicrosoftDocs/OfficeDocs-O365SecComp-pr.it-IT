---
title: Conservazione in caso di dispute di una cassetta postale
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'Attivare un blocco per controversia legale in una cassetta postale per conservare tutto il contenuto della cassetta postale, tra cui elementi eliminati e versioni originali degli elementi modificati. '
ms.openlocfilehash: 8f440f5fc0bc7dafd639bdf8136808aa2f3bd35f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026443"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>Conservazione in caso di dispute di una cassetta postale
 
Attivare un blocco per controversia legale in una cassetta postale per conservare tutto il contenuto della cassetta postale, tra cui elementi eliminati e versioni originali degli elementi modificati. Quando si attiva un blocco per controversia legale nella cassetta postale di un utente, anche il contenuto della cassetta postale di archiviazione dell'utente (se abilitata) viene messo in attesa. Gli elementi eliminati o modificati vengono conservati per un periodo specificato o fino a quando non viene rimosso il blocco per controversia legale dalla cassetta postale. Tutti questi elementi delle cassette postali vengono restituiti in una ricerca di [eDiscovery in locale](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx). 
  
> [!IMPORTANT]
> Il blocco per controversia legale conserva gli elementi nella cartella Elementi ripristinabili nella cassetta postale dell'utente.A seconda del numero e della dimensione degli elementi eliminati o modificati, la dimensione della cartella Elementi ripristinabili della cassetta postale potrebbe aumentare rapidamente. Per impostazione predefinita, la cartella Elementi ripristinabili è configurata con una quota elevata. In Exchange Online, questa quota viene aumentata automaticamente quando si attiva un blocco per controversia legale in una cassetta postale. In Exchange Server 2013 si consiglia di monitorare le cassette postali con blocco per controversia legale attivato ogni settimana per verificare non venga raggiunto il limite delle quote di Elementi ripristinabili. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 5 minuti
    
- L'impostazione Blocco per controversia legale potrebbe richiedere fino a 60 minuti per essere effettivo.
    
- È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "In-Place Hold" nell'argomento [Messaging policy e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) . 
    
- Per attivare il blocco per controversia legale in una cassetta postale di Exchange Online, è necessario disporre di una licenza di Exchange Online (Piano 2). Se una cassetta postale dispone di una licenza di Exchange Online (Piano 1), occorre assegnarle una licenza di Exchange Online Archiving distinta per attivare il blocco.
    
- Come descritto in precedenza, quando si esegue un blocco per controversia legale nella cassetta postale dell'utente, anche il contenuto nella cassetta postale di archiviazione dell'utente viene bloccato. Se si attiva un blocco per controversia legale in una cassetta postale principale locale in una distribuzione ibrida di Exchange, viene conservata anche la cassetta postale di archiviazione basata sul cloud (se abilitata).
    
- In Exchange Online, la quota per la cartella Elementi ripristinabili viene automaticamente aumentata a 100 GB quando per una cassetta postale si attiva il blocco per controversia legale. La dimensione predefinita della cartella è 30 GB.
    
- Conservazione per controversia legale consente di mantenere gli elementi eliminati e inoltre di mantenere le versioni originali degli elementi modificati fino a quando non viene rimosso l'attesa. È possibile specificare una durata di attesa, che consente di mantenere un elemento della cassetta postale per il periodo di durata specificato. Se si specifica una periodo di durata della conservazione, viene calcolata dalla data di ricezione di un messaggio o viene creato un elemento della cassetta postale. Per conservare gli elementi che soddisfano i criteri specificati, utilizzare an In-Place Hold per creare un'esenzione basata su query. Per ulteriori informazioni, vedere [creare o rimuovere un'archiviazione sul posto](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).
    
- Per attivare un blocco in una cassetta postale di Exchange Online tramite la shell, è necessario utilizzare Exchange Online PowerShell. Per ulteriori informazioni, vedere [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).
    
- L'impostazione di un blocco per controversia legale su una cassetta postale per le cartelle pubbliche non è supportata. Per applicare un blocco alle cartelle pubbliche, è necessario utilizzare il blocco sul posto.
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per attivare un blocco per controversia legale in una cassetta postale
<a name="sectionSection1"> </a>

1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nell'elenco delle cassette postali utente, fare clic sulla cassetta postale per cui si desidera attivare il blocco per controversia legale, quindi fare clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png).
    
3. Dalla pagina delle proprietà della cassetta postale, fare clic su **Funzionalità cassette postali**.
    
4. In **Blocco per controversia legale: disabilitato**, fare clic su **Abilita** per attivare il blocco per controversia legale nella cassetta postale. 
    
5. Nella pagina **Blocco per controversia legale**, inserire le seguenti informazioni opzionali: 
    
  - **Durata del blocco per controversia legale (giorni)** Utilizzare questa casella per specificare la durata di conservazione degli elementi della cassetta postale quando viene attivato il blocco per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale. Se si lascia la casella vuota, gli elementi vengono conservati a tempo indeterminato o fino a quando non viene rimossa la conservazione. Usare un numero di giorni per specificare la durata. 
    
  - **Nota** Utilizzare questa casella per informare l'utente che nella sua cassetta postale è attivo il blocco per controversia legale. La nota viene visualizzata nella cassetta postale dell'utente se quest'ultimo utilizza Outlook 2010 o versione successiva. 
    
  - **URL** Utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sul blocco per controversia legale. Questo URL viene visualizzato nella cassetta postale dell'utente se quest'ultimo utilizza Outlook 2010 o versione successiva. 
    
6. Fare clic su **Salva** nella pagina **Blocco per controversia legale**, quindi fare clic su **Save** nella pagina proprietà della cassetta postale. 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>Attivare un blocco per controversia legale a tempo indeterminato nella cassetta postale tramite la shell
<a name="sectionSection2"> </a>

In questo esempio viene attivato il blocco per controversia legale nella cassetta postale bsuneja@contoso.com. Gli elementi nella cassetta postale vengono conservati a tempo indeterminato o finché non viene rimosso il blocco.
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> Quando si attiva un blocco per controversia legale per un tempo indefinito (senza specificarne la durata), il valore della proprietà  _LitigationHoldDuration_ è impostato su  `Unlimited`. 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>Utilizzo della shell per attivare il blocco per controversia legale nella cassetta postale e conservare gli elementi per una durata specifica
<a name="sectionSection3"> </a>

In questo esempio viene attivato il blocco per controversia legale nella cassetta postale bsuneja@contoso.com e gli elementi vengono conservati per 2555 giorni (circa 7 anni): 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>Utilizzo della shell per attivare il blocco per controversia legale in tutte le cassette postali per una durata specifica
<a name="sectionSection4"> </a>

L'organizzazione può richiedere che tutti i dati delle cassette postali siano conservati per un periodo di tempo specifico. Prima di attivare il blocco per controversia legale per tutte le cassette postali nell'organizzazione, considerare quanto segue:
  
In questo esempio viene attivato il blocco per controversia legale in tutte le cassette postali utente di un anno (365 giorni).
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

In questo esempio viene utilizzato il cmdlet [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) per recuperare tutte le cassette postali nell'organizzazione, si specifica un filtro destinatari per includere tutte le cassette postali utente e viene trasmesso un elenco di cassette postali al cmdlet [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) per attivare il blocco per controversia legale e impostarne la durata. 
  
Per impostare un blocco indefinito in tutte le cassette postali utente, eseguire il comando precedente senza includere il parametro  _LitigationHoldDuration_. 
  
Vedere la sezione [Ulteriori informazioni](#moreinfo.md) per esempi relativi all'utilizzo di altre proprietà del destinatario in un filtro per includere o escludere una o più cassette postali. 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>Rimozione dalla conservazione in caso di dispute di una cassetta postale tramite shell
<a name="sectionSection5"> </a>

In questo esempio, viene rimosso un blocco per controversia legale dalla cassetta postale bsuneja@contoso.com.
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

P
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection6"> </a>

Per verificare la corretta attivazione di un blocco per controversia legale in una cassetta postale, effettuare una delle seguenti operazioni:
  
- Nell'interfaccia di amministrazione di Exchange:
    
1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nell'elenco delle cassette postali utente, fare clic sulla cassetta postale di cui si desidera verificare le impostazioni del blocco per controversia legale, quindi fare clic su **Modifica**![Icona Modifica](media/ITPro-EAC-EditIcon.png).
    
3. Dalla pagina delle proprietà della cassetta postale, fare clic su **Funzionalità cassette postali**.
    
4. In **Blocco per controversia legale**, verificare che il blocco sia attivato.
    
5. Fare clic su **Visualizza dettagli** per verificare quando è stato attivato il blocco per controversia legale e da chi. È inoltre possibile verificare o modificare i valori nelle caselle facoltative **Durata del blocco per controversia legale (giorni)**, **Nota** e **URL**. 
    
- In Shell, utilizzare uno dei seguenti comandi:
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    oppure
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    Se si attiva un blocco per controversia legale per un tempo indefinito, il valore della proprietà  _LitigationHoldDuration_ è impostato su  `Unlimited`.
    
## <a name="more-information"></a>Ulteriori informazioni
<a name="moreinfo"> </a>

- Se l'organizzazione richiede che tutti i dati delle cassette postali siano conservati per un periodo di tempo specifico, considerare quanto segue prima di attivare il blocco per controversia legale per tutte le cassette postali nell'organizzazione.
    
  - Quando si utilizza il comando precedente per attivare un blocco in tutte le cassette postali nell'organizzazione (oppure un set secondario di cassette postali corrispondenti a un filtro destinatario specificato), il blocco viene attivato solo per le cassette postali che esistono al momento dell'esecuzione del comando. Se si creano nuove cassette postali in un secondo momento, sarà necessario eseguire di nuovo il comando per attivare il blocco per le nuove cassette postali. Se si creano spesso nuove cassette postali, è possibile eseguire il comando come attività pianificata secondo la frequenza necessaria.
    
  - Attivare il blocco per controversia legale in tutte le cassette postali può influire notevolmente sulle dimensioni delle cassette postali. In un'organizzazione Exchange Server 2013, pianificare lo spazio di archiviazione adeguato per soddisfare i requisiti di conservazione dell'organizzazione.
    
  - La cartella Elementi ripristinabili presenta un proprio limite di archiviazione, quindi gli elementi nella cartella non pesano sul limite di archiviazione della cassetta postale. Come spiegato in precedenza, la conservazione dei dati delle cassette postali per un lungo periodo di tempo causa la crescita della cartella Elementi ripristinabili in una cassetta postale e nell'archivio di un utente. Per rendere possibile questo aumento in Exchange Online, la quota per la cartella Elementi ripristinabili viene automaticamente aumentata da 30 GB a 100 GB quando per una cassetta postale si attiva il blocco per controversia legale. 
    
    In Exchange Server 2013, il limite di archiviazione predefinito per la cartella elementi ripristinabili è anche 30 GB. È consigliabile monitorare periodicamente le dimensioni della cartella per assicurarsi che non raggiunge il limite previsto. Per ulteriori informazioni, vedere [Cartella elementi ripristinabili](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).
    
- Il comando precedente per attivare un blocco in tutte e cassette postali utilizza un filtro destinatario che restituisce tutte le cassette postali utente. È possibile utilizzare altre proprietà dei destinatari per un elenco delle cassette postali specifiche che è quindi possibile restituire al cmdlet **Set-Mailbox** per attivare un blocco per controversia legale in tali cassette postali. 
    
    Ecco alcuni esempi sull'utilizzo dei cmdlet **Get-Mailbox** e **Get-Recipient** per restituire un set secondario di cassette postali in base alle proprietà comuni di utenti o cassette postali. Tali esempi presumono che le proprietà della cassetta postale rilevante (ad esempio,  _CustomAttributeN_ o  _Department_) siano state popolate.
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    È possibile utilizzare altre proprietà della cassetta postale utente in un filtro per escludere o includere le cassette postali. Per ulteriori dettagli, vedere [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).
    

