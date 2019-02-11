---
title: Creare e gestire le cassette postali inattive in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: È possibile creare una cassetta postale inattiva in Office 365 applicando una conservazione o criteri di conservazione di Office 365 per la cassetta postale e quindi eliminare l'account utente di Office 365 corrispondente. Gli elementi in una cassetta postale inattiva vengono mantenuti per tutta la durata del criterio di conservazione o conservazione che è stato applicato prima che venga effettuata inattivo. Per eliminare definitivamente una cassetta postale inattiva, rimuove solo i criteri di conservazione o conservazione.
ms.openlocfilehash: de67068ded30f63e46a8a94c1030d45a12b56a2e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740838"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>Creare e gestire le cassette postali inattive in Office 365

Office 365 consente di mantenere il contenuto delle cassette postali eliminate. Questa funzionalità è denominata [delle cassette postali inattive](inactive-mailboxes-in-office-365.md). Cassette postali inattive consentono di mantenere posta elettronica ex dipendenti una volta terminata l'organizzazione. Una cassetta postale diventa inattiva quando una conservazione per controversia legale o un criterio di conservazione di Office 365 (creato in Office 365 Security &amp; centro conformità) viene applicato alla cassetta postale prima che venga eliminato l'account utente di Office 365 corrispondente. Il contenuto di una cassetta postale inattiva viene mantenuto per la durata dell'attesa effettuata nella cassetta postale prima che venga effettuata inattivo. In questo modo gli amministratori e responsabili della conformità record Manager utilizzare la ricerca del contenuto per la protezione &amp; centro conformità per cercare ed esportare il contenuto di una cassetta postale inattiva. Cassette postali inattive non possono ricevere posta elettronica e non vengono visualizzate nella Rubrica condivisa dell'organizzazione o altri elenchi.
  
> [!NOTE]
> Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- Per rendere inattiva una cassetta postale, è necessario assegnare una licenza di Exchange Online piano 2 in modo che una conservazione per controversia legale o un criterio di conservazione di Office 365 è possibile applicare alla cassetta postale prima che venga eliminato. Le licenze di Exchange Online piano 2 fanno parte di un sottoscrizioni Office 365 Enterprise E3 ed E5. Se una cassetta postale viene assegnata una licenza di Exchange Online piano 1 (che fa parte di una sottoscrizione a Office 365 Enterprise E1), è necessario assegnare una licenza separata archiviazione Exchange Online in modo da un'esenzione può essere applicata alla cassetta postale prima che venga eliminato. Per ulteriori informazioni, vedere [Archiviazione Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).
    
- La licenza associata alla cassetta postale di Exchange Online eliminata saranno disponibile dopo l'eliminazione di account utente di Office 365 corrispondente. È quindi possibile [assegnare licenze agli utenti di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) a un altro utente. 
    
- Se non si applica un blocco per controversia legale o un criterio di conservazione di Office 365 a una cassetta postale prima della sua eliminazione, il contenuto non verrà conservato e non potrà essere trovato. Tuttavia, è possibile recuperare la cassetta postale eliminata entro 30 giorni dall'eliminazione; se non viene recuperata entro 30 giorni, la cassetta postale e il suo contenuto vengono eliminati definitivamente.
    
- Per ulteriori informazioni sulla conservazione per controversia legale, vedere [archiviazione sul posto e conservazione per controversia legale](https://go.microsoft.com/fwlink/p/?LinkId=846124). Per ulteriori informazioni sui criteri di conservazione di Office 365 in sicurezza &amp; centro conformità, vedere [Panoramica di criteri di conservazione in Office 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Creare una cassetta postale inattiva

Esecuzione di una cassetta postale inattiva prevede due fasi: 1) effettuare la cassetta postale su conservazione per controversia legale o applicare un criterio di conservazione di Office 365 e 2) eliminazione della cassetta postale o account utente di Office 365 corrispondente. Dopo che la cassetta postale è inattiva, il relativo contenuto viene mantenuto fino a quando non viene rimosso il criterio di conservazione o conservazione.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>Passaggio 1: applicare il blocco per controversia legale a una cassetta postale o applicare un criterio di conservazione di Office 365

