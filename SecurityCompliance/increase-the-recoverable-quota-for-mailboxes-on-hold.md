---
title: Aumentare la quota degli elementi recuperabili per le cassette postali in attesa
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: "Abilitare la cassetta postale di archiviazione e attivare l'archiviazione per aumentare le dimensioni della cartella elementi recuperabili per una cassetta postale in Office 365 l'espansione automatica. "
ms.openlocfilehash: 2e7149ef10152a11dc638c04b61a261440b539b8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530325"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Aumentare la quota degli elementi recuperabili per le cassette postali in attesa

Il criterio di conservazione predefinito, ovvero denominato criterio di gestione record di messaggistica predefinito, vale a dire automaticamente applicata a nuove cassette postali in Exchange Online contiene un tag di conservazione denominate giorni 14 elementi recuperabili spostamento nell'archivio. Tag di conservazione Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente nella cartella elementi recuperabili di cassetta postale di archivio dell'utente dopo il periodo di conservazione 14 giorni per un elemento. A tale scopo, è necessario attivare cassetta postale di archivio dell'utente. Se la cassetta postale di archiviazione non è abilitata, viene eseguita alcuna azione, il che significa che non vengono spostati gli elementi nella cartella per una cassetta postale in attesa agli elementi ripristinabili la cassetta postale di archiviazione dopo il periodo di conservazione 14 giorni. Poiché non viene eliminato da una cassetta postale in attesa, è possibile che potrebbe essere superata la quota di archiviazione per la cartella elementi ripristinabili, soprattutto se non è abilitata cassetta postale di archivio dell'utente. 
  
Per ridurre le possibilità che superano questo limite, la quota di archiviazione per la cartella elementi recuperabili viene automaticamente aumentata da 30 GB a 100 GB quando un'esenzione viene messa in una cassetta postale di Exchange Online. Se la cassetta postale di archiviazione è abilitata, la quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale di archiviazione viene inoltre aumentata da 30 GB a 100 GB. Se l'archiviazione di espansione automatica delle funzionalità di Exchange Online è abilitata, la quota di archiviazione per la cartella elementi recuperabili nell'archivio dell'utente è un numero illimitata.
  
  La tabella seguente riepiloga la quota di archiviazione per la cartella Elementi ripristinabili. 
  
|**Posizione della cartella Elementi ripristinabili**|**Cassette postali non in blocco**|**Cassette postali in blocco**|
|:-----|:-----|:-----|
|Cassetta postale principale  <br/> |30 GB  <br/> |100 GB  <br/> |
|Cassetta postale di archiviazione<sup>\*</sup> <br/> |Illimitata  <br/> |Illimitata  <br/> |
|**Quota di archiviazione totale per la cartella Elementi ripristinabili** <br/> |Illimitata  <br/> |Illimitata  <br/> |
   
> [!NOTE]
> <sup>\*</sup>La quota di archiviazione iniziali per la cassetta postale di archiviazione è pari a 100 GB per gli utenti con una licenza di Exchange Online (piano 2). Tuttavia, quando è attivata l'espansione automatica di archiviazione, la quota di archiviazione per l'archivio dell'utente e la cartella elementi ripristinabili dell'archivio è illimitata. Per ulteriori informazioni sull'espansione automatica di archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md). 
  
Quando la quota di archiviazione per la cartella Elementi ripristinabili nella cassetta postale principale di una cassetta postale in blocco sta per raggiungere il limite, è possibile eseguire le operazioni seguenti:
  
- **Abilitare la cassetta postale di archiviazione e attivare l'archiviazione l'espansione automatica** - è possibile attivare una capacità di archiviazione illimitato per la cartella elementi ripristinabili semplicemente dall'abilitazione della cassetta postale di archiviazione e quindi riattivare la caratteristica archiviazione espansione automatica di Exchange In linea. Di conseguenza 100 GB per la cartella elementi ripristinabili nella cassetta postale principale e una numero illimitata quantità di capacità di archiviazione per la cartella elementi recuperabili nell'archivio dell'utente. Vedere Procedura: [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md) e [abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md).
    
    > [!NOTE]
    > Dopo aver abilitato l'archivio per una cassetta postale che si avvicina al superamento della quota di archiviazione per la cartella elementi ripristinabili, è possibile eseguire l'Assistente cartelle gestite per attivare manualmente l'Assistente per elaborare la cassetta postale in modo che gli elementi scaduti vengono spostati i Cartella degli elementi ripristinabili nella cassetta postale di archivio. Per istruzioni, vedere [il passaggio 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) . Si noti che la nuova cassetta postale di archiviazione possono quindi essere spostati altri elementi nella cassetta postale dell'utente. È consigliabile che indica all'utente che questa situazione può verificarsi dopo aver attivato la cassetta postale di archivio. 
  
