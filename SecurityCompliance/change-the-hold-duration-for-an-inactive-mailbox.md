---
title: Modificare la durata del blocco per una cassetta postale inattiva in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Dopo aver reso inattiva una cassetta postale di Office 365, è possibile modificare la durata del blocco o il criterio di conservazione di Office 365 assegnato alla cassetta postale inattiva. La durata del blocco definisce il periodo di conservazione degli elementi nella cartella elementi ripristinabili.
ms.openlocfilehash: 3f92d51505ba8a9a9f4b8e78d0fb79036b6db489
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220616"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Modificare la durata del blocco per una cassetta postale inattiva in Office 365

Una cassetta postale inattiva viene utilizzata per conservare la posta elettronica di un precedente dipendente dopo che quest'ultimo ha lasciato l'organizzazione. Una cassetta postale diventa inattiva quando ad essa viene applicato un blocco per controversia legale, un blocco sul posto, un criterio di conservazione di Office 365 o un blocco associato a un caso di eDiscovery e il corrispondente account utente di Office 365 viene eliminato. I contenuti di una cassetta postale inattiva vengono mantenuti per tutta la durata del blocco applicato alla cassetta postale prima che fosse resa inattiva. La durata del blocco definisce per quanto tempo gli elementi nella cartella Elementi ripristinabili vengono conservati. Quando la durata del blocco per un elemento nella cartella Elementi ripristinabili scade, questo viene eliminato definitivamente (cancellato) dalla cassetta postale inattiva. Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco o del criterio di conservazione di Office 365 assegnato alla cassetta postale inattiva.
  
> [!IMPORTANT]
> Abbiamo posticipato la scadenza del 1° luglio 2017 relativa alla creazione di un nuovo blocco sul posto per rendere inattiva una cassetta postale. Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online. Da quel momento, sarà possibile utilizzare soltanto blocchi per controversia legale e criteri di conservazione di Office 365 per creare una cassetta postale inattiva. Tuttavia, le cassette postali inattive esistenti disponibili nel blocco sul posto continueranno a essere supportate ed è possibile continuare a gestire i blocchi per controversia legale sulle cassette postali inattive. Ciò include le operazioni di modifica della durata di un blocco sul posto e di eliminazione definitiva di una cassetta postale inattiva mediante la rimozione del blocco sul posto. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per modificare la durata di un blocco per controversia legale su una cassetta postale inattiva, è necessario utilizzare Exchange Online PowerShell. Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). Tuttavia, è possibile utilizzare PowerShell di Exchange Online o EAC per modificare la durata del blocco per un blocco sul posto. Per modificare la durata del blocco di &amp; un criterio di conservazione di &amp; Office 365, è possibile utilizzare il Centro sicurezza e conformità di Office 365 o il Centro sicurezza e conformità.
    
