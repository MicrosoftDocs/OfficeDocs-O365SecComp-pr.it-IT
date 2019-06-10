---
title: Creare e gestire le cassette postali inattive in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: È possibile creare una cassetta postale inattiva in Office 365 applicando un criterio di conservazione o un blocco di Office 365 alla cassetta postale, quindi eliminando l'account utente di Office 365 corrispondente. Gli elementi di una cassetta postale inattiva vengono conservati per la durata del blocco o del criterio di conservazione applicato prima che venisse reso inattivo. Per eliminare definitivamente una cassetta postale inattiva, è sufficiente rimuovere il blocco o il criterio di conservazione.
ms.openlocfilehash: e07b062f6b77f18589334b141e38edddc5ea18c5
ms.sourcegitcommit: f88f14999aeb70ecf265cd98eb09a3304b150be8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "34768951"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>Creare e gestire le cassette postali inattive in Office 365

Office 365 rende possibile conservare il contenuto delle cassette postali eliminate. Questa funzionalità è denominata [cassette postali inattive](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. Una cassetta postale diventa inattiva quando un blocco per controversia legale o un criterio di conservazione di Office 365 (creato nel centro sicurezza e conformità di Office 365 o Microsoft 365) viene applicato alla cassetta postale prima che venga eliminato l'account utente di Office 365 corrispondente. I contenuti di una cassetta postale inattiva vengono mantenuti per tutta la durata del blocco applicato alla cassetta postale prima che fosse resa inattiva. In questo modo gli amministratori, i responsabili della conformità e i manager dei record possono utilizzare la ricerca contenuto per cercare ed esportare il contenuto di una cassetta postale inattiva. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.
  
> [!NOTE]
> Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per rendere inattiva una cassetta postale, deve essere assegnata una licenza di Exchange Online piano 2, in modo che sia possibile applicare una conservazione per controversia legale o un criterio di ritenzione di Office 365 alla cassetta postale prima che venga eliminata. Le licenze di Exchange Online piano 2 fanno parte di un abbonamento a Office 365 Enterprise E3 ed E5. Se a una cassetta postale viene assegnata una licenza di Exchange Online piano 1 (che fa parte di un abbonamento a Office 365 Enterprise E1), è necessario assegnarle una licenza di archiviazione Exchange Online distinta in modo che sia possibile applicare un'esenzione alla cassetta postale prima che venga eliminata. Per ulteriori informazioni, vedere [Archiviazione Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).
    
- La licenza associata a una cassetta postale di Exchange Online eliminata sarà disponibile dopo aver eliminato l'account utente di Office 365 corrispondente. È quindi possibile [assegnare licenze agli utenti di Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) a un altro utente. 
    
- Se un blocco per controversia legale o un criterio di conservazione di Office 365 (configurato per mantenere o conservare e quindi eliminare il contenuto) non viene applicato a una cassetta postale prima che venga eliminato, il contenuto della cassetta postale non verrà mantenuto o individuabile. Tuttavia, è possibile recuperare la cassetta postale eliminata entro 30 giorni dall'eliminazione; se non viene recuperata entro 30 giorni, la cassetta postale e il suo contenuto vengono eliminati definitivamente.
    
- For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). Per ulteriori informazioni sui criteri di conservazione di Office 365, vedere [Panoramica dei criteri di conservazione in Office 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Creare una cassetta postale inattiva

La realizzazione di una cassetta postale inattiva comporta due passaggi: 1) l'inserimento della cassetta postale in blocco per controversia legale o l'applicazione di un criterio di conservazione di Office 365 a esso e 2) l'eliminazione della cassetta postale o dell'account utente di Office 365 corrispondente. Quando la cassetta postale è inattiva, il contenuto viene conservato finché non vengono rimossi i criteri di conservazione o il blocco.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>Passaggio 1: applicare il blocco per controversia legale a una cassetta postale o applicare un criterio di conservazione di Office 365

L'inserimento di una cassetta postale in un blocco per controversia legale o l'applicazione di un criterio di conservazione di Office 365 (configurato per conservare o conservare e quindi eliminare il contenuto) conserva il contenuto della cassetta postale prima che venga eliminato. Con entrambi i tipi di blocchi viene conservato tutto il contenuto della cassetta postale, compresi gli elementi eliminati e le versioni originali degli elementi modificati. Gli elementi eliminati e modificati vengono conservati nella cassetta postale inattiva per un determinato periodo oppure finché non viene eliminata definitivamente la cassetta postale inattiva rimuovendo il blocco o i criteri di conservazione applicati alla cassetta postale inattiva.
  
Se un blocco è già attivo in una cassetta postale o se un criterio di conservazione di Office 365 è già applicato a una cassetta postale, allora sarà semplicemente necessario eliminare l'account utente di Office 365 corrispondente come descritto nel passaggio 2.
  
Per le procedure dettagliate sull'applicazione del blocco per controversia legale per una cassetta postale o sull'applicazione di un criterio di conservazione di Office 365, vedere:
  
- [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Panoramica dei criteri di conservazione in Office 365](retention-policies.md)
    
> [!NOTE]
> Per i blocchi per controversia legale e i criteri di conservazione di Office 365, è possibile creare un blocco indefinito o un blocco con scadenza. In caso di un blocco indefinito, il contenuto della cassetta postale inattiva viene conservato per sempre, finché il blocco non viene rimosso o finché la durata del blocco non viene modificata. Una volta rimosso il blocco o il criterio di conservazione (presumendo che la cassetta postale sia stata eliminata più di 30 giorni prima), la cassetta postale inattiva verrà contrassegnata per l'eliminazione definitiva e il suo contenuto non sarà conservato e non potrà essere trovato. In caso di un criterio di conservazione di Office 365 o di un blocco con scadenza, è necessario specificare la durata del blocco. La durata si applica ai singoli elementi e viene calcolata a partire dalla data in cui ciascun elemento è stato ricevuto o creato. Dopo che il blocco per un elemento della cassetta postale scade e che tale elemento viene spostato o si trova nella cartella Elementi ripristinabili nella cassetta postale inattiva, l'elemento viene definitivamente eliminato (cancellato) dalla cassetta postale inattiva dopo la scadenza del periodo di conservazione dell'elemento eliminato. 
  
