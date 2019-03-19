---
title: Gestire il controllo delle cassette postali
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: La registrazione di controllo delle cassette postali è attivata per impostazione predefinita in Microsoft 365 (denominato anche controllo delle cassette postali predefinito o controllo delle cassette postali per impostazione predefinita). Ciò significa che alcune azioni eseguite da proprietari, delegati e amministratori delle cassette postali vengono automaticamente registrate in un registro di controllo delle cassette postali, in cui è possibile cercare le attività eseguite sulla cassetta postale.
ms.openlocfilehash: 604b7fc26c2e97a5efce28fe844fbd066196c4ce
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670631"
---
# <a name="manage-mailbox-auditing"></a>Gestire il controllo delle cassette postali
  
A partire da gennaio 2019, Microsoft sta attivando la registrazione di controllo delle cassette postali per impostazione predefinita per tutte le organizzazioni di Microsoft 365. Ciò significa che alcune azioni eseguite dai proprietari, dai delegati e dagli amministratori delle cassette postali vengono registrate automaticamente e i record di controllo della cassetta postale corrispondente saranno disponibili quando si effettua la ricerca nel registro di controllo della cassetta postale. Prima che il controllo delle cassette postali fosse attivato per impostazione predefinita, è necessario abilitarlo manualmente per ogni cassetta postale dell'utente nell'organizzazione. 

Di seguito sono illustrati alcuni vantaggi del controllo delle cassette postali per impostazione predefinita:

- Il controllo verrà abilitato per impostazione predefinita quando si crea una nuova cassetta postale. Non è necessario abilitarlo manualmente per i nuovi utenti. 

