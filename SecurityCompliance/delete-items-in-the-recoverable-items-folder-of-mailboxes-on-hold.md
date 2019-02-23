---
title: Eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa-Guida per l'amministratore
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 'Per gli amministratori: eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa legale. Si tratta di un modo efficace per eliminare i dati che sono stati accidentalmente riversati in Office 365.'
ms.openlocfilehash: f3518dc1009b4e95472473f76e6cd41011bc6b3e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216956"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>Eliminare gli elementi nella cartella elementi ripristinabili delle cassette postali basate sul cloud in attesa-Guida per l'amministratore

La cartella elementi ripristinabili per una cassetta postale di Exchange Online esiste per proteggere da eliminazioni accidentali o dannose. Viene inoltre utilizzato per archiviare gli elementi conservati e accessibili dalle funzionalità di conformità di Office 365, ad esempio le ricerche di eDiscovery e le esenzioni. Tuttavia, in alcune situazioni le organizzazioni potrebbero avere dati che sono stati inavvertitamente conservati nella cartella elementi ripristinabili che devono essere eliminati. Ad esempio, un utente potrebbe inconsapevolmente inviare o inoltrare un messaggio di posta elettronica contenente informazioni riservate o informazioni che potrebbero avere gravi conseguenze per le aziende. Anche se il messaggio è stato eliminato definitivamente, potrebbe essere conservato per un periodo di tempo indefinito perché nella cassetta postale è stata inserita una conservazione legale. Questo scenario è noto come versamento dei dati poiché i dati sono stati inavvertitamente riversati in Office 365. In questi casi, è possibile eliminare gli elementi nella cartella elementi ripristinabili di un utente per una cassetta postale di Exchange Online, anche se la cassetta postale è in attesa con una delle diverse funzionalità di archiviazione di Office 365. Questi tipi di esenzioni includono la conservazione per controversia legale, le esenzioni sul posto, le esenzioni eDiscovery e i criteri di mantenimento &amp; di Office 365 creati nel centro sicurezza e conformità di Office 365. 
  
 In questo articolo viene illustrato come eliminare gli elementi dalla cartella elementi ripristinabili per le cassette postali basate sul cloud che sono in attesa. Questa procedura comporta la disattivazione dell'accesso alla cassetta postale e la disabilitazione del ripristino di un singolo elemento, la disattivazione dell'Assistente cartelle gestite dall'elaborazione della cassetta postale, la rimozione temporanea del blocco, l'eliminazione degli elementi dalla cartella elementi ripristinabili e il ripristino la cassetta postale alla configurazione precedente. Ecco il processo: 
  
