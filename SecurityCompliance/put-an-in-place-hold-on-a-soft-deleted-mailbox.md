---
title: Mettere an In-Place Hold in una cassetta postale eliminata in Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Informazioni su come creare un'archiviazione sul posto per una cassetta postale eliminata per rendere inattiva e mantenere il relativo contenuto. Quindi è possibile utilizzare gli strumenti di eDiscovery di Microsoft per la ricerca di cassette postali inattive.
ms.openlocfilehash: e666ac608ec224bf97caa947be2cb42b742c6fa9
ms.sourcegitcommit: ca97beff215d154b6ab006ce1222056434fde1a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "29740798"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Mettere an In-Place Hold in una cassetta postale eliminata in Exchange Online

Informazioni su come creare un'archiviazione sul posto per una cassetta postale eliminata per rendere inattiva e mantenere il relativo contenuto. Quindi è possibile utilizzare gli strumenti di eDiscovery di Microsoft per la ricerca di cassette postali inattive.
  
> [!NOTE]
> È stata posticipata la scadenza per la creazione di nuove archiviazioni sul posto in Exchange Online (in Office 365 ed Exchange Online piani autonomi). Ma più avanti in questo anno o un anno successivo anticipati, non sarà in grado di creare nuove archiviazioni sul posto di Exchange Online. In alternativa all'utilizzo di archiviazione sul posto, è possibile utilizzare i [casi di eDiscovery](https://go.microsoft.com/fwlink/?linkid=780738) o [criteri di conservazione](https://go.microsoft.com/fwlink/?linkid=827811) in Office 365 Security &amp; centro conformità. Dopo che è nuovo rimuovere archiviazioni sul posto, ancora sarà possibile modificare archiviazioni sul posto esistente e la creazione di nuove archiviazioni sul posto di Exchange Server 2013 e le distribuzioni ibride di Exchange continueranno a essere supportate. E ancora sarà in grado di effettuare le cassette postali di conservazione per controversia legale. 
  
Potrebbe essere una situazione in cui una persona ha lasciato l'organizzazione e le cassette postali e l'account utente corrispondente sono state eliminate. In un secondo momento, si nota non è presente nella cassetta postale che è necessario mantenere informazioni. Cosa potete fare? Se non è scaduto il periodo di conservazione delle cassette postali eliminate, è possibile inserire un'archiviazione sul posto nella cassetta postale eliminata (noti come una cassetta postale eliminata) e rendere una cassetta postale inattiva. Una *cassetta postale inattiva* viene utilizzato per mantenere la posta elettronica del dipendente precedente dopo potrà lascia l'organizzazione. Il contenuto di una cassetta postale inattiva viene conservato per la durata di In-Place Hold che è stato viene messa nella cassetta postale eliminata quando è stata effettuata inattivo. Dopo aver effettuata la cassetta postale inattiva, è possibile cercare la cassetta postale tramite eDiscovery In locale in Exchange Online, ricerca contenuto in Office 365 Security &amp; centro conformità o il centro eDiscovery in SharePoint Online. 
  
> [!NOTE]
> In Exchange Online, una cassetta postale eliminata è una cassetta postale è stata eliminata, ma è possibile ripristinare entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali eliminate in Exchange Online è 30 giorni. Questo significa che la cassetta postale può essere recuperato (o con una cassetta postale inattiva) entro 30 giorni da eliminare. Dopo 30 giorni, una cassetta postale eliminata è contrassegnata per l'eliminazione definitiva e non può essere ripristinata o rese inattiva. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per mettere an In-Place Hold in una cassetta postale eliminata. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) oppure il centro eDiscovery in SharePoint Online. 
    
- Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Eseguire il comando seguente per ottenere informazioni sull'identità sulle cassette postali eliminate all'interno dell'organizzazione. 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Mettere an In-Place Hold in una cassetta postale eliminata per effettuare una cassetta postale inattiva

Utilizzare il cmdlet **New-MailboxSearch** per effettuare una cassetta postale eliminata una cassetta postale inattiva. Per ulteriori informazioni, vedere [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Creare una variabile che contiene le proprietà delle cassette postali eliminate. 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > Nel comando precedente, utilizzare il valore della proprietà **ExchangeGuid** o **DistinguishedName** per identificare la cassetta postale eliminata. Queste proprietà sono univoche per ciascuna cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata potrebbe essere lo stesso indirizzo SMTP primario. 
  
2. Creare an In-Place Hold e inserirli nella cassetta postale eliminata. In questo esempio non viene specificato durata dell'attesa. In questo modo si terrà elementi per un tempo indefinito o fino alla rimozione di cassette postali inattive.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   È inoltre possibile specificare un intervallo di tempo di attesa quando si crea l'archiviazione sul posto. In questo esempio contiene gli elementi nella cassetta postale inattiva di circa 7 anni.
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Dopo pochi secondi, eseguire uno dei seguenti comandi per verificare che la cassetta postale eliminata una cassetta postale inattiva.
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    Oppure
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Ulteriori informazioni

Dopo aver apportato una cassetta postale eliminata una cassetta postale inattiva, esistono diversi modi per che gestire la cassetta postale. Per ulteriori informazioni, vedere:
  
- [Cambiare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [Recuperare una cassetta postale inattiva](recover-an-inactive-mailbox.md)
    
- [Ripristinare una cassetta postale inattiva](restore-an-inactive-mailbox.md)
    
- [Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo l'attesa)
