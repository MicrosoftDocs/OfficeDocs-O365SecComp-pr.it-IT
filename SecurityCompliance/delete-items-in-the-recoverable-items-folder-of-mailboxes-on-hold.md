---
title: Eliminare gli elementi nella cartella elementi recuperabili di cassette postali basate su cloud in attesa - della Guida di amministrazione
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Per gli amministratori: eliminare gli elementi nella cartella elementi recuperabili di un utente di una cassetta postale di Exchange Online, anche se tale cassetta postale viene messa in attesa legale. Si tratta in modo efficace per eliminare i dati che sono stata inavvertitamente passati in Office 365.'
ms.openlocfilehash: a10965ad088da98b4e4d84d823c124e5b192d505
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577085"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Eliminare gli elementi nella cartella elementi recuperabili di cassette postali basate su cloud in attesa - della Guida di amministrazione

Per proteggere da eliminazioni accidentali o intenzionali è presente la cartella elementi recuperabili per una cassetta postale di Exchange Online. Viene inoltre utilizzato per archiviare gli elementi vengono mantenuti e accedono dalla funzionalità di conformità di Office 365, ad esempio eDiscovery e conservazioni ricerche. In alcune situazioni, tuttavia, le organizzazioni potrebbero essere dati che sono stati mantenuti inavvertitamente nella cartella elementi ripristinabili è necessario eliminare. Ad esempio, un utente involontariamente inviare o di inoltrare un messaggio di posta elettronica contenente informazioni che possono avere conseguenze gravi business o informazioni riservate. Anche se il messaggio viene eliminato definitivamente, potrebbe essere conservato per un tempo indefinito perché una conservazione a fini giudiziari è stato inserito nella cassetta postale. In questo scenario è noto come perdita di dati in quanto i dati sono stati inavvertitamente passati in Office 365. In questi casi, è possibile eliminare elementi nella cartella elementi recuperabili di un utente per una cassetta postale di Exchange Online, anche se tale cassetta postale viene messa in attesa con una delle funzionalità di attesa diverse in Office 365. Questi tipi di conservazioni includono controversia contiene, archiviazioni sul posto, esenzioni eDiscovery e criteri di conservazione di Office 365 creati in Office 365 Security &amp; centro conformità. 
  
 In questo articolo viene illustrato come eliminare gli elementi dalla cartella elementi recuperabili per le cassette postali basate su cloud che in attesa. Questa procedura, è necessario disabilitare l'accesso alla cassetta postale e disattivazione ripristino di singoli elementi, disabilitare l'Assistente cartelle gestite dall'elaborazione della cassetta postale, rimuovere temporaneamente la conservazione, eliminazione di elementi dalla cartella elementi recuperabili e quindi il ripristino la cassetta postale per la configurazione precedente. Di seguito è il processo: 
  