Applicando a una cassetta postale il blocco per controversia legale o un criterio di conservazione di Office 365, il contenuto viene mantenuto nella cassetta postale prima che venga eliminata. Con entrambi i tipi di blocchi viene conservato tutto il contenuto della cassetta postale, compresi gli elementi eliminati e le versioni originali degli elementi modificati. Gli elementi eliminati e modificati vengono conservati nella cassetta postale inattiva per un determinato periodo oppure finché non viene eliminata definitivamente la cassetta postale inattiva rimuovendo il blocco o i criteri di conservazione applicati alla cassetta postale inattiva.
  
Se un blocco è già attivo in una cassetta postale o se un criterio di conservazione di Office 365 è già applicato a una cassetta postale, allora sarà semplicemente necessario eliminare l'account utente di Office 365 corrispondente come descritto nel passaggio 2.
  
Per le procedure dettagliate sull'applicazione del blocco per controversia legale per una cassetta postale o sull'applicazione di un criterio di conservazione di Office 365, vedere:
  
- [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
> [!NOTE]
> Per i blocchi per controversia legale e i criteri di conservazione di Office 365, è possibile creare un blocco indefinito o un blocco con scadenza. In caso di un blocco indefinito, il contenuto della cassetta postale inattiva viene conservato per sempre, finché il blocco non viene rimosso o finché la durata del blocco non viene modificata. Una volta rimosso il blocco o il criterio di conservazione (presumendo che la cassetta postale sia stata eliminata più di 30 giorni prima), la cassetta postale inattiva verrà contrassegnata per l'eliminazione definitiva e il suo contenuto non sarà conservato e non potrà essere trovato. In caso di un criterio di conservazione di Office 365 o di un blocco con scadenza, è necessario specificare la durata del blocco. La durata si applica ai singoli elementi e viene calcolata a partire dalla data in cui ciascun elemento è stato ricevuto o creato. Dopo che il blocco per un elemento della cassetta postale scade e che tale elemento viene spostato o si trova nella cartella Elementi ripristinabili nella cassetta postale inattiva, l'elemento viene definitivamente eliminato (cancellato) dalla cassetta postale inattiva dopo la scadenza del periodo di conservazione dell'elemento eliminato. 
  
### <a name="step-2-delete-the-mailbox"></a>Passaggio 2: Eliminare la cassetta postale

Dopo la cassetta postale viene messa in attesa o viene applicato un criterio di conservazione di Office 365, il passaggio successivo consiste nell'eliminare la cassetta postale. Il modo migliore per eliminare una cassetta postale consiste nell'eliminare l'account utente di Office 365 corrispondente nell'interfaccia di amministrazione di Office 365. Per informazioni sull'eliminazione di account utente di Office 365, vedere [eliminazione di un utente dall'organizzazione](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> È inoltre possibile eliminare la cassetta postale utilizzando il cmdlet **Remove-Mailbox** in PowerShell di Exchange Online. Per ulteriori informazioni, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Visualizzare un elenco delle cassette postali inattive


Per visualizzare un elenco delle cassette postali inattive all'interno dell'organizzazione:
  
1. Accedere a [https://protection.office.com/](https://protection.office.com/) e accedere utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365. 
    
2. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> * * conservazione * *.
    
3. Nella pagina **conservazione** fare clic su **altro**![puntini di sospensione barra di spostamento](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), quindi fare clic su **cassette postali inattive**.
    
    ![Nella pagina conservazione fare clic su altro e quindi fare clic su cassette postali inattive per visualizzare un elenco di cassette postali inattive](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Verrà visualizzata la pagina **delle cassette postali inattive** . Nota che viene visualizzato il numero totale di cassette postali inattive all'interno dell'organizzazione. 
    
    ![Viene visualizzato un elenco di tutte le cassette postali inattive all'interno dell'organizzazione](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
In alternativa, è possibile eseguire il seguente comando in Exchange Online PowerShell per visualizzare l'elenco delle cassette postali inattive.

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

È possibile fare clic su ![icona dei risultati di ricerca di esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **esportare** per visualizzare o scaricare un file CSV che contiene informazioni aggiuntive sulle cassette postali inattive all'interno dell'organizzazione. 
  
È inoltre possibile eseguire il comando seguente per esportare l'elenco delle cassette postali inattive e altre informazioni su un file CSV. In questo esempio viene creato il file CSV nella directory corrente.

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> È possibile che una cassetta postale inattiva può avere lo stesso indirizzo SMTP come una cassetta postale utente attivo. In questo caso, il valore della proprietà **ExchangeGuid** o **DistinguishedName** utilizzabile per identificare in modo univoco una cassetta postale inattiva. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Ricerca ed esportazione del contenuto di una cassetta postale inattiva

È possibile accedere il contenuto delle cassette postali inattive mediante lo strumento di ricerca del contenuto per la protezione &amp; centro conformità. Quando si esegue la ricerca di una cassetta postale inattiva, è possibile creare la query di ricerca per cercare gli elementi specifici oppure è possibile restituire l'intero contenuto della cassetta postale inattiva. È possibile visualizzare in anteprima i risultati della ricerca o esportare i risultati della ricerca in un file di dati di Outlook (PST) o come messaggi di posta elettronica singolo. Per le procedure dettagliate per la ricerca di cassette postali e l'esportazione dei risultati della ricerca, vedere gli argomenti seguenti:
  
- [Ricerca del contenuto in Office 365](content-search.md)
    
- [Esportare i risultati di ricerca del contenuto da Office 365 Security &amp; centro conformità](export-search-results.md)
    
Ecco alcuni aspetti da tenere presenti durante la ricerca delle cassette postali inattive.
  
- Se una ricerca di contenuto include una cassetta postale utente e cassetta postale viene quindi rese inattive, ricerca contenuto continua per la ricerca di cassette postali inattive quando si esegue nuovamente la ricerca dopo diventa inattivo.
    
- In alcuni casi, un utente può disporre di una cassetta postale attiva e una cassetta postale inattiva che hanno lo stesso indirizzo SMTP. In questo caso, verrà cercata solo la cassetta postale specifica che si seleziona un percorso per una ricerca di contenuto. In altre parole, se si aggiunge una ricerca cassetta postale dell'utente, non è possibile presupporre che verranno eseguita la ricerca cassette postali attive e inattive, solo la cassetta postale aggiunto in modo esplicito per la ricerca verrà eseguita la ricerca.
    
- È consigliabile evitare di dover delle cassette postali attivi e inattive cassette postali con lo stesso indirizzo SMTP. Se si desidera riutilizzare l'indirizzo SMTP attualmente assegnato a una cassetta postale inattiva, è consigliabile ripristinare la cassetta postale inattiva o ripristinare il contenuto di una cassetta postale inattiva a una cassetta postale attiva (o l'archivio di una cassetta postale attiva) e quindi eliminare il cassette postali inattive.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Modificare la durata del blocco per una cassetta postale inattiva

Dopo aver effettuata una cassetta postale inattiva, è possibile modificare la durata della conservazione o il criterio di conservazione di Office 365 applicate a cassette postali inattive. Per le procedure dettagliate, vedere [modificare la durata della conservazione per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Se un dipendente precedente restituisce all'organizzazione o un nuovo dipendente è stato assunto deve essere eseguita su professionali del dipendente chiusa, è possibile ripristinare il contenuto delle cassette postali inattive. Quando si ripristina una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, vengono mantenuti il contenuto e struttura di cartelle delle cassette postali inattive e la cassetta postale è collegata a un nuovo account utente. Dopo avere recuperato, cassette postali inattive non esiste più. Per ulteriori informazioni e procedure dettagliate avviene quando si ripristina una cassetta postale inattiva, vedere [ripristino di una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Ripristinare il contenuto di una cassetta postale inattiva in un'altra cassetta postale

Se l'altro impiegato assume la responsabilità di un dipendente precedente o un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva per una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. Cassette postali inattive viene mantenuta e manterrà una cassetta postale inattiva. Cassette postali inattive possono comunque essere ricerca quando si utilizza eDiscovery, è possibile ripristinare il contenuto a un'altra cassetta postale o può essere recuperato o eliminato in un secondo momento. Per le procedure dettagliate, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminare una cassetta postale inattiva

Se non più necessaria mantenere il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente la cassetta postale inattiva la rimozione dell'esenzione o rimuovendo il criterio di conservazione di Office 365 applicato a cassette postali inattive. Se la cassetta postale è stata eliminata più di 30 giorni, la cassetta postale verrà contrassegnata per l'eliminazione definitiva dopo si rimuove il blocco e la cassetta postale diventeranno non ripristinabile. Se è stata eliminata la cassetta postale negli ultimi 30 giorni, è comunque possibile ripristinare la cassetta postale dopo aver rimosso il criterio di conservazione o conservazione. Per le procedure dettagliate per la rimozione di un'esenzione o un criterio di conservazione di Office 365 per eliminare definitivamente una cassetta postale inattiva, vedere [eliminazione di una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).