### <a name="step-2-delete-the-mailbox"></a>Passaggio 2: Eliminare la cassetta postale

Dopo aver applicato un blocco o un criterio di conservazione di Office 365 alla cassetta postale, il passaggio successivo consiste nell'eliminazione della cassetta postale. Il modo migliore per eliminare una cassetta postale consiste nell'eliminare l'account utente di Office 365 corrispondente nell'interfaccia di amministrazione di Microsoft 365. Per informazioni sull'eliminazione degli account utente di Office 365, vedere [eliminare un utente dall'organizzazione](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> È inoltre possibile eliminare la cassetta postale utilizzando il cmdlet **Remove-Mailbox** in PowerShell di Exchange Online. Per ulteriori informazioni, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Visualizzazione di un elenco di cassette postali inattive

Per visualizzare un elenco delle cassette postali inattive nell'organizzazione:
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Fare clic su > **conservazione**della **governance dei dati**.
    
3. Nella pagina **conservazione** fare clic su **altre**![ellissi](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)della barra di spostamento e quindi fare clic su **cassette postali inattive**.
    
    ![Nella pagina conservazione fare clic su altro e quindi su cassette postali inattive per visualizzare un elenco di cassette postali inattive](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Viene visualizzata la pagina delle **cassette postali inattive** . Nota viene visualizzato il numero totale di cassette postali inattive nell'organizzazione. 
    
    ![Viene visualizzato un elenco di tutte le cassette postali inattive nell'organizzazione.](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
In alternativa, è possibile eseguire il comando seguente in Exchange Online PowerShell per visualizzare l'elenco delle cassette postali inattive.

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

È possibile fare ![clic su Esporta esportazione](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **** delle icone dei risultati della ricerca per visualizzare o scaricare un file CSV che contiene informazioni aggiuntive sulle cassette postali inattive nell'organizzazione. 
  
È inoltre possibile eseguire il comando seguente per esportare l'elenco delle cassette postali inattive e altre informazioni in un file CSV. In questo esempio, il file CSV viene creato nella directory corrente.

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> È possibile che una cassetta postale inattiva possa avere lo stesso indirizzo SMTP di una cassetta postale utente attiva. In questo caso, è possibile utilizzare il **** valore della proprietà Distinguished o **ExchangeGuid** per identificare in modo univoco una cassetta postale inattiva. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Ricerca ed esportazione del contenuto di una cassetta postale inattiva

È possibile accedere al contenuto della cassetta postale inattiva utilizzando lo strumento di ricerca contenuto nel centro sicurezza & conformità. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Esportare i risultati della Ricerca contenuto](export-search-results.md)
    
Di seguito sono riportate alcune considerazioni da tenere presenti durante la ricerca di cassette postali inattive.
  
- Se una ricerca di contenuto include una cassetta postale utente e la cassetta postale viene resa inattiva, la ricerca di contenuto continuerà a eseguire una ricerca nella cassetta postale inattiva quando si rieseguirà la ricerca dopo che sarà inattiva.
    
- In alcuni casi, un utente può disporre di una cassetta postale attiva e di una cassetta postale inattiva con lo stesso indirizzo SMTP. In questo caso, verrà cercata solo la cassetta postale specifica selezionata come percorso per una ricerca di contenuto. In altre parole, se si aggiunge una cassetta postale di un utente a una ricerca, non è possibile presumere che vengano cercate entrambe le cassette postali attive e inattive. verrà cercata solo la cassetta postale che si aggiunge esplicitamente alla ricerca.
    
- È consigliabile evitare di disporre di una cassetta postale attiva e di una cassetta postale inattiva con lo stesso indirizzo SMTP. Se è necessario riutilizzare l'indirizzo SMTP attualmente assegnato a una cassetta postale inattiva, è consigliabile recuperare la cassetta postale inattiva o ripristinare il contenuto di una cassetta postale inattiva in una cassetta postale attiva (o l'archivio di una cassetta postale attiva), quindi eliminare il cassetta postale inattiva.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Modificare la durata del blocco per una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco o il criterio di conservazione di Office 365 applicato alla cassetta postale inattiva. Per le procedure dettagliate, vedere [modificare la durata del blocco per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Se l'ex dipendente torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del dipendente rimosso, è possibile recuperare i contenuti della cassetta postale inattiva. Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per le procedure dettagliate e ulteriori informazioni sui casi in cui si ripristina una cassetta postale inattiva, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Ripristinare il contenuto di una cassetta postale inattiva in un'altra cassetta postale

Se un altro dipendente assume le responsabilità di un ex dipendente o se un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento. Per le procedure dettagliate, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Eliminare una cassetta postale inattiva

Se non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminarla definitivamente rimuovendo il blocco o i criteri di conservazione di Office 365 a essa applicati. Se la cassetta postale è stata eliminata più di 30 giorni prima, verrà contrassegnata per l'eliminazione definitiva dopo la rimozione del blocco e non sarà più recuperabile. Se la cassetta postale è stata eliminata negli ultimi 30 giorni, è ancora possibile recuperarla dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate per la rimozione di un blocco o di un criterio di conservazione di Office 365 per eliminare definitivamente una cassetta postale inattiva, vedere [eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).