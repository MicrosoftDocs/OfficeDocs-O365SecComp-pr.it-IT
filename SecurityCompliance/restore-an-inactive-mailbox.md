---
title: Ripristinare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Se un nuovo dipendente o un altro utente ha bisogno dell'accesso al contenuto di una cassetta postale inattiva in Office 365, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva a una cassetta postale esistente.
ms.openlocfilehash: fa3572ef34a905ae2216672ed42507f0c712accb
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296619"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>Ripristinare una cassetta postale inattiva in Office 365

Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se un altro dipendente assume le responsabilità del dipendente rimosso o se quest'ultimo ritorna nell'organizzazione, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente: 
  
- **Ripristinare una cassetta postale inattiva** Se l'altro dipendente assume le responsabilità di un dipendente rimosso o se un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. È inoltre possibile ripristinare l'archivio da una cassetta postale inattiva. Dopo il ripristino, la cassetta postale inattiva viene mantenuta e viene conservata come una cassetta postale inattiva. In questo argomento vengono descritte le procedure per il ripristino di una cassetta postale inattiva. 
    
- **Recuperare una cassetta postale inattiva** Se il dipendente defunto torna all'organizzazione o se un nuovo dipendente viene assunto per assumersi le responsabilità del dipendente, è possibile ripristinare il contenuto della cassetta postale inattiva. Questo metodo converte la cassetta postale inattiva in una nuova cassetta postale che contiene il contenuto della cassetta postale inattiva. Dopo il ripristino, la cassetta postale inattiva non esiste più. Per le procedure dettagliate, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
    
Per ulteriori informazioni sulle differenze tra ripristino e recupero di una cassetta postale inattiva, vedere la sezione **more information** in questo articolo. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario utilizzare Exchange Online PowerShell per ripristinare una cassetta postale inattiva. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Eseguire il seguente comando in PowerShell di Exchange Online per ottenere informazioni di identità per le cassette postali inattive nell'organizzazione. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Utilizzare le informazioni restituite da questo comando per ripristinare una cassetta postale inattiva specifica.
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="restore-an-inactive-mailbox"></a>Ripristinare una cassetta postale inattiva

Utilizzare il cmdlet **New-MailboxRestoreRequest** con i parametri  _SourceMailbox_ e  _TargetMailbox_ per ripristinare il contenuto di una cassetta postale inattiva in una cassetta postale esistente. Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Creare una variabile che contiene le proprietà della cassetta postale inattiva. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario. 
  
2. Ripristinare il contenuto della cassetta postale inattiva in una cassetta postale esistente. Il contenuto della cassetta postale inattiva (cassetta postale di origine) viene unito nelle cartelle corrispondenti nella cassetta postale esistente (cassetta postale di destinazione).
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   In alternativa, è possibile specificare una cartella di primo livello nella cassetta postale di destinazione in cui si desidera ripristinare il contenuto dalla cassetta postale inattiva. Se la cartella di destinazione specificata o la struttura di cartelle di destinazione non esiste già nella cassetta postale di destinazione, viene creata durante il processo di ripristino. 
    
    Questo esempio consente di copiare elementi e sottocartelle da una cassetta postale inattiva a una cartella denominata "Cassetta postale inattiva" nella struttura di cartelle di primo livello della cassetta postale di destinazione.
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Ripristinare l'archivio da una cassetta postale inattiva

Se una cassetta postale inattiva dispone di una cassetta postale di archiviazione, è anche possibile ripristinarla nella cassetta postale di archiviazione di una cassetta postale esistente. Per ripristinare l'archivio da una cassetta postale inattiva, è necessario aggiungere le opzioni  _SourceIsArchive_ e  _TargetIsAchive_ al comando utilizzato per ripristinare una cassetta postale inattiva. 
  
1. Creare una variabile che contiene le proprietà della cassetta postale inattiva. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario. 
  
2. Ripristinare il contenuto dell'archivio dalla cassetta postale inattiva (archivio di origine) all'archivio di una cassetta postale esistente (archivio di destinazione). In questo esempio, il contenuto dell'archivio di origine viene copiato in una cartella denominata "Archivio della cassetta postale inattiva" nell'archivio della cassetta postale di destinazione.

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** Quando si ripristina una cassetta postale inattiva, la cassetta postale viene sostanzialmente convertita in una nuova cassetta postale, il contenuto e la struttura delle cartelle della cassetta postale inattiva vengono mantenuti e la cassetta postale è collegata a un nuovo account utente. Dopo il ripristino, la cassetta postale inattiva non esiste più e tutte le modifiche apportate al contenuto nella nuova cassetta postale influiranno sul contenuto originariamente in attesa nella cassetta postale inattiva. Viceversa, quando si ripristina una cassetta postale inattiva, il contenuto viene semplicemente copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane una cassetta postale inattiva. Tutte le modifiche apportate al contenuto della cassetta postale di destinazione non influiscono sul contenuto originale mantenuto nella cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando lo [strumento di ricerca del contenuto](run-a-content-search-in-the-security-and-compliance-center.md) nel centro &amp; sicurezza e conformità di Office 365, il suo contenuto può essere ripristinato in un'altra cassetta postale oppure può essere recuperato o eliminato in un secondo momento. 
    