- Per connettersi a PowerShell di Exchange Online o &amp; al centro sicurezza e conformità, vedere uno degli argomenti seguenti:
    
  - [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Connettersi a PowerShell in Centro sicurezza e conformità di Office 365](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Tenere presenta che i blocchi associati ai casi di eDiscovery sono blocchi infiniti, il che significa non esiste una durata del blocco che può essere modificata. Gli elementi vengono conservati all'infinito o finché il blocco non viene rimosso e la cassetta postale non viene eliminata.
    
- Per ulteriori informazioni sulle cassette postali inattive, vedere [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Passaggio 1: identificare i blocchi su una cassetta postale inattiva

Poiché diversi tipi di blocchi o uno o più criteri di conservazione di Office 365 potrebbero essere applicati a una cassetta postale inattiva, il primo passaggio consiste nell'identificare i blocchi applicati a una cassetta postale inattiva.
  
Eseguire il seguente comando in Exchange Online per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
Il valore **true** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva è in blocco per controversia legale. Se un blocco sul posto, eDiscovery Hold o il criterio di conservazione di Office 365 viene inserito in una cassetta postale inattiva, viene visualizzato un GUID per il blocco o il criterio di conservazione come valore per la proprietà **InPlaceHolds** . Ad esempio, di seguito vengono illustrati i risultati per 5 cassette postali inattive. 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
Nella tabella seguente vengono identificati i cinque tipi diversi di blocco utilizzati per rendere inattiva ogni cassetta postale.
  
|**Cassetta postale inattiva**|**Tipo di blocco**|**Come identificare il blocco sulla cassetta postale inattiva**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Blocco per controversia legale  <br/> |La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.  <br/> |
|Pilar Pinilla  <br/> |Blocco sul posto  <br/> |La proprietà  *InPlaceHolds*  contiene il GUID del blocco sul posto applicato alla cassetta postale inattiva. È possibile stabilire che si tratta di un blocco sul posto perché l'ID non inizia con un prefisso.  <br/> È possibile utilizzare il `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando in Exchange Online PowerShell per ottenere informazioni sul blocco sul posto della cassetta postale inattiva.  <br/> |
|Mario Necaise  <br/> |Criteri di conservazione di Office 365 a livello di organizzazione &amp; nel centro sicurezza e conformità  <br/> |La proprietà *InPlaceHolds* è vuota. Ciò indica che uno o più criteri di conservazione di Office 365 a livello di organizzazione o di Exchange vengono applicati alla cassetta postale inattiva. In questo caso, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando in Exchange Online PowerShell per ottenere un elenco dei GUID per i criteri di conservazione di Office 365 a livello dell'organizzazione. Il GUID per i criteri di conservazione a livello dell'organizzazione applicati alle cassette postali di `mbx` Exchange inizia con il prefisso. ad esempio `mbxa3056bb15562480fadb46ce523ff7b02`.<br/> <br/>Per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale inattiva, eseguire il comando seguente in PowerShell &amp; per il Centro sicurezza e conformità.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Criteri di conservazione di Office 365 nel &amp; centro conformità di sicurezza applicato a cassette postali specifiche  <br/> |La proprietà  *InPlaceHolds*  contiene il GUID del criterio di conservazione di Office 365 applicato alla cassetta postale inattiva. È possibile stabilire che si tratta di un criterio di conservazione applicato a specifiche cassette postali perché il GUID inizia con il prefisso  `mbx`. Tenere presente che il GUID del criterio di conservazione applicato alla cassetta postale inattiva iniziava con il prefisso  `skp`, indicando che il criterio di conservazione è applicato alle conversazioni di Skype for Business.  <br/><br/> Per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale inattiva, eseguire il comando seguente in PowerShell &amp; per il Centro sicurezza e conformità.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Assicurarsi di rimuovere il `mbx` prefisso o `skp` quando si esegue questo comando.  <br/> |
|Abraham McMahon  <br/> |blocco del caso di eDiscovery nel &amp; Centro sicurezza e conformità  <br/> |La proprietà  *InPlaceHolds*  contiene il GUID del blocco caso eDiscovery applicato alla cassetta postale inattiva. È possibile stabilire che si tratta di un blocco caso eDiscovery perché il GUID inizia con il prefisso  `UniH`.  <br/> È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in PowerShell &amp; per la conformità al centro sicurezza per ottenere informazioni sul caso di eDiscovery a cui è associato il blocco sulla cassetta postale inattiva. Ad esempio, è possibile eseguire il comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` per visualizzare il nome del blocco del caso che si trova nella cassetta postale inattiva. Assicurarsi di rimuovere il `UniH` prefisso quando si esegue questo comando.<br/><br/> Per identificare il caso eDiscovery a cui è associato il blocco applicato alla cassetta postale inattiva, eseguire i seguenti comandi.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Nota:** Non è consigliabile utilizzare eDiscovery per le cassette postali inattive. Ciò è dovuto al fatto che i casi di eDiscovery sono destinati a casi specifici relativi a un problema legale. A un certo punto, probabilmente si concluderà un caso legale e le esenzioni associate al caso verranno rimosse e il caso di eDiscovery verrà chiuso (o eliminato). Infatti, se una conservazione inserita in una cassetta postale inattiva è associata a un caso di eDiscovery e il blocco viene rilasciato o se il caso eDiscovery è chiuso o eliminato, la cassetta postale inattiva viene eliminata definitivamente. 

Per ulteriori informazioni sui criteri di conservazione di Office 365, vedere [Overview of](retention-policies.md)Retention Policies.
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Passaggio 2: modificare la durata del blocco per una cassetta postale inattiva

Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel modificare la durata del blocco. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Modificare la durata di un blocco per controversia legale

Ecco come utilizzare Exchange Online PowerShell per modificare la durata di un blocco per controversia legale applicato a una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando seguente per modificare la durata del blocco. In questo esempio, la durata del blocco viene impostata su un periodo di tempo illimitato.
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

Il risultato è che gli elementi nella cassetta postale inattiva vengono conservati per sempre o finché il blocco non viene rimosso o la durata del blocco non viene modificata.
  
> [!TIP]
> Il modo migliore per identificare una cassetta postale inattiva consiste nell'utilizzare il relativo valore **Distinguished Name** o **Exchange GUID**. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Modificare la durata del blocco sul posto

 È possibile utilizzare l'interfaccia di amministrazione di Exchange o Exchange Online PowerShell per modificare la durata di un blocco sul posto. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Modifica della durata del blocco tramite l'interfaccia di amministrazione di Exchange

1. Se si conosce il nome del blocco sul posto che si desidera modificare, passare al passaggio successivo. In caso contrario, eseguire il comando riportato di seguito per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto ottenuto nel [passaggio 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Nell'interfaccia di amministrazione di Exchange, andare a **gestione** \> **della conformità &amp; sul posto eDiscovery Hold**.
    
3. Selezionare il blocco sul posto che si desidera modificare, quindi fare clic su **modifica** ![icona](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)modifica.
    
4. Nella pagina proprietà **blocco eDiscovery &amp; sul posto** fare clic su **blocco sul posto**. 
    
5. Eseguire una delle operazioni seguenti in base alla durata del blocco corrente:
    
1. Fare clic su **Blocca illimitatamente** per conservare gli elementi per un periodo di tempo illimitato. 
    
2. Fare clic su **Specifica numero di giorni per contenere gli elementi relativi alla data di ricezione** in modo che gli elementi vengano conservati per un periodo specifico. Digitare il numero di giorni in cui si desidera conservare gli elementi. 
    
    ![Schermata della modifica della durata per un blocco sul posto](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Fare clic su **Salva**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Utilizzare Exchange Online PowerShell per modificare la durata del blocco

1. Se si conosce il nome del blocco sul posto che si desidera modificare, passare al passaggio successivo. In caso contrario, eseguire il comando riportato di seguito per ottenere il nome del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto ottenuto nel [passaggio 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Eseguire il comando seguente per modificare la durata del blocco. In questo esempio, la durata del blocco viene impostata su un periodo di 2.555 giorni (circa 7 anni). 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Per impostare la durata del blocco su un periodo di tempo illimitato, utilizzare  _-ItemHoldPeriod unlimited_
  
## <a name="more-information"></a>Ulteriori informazioni

- **Come viene calcolata la durata del blocco per un elemento in una cassetta postale inattiva** La durata viene calcolata a partire dalla data originale di ricezione o creazione dell'elemento della cassetta postale. 
    
- **Effetti della scadenza della durata del blocco** Quando la durata del blocco per un elemento della cassetta postale nella cartella Elementi ripristinabili scade, questo viene eliminato definitivamente (cancellato) dalla cassetta postale inattiva. Se non esiste alcuna durata specificata per il blocco applicato alla cassetta postale inattiva, gli elementi nella cartella Elementi ripristinabili non verranno mai cancellati (a meno che la durata del blocco della cassetta postale inattiva non venga modificata). 
    
- **Un criterio di conservazione di Exchange è ancora elaborato nelle cassette postali inattive?** Se un criterio di conservazione di Exchange (la funzionalità di Gestione record di messaggistica o MRM in Exchange Online) è stato applicato alla cassetta postale quando era inattiva, i criteri di eliminazione (che sono configurati con tag di conservazione in un'azione conservazione **Delete** ) continuerà a essere elaborato nella cassetta postale inattiva. Questo significa che gli elementi che sono contrassegnati con un criterio di eliminazione verranno spostati nella cartella Elementi ripristinabili quando scade il periodo di conservazione. Questi elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata del blocco. 
    
    Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di conservazione configurati con un'azione conservazione **MoveToArchive** ) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Poiché un utente non può accedere a una cassetta postale inattiva, non c'è motivo di consumare risorse del centro dati per elaborare criteri di archiviazione. 
    
- **Per controllare la nuova durata del blocco, eseguire uno dei seguenti comandi.** Il primo comando è per il blocco per controversia legale, il secondo per il blocco sul posto. 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Come per le cassette postali normali, l'Assistente cartelle gestite elabora anche le cassette postali inattive.** In Exchange Online, l'Assistente cartelle gestite elabora le cassette postali circa ogni 7 giorni. Dopo aver modificato la durata del blocco per una cassetta postale inattiva, è possibile utilizzare il cmdlet **Start-ManagedFolderAssistant** per avviare immediatamente l'elaborazione della nuova durata del blocco per la cassetta postale inattiva. Eseguire il comando riportato di seguito. 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Se sono abilitati numerosi blocchi in una cassetta postale inattiva, non vengono visualizzati tutti i GUID dei blocchi.** È possibile eseguire il seguente comando per visualizzare i GUID per tutti i blocchi (ad eccezione dei blocchi per controversia legale) che vengono applicati a una cassetta postale inattiva. 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