- **Crea un criterio di conservazione personalizzata per le cassette postali in attesa** - oltre abilitazione della cassetta postale di archiviazione e l'archiviazione delle cassette postali su conservazione per controversia legale o archiviazione sul posto, l'espansione automatica è inoltre possibile creare un criterio di conservazione personalizzata per le cassette postali su in attesa. Ciò si è applicare un criterio di conservazione alle cassette postali in attesa è diverso dal criterio Gestione record di messaggistica predefinito viene applicato alle cassette postali che non sono in attesa. In tal modo si per applicare i tag di conservazione sono progettati per le cassette postali in attesa. Esse comprendono la creazione di un nuovo tag di conservazione per la cartella elementi ripristinabili. 
    
Il resto di questo argomento descrive procedure dettagliate per creare criteri di conservazione personalizzati per le cassette postali in blocco.
  
[Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[Passaggio 2: creare un nuovo criterio di conservazione per le cassette postali in attesa](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Passaggio 1: Creazione di un nuovo tag di conservazione per la cartella Elementi ripristinabili

Il primo passaggio consiste nel creare un tag di conservazione personalizzata (detta tag criterio di conservazione o tag) per la cartella elementi recuperabili. Come indicato in precedenza, questo RPT Sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente nella cartella elementi recuperabili di cassetta postale di archivio dell'utente. È necessario utilizzare PowerShell per creare un tag per la cartella elementi recuperabili. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC). 
  
1. [Connessione a Exchange Online tramite remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. Eseguire il seguente comando per creare un nuovo RPT nella cartella Elementi ripristinabili:  
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Ad esempio, il seguente comando crea un RPT per la cartella Elementi ripristinabili denominata "Spostamento degli elementi ripristinabili dopo 30 giorni per le cassette postali in blocco", con un periodo di conservazione di 30 giorni. Ciò significa che dopo che un elemento è stato nella cartella Elementi ripristinabili per 30 giorni, viene spostato nella cartella Elementi ripristinabili nella cassetta postale di archiviazione dell'utente.
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > È consigliabile che il periodo di conservazione (definito dal parametro _AgeLimitForRetention_ ) per il tag degli elementi ripristinabili è lo stesso del periodo di mantenimento elementi eliminati per le cassette postali che verrà applicato il tag. Ciò consente l'intero periodo di mantenimento per ripristinare gli elementi eliminati prima che venga vengono spostati nella cassetta postale di archivio. Nell'esempio precedente, il periodo di conservazione è stato impostato su 30 giorni partendo dal presupposto che il periodo di mantenimento elementi eliminati per le cassette postali è anche 30 giorni. Una cassetta postale di Exchange Online è configurata per conservare gli elementi eliminati 14 giorni, per impostazione predefinita. Ma è possibile modificare questa impostazione per un massimo di 30 giorni. Per ulteriori informazioni, vedere [modificare il periodo di mantenimento elementi eliminati per una cassetta postale di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940). 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>Passaggio 2: Creazione di nuovi criteri di conservazione per le cassette postali in blocco

Il passaggio successivo consiste nel creare nuovi criteri di conservazione e aggiungere tag di conservazione, inclusi i RPT di elementi ripristinabili creati nel Passaggio 1. I nuovi criteri verranno applicati alle cassette postali in blocco nel passaggio successivo.  
  
Prima di creare i nuovi criteri di conservazione, determinare quali tag di conservazione aggiuntivi aggiungere. Per un elenco dei tag di conservazione che vengono aggiunti ai criteri di gestione record di messaggistica predefiniti e per informazioni sulla creazione di nuovi tag di conservazione, vedere gli articoli seguenti:
  
- [Default criterio di conservazione in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [Cartelle predefinite che supportano i tag del criterio di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- La sezione "Creare un tag di conservazione" nell'argomento [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) .
    
È possibile utilizzare EAC o Exchange Online PowerShell per creare un criterio di conservazione.
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>Creazione di un criterio di conservazione tramite l'interfaccia di amministrazione di Exchange
  
1. In EAC, andare a **Gestione conformità** \> **i criteri di conservazione**e quindi fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif).
    
2. Nella pagina **Nuovo criterio di conservazione**, in **Nome**, digitare un nome che descriva lo scopo del criterio di conservazione, ad esempio, **MRM Policy for Mailboxes on Hold**.  
    
3. **I tag di conservazione**, fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif).
    
4. Nell'elenco dei tag di conservazione, selezionare l’elemento RPT di Elementi ripristinabili creato nel Passaggio 1, quindi fare clic su **Aggiungi**.
    
    ![Selezionare il tag di conservazione Elementi recuperabili personalizzato](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. Selezionare i tag di conservazione aggiuntivi da aggiungere ai criteri di conservazione. Ad esempio, è possibile aggiungere gli stessi tag inclusi nei criteri di gestione record di messaggistica.
    
6. Dopo aver completato l'aggiunta dei tag di conservazione, fare clic su **OK**.
    
7. Fare clic su **Salva** per creare i nuovi criteri di conservazione. 
    
    Tenere presente che i tag di conversazione collegati ai criteri di conservazione vengono visualizzati nel riquadro dei dettagli.
    
    ![I tag di conversazione collegati al criterio di conservazione vengono visualizzati nel riquadro dei dettagli](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Utilizzare Exchange Online PowerShell per creare un criterio di conservazione
  
Per creare nuovi criteri di conservazione per le cassette postali in blocco, eseguire il seguente comando:  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Il comando seguente, ad esempio, crea il criterio di conservazione e tag di conservazione collegati, come illustrato nella figura precedente.
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>Passaggio 3: Applicazione dei nuovi criteri di conservazione alle cassette postali in blocco

L'ultimo passaggio è per applicare il nuovo criterio di conservazione creata nel passaggio 2 per le cassette postali in attesa nell'organizzazione. È possibile utilizzare EAC o Exchange Online PowerShell per applicare il criterio di conservazione a una singola cassetta postale o a più cassette postali. 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Utilizzare EAC per applicare i nuovi criteri di conservazione
  
1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nella visualizzazione elenco, selezionare la cassetta postale che si desidera applicare il criterio di conservazione per e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
3. Nella pagina **Cassetta postale utente**, fare clic su **Funzionalità delle cassette postali**.
    
4. In **Criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**.
    
È anche possibile utilizzare EAC per applicare criteri di conservazione a più cassette postali.
  
1. Andare a **Destinatari** \> **Cassette postali**.
    
2. Nell'elenco, utilizzare il tasto Maiusc o Ctrl per selezionare più cassette postali.
    
3. Nel riquadro dei dettagli, fare clic su **Altre opzioni**.
    
4. In **Criterio di conservazione**, fare clic su **Aggiorna**.
    
5. Nella pagina **Assegna in blocco i criteri di conservazione**, selezionare i criteri di conservazione creati nel passaggio 2, quindi fare clic su **Salva**.  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Utilizzare Exchange Online PowerShell per applicare il nuovo criterio di conservazione
  
È possibile utilizzare Exchange Online PowerShell per applicare un nuovo criterio di conservazione a una singola cassetta postale. Ma l'efficacia di PowerShell che è possibile utilizzare per identificare rapidamente tutte le cassette postali nell'organizzazione su conservazione per controversia legale o archiviazione sul posto e quindi applicano il nuovo criterio di conservazione per tutte le cassette postali in attesa in un unico comando. Di seguito sono riportati alcuni esempi dell'utilizzo di PowerShell di Exchange per applicare un criterio di conservazione a una o più cassette postali. Tutti gli esempi di applicare il criterio di conservazione creato nel passaggio 2.
  
In questo esempio vengono applicati nuovi criteri di conservazione alla cassetta postale di Pilar Pinilla.
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco per controversia legale.
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

In questo esempio vengono applicati nuovi criteri di conservazione a tutte le cassette postali dell'organizzazione in blocco sul posto.
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

È possibile utilizzare il cmdlet **Get-Mailbox** per verificare che siano stati applicati i nuovi criteri di conservazione. 
  
Ecco alcuni esempi per verificare che i comandi negli esempi precedenti abbiano applicato i criteri di conservazione "Criteri di gestione record di messaggistica per le cassette postali in blocco" alle cassette postali in blocco per controversia legale e alle cassette postali in blocco sul posto.
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>Passaggio 4 (facoltativo): Esecuzione dell'Assistente cartelle gestite per applicare le nuove impostazioni di conservazione

Dopo aver applicato il nuovo criterio di conservazione alle cassette postali in attesa, potrebbero essere necessari fino a 7 giorni di Exchange Online per l'Assistente cartelle gestite elaborare le cassette postali utilizzando le impostazioni nel nuovo criterio di conservazione. Anziché attendere l'Assistente cartelle gestite per l'esecuzione, è possibile utilizzare il cmdlet **Start-ManagedFolderAssistant** per attivare manualmente l'Assistente per elaborare le cassette postali che è stato applicato il nuovo criterio di conservazione a. 
  
Eseguire il seguente comando per avviare l'Assistente cartelle gestite per la cassetta postale di Pilar Pinilla.
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Eseguire il seguente comando per avviare l'Assistente cartelle gestite per tutte le cassette postali in blocco.
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Ulteriori informazioni

- Dopo aver abilitato cassetta postale di archivio dell'utente, è consigliabile che indica all'utente che altri elementi nella cassetta postale (non solo gli elementi nella cartella elementi ripristinabili) potrebbe essere spostati la cassetta postale di archiviazione. Perché il criterio di gestione record di messaggistica predefinito assegnato alle cassette postali di Exchange Online contiene un tag di conservazione (denominato Default 2 anni spostamento nell'archivio) che sposta gli elementi nella cassetta postale di archivio di due anni dopo la data, l'elemento è stato recapitato alla cassetta postale o creato con il utente. Per ulteriori informazioni, vedere [Criteri di conservazione predefiniti in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- Dopo aver abilitato cassetta postale di archivio dell'utente, potrebbe anche informare l'utente che è possibile recuperare elementi eliminati in cartella elementi ripristinabili nella cassetta postale di archivio. È possibile ottenere questo risultato in Outlook selezionare la cartella **Posta eliminata** nella cassetta postale di archiviazione e quindi fare clic su **Recupera elementi eliminati dal Server** nella scheda **Home** . Per ulteriori informazioni sugli elementi eliminati il ripristino, vedere [che recupera elementi eliminati in Outlook per Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829). 