[Passaggio 1: raccogliere informazioni sulla cassetta postale](#step-1-collect-information-about-the-mailbox)

[Passaggio 2: preparare la cassetta postale](#step-2-prepare-the-mailbox)

[Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale](#step-3-remove-all-holds-from-the-mailbox)

[Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale](#step-4-remove-the-delay-hold-from-the-mailbox)

[Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili](#step-5-delete-items-in-the-recoverable-items-folder)

[Passaggio 6: ripristinare lo stato precedente della cassetta postale](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Le procedure descritte in questo articolo determinano l'eliminazione definitiva (eliminata) dei dati da una cassetta postale di Exchange Online. Questo significa che i messaggi eliminati dalla cartella elementi ripristinabili non possono essere recuperati e non saranno disponibili per la ricerca legale o per altri scopi di conformità. Se si desidera eliminare i messaggi da una cassetta postale che viene mantenuta come parte di un blocco per controversia legale, archiviazione sul posto, blocco di eDiscovery o criteri di conservazione di Office 365 creati nel centro &amp; sicurezza e conformità di Office 365, consultare la sezione gestione dei record o legale reparti prima di rimuovere il blocco. È possibile che l'organizzazione disponga di un criterio che definisce se una cassetta postale in attesa o un evento di perdita dei dati ha la priorità. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnati entrambi i ruoli di gestione seguenti in Exchange Online per cercare ed eliminare i messaggi dalla cartella elementi ripristinabili nel passaggio 5.
    
  - **Ricerca cassette** postali-questo ruolo consente di effettuare ricerche nelle cassette postali dell'organizzazione. Per impostazione predefinita, gli amministratori di Exchange non sono assegnati a questo ruolo. Per assegnare manualmente questo ruolo, aggiungersi come membro del gruppo di ruoli Gestione individuazione in Exchange Online. 
    
  - **Esportazione delle cassette postali** -questo ruolo consente di eliminare i messaggi dalla cassetta postale di un utente. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli. Per eliminare i messaggi dalle cassette postali degli utenti, è possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. 
    
- La procedura descritta in questo articolo non è supportata per le cassette postali inattive. Ciò è dovuto al fatto che non è possibile riapplicare un blocco (o un criterio di conservazione di Office 365) a una cassetta postale inattiva dopo averlo rimosso. Quando si rimuove un'esenzione da una cassetta postale inattiva, viene modificata in una normale cassetta postale eliminata temporaneamente e viene eliminata definitivamente dall'organizzazione dopo che è stata elaborata dall'Assistente cartelle gestite.
    
- Non è possibile eseguire questa procedura per una cassetta postale che è stata assegnata a un criterio di conservazione di Office 365 che è stato bloccato con un blocco di conservazione. Ciò è dovuto al fatto che un blocco di conservazione impedisce di rimuovere o escludere la cassetta postale dal criterio di conservazione di Office 365 e di disabilitare l'Assistente cartelle gestite nella cassetta postale. Per ulteriori informazioni sul blocco dei criteri di conservazione, vedere [Locking a Retention Policy](retention-policies.md#locking-a-retention-policy).
    
- Se non si dispone di una cassetta postale in attesa (o se non è stato abilitato il ripristino di un singolo elemento), è possibile eliminare gli elementi dalla cartella elementi ripristinabili. Per ulteriori informazioni su come eseguire questa operazione, vedere [cercare ed eliminare i messaggi ](https://go.microsoft.com/fwlink/?linkid=852453).
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Passaggio 1: raccogliere informazioni sulla cassetta postale

Questo primo passaggio consiste nel raccogliere le proprietà selezionate dalla cassetta postale di destinazione che influenzerà questa procedura. Assicurarsi di annotare queste impostazioni o salvarle in un file di testo, perché si modificheranno alcune di queste proprietà e quindi si tornerà ai valori originali del passaggio 6, dopo aver eliminato gli elementi dalla cartella elementi ripristinabili. Ecco un elenco delle proprietà della cassetta postale che è necessario raccogliere.
  
-  *SingleItemRecoveryEnabled* e *RetainDeletedItemsFor* ; Se necessario, è possibile disabilitare il ripristino singolo e aumentare il periodo di conservazione degli elementi eliminati nel passaggio 3. 
    
-  *LitigationHoldEnabled* e *InPlaceHolds* ; è necessario identificare tutti gli appigli posizionati nella cassetta postale in modo da poterli rimuovere temporaneamente nel passaggio 3. Vedere la sezione [ulteriori informazioni](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale. 
    
Inoltre, è necessario ottenere le impostazioni di accesso client delle cassette postali in modo da poterle disabilitare temporaneamente in modo che il proprietario (o altri utenti) non riesca ad accedere alla cassetta postale durante questa procedura. Infine, è possibile ottenere la dimensione corrente e il numero di elementi nella cartella elementi ripristinabili. Dopo aver eliminato gli elementi nella cartella elementi ripristinabili nel passaggio 5, è possibile utilizzare queste informazioni per verificare che gli elementi siano stati effettivamente rimossi.
  
1. [Connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Assicurarsi di utilizzare un nome utente e una password per un account amministratore a cui sono stati assegnati i ruoli di gestione idonei in Exchange Online. 
    
2. Eseguire il seguente comando per ottenere informazioni sul ripristino di un singolo elemento e sul periodo di conservazione degli elementi eliminati.

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Se il ripristino di un singolo elemento è abilitato, è necessario disattivarlo nel passaggio 2. Se il periodo di conservazione degli elementi eliminati non è impostato per 30 giorni (il valore massimo in Exchange Online), è possibile aumentarlo nel passaggio 2. 
    
3. Eseguire il seguente comando per ottenere le impostazioni di accesso alle cassette postali per la cassetta postale. 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Nel passaggio 2 vengono disattivati tutti questi metodi di accesso.
    
4. Eseguire il seguente comando per ottenere informazioni sulle esenzioni e sui criteri di conservazione di Office 365 applicati alla cassetta postale.
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta. 
  
5. Eseguire il seguente comando per ottenere informazioni su tutti i criteri di conservazione di Office 365 a livello di organizzazione. 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   Se l'organizzazione dispone di criteri di conservazione di Office 365 a livello di organizzazione, sarà necessario escludere la cassetta postale da questi criteri nel passaggio 3.

   > [!TIP]
    > Se nella proprietà *InPlaceHolds* sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni valore su una riga distinta. 
  
6. Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente. 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Se la cassetta postale di archiviazione dell'utente è abilitata, eseguire il comando riportato di seguito per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione. 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Quando si eliminano gli elementi nel passaggio 5, è possibile scegliere di eliminare o non eliminare gli elementi nella cartella elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente. Se per la cassetta postale è abilitata l'archiviazione con espansione automatica, gli elementi in una cassetta postale di archiviazione ausiliaria non verranno eliminati.
  
## <a name="step-2-prepare-the-mailbox"></a>Passaggio 2: preparare la cassetta postale

Dopo aver raccolto e salvato le informazioni sulla cassetta postale, il passaggio successivo consiste nel preparare la cassetta postale eseguendo le attività seguenti: 
  
- **Disabilitare l'accesso client alla cassetta postale** , in modo che il proprietario della cassetta postale non possa accedere alla propria cassetta postale e apportare le modifiche ai dati della cassetta postale durante questa procedura. 
    
- **Aumentare il periodo di conservazione degli elementi eliminati** fino a 30 giorni (il valore massimo in Exchange Online), in modo che gli elementi non vengano eliminati dalla cartella elemento ripristinabile prima di poterli eliminare nel passaggio 5. 
    
- **Disabilitare il ripristino di un singolo elemento** in modo che gli elementi non vengano conservati (per la durata del periodo di conservazione degli elementi eliminati) dopo averli eliminati dalla cartella elementi ripristinabili nel passaggio 5. 
    
- **Disabilitare l'Assistente cartelle gestite** in modo che non elabori la cassetta postale e mantenga gli elementi eliminati nel passaggio 5. 
    
Eseguire le operazioni seguenti in PowerShell di Exchange Online.
  
1. Eseguire il seguente comando per disabilitare tutti gli accessi client alla cassetta postale. La sintassi del comando presuppone che tutti i metodi di accesso client siano stati abilitati nella cassetta postale.

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > Per disabilitare tutti i metodi di accesso client alla cassetta postale, potrebbero essere necessari fino a 60 minuti. Si noti che la disabilitazione di questi metodi di accesso non disconnetterà il proprietario della cassetta postale a cui è attualmente connesso. Se il proprietario non ha eseguito l'accesso, non sarà in grado di accedere alla propria cassetta postale dopo che questi metodi di accesso sono stati disabilitati. 
  
2. Eseguire il seguente comando per aumentare il periodo di conservazione degli elementi eliminati per un massimo di 30 giorni. Si presuppone che l'impostazione corrente sia inferiore a 30 giorni. 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Per disabilitare il ripristino di un singolo elemento, eseguire il comando riportato di seguito.
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > Per disabilitare il ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti. Non eliminare gli elementi nella cartella elementi ripristinabili fino a quando non è trascorso questo periodo. 
  
4. Eseguire il seguente comando per evitare che l'Assistente cartelle gestite esegua l'elaborazione della cassetta postale. Come spiegato in precedenza, è possibile disabilitare l'Assistente cartelle gestite solo se un criterio di conservazione di Office 365 con un blocco di conservazione non viene applicato alla cassetta postale. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Passaggio 3: rimuovere tutte le esenzioni dalla cassetta postale

L'ultimo passaggio prima di poter eliminare gli elementi dalla cartella elementi ripristinabili consiste nel rimuovere tutte le esenzioni (identificate nel passaggio 1) inserite nella cassetta postale. Tutte le esenzioni devono essere rimosse in modo che gli elementi non vengano conservati dopo averli eliminati dalla cartella elementi ripristinabili. Nelle sezioni seguenti sono contenute informazioni sulla rimozione di diversi tipi di esenzioni su una cassetta postale. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti su come identificare il blocco dei tipi che potrebbe essere posizionato su una cassetta postale. Per ulteriori informazioni, vedere [come identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Come indicato in precedenza, consultare la gestione dei record o i reparti giuridici prima di rimuovere un'esenzione da una cassetta postale. 
  
 ### <a name="litigation-hold"></a>Conservazione in caso di dispute
  
Eseguire il seguente comando in Exchange Online PowerShell per rimuovere un blocco per controversia legale dalla cassetta postale.

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> Analogamente alla disattivazione dei metodi di accesso client e del ripristino di un singolo elemento, potrebbero essere necessari fino a 60 minuti per rimuovere il blocco per controversia legale. Non eliminare gli elementi dalla cartella elementi ripristinabili fino a quando non è trascorso questo periodo. 
  
 ### <a name="in-place-hold"></a>Blocco sul posto
  
Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco sul posto applicato alla cassetta postale. Utilizzare il GUID per il blocco sul posto identificato nel passaggio 1. 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
Dopo aver identificato il blocco sul posto, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o Exchange Online PowerShell per rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [creare o rimuovere un blocco sul posto](https://go.microsoft.com/fwlink/?linkid=852668).
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Criteri di conservazione di Office 365 applicati a cassette postali specifiche
  
Eseguire il seguente comando in [PowerShell per il &amp; Centro sicurezza e conformità di Office 365](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale. Utilizzare il GUID (escluso il `mbx` prefisso `skp` o) per i criteri di conservazione identificati nel passaggio 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
Dopo aver identificato il criterio di conservazione, passare alla pagina **conservazione** **Data Governance** \> nel centro &amp; sicurezza e conformità, modificare i criteri di conservazione identificati nel passaggio precedente e rimuovere la cassetta postale dall'elenco dei destinatari inclusi nel criterio di conservazione. 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Criteri di conservazione di Office 365 a livello di organizzazione
  
I criteri di conservazione di Office 365 a livello di organizzazione e di Exchange sono applicati a tutte le cassette postali dell'organizzazione. Vengono applicati a livello di organizzazione (non a livello di cassetta postale) e vengono restituiti quando si esegue il cmdlet **Get-OrganizationConfig** nel passaggio 1. Eseguire il seguente comando in [PowerShell &amp; per il Centro sicurezza e conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare i criteri di conservazione di Office 365 a livello dell'organizzazione. Utilizzare il GUID (escluso il `mbx` prefisso) per i criteri di conservazione a livello dell'organizzazione identificati nel passaggio 1. 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

dopo aver identificato i criteri di conservazione di Office 365 a livello di organizzazione, passare alla pagina \> **conservazione** governance &amp; **data** nel centro sicurezza e conformità, modificare tutti i criteri di conservazione a livello di organizzazione identificati nell' passaggio precedente e aggiungere la cassetta postale all'elenco dei destinatari esclusi. In questo modo, la cassetta postale dell'utente verrà rimossa dal criterio di conservazione. 

### <a name="office-365-retention-labels"></a>Etichette di conservazione di Office 365

Ogni volta che un utente applica un'etichetta configurata per mantenere il contenuto o mantenere e quindi eliminare il contenuto in una cartella o un elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* viene impostata su **true**. In questo caso, la cassetta postale viene considerata attiva, come se fosse stata inserita in una conservazione per controversia legale o assegnata a un criterio di ritenzione di Office 365.

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il comando seguente in PowerShell di Exchange Online:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Dopo aver identificato che una cassetta postale è in attesa perché viene applicata un'etichetta di conservazione a una cartella o a un elemento, è possibile utilizzare lo strumento di ricerca contenuto nel centro sicurezza & Compliance per cercare gli elementi contrassegnati utilizzando la condizione di ricerca di ComplianceTag. Per ulteriori informazioni, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Per ulteriori informazioni sulle etichette, vedere [Overview of Office 365 labels](labels.md).

 ### <a name="ediscovery-case-holds"></a>blocco del caso di eDiscovery
  
Eseguire i seguenti comandi in [PowerShell &amp; per il Centro sicurezza e conformità](https://go.microsoft.com/fwlink/?linkid=627084) per identificare il blocco associato a un caso di eDiscovery applicato alla cassetta postale. Utilizzare il GUID (escluso il `UniH` prefisso) per il blocco eDiscovery identificato nel passaggio 1. Si noti che il secondo comando Visualizza il nome del caso di eDiscovery a cui è associato il blocco. il terzo comando Visualizza il nome dell'esenzione. 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

Dopo aver identificato il nome del caso eDiscovery e il blocco, passare alla pagina \> **analisi ricerca &amp; ** **eDiscovery** nel centro sicurezza &amp; e conformità, aprire il caso e rimuovere la cassetta postale dall'esenzione. Per ulteriori informazioni, vedere [gestire i casi di eDiscovery nel centro sicurezza &amp; e conformità di Office 365](manage-ediscovery-cases.md).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Passaggio 4: rimuovere la sospensione di ritardo dalla cassetta postale

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* è impostato su **true**. Questo problema si verifica quando l'Assistente cartelle gestite elabora la cassetta postale e rileva che è stata rimossa un'esenzione. Si tratta di un *blocco di ritardo* che indica che la rimozione effettiva del blocco viene posticipata di 30 giorni per evitare che i dati vengano eliminati definitivamente dalla cassetta postale. Lo scopo di un blocco di ritardo consiste nell'assegnare agli amministratori la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un'esenzione.  Quando viene immessa una conservazione per la cassetta postale, la cassetta postale è ancora considerata attiva per una durata illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, scade il ritardo e Office 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà *DelayHoldApplied* su **false**) in modo che il blocco venga effettivamente rimosso. 

Prima di poter eliminare gli elementi nel passaggio 5, è necessario rimuovere il blocco di ritardo dalla cassetta postale. Per prima cosa, determinare se il blocco di ritardo viene applicato alla cassetta postale eseguendo il comando seguente in PowerShell di Exchange Online:

```
Get-Mailbox <username> | FL DelayHoldApplied
```

Se il valore della proprietà *DelayHoldApplied* è impostato su **false**, nella cassetta postale non è stato applicato un blocco di ritardo. È possibile passare al passaggio 5 ed eliminare gli elementi nella cartella elementi ripristinabili.

Se il valore della proprietà *DelayHoldApplied* è impostato su **true**, eseguire il comando riportato di seguito per rimuovere il blocco di ritardo:

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
Tenere presente che è necessario essere assegnati al ruolo di blocco legale in Exchange Online per utilizzare il parametro *RemoveDelayHoldApplied* .

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Passaggio 5: eliminare gli elementi nella cartella elementi ripristinabili

A questo punto si è pronti per eliminare effettivamente gli elementi nella cartella elementi ripristinabili utilizzando il cmdlet [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) in Exchange Online PowerShell. Quando si esegue il cmdlet **Search-Mailbox** , sono disponibili tre opzioni. 
  
- Copiare gli elementi in una cassetta postale di destinazione prima di eliminarli in modo da poter esaminare gli elementi, se necessario, prima di eliminarli.
    
- Copiare gli elementi in una cassetta postale di destinazione ed eliminarli nello stesso comando.
    
- Eliminare gli elementi senza copiarli in una cassetta postale di destinazione. 
    
Tenere presente che gli elementi nella cartella elementi ripristinabili nella cassetta postale di archiviazione principale dell'utente verranno eliminati anche quando si esegue il cmdlet **Search-Mailbox** . Per evitare questo, è possibile includere l'opzione *DoNotIncludeArchive* . Come indicato in precedenza, se l'archiviazione con espansione automatica è abilitata per la cassetta postale, il cmdlet * * Search-Mailbox * * non elimina gli elementi in una cassetta postale di archiviazione ausiliaria. Per ulteriori informazioni sull'espansione automatica dell'archivio, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).
  
> [!NOTE]
> Se si include una query di ricerca (usando il parametro  *SearchQuery*  ), il cmdlet **Search-Mailbox** restituirà un massimo di 10.000 elementi nei risultati della ricerca. Pertanto se si include una query di ricerca, potrebbe essere necessario eseguire il comando **Search-Mailbox** più volte per eliminare più di 10.000 elementi. 
  
Negli esempi seguenti viene illustrata la sintassi dei comandi per ognuna di queste opzioni. In questi esempi viene `-SearchQuery size>0` utilizzato il valore del parametro, che consente di eliminare tutti gli elementi da tutte le sottocartelle nella cartella elementi ripristinabili. Se è necessario eliminare solo gli elementi che soddisfano condizioni specifiche, è anche possibile utilizzare il parametro *SearchQuery* per specificare altre condizioni, ad esempio l'oggetto di un messaggio o un intervallo di date. Per ulteriori informazioni, vedere gli [altri esempi di utilizzo del parametro SearchQuery](#other-examples-of-using-the-searchquery-parameter) . 
  
### <a name="example-1"></a>Esempio 1

In questo esempio vengono copiati tutti gli elementi della cartella elementi ripristinabili dell'utente in una cartella della cassetta postale di individuazione dell'organizzazione. In questo modo è possibile esaminare gli elementi prima di eliminarli definitivamente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

Nell'esempio precedente, non è necessario copiare gli elementi nella cassetta postale di ricerca di individuazione. È possibile copiare i messaggi in tutte le cassette postali di destinazione. Tuttavia, per impedire l'accesso ai dati delle cassette postali potenzialmente sensibili, è consigliabile copiare i messaggi in una cassetta postale che ha accesso limitato a personale autorizzato. Per impostazione predefinita, l'accesso alla cassetta postale di ricerca di individuazione predefinita è limitato ai membri del gruppo di ruoli Gestione individuazione in Exchange Online. 
  
### <a name="example-2"></a>Esempio 2

In questo esempio vengono copiati tutti gli elementi della cartella elementi ripristinabili dell'utente in una cartella della cassetta postale di individuazione dell'organizzazione e quindi vengono eliminati gli elementi dalla cartella elementi ripristinabili dell'utente.

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>Esempio 3

In questo esempio vengono eliminati tutti gli elementi nella cartella elementi ripristinabili dell'utente, senza copiarli in una cassetta postale di destinazione. 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>Altri esempi di utilizzo del parametro SearchQuery

Di seguito sono riportati alcuni esempi di utilizzo del parametro *SearchQuery* per trovare messaggi specifici. Se si utilizza il parametro *SearchQuery* per cercare elementi specifici, è consigliabile copiare i risultati della ricerca in una cassetta postale di destinazione in modo che sia possibile esaminare i risultati della ricerca e quindi rivedere la query se necessario prima di eliminare i risultati di una ricerca. 
  
In questo esempio vengono restituiti i messaggi che contengono una frase specifica nel campo Subject.
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

In questo esempio vengono restituiti i messaggi che sono stati inviati entro l'intervallo di date specificato.
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
In questo esempio vengono restituiti i messaggi che sono stati inviati alla persona specificata.

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>Verificare che gli elementi siano stati eliminati

Per verificare la corretta eliminazione degli elementi dalla cartella elementi ripristinabili di una cassetta postale, utilizzare il cmdlet **Get-MailboxFolderStatistics** in PowerShell di Exchange Online per controllare la dimensione e il numero di elementi nella cartella elementi ripristinabili. È possibile confrontare queste statistiche con quelle raccolte nel passaggio 1. 
  
Eseguire il seguente comando per ottenere la dimensione corrente e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale principale dell'utente. 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
Eseguire il seguente comando per ottenere le dimensioni e il numero totale di elementi nelle cartelle e nelle sottocartelle della cartella elementi ripristinabili nella cassetta postale di archiviazione dell'utente. 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Passaggio 6: ripristinare lo stato precedente della cassetta postale

Il passaggio finale consiste nel ripristinare la configurazione precedente della cassetta postale. Questo significa reimpostare le proprietà modificate nel passaggio 2 e riapplicare le esenzioni rimosse al passaggio 3. Sono inclusi i seguenti:
  
- Modifica del periodo di conservazione degli elementi eliminati sul valore precedente. In alternativa, è possibile lasciare questo set a 30 giorni, ovvero il valore massimo in Exchange Online.
    
- Riattivazione del ripristino di un singolo elemento.
    
- Riattivare i metodi di accesso client in modo che il proprietario possa accedere alla propria cassetta postale.
    
- Riapplicare le esenzioni e i criteri di conservazione di Office 365 rimossi.
    
- Riattivare l'Assistente cartelle gestite per elaborare la cassetta postale.
    
> [!IMPORTANT]
> È consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione di Office 365 (e verificare che sia sul posto) prima di riabilitare l'Assistente cartelle gestite per elaborare la cassetta postale. 
  
Eseguire i passaggi seguenti (nella sequenza specificata) in PowerShell di Exchange Online.
  
1. Eseguire il seguente comando per ripristinare il valore originale del periodo di conservazione degli elementi eliminati. Si presuppone che l'impostazione precedente sia inferiore a 30 giorni. ad esempio, 14 giorni. 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. Eseguire il seguente comando per riattivare il ripristino di un singolo elemento.
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Eseguire il seguente comando per riabilitare tutti i metodi di accesso client alla cassetta postale.
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. Riapplicare le esenzioni rimosse nel passaggio 3. A seconda del tipo di blocco, utilizzare una delle procedure seguenti.
    
    **Conservazione in caso di dispute**
    
    Eseguire il seguente comando per riattivare un blocco per controversia legale per la cassetta postale.
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **Conservazione in locale**
    
    Utilizzare EAC (o Exchange Online PowerShell) per aggiungere di nuovo la cassetta postale all'archiviazione sul posto. 
    
    **Criteri di conservazione di Office 365 applicati a cassette postali specifiche**
    
    Utilizzare il centro &amp; sicurezza e conformità per aggiungere di nuovo la cassetta postale ai criteri di conservazione di Office 365. Passare alla pagina **** \> **conservazione** governance data nel centro sicurezza &amp; e conformità, modificare il criterio di conservazione e aggiungere di nuovo la cassetta postale all'elenco dei destinatari a cui è applicato il criterio di conservazione. 
    
    **Criteri di conservazione di Office 365 a livello di organizzazione**
    
    Se è stato rimosso un criterio di conservazione a livello di organizzazione o a livello di Exchange, escluderlo dal criterio, utilizzare &amp; il Centro sicurezza e conformità per rimuovere la cassetta postale dall'elenco degli utenti esclusi. Passare alla pagina **** \> **conservazione** governance data nel centro sicurezza &amp; e conformità, modificare il criterio di conservazione a livello dell'organizzazione e rimuovere la cassetta postale dall'elenco dei destinatari esclusi. In questo modo verrà applicato di nuovo il criterio di conservazione alla cassetta postale dell'utente. 
    
    **blocco del caso di eDiscovery**
    
    Utilizzare il centro &amp; sicurezza e conformità per aggiungere la cassetta postale che è associata a un caso di eDiscovery. Passare alla pagina **analisi &amp; ** \> di ricerca di **eDiscovery** nel centro &amp; sicurezza e conformità, aprire il caso e riaggiungere la cassetta postale all'esenzione. 
    
5. Eseguire il seguente comando per consentire all'Assistente cartelle gestite di elaborare di nuovo la cassetta postale. Come indicato in precedenza, è consigliabile attendere 24 ore dopo la riapplicazione di un blocco o un criterio di conservazione di Office 365 (e verificare che sia sul posto) prima di abilitare di nuovo l'Assistente cartelle gestite. 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. Per verificare che la cassetta postale sia stata ripristinata alla configurazione precedente, è possibile eseguire i comandi seguenti e quindi confrontare le impostazioni con quelle raccolte nel passaggio 1.

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>Ulteriori informazioni

Di seguito viene riportata una tabella in cui viene descritto come identificare diversi tipi di esenzioni in base ai valori della proprietà *InPlaceHolds* quando si eseguono i cmdlet **Get-Mailbox** o **Get-OrganizationConfig** . Per informazioni più dettagliate, vedere [How to identificare il tipo di blocco posizionato su una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Come spiegato in precedenza, è necessario rimuovere tutte le esenzioni e i criteri di conservazione di Office 365 da una cassetta postale prima di poter eliminare correttamente gli elementi nella cartella elementi ripristinabili. 
  
|**Tipo di blocco**|**Valore di esempio**|**Come identificare il blocco**|
|:-----|:-----|:-----|
|Blocco per controversia legale  <br/> | `True` <br/> |La proprietà  *LitigationHoldEnabled*  è impostata su  `True`.  <br/> |
|Blocco sul posto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La proprietà *InPlaceHolds* contiene il GUID del blocco sul posto applicato alla cassetta postale. È possibile indicare che si tratta di un blocco sul posto poiché il GUID non inizia con un prefisso.<br/> È possibile utilizzare il `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando in PowerShell di Exchange Online per ottenere informazioni sul blocco sul posto sulla cassetta postale.  <br/> |
| Criteri di conservazione di Office 365 nel &amp; centro conformità di sicurezza applicato a cassette postali specifiche  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> oppure  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Quando si esegue il cmdlet **Get-Mailbox** , la proprietà *InPlaceHolds* contiene anche i GUID dei criteri di conservazione di Office 365 applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia `mbx` con il prefisso. Si noti che se il GUID del criterio di conservazione inizia con `skp` il prefisso, indica che il criterio di conservazione viene applicato alle conversazioni di Skype for business.<br/> Per identificare i criteri di conservazione di Office 365 applicati alla cassetta postale, eseguire il comando seguente in PowerShell &amp; per il Centro sicurezza e conformità: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Assicurarsi di rimuovere il `mbx` prefisso o `skp` quando si esegue questo comando.  <br/> |
|Criteri di conservazione di Office 365 a livello di organizzazione &amp; nel centro sicurezza e conformità  <br/> |Nessun valore  <br/> oppure  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(indica che la cassetta postale è esclusa da un criterio a livello di organizzazione)  <br/> |Anche se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è ancora possibile che siano presenti uno o più criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale.  <br/> Per verificarlo, è possibile eseguire il `Get-OrganizationConfig | FL InPlaceHolds` comando in Exchange Online PowerShell per ottenere un elenco dei GUID per i criteri di conservazione di Office 365 a livello dell'organizzazione. Il GUID per i criteri di conservazione a livello dell'organizzazione applicati alle cassette postali di Exchange inizia con il `mbx` prefisso. ad esempio `mbxa3056bb15562480fadb46ce523ff7b02`.<br/> Per identificare i criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale, eseguire il comando seguente in &amp; PowerShell per il Centro sicurezza e conformità: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Si noti che se una cassetta postale è stata esclusa da un criterio di conservazione di Office 365 a livello di organizzazione, il GUID per il criterio di conservazione viene visualizzato nella proprietà *InPlaceHolds* della cassetta postale dell'utente quando si esegue il cmdlet **Get-Mailbox** . è identificato dal prefisso `-mbx`; Per esempio`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|blocco del caso di eDiscovery nel &amp; Centro sicurezza e conformità  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La proprietà *InPlaceHolds* contiene inoltre il GUID di qualsiasi blocco associato a un caso di eDiscovery nel centro &amp; sicurezza e conformità che potrebbe essere posizionato sulla cassetta postale. Si può dire che si tratta di un caso di eDiscovery, perché il GUID `UniH` inizia con il prefisso.<br/> È possibile utilizzare il `Get-CaseHoldPolicy` cmdlet in PowerShell &amp; per la conformità al centro sicurezza per ottenere informazioni sul caso di eDiscovery a cui è associato il blocco della cassetta postale. Ad esempio, è possibile eseguire il comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` per visualizzare il nome del blocco del caso che si trova nella cassetta postale. Assicurarsi di rimuovere il `UniH` prefisso quando si esegue questo comando.<br/><br/> Per identificare il caso di eDiscovery a cui è associato il blocco della cassetta postale, eseguire i comandi seguenti:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


