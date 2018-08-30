---
title: Ripristinare una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: "Se un dipendente precedente restituisce all'organizzazione o un nuovo dipendente è stato assunto deve essere eseguita su professionali di un dipendente chiusa, è possibile ripristinare il contenuto delle cassette postali inattive in Office 365. Quando si ripristina una cassetta postale inattiva, viene convertita in una nuova cassetta postale che include il contenuto delle cassette postali inattive. "
ms.openlocfilehash: dcc84e44454a75f8b4dac953599632d632f340b9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531358"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>Ripristinare una cassetta postale inattiva in Office 365

Una cassetta postale inattiva (che è un tipo di cassetta postale eliminata temporaneamente) viene utilizzata per mantenere la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Se tale dipendente torna nell'organizzazione o se un altro dipendente assume le responsabilità del dipendente precedente, esistono due modi che consentono di rendere disponibile il contenuto della cassetta postale inattiva a un utente: 
  
- **Recuperare una cassetta postale inattiva** Se l'ex dipendente torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del precedente dipendente, è possibile recuperare i contenuti della cassetta postale inattiva. Questo metodo consente di convertire la cassetta postale inattiva in una nuova cassetta postale attiva con il contenuto della cassetta postale inattiva. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Le procedure descritte in questo argomento illustrano tale metodo. 
    
- **Ripristinare una cassetta postale inattiva** Se l'altro impiegato assume la responsabilità del dipendente precedente o un altro utente deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva per una cassetta postale esistente. È inoltre possibile ripristinare l'archivio di una cassetta postale inattiva. Per le procedure di questo metodo, vedere [ripristino di una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).
    
Vedere la sezione [Ulteriori informazioni](recover-an-inactive-mailbox.md#moreinfo) per maggiori dettagli sulle differenze tra recupero e ripristino di una cassetta postale inattiva, oltre a una descrizione di cosa accade quando viene recuperata una cassetta postale inattiva.
  
> [!NOTE]
> È stata posticipata la scadenza per la creazione di nuove archiviazioni sul posto per rendere inattiva una cassetta postale. Ma un certo punto in futuro, non sarà in grado di creare nuove archiviazioni sul posto di Exchange Online. A quel punto, solo i criteri di conservazione contiene controversie legali e Office 365 possono essere utilizzati per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti presenti In-Place Hold continueranno a essere supportate ed è possibile continuare a gestire In-Place Holds sulle cassette postali inattive. Sono incluse cambiare la durata di an In-Place Hold e in modo permanente l'eliminazione di una cassetta postale inattiva rimuovendo l'archiviazione sul posto. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario utilizzare Exchange Online PowerShell per ripristinare una cassetta postale inattiva. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).
    
- Eseguire il seguente comando per ottenere informazioni di identità per le cassette postali inattive dell'organizzazione. 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    Utilizzare le informazioni restituite da questo comando per recuperare una cassetta postale inattiva specifica.
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Utilizzare il cmdlet **New-Mailbox** con il parametro *InactiveMailbox* per recuperare una cassetta postale inattiva. 
  
1. Creare una variabile che contiene le proprietà della cassetta postale inattiva. 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > Nel comando precedente, usare il valore della proprietà **DistinguishedName** o **ExchangeGUID** per identificare la cassetta postale inattiva. Queste proprietà sono univoche per ogni cassetta postale nell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale inattiva possano avere lo stesso indirizzo SMTP primario. 
  
2. In questo esempio vengono utilizzate le proprietà ottenute nel comando precedente consente di recuperare le cassette postali inattive in una cassetta postale attiva per l'utente di Ann Beebe. Assicurarsi che i valori specificati per i parametri *Name* e *MicrosoftOnlineServicesID* siano univoci all'interno dell'organizzazione. 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    L'indirizzo SMTP primario della cassetta postale inattiva recuperata avranno lo stesso valore di quello specificato dal parametro *MicrosoftOnlineServicesID* . 
    
Dopo il recupero di una cassetta postale inattiva, viene creato anche un nuovo account utente di Office 365. È necessario attivare questo account utente assegnando una licenza. Per assegnare una licenza nell'interfaccia di amministrazione di Office 365, vedere [Assegnare licenze agli utenti in Office 365 per le aziende](https://go.microsoft.com/fwlink/p/?LinkId=276798).
  
## <a name="more-information"></a>Ulteriori informazioni

- **Qual è la differenza principale tra il recupero e il ripristino di una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, la cassetta postale viene sostanzialmente convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. Dopo il recupero, la cassetta postale inattiva non esiste più e le eventuali modifiche apportate al contenuto della nuova cassetta postale vengono applicate al contenuto originariamente conservato nella cassetta postale inattiva. Al contrario, quando si ripristina una cassetta postale inattiva, il contenuto viene semplicemente copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. Le eventuali modifiche apportate al contenuto nella cassetta postale di destinazione non vengono applicate al contenuto originale conservato nella cassetta postale inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery sul posto, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento. 
    