[Passaggio 1: Raccolta delle informazioni sulla cassetta postale](#step-1-collect-information-about-the-mailbox)

[Passaggio 2: Preparare la cassetta postale](#step-2-prepare-the-mailbox)

[Passaggio 3: Rimuovere tutte le esenzioni dalla cassetta postale](#step-3-remove-all-holds-from-the-mailbox)

[Passaggio 4: Rimuovere la conservazione di ritardo dalla cassetta postale](#step-4-remove-the-delay-hold-from-the-mailbox)

[Passaggio 5: Eliminare gli elementi nella cartella elementi ripristinabili](#step-5-delete-items-in-the-recoverable-items-folder)

[Passaggio 6: Ripristinare la cassetta postale allo stato precedente](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Le procedure descritte in questo articolo genera dati vengono eliminati definitivamente dalla cassetta postale di Exchange Online. Significa che i messaggi eliminati dalla cartella elementi ripristinabili non possono essere recuperati e non saranno disponibili per esibizione o per altri motivi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che viene messa in attesa come parte di una conservazione per controversia legale, archiviazione sul posto, tenere premuto eDiscovery oppure il criterio di conservazione di Office 365 creato in Office 365 Security &amp; centro conformità, controllo con la gestione dei record o legale reparti prima della rimozione dell'esenzione. L'organizzazione potrebbe disporre di un criterio che definisce se una cassetta postale in attesa o un problema di perdita dei dati ha la priorità. 
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario assegnare entrambi i seguenti ruoli di gestione di Exchange Online per cercare ed eliminare messaggi dalla cartella elementi ripristinabili nel passaggio 5.
    
  - **Cassetta postale di ricerca** - questo ruolo consente di cercare cassette postali nell'organizzazione. Gli amministratori di Exchange non sono assegnati al ruolo per impostazione predefinita. Per assegnare questo ruolo, aggiungere l'utente come membro del gruppo di ruoli gestione individuazione in Exchange Online. 
    
  - **Cassetta postale di importazione ed esportazione** : questo ruolo consente di eliminare i messaggi dalla cassetta postale dell'utente. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruolo. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione di Exchange Online. 
    
- La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Ciò avviene perché non è possibile applicare nuovamente una conservazione o criteri di conservazione di Office 365, a una cassetta postale inattiva dopo la rimozione. Quando si rimuove un'esenzione da una cassetta postale inattiva, viene modificato in una normale cassetta postale eliminata e verranno eliminato definitivamente dall'organizzazione dopo che viene elaborato dall'Assistente cartelle gestite.
    
- È possibile eseguire questa procedura per una cassetta postale che è stata assegnata un criterio di conservazione di Office 365 è stata bloccata con un blocco di conservazione. Ciò avviene perché un blocco di conservazione impedisce la rimozione o ad eccezione della cassetta postale dal criterio di conservazione di Office 365 e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sul blocco di criteri di conservazione, vedere [il blocco di un criterio di conservazione](retention-policies.md#locking-a-retention-policy).
    
- Se una cassetta postale non viene messa in attesa o non dispone di individuazione di singoli elementi, è sufficiente eliminare gli elementi dalla cartella elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere [cercare ed eliminare i messaggi ](https://go.microsoft.com/fwlink/?linkid=852453).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Passaggio 1: Raccolta delle informazioni sulla cassetta postale

Il primo passaggio consiste nel raggruppare le proprietà selezionate dalla cassetta postale di destinazione che incide questa procedura. Assicurarsi di prendere nota di queste impostazioni o li si salva un file di testo poiché sarà modificare alcune di queste proprietà e quindi ripristinare i valori originali nel passaggio 6 dopo l'eliminazione degli elementi dalla cartella elementi ripristinabili. Ecco un elenco di proprietà della cassetta postale che è necessario raccogliere.
  
-  *SingleItemRecoveryEnabled* e *RetainDeletedItemsFor* ; Se necessario, si verrà disattivare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3. 
    
-  *LitigationHoldEnabled* e *InPlaceHolds* ; è necessario identificare tutte le esenzioni inserite nella cassetta postale in modo che è possibile rimuovere temporaneamente nel passaggio 3. Vedere la sezione [informazioni](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) per suggerimenti su come identificare la conservazione di tipo che può essere messa in una cassetta postale. 
    
Inoltre, è necessario ottenere la cassetta postale di impostazioni di accesso client in modo che è possibile disattivare temporaneamente essi in modo che il proprietario (o altri utenti) non possono accedere alla cassetta postale durante la procedura. Infine, è possibile ottenere le dimensioni correnti e il numero di elementi nella cartella elementi ripristinabili. Dopo l'eliminazione degli elementi nella cartella elementi ripristinabili nel passaggio 5, si utilizzerà queste informazioni per verificare che gli elementi sono state effettivamente rimosse.
  
1. [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e password di un account amministratore che è stato assegnato i ruoli di gestione appropriati in Exchange Online. 
    
2. Eseguire il comando seguente per ottenere informazioni sul ripristino di singoli elementi e il periodo di mantenimento elementi eliminati.

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se il ripristino di singoli elementi è attivato, è necessario disabilitare nel passaggio 2. Se non viene impostato il periodo di mantenimento elementi eliminati per 30 giorni (il valore massimo in Exchange Online), quindi è possibile aumentare nel passaggio 2. 
    
3. Eseguire il comando seguente per ottenere le impostazioni di accesso per la cassetta postale della cassetta postale. 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Si verrà disabilitare tutti questi metodi di accesso nel passaggio 2.
    
4. Eseguire il comando seguente per ottenere informazioni sulle esenzioni e Office 365 i criteri di conservazione applicati alla cassetta postale.
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Se non esistono troppi valori nella proprietà *InPlaceHolds* e non tutti gli elementi visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore in una riga distinta. 
  
5. Eseguire il comando seguente per ottenere informazioni su eventuali criteri di conservazione a livello di organizzazione Office 365. 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   Se l'organizzazione dispone di eventuali criteri di conservazione a livello di organizzazione Office 365, è necessario escludere la cassetta postale da questi criteri nel passaggio 3.

   > [!TIP]
    > Se non esistono troppi valori nella proprietà *InPlaceHolds* e non tutti gli elementi visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore in una riga distinta. 
  
6. Eseguire il comando seguente per ottenere le dimensioni corrente e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale principale dell'utente. 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se è abilitata cassetta postale di archivio dell'utente, eseguire il comando seguente per ottenere le dimensioni e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale di archivio. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Quando si eliminano elementi nel passaggio 5, è possibile scegliere di eliminare o non eliminare elementi contenuti nella cartella elementi ripristinabili nella cassetta postale di archivio principale dell'utente. Si noti che se l'espansione automatica di archiviazione è abilitata per la cassetta postale, gli elementi in una cassetta postale di archivio ausiliaria non vengono eliminati.
  
## <a name="step-2-prepare-the-mailbox"></a>Passaggio 2: Preparare la cassetta postale

Dopo aver raccolto e il salvataggio delle informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le operazioni seguenti: 
  
- **Disabilitare l'accesso client alla cassetta postale** in modo che il proprietario della cassetta postale non può accedere alle cassette postali e apportare le modifiche ai dati delle cassette postali durante la procedura. 
    
- **Aumentare il periodo di mantenimento elementi eliminati** a 30 giorni (il valore massimo in Exchange Online) in modo che gli elementi non vengono cancellati dalla cartella elementi recuperabili prima di eliminarli nel passaggio 5. 
    
- **Disattivazione ripristino di un singolo elemento** in modo che gli elementi non verrà mantenuto (per la durata del periodo di mantenimento elementi eliminati) che sono state eliminate dalla cartella elementi ripristinabili nel passaggio 5. 
    
- **Disattivare l'Assistente cartelle gestite** in modo che non elaborare la cassetta postale e conservazione degli elementi eliminati nel passaggio 5. 
    
Eseguire la procedura seguente in Exchange Online PowerShell.
  
1. Eseguire il seguente comando per disabilitare tutti i client l'accesso alla cassetta postale. La sintassi del comando si presuppone che tutti i metodi di accesso client siano stati abilitati per la cassetta postale.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > Potrebbero richiedere fino a 60 minuti per disabilitare tutti i metodi di accesso client per la cassetta postale. Si noti che la disattivazione di questi metodi di accesso non disconnettere proprietario della cassetta postale che attualmente effettuati l'accesso. Se il proprietario non viene eseguito l'accesso, quindi non saranno in grado di accedere alla cassetta postale dopo che questi metodi di accesso sono disabilitati. 
  
2. Eseguire il comando seguente per aumentare il numero massimo di 30 giorni del periodo di mantenimento elementi eliminati. Si presuppone che l'impostazione corrente è minore di 30 giorni. 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Eseguire il seguente comando per disabilitare il ripristino di un singolo elemento.
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Potrebbero richiedere fino a 60 minuti per disattivare il ripristino di un singolo elemento. Non eliminare gli elementi nella cartella elementi ripristinabili fino questo periodo di tempo. 
  
4. Eseguire il comando seguente per impedire l'Assistente cartelle gestite di elaborazione della cassetta postale. Come indicato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se un criterio di conservazione di Office 365 con un blocco di conservazione non viene applicato alla cassetta postale. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Passaggio 3: Rimuovere tutte le esenzioni dalla cassetta postale

L'ultimo passaggio prima che è possibile eliminare gli elementi dalla cartella elementi ripristinabili è per rimuovere tutte le esenzioni (identificato nel passaggio 1) inserite nella cassetta postale. Tutte le esenzioni devono essere eliminate in modo che non verranno mantenuti gli elementi che sono state eliminate dalla cartella elementi ripristinabili. Nelle sezioni seguenti contengono informazioni sulla rimozione di diversi tipi di conservazioni su una cassetta postale. Vedere la sezione [informazioni](#more-information) per suggerimenti su come identificare la conservazione di tipo che può essere messa in una cassetta postale. Per ulteriori informazioni, vedere [come identificare il tipo di archiviazione inserito in una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Come descritto in precedenza, verificare con la gestione dei record o reparti legali prima di rimuovere un'esenzione da una cassetta postale. 
  
 ### <a name="litigation-hold"></a>Conservazione in caso di dispute
  
Eseguire il seguente comando in Exchange Online PowerShell per rimuovere una conservazione per controversia legale dalla cassetta postale.

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Equivale a disattivare i metodi di accesso client e il ripristino di un singolo elemento, può richiedere fino a 60 minuti per rimuovere la conservazione per controversia legale. Non eliminare elementi dalla cartella elementi ripristinabili fino questo periodo di tempo. 
  
 ### <a name="in-place-hold"></a>Blocco sul posto
  
Eseguire il seguente comando in Exchange Online PowerShell per identificare l'archiviazione sul posto che viene inserito nella cassetta postale. Utilizzare il GUID per l'archiviazione sul posto identificato nel passaggio 1. 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
Dopo aver identificato In-Place Hold, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 applicati criteri di conservazione cassette postali specifiche
  
Eseguire il comando seguente in [protezione di Office 365 &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare il criterio di conservazione di Office 365 applicato alla cassetta postale. Utilizzare il GUID (escluso il `mbx` o `skp` prefisso) per il criterio di conservazione identificato nel passaggio 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
Dopo aver identificato i criteri di conservazione, passare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione identificato nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di conservazione. 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Criteri di conservazione a livello di organizzazione Office 365
  
Livello di organizzazione e i criteri di conservazione Exchange livello Office 365 vengono applicati a tutte le cassette postali nell'organizzazione. Vengono applicati a livello di organizzazione (non il livello delle cassette postali) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Eseguire il comando seguente in [protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione a livello di organizzazione Office 365. Utilizzare il GUID (escluso il `mbx` prefisso) per i criteri di conservazione a livello di organizzazione identificato nel passaggio 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Dopo aver identificato i criteri di conservazione a livello di organizzazione Office 365, passare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare ogni criterio di conservazione in tutta l'organizzazione è definito il precedente passaggio e aggiungere la cassetta postale per l'elenco dei destinatari esclusi. In questo modo verrà rimosso cassetta postale dell'utente dal criterio di conservazione. 

### <a name="office-365-retention-labels"></a>Etichette di conservazione di Office 365

Ogni volta che un utente applica un'etichetta è configurata per conservare il contenuto o mantenere e quindi eliminare il contenuto di una cartella o un elemento nella propria cassetta postale, le proprietà della cassetta postale *ComplianceTagHoldApplied* è impostata su **True**. In questo caso, la cassetta postale è considerata da in attesa, come se è stata inserita nella conservazione per controversia legale o assegnato a un criterio di conservazione di Office 365.

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il seguente comando in Exchange Online PowerShell:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Dopo aver identificato che una cassetta postale è in attesa perché un'etichetta di conservazione viene applicata a una cartella o un elemento, è possibile utilizzare lo strumento di ricerca del contenuto per la protezione e gli elementi con etichetta centro conformità effettuare una ricerca utilizzando la condizione di ricerca ComplianceTag. Per ulteriori informazioni, vedere la sezione "Criteri di ricerca" in [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Per ulteriori informazioni sulle etichette, vedere [Panoramica di Office 365 etichette](labels.md).

 ### <a name="ediscovery-case-holds"></a>contiene i casi eDiscovery
  
Eseguire i seguenti comandi [protezione &amp; PowerShell centro conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare la conservazione associata a un caso eDiscovery applicato alla cassetta postale. Utilizzare il GUID (escluso il `UniH` prefisso) per eDiscovery attesa identificato nel passaggio 1. Si noti che il secondo comando viene visualizzato il nome del caso eDiscovery che esenzione associata; il terzo comando viene visualizzato il nome dell'esenzione. 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

Dopo aver identificato il nome del caso eDiscovery e conservazione, passare al **ricerca &amp; indagini** \> pagina **eDiscovery** la protezione &amp; centro conformità, aprire il caso e rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [gestione dei casi di eDiscovery in Office 365 Security &amp; centro conformità](manage-ediscovery-cases.md).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Passaggio 4: Rimuovere la conservazione di ritardo dalla cassetta postale

Dopo la rimozione di qualsiasi tipo di attesa da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* è impostato su **True**. Questa operazione viene eseguita la volta successiva l'Assistente cartelle gestite elaborata la cassetta postale e rileva che è stata rimossa un'esenzione. Questo viene chiamato un *ritardo di attesa* e si intende che la rimozione effettiva dell'esenzione è ritardata per 30 giorni impedire che i dati vengano rimossi definitivamente dalla cassetta postale. (Lo scopo di un'esenzione ritardo deve fornire gli amministratori la possibilità di cercare o il ripristino di elementi delle cassette postali che verranno cancellati dopo la rimozione di un'esenzione).  Quando un'esenzione ritardo viene effettuata nella cassetta postale, la cassetta postale è ancora considerata in attesa per un periodo illimitato come se la cassetta postale è stata controversie legali. Dopo 30 giorni, scade la conservazione di ritardo e Office 365 verrà automaticamente tenta di rimuovere la conservazione di ritardo (impostando la proprietà *DelayHoldApplied* su **False**) in modo che la conservazione viene effettivamente rimosso. 

È possibile eliminare gli elementi nel passaggio 5, è necessario rimuovere la conservazione di ritardo dalla cassetta postale. Determinare innanzitutto se la conservazione di ritardo viene applicata alla cassetta postale eseguendo il comando seguente in Exchange Online PowerShell:

```
Get-Mailbox <username> | FL DelayHoldApplied
```

Se il valore della proprietà *DelayHoldApplied* è impostato su **False**, un ritardo è non stato sospeso sulla cassetta postale. È possibile procedere al passaggio 5 ed eliminare elementi nella cartella elementi ripristinabili.

Se il valore della proprietà *DelayHoldApplied* è impostato su **True**, eseguire il comando seguente per rimuovere la conservazione di ritardo:

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
Si noti che è necessario appartenere al ruolo giudiziari di Exchange Online utilizzare il parametro *RemoveDelayHoldApplied* .

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Passaggio 5: Eliminare gli elementi nella cartella elementi ripristinabili

A questo punto si è pronti per eliminare gli elementi nella cartella elementi ripristinabili effettivamente utilizzando il cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) in Exchange Online PowerShell. Sono disponibili tre opzioni quando si esegue il cmdlet **Search-Mailbox** . 
  
- Copiare gli elementi in una cassetta postale di destinazione prima di eliminarli in modo che è possibile esaminare gli elementi, se necessario, prima di eliminarli.
    
- Copiare gli elementi in una cassetta postale di destinazione ed eliminarle nello stesso comando.
    
- Eliminare gli elementi senza vengono copiati in una cassetta postale di destinazione. 
    
Si noti che gli elementi nella cartella elementi ripristinabili nella cassetta postale di archivio principale dell'utente verranno eliminati anche quando si esegue il * * Search-Mailbox * * cmdlet. Per evitare questo problema, è possibile includere l'opzione *DoNotIncludeArchive* . E come descritto in precedenza, se l'archiviazione l'espansione automatica è abilitata per la cassetta postale di * * Search-Mailbox * * cmdlet non elementi eliminati in una cassetta postale di archivio ausiliaria. Per ulteriori informazioni sull'espansione automatica archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md).
  
> [!NOTE]
> Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi. 
  
Nell'esempio seguente mostra la sintassi dei comandi per ognuna di queste opzioni. Utilizzano questi esempi di `-SearchQuery size>0` valore del parametro, che elimina tutti gli elementi da tutte le sottocartelle nella cartella elementi ripristinabili. Se si desidera eliminare solo gli elementi che soddisfano le condizioni specifiche, è possibile utilizzare anche il parametro *SearchQuery* consente di specificare altre condizioni, ad esempio l'oggetto di un messaggio o un intervallo di date. Vedere gli [altri esempi di utilizzo del parametro SearchQuery](#other-examples-of-using-the-searchquery-parameter) riportata di seguito. 
  
### <a name="example-1"></a>Esempio 1

In questo esempio copia tutti gli elementi nella cartella elementi ripristinabili dell'utente in una cartella di cassetta postale di individuazione dell'organizzazione. Consente di controllare gli elementi prima di eliminare definitivamente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

Nell'esempio precedente, non è necessario copiare gli elementi per la cassetta postale di individuazione. È possibile copiare i messaggi a qualsiasi cassetta postale di destinazione. Tuttavia, per impedire l'accesso ai dati delle cassette postali riservate, è consigliabile copiare messaggi in una cassetta postale che dispone dell'accesso limitato per il personale autorizzato. Per impostazione predefinita, l'accesso per la cassetta postale di individuazione predefinita è limitato ai membri del gruppo di ruoli gestione individuazione in Exchange Online. 
  
### <a name="example-2"></a>Esempio 2

In questo esempio copia tutti gli elementi nella cartella elementi ripristinabili dell'utente in una cartella nella cassetta postale di individuazione dell'organizzazione e quindi Elimina gli elementi dalla cartella elementi ripristinabili dell'utente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>Esempio 3

In questo esempio consente di eliminare tutti gli elementi nella cartella elementi ripristinabili dell'utente, senza copiarli una cassetta postale di destinazione. 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>Altri esempi di utilizzo del parametro SearchQuery

Di seguito sono forniti alcuni esempi dell'utilizzo del parametro *SearchQuery* per individuare i messaggi specifici. Se si utilizza il parametro *SearchQuery* consente di eseguire ricerche per gli elementi specifici, è consigliabile copiare i risultati della ricerca per una cassetta postale di destinazione in modo che sia possibile esaminare i risultati della ricerca e quindi modificare la query se necessario prima di eliminare i risultati della ricerca. 
  
In questo esempio restituisce i messaggi che contengono una frase specifica nel campo oggetto.
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

In questo esempio restituisce i messaggi inviati all'interno dell'intervallo di date specificato.
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
In questo esempio restituisce i messaggi inviati alla persona specificata.

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>Verificare che gli elementi sono stati eliminati

Per verificare che è stato eliminato elementi dalla cartella elementi recuperabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** di Exchange Online PowerShell per controllare le dimensioni e numero di elementi nella cartella elementi recuperabili. È possibile confrontare le statistiche con quelle che raccolte nel passaggio 1. 
  
Eseguire il comando seguente in per ottenere le dimensioni corrente e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale principale dell'utente. 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
Eseguire il comando seguente per ottenere le dimensioni e il numero totale di elementi in cartelle e le sottocartelle presenti nella cartella elementi ripristinabili nella cassetta postale di archivio dell'utente. 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Passaggio 6: Ripristinare la cassetta postale allo stato precedente

Il passaggio finale consiste nel ripristinare la cassetta postale torna alla configurazione precedente. Ciò significa reimpostazione le proprietà modificate nel passaggio 2 e la riapplicazione esenzioni rimosso nel passaggio 3. Includono:
  
- Modifica del periodo di mantenimento elementi eliminati sul valore precedente. In alternativa, è possibile lasciare questa impostazione per 30 giorni, il valore massimo di Exchange Online.
    
- Riabilitazione di ripristino di un singolo elemento.
    
- Riabilitazione di metodi di accesso client in modo che il proprietario può accedere alla cassetta postale.
    
- Riapplicazione le esenzioni e i criteri di conservazione Office 365 che sia stata rimossa.
    
- Riabilitazione Assistente cartelle gestite per elaborare la cassetta postale.
    
> [!IMPORTANT]
> È consigliabile attendere 24 ore dopo la riapplicazione un'esenzione o Office 365 retention policy (e verifica sul posto) prima che si riabilita l'Assistente cartelle gestite per elaborare la cassetta postale. 
  
Eseguire la procedura seguente (nella sequenza specificata) in Exchange Online PowerShell.
  
1. Esegui il comando seguente per modificare il periodo di mantenimento elementi eliminati eseguire il valore originale. Si presuppone che l'impostazione precedente è minore di 30 giorni. ad esempio 14 giorni. 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. Eseguire il comando seguente per abilitare di nuovo il ripristino di un singolo elemento.
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Eseguire il comando seguente per abilitare di nuovo tutti i metodi di accesso client per la cassetta postale.
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. Riapplicare le conservazioni rimosso nel passaggio 3. A seconda del tipo di attesa, utilizzare una delle procedure seguenti.
    
    **Conservazione in caso di dispute**
    
    Eseguire il comando seguente per abilitare di nuovo un conservazione per controversia legale per la cassetta postale.
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **Conservazione in locale**
    
    Utilizzare EAC (o Exchange Online PowerShell) per aggiungere la cassetta postale In-Place Hold. 
    
    **Office 365 applicati criteri di conservazione cassette postali specifiche**
    
    Utilizzare la protezione &amp; centro conformità per aggiungere la cassetta postale il criterio di conservazione di Office 365. Andare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione e aggiungere la cassetta postale all'elenco dei destinatari che viene applicato il criterio di conservazione. 
    
    **Criteri di conservazione a livello di organizzazione Office 365**
    
    Se è stato rimosso un livello di organizzazione o un criterio di conservazione di Exchange a livello escludendo dal criterio, quindi utilizzare la protezione &amp; centro conformità per rimuovere la cassetta postale dall'elenco di escludere gli utenti. Andare alla **governance data** \> pagina **conservazione** nel titolo &amp; centro conformità, modificare il criterio di conservazione a livello di organizzazione e rimuovere la cassetta postale dall'elenco dei destinatari esclusi. In questo modo applicherà nuovamente il criterio di conservazione cassetta postale dell'utente. 
    
    **contiene i casi eDiscovery**
    
    Utilizzare la protezione &amp; centro conformità per aggiungere la cassetta postale di eseguire il backup dell'esenzione associata a un caso eDiscovery. Visitare il **ricerca &amp; indagini** \> pagina **eDiscovery** la protezione &amp; centro conformità, aprire il caso e aggiungere la cassetta postale dell'esenzione. 
    
5. Eseguire il comando seguente per consentire l'Assistente cartelle gestite di elaborare nuovamente la cassetta postale. Come affermato in precedenza, è consigliabile attendere 24 ore dopo la riapplicazione un'esenzione o Office 365 retention policy (e verifica sul posto) prima che si riabilita l'Assistente cartelle gestite. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. Per verificare che la cassetta postale è stata ripristinata nuovamente la configurazione precedente, è possibile eseguire i comandi seguenti e quindi confrontare le impostazioni di quelle raccolte nel passaggio 1.

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>Ulteriori informazioni

Di seguito è riportata una tabella in cui viene illustrato come identificare i diversi tipi di conservazioni in base ai valori nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox** o **Get-OrganizationConfig** . Per ulteriori informazioni, vedere [come identificare il tipo di archiviazione inserito in una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Come precedentemente illustrato, è necessario rimuovere tutte le esenzioni e criteri di conservazione di Office 365 da una cassetta postale prima correttamente possono eliminare gli elementi nella cartella elementi ripristinabili. 
  
|**Tipo di blocco**|**Valore di esempio**|**Come identificare la conservazione**|
|:-----|:-----|:-----|
|Blocco per controversia legale  <br/> | `True` <br/> |La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.  <br/> |
|Blocco sul posto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La proprietà *InPlaceHolds* contiene il GUID In-Place Hold che viene inserito nella cassetta postale. È possibile stabilire che ciò avviene an In-Place Hold perché il GUID non inizia con un prefisso.<br/> È possibile utilizzare il comando  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL' comando in Exchange Online PowerShell per ottenere informazioni sull'archiviazione sul posto nella cassetta postale.  <br/> |
| Criteri di conservazione di Office 365 in sicurezza &amp; centro conformità applicate a determinate cassette postali  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oppure  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Quando si esegue il cmdlet **Get-Mailbox** , la proprietà *InPlaceHolds* contiene inoltre i GUID di Office 365 i criteri di conservazione applicati alla cassetta postale. È possibile identificare i criteri di conservazione in quanto il GUID inizia con la `mbx` prefisso. Si noti che se il GUID del criterio di conservazione inizia con la `skp` prefisso, che indica che viene applicato il criterio di conservazione Skype per le conversazioni di Business.<br/> Al criterio di conservazione identità Office 365 applicato alla cassetta postale, eseguire il comando seguente in sicurezza &amp; PowerShell centro conformità: <br/> <br/>"Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nome FL`<br/><br/>Be sure to remove the  `mbx` or  `skp' quando si esegue questo comando.  <br/> |
|Criteri di conservazione a livello di organizzazione Office 365 in sicurezza &amp; centro conformità  <br/> |Nessun valore  <br/> oppure  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica che la cassetta postale è escluso da un criterio a livello di organizzazione)  <br/> |Anche se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , ancora potrebbero verificarsi uno o più a livello di organizzazione Office 365 criteri di conservazione applicati alla cassetta postale.  <br/> Per verificare questa impostazione, è possibile eseguire il "Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy<retention policy GUID without prefix> | Nome FL`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `mbx -`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696' <br/> |
|caso di eDiscovery attesa nella protezione &amp; centro conformità  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La proprietà *InPlaceHolds* contiene anche il GUID di qualsiasi sospensione associata a un caso eDiscovery in sicurezza &amp; centro conformità che può essere messa sulla cassetta postale. È possibile sapere si tratta di un'esenzione casi di eDiscovery in quanto il GUID inizia con la `UniH` prefisso.<br/> È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in sicurezza &amp; PowerShell centro conformità per ottenere informazioni relative al caso eDiscovery esenzione sulla cassetta postale associata. Ad esempio, è possibile eseguire il comando "Get-CaseHoldPolicy<hold GUID without prefix> | Nome FL` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`$CaseHold.CaseId Get-ComplianceCase | Nome FL'