- **Come si trovano le cassette postali inattive?** Per ottenere un elenco delle cassette postali inattive nell'organizzazione e visualizzare le informazioni utili per il ripristino di una cassetta postale inattiva, è possibile eseguire questo comando. 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Utilizzare un blocco per controversia legale o un criterio di conservazione di Office 365 per mantenere il contenuto della cassetta postale inattiva.** Se si desidera mantenere lo stato di una cassetta postale inattiva dopo averla ripristinata, è possibile applicare alla cassetta postale di destinazione un [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) o un [criterio di conservazione di Office 365](retention-policies.md) prima di ripristinare la cassetta postale inattiva. Ciò impedirà l'eliminazione definitiva degli elementi della cassetta postale inattiva dopo averli ripristinati nella cassetta postale di destinazione. 
    
- **Abilitare il blocco di conservazione sulla cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva.** Poiché gli elementi delle cassette postali di una cassetta postale inattiva potrebbero essere obsoleti, è consigliabile abilitare il blocco di conservazione sulla cassetta postale di destinazione prima di ripristinare una cassetta postale inattiva. Quando si posiziona una cassetta postale in attesa di conservazione, i criteri di conservazione assegnati non verranno elaborati fino alla rimozione del blocco di conservazione o fino alla scadenza del periodo di conservazione. In questo modo il proprietario della cassetta postale di destinazione è in grado di gestire i vecchi messaggi dalla cassetta postale inattiva. In caso contrario, il criterio di conservazione potrebbe eliminare gli elementi obsoleti (o spostare gli elementi nella cassetta postale di archiviazione, se abilitata) scaduti in base alle impostazioni di conservazione configurate per la cassetta postale di destinazione. Per ulteriori informazioni, vedere [posizionare una cassetta postale sulla conservazione Conservare in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Cosa consente di fare l'opzione AllowLegacyDNMismatch?** Negli esempi precedenti sul ripristino di una cassetta postale inattiva, l'opzione **AllowLegacyDNMismatch** viene utilizzata per consentire il ripristino della cassetta postale inattiva in una cassetta postale di destinazione diversa. In un comune scenario di ripristino, l'obiettivo è quello di ripristinare il contenuto in cui le cassette postali di origine e di destinazione sono la stessa cassetta postale. In questo caso, per impostazione predefinita, il cmdlet **New-MailboxRestoreRequest** consente di verificare che il valore della proprietà **LegacyExchangeDN** per le cassette postali di origine e di destinazione sia lo stesso. Ciò impedisce di ripristinare accidentalmente una cassetta postale di origine nella cassetta postale di destinazione errata. Se si tenta di ripristinare una cassetta postale inattiva senza l'utilizzo dell'opzione **AllowLegacyDNMismatch**, il comando potrebbe avere esito negativo se le cassette postali di origine e di destinazione presentano valori diversi per la proprietà **LegacyExchangeDN**. 
    
- **È possibile utilizzare altri parametri con il cmdlet New-MailboxRestoreRequest per implementare scenari di ripristino diversi per le cassette postali inattive.** Ad esempio, è possibile eseguire questo comando per ripristinare l'archivio dalla cassetta postale inattiva nella cassetta postale principale della cassetta postale di destinazione. 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  È inoltre possibile ripristinare la cassetta postale principale inattiva nell'archivio della cassetta postale di destinazione eseguendo questo comando.

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **Cosa consente di fare il parametro TargetRootFolder?** Come descritto in precedenza, è possibile utilizzare il parametro **TargetRootFolder** per specificare una cartella nel livello superiore della struttura della cartella (denominato anche radice) nella cassetta postale di destinazione in cui ripristinare il contenuto della cassetta postale inattiva. Se non si utilizza questo parametro, gli elementi della cassetta postale inattiva vengono uniti in cartelle predefinite corrispondenti della cassetta postale di destinazione e le cartelle personalizzate vengono ricreate nella radice della cassetta postale di destinazione. Le seguenti illustrazioni evidenziano le differenze nell'utilizzo o meno del parametro **TargetRootFolder**. 
    
    **Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder non viene utilizzato**
    
    ![Schermata visualizzata quando non viene utilizzato il parametro TargetRootFolder](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Gerarchia delle cartelle nella cassetta postale di destinazione quando il parametro TargetRootFolder viene utilizzato**
    
    ![Schermata visualizzata quando viene utilizzato il parametro TargetRootFolder](media/300da592-7323-48db-b8a4-07012259d113.png)

  