- Non è necessario gestire le azioni delle cassette postali controllate. Per impostazione predefinita, per ogni tipo di accesso viene controllata una serie di azioni delle cassette postali definite. Questi [tipi di accesso](#mailbox-actions-logged-by-default) sono Owner, Delegate e admin.

- Le nuove azioni delle cassette postali rilasciate da Microsoft verranno controllate per impostazione predefinita. Quando Microsoft rilascia una nuova azione della cassetta postale (in particolare quelle che consentono di proteggere l'organizzazione e la guida con indagini forensi), viene automaticamente aggiunta all'elenco delle azioni delle cassette postali controllate per impostazione predefinita. Ciò significa che non è necessario aggiungere nuove azioni all'elenco delle azioni delle cassette postali eseguite da proprietari, delegati o amministratori. 

- Assicurarsi di controllare le stesse azioni per tutte le cassette postali, in modo da disporre di un criterio di controllo della cassetta postale coerente nell'organizzazione.

> [!TIP]
> La cosa importante da ricordare è che con il rilascio del controllo delle cassette postali per impostazione predefinita, non è necessario eseguire alcuna operazione per la gestione del controllo delle cassette postali. Tuttavia, per ulteriori informazioni, modificare il comportamento dalle impostazioni predefinite o disattivarlo completamente, questo articolo può essere di aiuto.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Verificare che il controllo delle cassette postali per impostazione predefinita sia attivato

Per verificare che il controllo delle cassette postali per impostazione predefinita sia attivato per l'organizzazione, eseguire il comando seguente in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```
Get-OrganizationConfig | FL AuditDisabled
``` 

Il valore **false** indica che il controllo delle cassette postali è abilitato per impostazione predefinita per l'organizzazione. 

Quando il controllo delle cassette postali è attivato per impostazione predefinita (quando la proprietà *AuditDisabled* è impostata su **false**), l'impostazione dell'organizzazione ignorerà le impostazioni di controllo delle cassette postali per una cassetta postale specifica. Ad esempio, se la proprietà *AuditEnabled consente* di una cassetta postale è impostata su **false**, ma il controllo delle cassette postali per impostazione predefinita è abilitato per l'organizzazione, le azioni predefinite della cassetta postale verranno controllate per tale cassetta postale. Se il controllo delle cassette postali è stato disabilitato in modo esplicito per una cassetta postale specifica e si desidera disabilitarlo, è possibile configurare il bypass per il controllo delle cassette postali per il proprietario della cassetta postale e per gli altri utenti a cui è stato delegato l'accesso alla cassetta postale. Per ulteriori informazioni, vedere la sezione [ignorare la registrazione di controllo delle cassette postali](#bypass-mailbox-audit-logging) in questo articolo.

> [!NOTE]
> Quando il controllo delle cassette postali è attivato per impostazione predefinita, la proprietà *AuditEnabled consente* di una cassetta postale non viene modificata in **true** se è stata attualmente impostata su **false**. In altre parole, il controllo delle cassette postali per impostazione predefinita ignora la proprietà *AuditEnabled consente* per una cassetta postale.

## <a name="supported-mailbox-types"></a>Tipi di cassette postali supportate

Nella tabella seguente vengono illustrati i tipi di cassette postali attualmente supportati dal controllo delle cassette postali per impostazione predefinita:

|Tipo di cassetta postale|Supportato|Non supportato|
|:---------|:---------:|:---------:|
|Cassette postali utente    |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         |
|Cassette postali condivise    |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |       |
|Cassette postali di gruppo di Office 365    |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)         |         |
|Cassette postali per la risorsa    |      |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |
|Cassette postali delle cartelle pubbliche    |       |![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)  |
||||

## <a name="mailbox-actions-logged-by-default"></a>Azioni delle cassette postali registrate per impostazione predefinita

Per impostazione predefinita, per ogni tipo di accesso viene registrata una serie di azioni della cassetta postale:  

   - **Owner** : il proprietario della cassetta postale. 
   
   - **Delegate** : un altro utente a cui è stata assegnata l'autorizzazione Senda, SendOnBehalf o FullAccess per la cassetta postale di una persona. Si noti che un amministratore a cui è stata assegnata l'autorizzazione FullAccess per la cassetta postale di un utente viene considerato anche un utente delegato.
   
    - **Admin** -le cassette postali sono considerate accessibili da un tipo di accesso di amministratore solo negli scenari seguenti:
    
       - Quando una cassetta postale viene cercata con uno dei seguenti strumenti di Microsoft eDiscovery: 

         - Ricerca contenuto nel centro conformità.
       
         -  eDiscovery o Advanced eDiscovery nel centro conformità.
       
         - EDiscovery sul posto in Exchange Online.
       - Quando si utilizza l' [Editor MAPI di Microsoft Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=204086) per accedere alla cassetta postale.     

Nella tabella seguente sono riportate le azioni delle cassette postali attualmente registrate per impostazione predefinita per ogni tipo di accesso.

|Azioni amministrative|Azioni deLegate|Azioni del proprietario|
|:---------|:---------|:---------|
|Creazione    |Creazione       | HardDelete        |
|HardDelete    |HardDelete        |MoveToDeletedItems       |
|MoveToDeletedItems    |MoveToDeletedItems         |SoftDelete         |
|SendAs    |SendAs      |    Aggiorna     |
|SendOnBehalf    |SendOnBehalf       |UpdateCalendarDelegation        |
|SoftDelete     |SoftDelete      | UpdateFolderPermissions        |
|Aggiorna    |Aggiorna       |UpdateInboxRules         |
|UpdateCalendarDelegation    | UpdateFolderPermissions        |         |
|UpdateFolderPermissions     | UpdateInboxRules        |         |
|UpdateInboxRules     |         |         |
||||

Di seguito sono riportate le descrizioni per queste azioni. 

|Azione della cassetta postale|Descrizione|
|:---------|:---------|
|**Creazione** <br/> |Un elemento è stato creato nella cartella calendario, contatti, note o attività nella cassetta postale. ad esempio, viene creata una nuova convocazione di riunione. Si noti che la creazione, l'invio o la ricezione di un messaggio non viene controllato. Inoltre, la creazione di una cartella delle cassette postali non viene controllata.  <br/> |
|**HardDelete** <br/> |Messaggio eliminato dalla cartella Elementi ripristinabili.  <br/> |
|**MoveToDeletedItems** <br/> |Messaggio eliminato e spostato nella cartella Posta eliminata.  <br/> |
|**SendAs** <br/> |Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.  <br/> |
|**SendOnBehalf** <br/> |Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.  <br/> |
|**SoftDelete** <br/> |Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.  <br/> |
|**Aggiorna** <br/> |Modifiche apportate a un messaggio o alle relative proprietà.  <br/> |
|**UpdateCalendarDelegation** <br/> |Una delega del calendario è stata assegnata a una cassetta postale. La delega del calendario fornisce a un altro utente nella stessa organizzazione le autorizzazioni per la gestione del calendario del proprietario della cassetta postale.  <br/> |
|**UpdateFolderPermissions** <br/> |È stata modificata un'autorizzazione per la cartella. Autorizzazioni per le cartelle controllare quali utenti dell'organizzazione possono accedere alle cartelle in una cassetta postale e i messaggi che si trovano in tali cartelle.  <br/> |
|**UpdateInboxRules** <br/> |È stata aggiunta, rimossa o modificata una regola di posta in arrivo. Le regole di posta in arrivo vengono utilizzate per elaborare i messaggi nella posta in arrivo dell'utente in base alle condizioni specificate e intraprendere azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o l'eliminazione di un messaggio.  <br/> |
|||

Per un elenco completo delle azioni delle cassette postali, incluse le azioni che sono disponibili ma che non sono incluse nel set di azioni predefinite, vedere la sezione [azioni di controllo delle cassette postali](#mailbox-auditing-actions) in questo articolo.

> [!IMPORTANT]
> Se le azioni delle cassette postali sono state configurate in modo esplicito per il controllo di qualsiasi tipo di accesso prima che il controllo della cassetta postale sia attivato per impostazione predefinita per l'organizzazione, la configurazione esistente della cassetta postale avrà la precedenza e non verrà sovrascritta dalla cassetta postale predefinita. azioni descritte in questa sezione. Se in qualsiasi momento si desidera ripristinare le azioni delle cassette postali predefinite, è possibile eseguire il comando **Set-Mailbox-DefaultAuditSet** . Per ulteriori informazioni su questa operazione, vedere la sezione [ripristinare le azioni delle cassette postali predefinite](#restore-the-default-mailbox-actions) in questo articolo.

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Verificare che le azioni delle cassette postali predefinite vengano registrate per ogni tipo di accesso

Con la versione di controllo delle cassette postali attiva per impostazione predefinita, è stata aggiunta una nuova proprietà della cassetta postale denominata *DefaultAuditSet* . Questa proprietà indica se le azioni delle cassette postali predefinite (gestite da Microsoft) vengono controllate per ogni tipo di accesso per una cassetta postale specificata. Per visualizzare i valori di questa proprietà, è possibile eseguire il comando seguente:

```
Get-Mailbox <username> | FL DefaultAuditSet
```

Il valore `Admin, Delegate, Owner` indica che vengono controllate le azioni predefinite delle cassette postali per tutti e tre i tipi di accesso e che un amministratore dell'organizzazione *non ha* modificato le azioni per qualsiasi tipo di accesso. Nota Questo è lo stato predefinito dopo che il controllo delle cassette postali per impostazione predefinita viene inizialmente attivato all'interno dell'organizzazione. 

Se un amministratore dell'organizzazione ha modificato le azioni della cassetta postale controllate per un tipo di accesso (utilizzando il cmdlet **Set-Mailbox** con i parametri *AuditAdmin*, *AuditDelegate*o *AuditOwner* ), il valore di la proprietà *DefaultAuditSet* sarà diversa dal valore predefinito. Ad esempio, un valore `Owner` indica che vengono controllate solo le azioni delle cassette postali predefinite per il proprietario della cassetta postale e che le azioni per `Delegate` e `Admin` sono state modificate. Se non sono visualizzati valori per la proprietà *DefaultAuditSet* (denominato anche valore *null* ), le azioni delle cassette postali per tutti e tre i tipi di accesso sono state modificate.

Per ulteriori informazioni sulla modifica delle azioni delle cassette postali di cui è stato eseguito il controllo, vedere la sezione [modifica o Ripristina azioni delle cassette postali registrate per impostazione predefinita](#change-or-restore-mailbox-actions-logged-by-default) in questo articolo.

### <a name="display-a-list-of-mailbox-actions-logged-by-default"></a>Visualizzazione di un elenco delle azioni delle cassette postali registrate per impostazione predefinita

È possibile eseguire i comandi seguenti in PowerShell di Exchange Online per visualizzare l'elenco delle azioni delle cassette postali che sono attualmente in corso per una cassetta postale per ogni tipo di accesso:

**Azioni del proprietario**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditOwner
```

**Azioni deLegate**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditDelegate
```

**Azioni amministrative**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Modificare o ripristinare le azioni delle cassette postali registrate per impostazione predefinita

Come spiegato in precedenza, uno dei vantaggi principali del controllo delle cassette postali per impostazione predefinita è che non è necessario gestire le azioni delle cassette postali controllate. Microsoft esegue questa operazione per l'utente e aggiungerà automaticamente nuove azioni delle cassette postali da controllare per impostazione predefinita quando vengono rilasciate. Tuttavia, l'organizzazione può avere motivi per controllare un insieme di azioni delle cassette postali diverse da quelle predefinite. In questa sezione viene illustrato come modificare le azioni delle cassette postali controllate per ogni tipo di accesso e come ripristinare le azioni predefinite gestite da Microsoft.

> [!IMPORTANT]
> Se si apportano modifiche alle azioni delle cassette postali per un utente che viene registrato per impostazione predefinita (come descritto nella sezione successiva), tutte le nuove azioni della cassetta postale rilasciate da Microsoft non verranno controllate per tali cassette postali. Sarà necessario aggiungere in modo esplicito una nuova azione della cassetta postale all'elenco delle azioni controllate per un tipo di accesso.

### <a name="change-the-mailbox-actions-to-audit"></a>Modificare le azioni delle cassette postali da controllare

È possibile utilizzare il cmdlet **Set-Mailbox** con i parametri *AuditAdmin*, *AuditDelegate*o *AuditOwner* per modificare le azioni della cassetta postale sottoposte a controllo, a seconda del tipo di accesso. Poiché questi parametri relativi al controllo sono parametri multivalore, ovvero possono avere più di un valore, esistono due modi diversi per modificarli.

- È possibile specificare più azioni delle cassette postali che sovrascrivono le azioni esistenti utilizzando la `action1,action2,...actionN`sintassi seguente:.

- È possibile aggiungere o rimuovere una o più azioni della cassetta postale senza influire sui record esistenti utilizzando la sintassi seguente `@{Add="action1","value2"}` : `@{Remove="action1","action2"}`oppure.

Indipendentemente dal metodo utilizzato per modificare le azioni delle cassette postali di cui è stato eseguito il controllo, le azioni delle cassette postali controllate per impostazione predefinita (per il tipo di accesso modificato) non verranno più gestite da Microsoft. Inoltre, il valore del tipo di accesso modificato non verrà visualizzato nel parametro della cassetta postale di *DefaultAuditSet* descritto in [precedenza](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

Di seguito sono riportati alcuni esempi di utilizzo di uno di questi metodi per modificare le azioni delle cassette postali da controllare per ognuno dei diversi tipi di accesso. 

In questo esempio vengono modificate le azioni delle cassette postali di amministrazione sovrascrivendo le azioni predefinite con SoftDelete e HardDelete. 

```
Set-Mailbox <username> -AuditAdmin HardDelete,SoftDelete
```

In questo esempio viene aggiunta l'azione proprietaria di MailboxLogin. 

```
Set-Mailbox <username> -AuditOwner @{Add="MailboxLogin"}
```

In questo esempio viene rimossa l'azione delegata MoveToDeletedItems.

```
Set-Mailbox <username> -AuditDelegate @{Remove="MoveToDeletedItems"}
```

#### <a name="checking-the-defaultauditset-property"></a>Verifica della proprietà DefaultAuditSet

Dopo aver modificato le azioni delle cassette postali predefinite per un tipo di accesso, la proprietà *DefaultAuditSet* della cassetta postale verrà aggiornata automaticamente in modo da riflettere questa modifica. Ad esempio, se si esegue `Get-Mailbox <username> | FL DefaultAuditSet` dopo la prima aggiunta o rimozione di un'azione del proprietario della cassetta postale, il comando restituirà solo un `Admin, Delegate`valore di. Ciò indica che le azioni predefinite delle cassette postali per il proprietario sono state modificate e questo significa che tutte le nuove azioni del proprietario della cassetta postale rilasciate da Microsoft non verranno aggiunte automaticamente alla cassetta postale. Lo stesso vale per la modifica delle azioni delle cassette postali per l'amministratore o il tipo di accesso delegato.

### <a name="restore-the-default-mailbox-actions"></a>Ripristinare le azioni predefinite delle cassette postali

Se sono state apportate modifiche alle azioni delle cassette postali controllate per un tipo di accesso, è possibile ripristinare le azioni delle cassette postali predefinite controllate `Set-Mailbox -DefaultAuditSet` eseguendo il comando. Quando si esegue questa operazione, si verificheranno le seguenti operazioni:

- L'elenco corrente delle azioni delle cassette postali verrà sostituito con le azioni predefinite delle cassette postali per il tipo di accesso appropriato.
 
- Tutte le nuove azioni delle cassette postali rilasciate da Microsoft verranno aggiunte automaticamente all'elenco per il tipo di accesso appropriato.

- La [proprietà della cassetta postale di DefaultAuditSet](#checking-the-defaultauditset-property) verrà aggiornata per includere il tipo di accesso appropriato.

Per ripristinare le azioni delle cassette postali predefinite per tutti i tipi di accesso, eseguire il seguente comando:

```
Set-Mailbox <username> -DefaultAuditSet Admin,Delegate,Owner
```

È possibile utilizzare questo comando per ripristinare le azioni predefinite delle cassette postali per uno qualsiasi dei tipi di accesso (utilizzando i valori **admin**, **delegate**o **owner** per il parametro *DefaultAuditSet* ).

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Disattivare il controllo delle cassette postali per impostazione predefinita per l'organizzazione

Se per qualche motivo l'organizzazione decide di non voler controllare le azioni delle cassette postali, è possibile disattivare il controllo delle cassette postali per impostazione predefinita per l'intera organizzazione eseguendo il comando seguente in PowerShell di Exchange Online:

```
Set-OrganizationConfig -AuditDisabled $true
```

Quando il controllo delle cassette postali per impostazione predefinita è disattivato (la proprietà *AuditDisabled* è impostata su **true**) per l'organizzazione, si verificheranno le seguenti operazioni:

- Il controllo delle cassette postali è disabilitato per l'organizzazione.

- Nessuna azione della cassetta postale verrà controllata (a partire dal momento in cui il controllo è disabilitato per l'organizzazione), anche se la proprietà *AuditEnabled consente* di una cassetta postale è impostata su **true**.

- Il controllo delle cassette postali non verrà abilitato per le nuove cassette postali e l'impostazione della proprietà *AuditEnabled consente* su una nuova cassetta postale (o esistente) su **true** verrà ignorata.

- Tutte le impostazioni di associazione di controllo delle cassette postali di bypass (configurate utilizzando il cmdlet **Set-MailboxAuditBypassAssociation** ) verranno ignorate.

- I record di controllo delle cassette postali esistenti devono essere conservati fino alla scadenza del periodo di validità del registro di controllo.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Attivazione del controllo delle cassette postali per impostazione predefinita

Per riattivare il controllo della cassetta postale per l'organizzazione, è sufficiente eseguire il seguente comando in PowerShell di Exchange Online:

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Ignorare la registrazione di controllo delle cassette postali

Attualmente, non è possibile disabilitare il controllo della cassetta postale per cassette postali specifiche quando l'esecuzione del controllo delle cassette postali è attivata per impostazione predefinita nell'organizzazione. Ad esempio, se si imposta la proprietà della cassetta postale *AuditEnabled consente* su **false** , verrà ignorata.  Tuttavia, è comunque possibile utilizzare il cmdlet **Set-MailboxAuditBypassAssociation** in Exchange Online PowerShell per impedire la registrazione delle azioni delle cassette postali eseguite da utenti specifici. Quando si ignora il controllo delle cassette postali, le azioni delle cassette postali eseguite da un utente specifico non vengono controllate, indipendentemente dalla cassetta postale in cui vengono eseguite tali azioni. Se si ignora il controllo delle cassette postali per un utente specifico, le azioni del proprietario della cassetta postale eseguite dall'utente non verranno registrate. Se allo stesso utente vengono assegnate le autorizzazioni per la cassetta postale di un altro utente (o una cassetta postale condivisa), le azioni delegate eseguite dal primo utente non verranno registrate.

Per ignorare la registrazione di controllo della cassetta postale per un utente specifico, eseguire il comando riportato di seguito:

```
Set-MailboxAuditBypassAssociation -Identity <username> -AuditByPassEnabled $true
```

Per verificare che il controllo sia bypassato per l'utente specificato, eseguire il comando riportato di seguito:

```
Get-MailboxAuditBypassAssociation -Identity <username> | FL AuditByPassEnabled
```

Il valore **true** indica che la registrazione di controllo delle cassette postali viene ignorata per quell'utente.

## <a name="mailbox-auditing-actions"></a>Azioni di controllo delle cassette postali
  
Nella tabella seguente sono riepilogate le azioni che vengono controllate per ogni tipo di accesso utente. Nella tabella, un asterisco ( **\*** ) indica che l'azione è registrata per impostazione predefinita. Un **No** indica che non è possibile registrare un'azione per il tipo di accesso. Si noti che un amministratore a cui è stata assegnata l'autorizzazione di accesso completo per la cassetta postale di un utente viene considerato un utente delegato. 
  
|**Azione**|**Descrizione**|**Admin**|**Delegato**|**Proprietario**|
|:-----|:-----|:-----|:-----|:-----|
|**Copia** <br/> |Messaggio copiato in un'altra cartella.  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|**Creazione** <br/> |Elemento creato nella cartella Calendario, Contatti, Note o Attività nella cassetta postale; ad esempio, viene creata una nuova convocazione di riunione. Si noti che la creazione, l'invio o la ricezione di un messaggio non viene controllato. Inoltre, la creazione di una cartella delle cassette postali non viene controllata.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì  <br/> |
|**FolderBind**\** <br/> |Accesso effettuato a una cartella della cassetta postale. Tale azione viene registrata anche quando l'amministratore o un delegato apre la cassetta postale.  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|**HardDelete** <br/> |Messaggio eliminato dalla cartella Elementi ripristinabili.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**MailboxLogin** <br/> |L'utente ha eseguito l'accesso alla propria cassetta postale.  <br/> |No  <br/> |No  <br/> |Sì  <br/> |
|**MessageBind**\*** <br/> |Messaggio visualizzato nel riquadro di anteprima o aperto.  <br/> |Sì  <br/> |No  <br/> |No  <br/> |
|**Move** <br/> |Messaggio spostato in un'altra cartella.  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|**MoveToDeletedItems** <br/> |Messaggio eliminato e spostato nella cartella Posta eliminata.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**SendAs** <br/> |Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.  <br/> |Sì\*  <br/> |Sì\*  <br/> |No  <br/> |
|**SendOnBehalf** <br/> |Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.  <br/> |Sì\*  <br/> |Sì\*  <br/> |No  <br/> |
|**SoftDelete** <br/> |Messaggio eliminato in modo definitivo dalla cartella Posta eliminata. Gli elementi eliminati temporaneamente vengono spostati nella cartella Elementi ripristinabili.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**Aggiorna** <br/> |Modifiche apportate a un messaggio o alle relative proprietà.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**UpdateCalendarDelegation** <br/> |Una delega del calendario è stata assegnata a una cassetta postale. La delega del calendario fornisce a qualcun altro nelle autorizzazioni dell'organizzazione la gestione del calendario del proprietario della cassetta postale.  <br/> |Sì\*  <br/> |No  <br/> |Sì\*  <br/> |
|**UpdateFolderPermissions** <br/> |È stata modificata un'autorizzazione per la cartella. Autorizzazioni per le cartelle controllare quali utenti dell'organizzazione possono accedere alle cartelle in una cassetta postale e i messaggi che si trovano in tali cartelle.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
|**UpdateInboxRules** <br/> |È stata aggiunta, rimossa o modificata una regola di posta in arrivo. Le regole di posta in arrivo vengono utilizzate per elaborare i messaggi nella posta in arrivo dell'utente in base alle condizioni specificate e intraprendere azioni quando vengono soddisfatte le condizioni di una regola, ad esempio lo spostamento di un messaggio in una cartella specificata o l'eliminazione di un messaggio.  <br/> |Sì\*  <br/> |Sì\*  <br/> |Sì\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>Controllo per impostazione predefinita quando è abilitato il controllo delle cassette postali predefinito per il tipo di accesso. <br/><br/>  <sup>\*\*</sup>I record di controllo per le operazioni di associazione delle cartelle eseguite dai delegati vengono consolida Viene generato un record di controllo per l'accesso a una singola cartella entro un intervallo di tempo di 24 ore. <br/><br/> L'azione MessageBind è stata deprecata in Exchange Online e non è più disponibile per l'aggiunta all'elenco delle azioni delle cassette postali per il tipo di accesso di amministratore. <sup> \* \* \* </sup> 

## <a name="more-information"></a>Ulteriori informazioni

- Per impostazione predefinita, i record del registro di controllo della cassetta postale vengono conservati per 90 giorni e quindi eliminati. È possibile modificare il limite di validità dei record del registro di controllo utilizzando il comando **Set-Mailbox-AuditLogAgeLimit** in PowerShell di Exchange Online. Si noti che l'aumento del limite di validità predefinito dei record di controllo delle cassette postali non influisce sul limite di validità di 90 giorni per i record del registro di controllo della cassetta postale nel registro di controllo di Microsoft 365 Ad esempio, se si aumenta il limite di validità dei record del registro di controllo delle cassette postali a 365 giorni, il record di controllo della cassetta postale sarà ricercabile nel registro di controllo di Microsoft 365 solo 90 giorni dopo l'evento corrispondente. In questo caso, è necessario eseguire una ricerca nel registro di controllo della cassetta postale dell'utente per i record precedenti a 90 giorni. Per ulteriori informazioni sulla ricerca dei registri di controllo delle cassette postali, vedere [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog).

- Se la proprietà *AuditLogAgeLimit* di una cassetta postale è stata modificata prima che il controllo delle cassette postali venga attivato per impostazione predefinita per l'organizzazione, il periodo di validità del registro di controllo esistente per tale cassetta postale non verrà modificato. in altre parole, il controllo delle cassette postali per impostazione predefinita non ha effetto sul limite di validità corrente per i record di controllo delle cassette postali.

- I record del registro di controllo delle cassette postali sono archiviati in una sottocartella (denominata *Audit*) nella cartella elementi ripristinabili nella cassetta postale di ogni utente. Tenere presenti le considerazioni seguenti sui record di controllo delle cassette postali e sulla cartella elementi ripristinabili.
   
    - I record di controllo delle cassette postali sono confrontati con la quota di archiviazione della cartella elementi ripristinabili, che è 30 GB per impostazione predefinita (la quota di avviso è 20). Si noti che la quota di archiviazione per la cartella elementi ripristinabili viene automaticamente aumentata da 100 GB (quota di avviso di 90 MB) quando viene inserita un'esenzione in una cassetta postale o se la cassetta postale viene assegnata a un criterio di conservazione nel centro conformità.

    - I record di controllo della cassetta postale contano anche rispetto al limite della cartella [per la cartella elementi ripristinabili](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). Il numero massimo di elementi, ovvero i record di controllo in questo caso, che possono essere archiviati nella sottocartella controlli è 3 milioni elementi. 

      > [!NOTE]
      > È improbabile che il controllo delle cassette postali per impostazione predefinita influenzi la quota di archiviazione o il limite della cartella per la cartella elementi ripristinabili. 

    - È possibile eseguire il comando seguente in PowerShell di Exchange Online per visualizzare le dimensioni e il numero di elementi nella sottocartella revisioni nella cartella elementi ripristinabili: 
       ```
       Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | FL FolderPath,FolderSize,ItemsInFolder
       ```

     - Non è possibile accedere direttamente a un record del registro di controllo nella cartella elementi ripristinabili. al contrario, si utilizza il cmdlet **Search-MailboxAuditLog** o si effettua una ricerca nel registro di controllo di Microsoft 365 per individuare e visualizzare i record di controllo delle cassette postali.

- Se una cassetta postale viene conservata o assegnata a un criterio di conservazione nel centro conformità, i record del registro di controllo continuano a essere conservati per la durata definita dalla proprietà *AuditLogAgeLimit* per la cassetta postale (impostata su 90 giorni per impostazione predefinita). Per mantenere i record del registro di controllo più a lungo per le cassette postali in attesa, è necessario aumentare il periodo di conservazione aumentando il valore della proprietà *AuditLogAgeLimit* .