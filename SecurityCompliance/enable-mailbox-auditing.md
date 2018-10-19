---
title: Abilitare il controllo delle cassette postali in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: In Office 365, è possibile attivare registrazione di controllo della cassetta postale per la registrazione accessi effettuati dai proprietari delle cassette postali, i delegati e amministratori. Per impostazione predefinita, il controllo delle cassette postali in Office 365 non è attivato. Dopo aver abilitato la registrazione per una cassetta postale di controllo delle cassette postali, è possibile cercare il Registro di controllo di Office 365 per le attività eseguite sulla cassetta postale.
ms.openlocfilehash: 6d3de226e7c0e03be824b14e1b16fadaae3f040e
ms.sourcegitcommit: 8294182d4dd124f035a221de0b90159ef7eec4ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "25639665"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>Abilitare il controllo delle cassette postali in Office 365
  
In Office 365, è possibile attivare registrazione di controllo della cassetta postale per la registrazione accessi effettuati dai proprietari delle cassette postali, i delegati e amministratori. Per impostazione predefinita, il controllo delle cassette postali in Office 365 non è attivato. Pertanto, gli eventi di controllo non viene visualizzato nei risultati quando si esegue una ricerca nel Registro di controllo di Office 365 per l'attività delle cassette postali. Ma dopo l'attivazione della cassetta postale registrazione di controllo per una cassetta postale utente, è possibile cercare il Registro di controllo per l'attività delle cassette postali. Inoltre, quando il controllo delle cassette postali la registrazione è attivata, alcune azioni eseguite dagli amministratori, delegati, e vengono registrati i proprietari per impostazione predefinita. Per eseguire l'accesso (e quindi cercare) azioni aggiuntive, vedere il passaggio 3.

## <a name="before-you-begin"></a>Prima di iniziare
  
- È necessario utilizzare Exchange Online PowerShell per abilitare la registrazione di controllo. Non è possibile utilizzare la protezione di Office 365 &amp; centro conformità o l'interfaccia di amministrazione di Exchange.
    
- Non è possibile abilitare la registrazione per la cassetta postale associata a un gruppo di Office 365 o un team di Microsoft Teams di controllo delle cassette postali.
    
- Un amministratore al quale sono state assegnate autorizzazioni accesso completo per la cassetta postale di un utente viene considerato un utente delegato.
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>Passaggio 1: Connessione a Exchange Online PowerShell

1. Nel computer locale, aprire Windows PowerShell ed eseguire il comando riportato di seguito.
   
    ```
    $UserCredential = Get-Credential
    ```

2. Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e la password per l'account dell'amministratore globale Office 365 e fare clic su **OK**.
    
3. Eseguire il comando riportato di seguito:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Eseguire il comando riportato di seguito.

    ```
    Import-PSSession $Session
    ```
   
4. Per verificare di essere connessi alla propria organizzazione Exchange Online, eseguire il seguente comando per visualizzare un elenco di tutte le cassette postali dell'organizzazione:
    
    ```
    Get-Mailbox
    ```
  
Per ulteriori informazioni o se si riscontrano problemi di connessione per l'organizzazione Exchange Online, vedere [Connessione a Exchange Online tramite remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
## <a name="step-2-enable-mailbox-audit-logging"></a>Passaggio 2: Abilitare la registrazione di controllo della cassetta postale

Dopo essersi connessi all'organizzazione Exchange Online, utilizzare PowerShell per abilitare la registrazione per una cassetta postale di controllo delle cassette postali. In alternativa, è possibile abilitare il controllo delle cassette postali per tutte le cassette postali nell'organizzazione.
  
Questo esempio viene attivata la registrazione per la cassetta postale Pilar Pinilla di controllo delle cassette postali.
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

In questo esempio viene illustrato come abilitare la registrazione di controllo della cassetta postale per tutte le cassette postali nell'organizzazione.
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>Passaggio 3: Specificare le azioni da sottoporre a controllo