- **Cosa accade quando viene recuperata una cassetta postale inattiva?** Quando si recupera una cassetta postale inattiva, si verifica quanto segue: 
    
  - Il blocco per controversia legale (se era stato abilitato per la cassetta postale inattiva) viene rimosso.
    
  - I blocchi sul posto vengono rimossi. Ciò indica che la cassetta postale inattiva viene rimossa come cassetta postale di origine da qualsiasi ricerca dei blocchi sul posto o di eDiscovery sul posto. 
    
  - La cassetta postale inattiva viene rimossa da qualsiasi criterio di conservazione di Office 365 applicato a essa.
    
  - Il periodo di recupero di un singolo elemento (che è definito dalla proprietà della cassetta postale **RetainDeletedItemsFor** ) è impostato su 30 giorni. In genere, quando si crea una nuova cassetta postale in Exchange Online, il periodo di conservazione è impostato su 14 giorni. Impostandolo sul valore massimo di 30 giorni, si ha più tempo per recuperare i dati eliminati definitivamente (o cancellati) dalla cassetta postale inattiva. È anche possibile disabilitare il recupero di un singolo elemento o reimpostare il periodo di conservazione di un singolo elemento sul valore predefinito di 14 giorni. Per ulteriori informazioni, vedere [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).
    
  - Il blocco della conservazione è abilitato e la sua durata è impostata su 30 giorni. Ciò significa che i criteri di conservazione predefiniti di Exchange e i criteri di conservazione di Office 365 a livello di organizzazione o a livello di Exchange assegnati alla nuova cassetta postale non vengono elaborati per 30 giorni. In questo modo, il dipendente che ritorna nell'organizzazione o il nuovo proprietario della cassetta postale inattiva ha tutto il tempo di gestire i vecchi messaggi. In caso contrario, i criteri di conservazione di Exchange o di Office 365 potrebbero eliminare gli elementi della vecchia cassetta postale (o spostarli nella cassetta postale di archiviazione, se abilitata) che sono scaduti in base alle impostazioni configurate per i criteri di conservazione di Exchange o di Office 365. Dopo 30 giorni, il blocco della conservazione scade, la proprietà della cassetta postale **RetentionHoldEnabled** viene impostata su **False** e Assistente cartelle gestite avvia l'elaborazione dei criteri assegnati alla cassetta postale. Se non è necessario questo intervallo di tempo aggiuntivo, è possibile rimuovere il blocco della conservazione. In alternativa, è possibile aumentare la durata del blocco della conservazione utilizzando il comando **Set-Mailbox -EndDateForRetentionHold**. Per ulteriori informazioni, vedere [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).
    
- **Applicare un blocco alla cassetta postale recuperata se è necessario conservare lo stato originale della cassetta postale inattiva.** Per impedire che il proprietario o i criteri di conservazione della nuova cassetta postale eliminino definitivamente i messaggi dalla cassetta postale inattiva recuperata, è possibile applicare alla cassetta postale il blocco per controversia legale. Per ulteriori informazioni, vedere [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286).
    
- **Quali ID utente è possibile utilizzare durante il ripristino di una cassetta postale inattiva?** Quando si ripristina una cassetta postale inattiva, il valore specificato per il parametro *MicrosoftOnlineServicesID* può essere diverso da quello originale che è stato associato alla cassetta postale inattiva. È inoltre possibile utilizzare l'ID utente originale. Ma, come descritto in precedenza, verificare che i valori utilizzati per *il nome* e *MicrosoftOnlineServicesID* siano univoci all'interno dell'organizzazione quando si ripristina la cassetta postale inattiva. 
    
- **Cosa fare se il periodo di conservazione della cassetta postale inattiva è scaduto?** Se una cassetta postale inattiva è stata eliminata temporaneamente meno di 30 giorni prima, non è possibile utilizzare il comando **New-Mailbox -InactiveMailbox** per recuperarla. Per recuperarla, è necessario ripristinare l'account utente di Office 365 corrispondente. Per ulteriori informazioni, vedere [Eliminare o ripristinare un utente](https://go.microsoft.com/fwlink/p/?LinkId=279162).
    
- **Come si stabilisce se il periodo di conservazione di una cassetta postale inattiva eliminata temporaneamente è scaduto?** Eseguire il comando riportato di seguito. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    Se non è presente un valore per la proprietà **ExternalDirectoryObjectId**, il periodo di conservazione della cassetta postale è scaduto ed è possibile recuperare la cassetta postale inattiva eseguendo il comando **New-Mailbox -InactiveMailbox**. Se esiste un valore per la proprietà **ExternalDirectoryObjectId**, il periodo di conservazione della cassetta postale eliminata temporaneamente non è scaduto ed è necessario recuperare la cassetta postale ripristinando l'account utente di Office 365. Vedere [Eliminare o ripristinare un utente](https://go.microsoft.com/fwlink/p/?LinkId=279162)
    
- **Considerare l'abilitazione della cassetta postale di archiviazione dopo il ripristino di una cassetta postale inattiva.** In tal modo la restituzione di un utente o un nuovo dipendente vecchi messaggi spostare la cassetta postale di archiviazione. E quando scade l'attesa di conservazione, i criteri di archiviazione che fa parte del criterio di conservazione Exchange predefiniti assegnato a elementi che sono due anni vengono spostati cassette postali di Exchange Online o precedente la cassetta postale di archiviazione. Se non si attiva la cassetta postale di archiviazione, gli elementi aventi più di due anni rimarranno nella cassetta postale principale dell'utente. Per ulteriori informazioni, vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md).
 