Quando si abilita il controllo di una cassetta postale, alcune azioni eseguite dal proprietario della cassetta postale vengono controllate per impostazione predefinita. È necessario specificare altre azioni proprietario da controllare. Vedere la tabella nella sezione [azioni di controllo della cassetta postale](#mailbox-auditing-actions) per un elenco e una descrizione delle azioni di proprietario connessi per impostazione predefinita e le altre azioni che possono essere controllate. 
  
In questo esempio aggiunge le azioni di proprietario **MailboxLogin** e **HardDelete** alla cassetta postale di controllo per la cassetta postale Pilar Pinilla. In questo esempio si presuppone che il controllo delle cassette postali è già stato abilitato per la cassetta postale. 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

In questo esempio viene abilitato per la cassetta postale di Don Hall la registrazione di controllo delle cassette postali e viene specificato che verrà registrato solo l'azione **MailboxLogin** eseguita dal proprietario della cassetta postale. Si noti che in questo esempio sovrascrive l'azione UpdateFolderPermissions predefinita. 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
In questo esempio aggiunge le azioni di proprietario **SoftDelete** , **HardDelete**e **MailboxLogin**a tutte le cassette postali nell'organizzazione. In questo esempio si presuppone che il controllo delle cassette postali è già stato abilitato per tutte le cassette postali. 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la registrazione di controllo di una cassetta postale sia attiva, utilizzare il cmdlet **Get-Mailbox** per recuperare le impostazioni di controllo per la cassetta postale. 
  
In questo esempio viene illustrato come recuperate le impostazioni di controllo per Pilar Pinilla.

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
In questo esempio viene illustrato come recuperate le impostazioni di controllo per tutte le cassette postali utente nell'organizzazione.

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
Il valore **True** per la proprietà **AuditEnabled** consente di verificare il controllo delle cassette postali è abilitata la registrazione. 
    
## <a name="mailbox-auditing-actions"></a>Azioni di controllo della cassetta postale
  
Nella tabella seguente vengono riportate le azioni che possono essere registrate dalla cassetta postale di registrazione di controllo. La tabella include l'azione che può essere registrato per il tipo di accesso utente diverso. Nella tabella, **No** indica che non è possibile registrare un'azione per quel tipo di accesso. Un asterisco ( **\*** ) indica che l'azione viene registrata per impostazione predefinita durante la registrazione di controllo della cassetta postale è abilitata per la cassetta postale. 
  
|**Azione**|**Descrizione**|**Amministratore**|**Delegato\*\*\***|**Owner**|
|:-----|:-----|:-----|:-----|:-----|
|**Copia** <br/> |Messaggio copiato in un'altra cartella.  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|**Create** <br/> |Viene creato un elemento nella cartella Calendario, contatti, note o attività nella cassetta postale; ad esempio, viene creata una nuova convocazione riunione. Si noti che non è possibile controllare la creazione, inviare né ricevere un messaggio. Inoltre, non è controllata la creazione di una cartella delle cassette postali.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**FolderBind** <br/> |Accesso effettuato a una cartella della cassetta postale. Tale azione viene registrata anche quando l'amministratore o un delegato apre la cassetta postale.  <br/> |Sì  <br/> |Sì\*\*  <br/> |No  <br/> |
|**HardDelete** <br/> |Messaggio eliminato dalla cartella Elementi ripristinabili.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**MailboxLogin** <br/> |Accesso effettuato dall'utente alla propria cassetta postale.  <br/> |No  <br/> |No  <br/> |Sì  <br/> |
|**MessageBind** <br/> |Messaggio visualizzato nel riquadro di anteprima o aperto.  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|**Move** <br/> |Messaggio spostato in un'altra cartella.  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|**MoveToDeletedItems** <br/> |Messaggio eliminato e spostato nella cartella Posta eliminata.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**SendAs** <br/> |Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.  <br/> |Sì\*  <br/> |Sì\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.  <br/> |Sì\*  <br/> |Sì\*  <br/> |No  <br/> |
|**SoftDelete** <br/> |Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**Aggiorna** <br/> |Modifiche apportate a un messaggio o alle relative proprietà.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**UpdateCalendarDelegation** <br/> |Una delega per il calendario è stata assegnata a una cassetta postale. Delega per il calendario permette di utilizzare un utente nelle stesse autorizzazioni dell'organizzazione per gestire il calendario del proprietario della cassetta postale.  <br/> |Sì\*  <br/> |No  <br/> |Sì\*  <br/> |
|**UpdateFolderPermissions** <br/> |È stata modificata un'autorizzazione di cartella. Controllo delle autorizzazioni delle cartelle che gli utenti dell'organizzazione possono accedere alle cartelle in una cassetta postale e i messaggi posizionati in tali cartelle.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**UpdateInboxRules** <br/> |È stato aggiunta, rimossa o modifica una regola di posta in arrivo. Regole posta in arrivo vengono utilizzate per elaborare i messaggi di posta in arrivo dell'utente in base alle condizioni specificate ed eseguire azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o eliminazione di un messaggio.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Per impostazione predefinita controllati se è abilitato il controllo di una cassetta postale.<br/><br/>  <sup>\*\*</sup>Consolidate voci per le azioni di binding cartella eseguite dai delegati. Una voce di registro viene generata per l'accesso alle cartelle singole durante un periodo di 24 ore.<br/><br/><sup>\*\*\*</sup>Un amministratore è stata assegnata l'autorizzazione accesso completo alla cassetta postale dell'utente viene considerato un utente delegato. 
  
Se non è più necessario determinati tipi di azioni della cassetta postale da controllare, è necessario modificare di configurazione della registrazione di controllo della cassetta postale per disabilitare le azioni. Voci di registro esistenti non vengono eliminate fino a raggiungere la validità della conservazione per le voci del Registro di controllo. Per ulteriori informazioni sul periodo di conservazione per le voci del Registro di controllo, vedere la sezione "informazioni preliminari" in [ricerca il controllo di accesso nel centro conformità protezione di Office 365](search-the-audit-log-in-security-and-compliance.md#before-you-begin).
  
## <a name="more-infotab"></a>[Altre info](#tab/)
  
- Utilizzare il Registro di controllo di Office 365 per la ricerca per l'attività delle cassette postali che sono stati registrati. È possibile cercare attività per una cassetta postale utente specifico. La schermata seguente mostra un elenco di attività di cassette postali che è possibile cercare nel Registro di controllo di Office 365. Notare che queste attività sono le stesse operazioni descritte nella sezione "Operazioni il controllo delle cassette postali" in questo argomento.
    
    ![È possibile cercare il Registro di controllo di Office 365 per le azioni di controllo delle cassette postali selezionando "Attività della cassetta postale di Exchange" nell'elenco a discesa delle attività](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    Nella tabella seguente viene descritto ogni delle cassette postali attività è possibile cercare e viene corrispondente cassetta postale controllo azione.
    
    |**Attività nel Registro di controllo**|**Azione di controllo delle cassette postali**|
    |:-----|:-----|
    |Elemento della cassetta postale creata  <br/> |Creazione  <br/> |
    |Messaggi copiati in un'altra cartella  <br/> |Copia  <br/> |
    |Effettuato l'accesso alla cassetta postale utente  <br/> |MailboxLogin  <br/> |
    |Utilizzo di autorizzazioni Invia per conto di messaggio è stato inviato  <br/> |SendOnBehalf  <br/> |
    |Messaggi eliminati dalla cassetta postale  <br/> |HardDelete  <br/> |
    |Spostare i messaggi nella cartella Posta eliminata  <br/> |MoveToDeletedItems  <br/> |
    |Spostare i messaggi in un'altra cartella  <br/> |Move  <br/> |
    |Utilizzo di autorizzazioni Invia come messaggio è stato inviato  <br/> |SendAs  <br/> |
    |Messaggio aggiornato  <br/> |Aggiorna  <br/> |
    |Messaggi eliminati dalla cartella Posta eliminata  <br/> |SoftDelete  <br/> |
    |Sono state aggiunte le autorizzazioni per cartella  <br/> |UpdateFolderPermissions  <br/> |
    |Modifica delle autorizzazioni della cartella  <br/> |UpdateFolderPermissions  <br/> |
    |Autorizzazioni rimosse dalla cartella  <br/> |UpdateFolderPermissions  <br/> |
    |Sono state aggiunta o rimossa utente con l'accesso delegato alla cartella Calendario  <br/> |UpdateCalendarDelegation  <br/> |
   
    Si noti che le attività **sono state aggiunte delegare autorizzazioni di cassette postali** e **sono stati rimossi delegare autorizzazioni di cassetta postale** mostrate nella figura precedente non sono correlate alla cassetta postale il controllo delle azioni. Indica se un amministratore assegnato o rimossa l'autorizzazione delle cassette postali FullAccess. 
    
    Per informazioni sul Registro di controllo di Office 365, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).
    
- Si presume che alla cassetta postale acceda un amministratore esclusivamente nei seguenti scenari:
    
  - EDiscovery in locale in Exchange Online o ricerca contenuto in Office 365 viene utilizzato per cercare una cassetta postale.
    
  - L'[editor MAPI di Microsoft Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=204086) viene utilizzato per accedere alla cassetta postale. 
    
- Quando si abilita la registrazione di controllo delle cassette postali, è possibile specificare anche quali azioni (ad esempio, accesso oppure spostamento o eliminazione di un messaggio) verranno registrate per ciascun tipo di utente (amministratore, delegato o proprietario). 
    
- Per disattivare la registrazione di controllo delle cassette postali, eseguire il seguente comando:

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- Le azioni che vengono controllate per ogni tipo di utente non vengono visualizzate quando si esegue il cmdlet **Get-Mailbox** . Ma è possibile eseguire i seguenti comandi per visualizzare tutte le azioni controllate per un tipo di accesso utente specifico. 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- È inoltre possibile esportare una registrazione di controllo delle cassette postali e specificare le voci da includere per uno o più utenti. Ogni voce del Registro di controllo e il report include informazioni sull'utente che ha eseguito l'azione e quando l'azione eseguita e se l'operazione ha avuto esito positivo. Per ulteriori informazioni, vedere [esportare registri di controllo delle cassette postali](https://go.microsoft.com/fwlink/p/?LinkID=404104).
