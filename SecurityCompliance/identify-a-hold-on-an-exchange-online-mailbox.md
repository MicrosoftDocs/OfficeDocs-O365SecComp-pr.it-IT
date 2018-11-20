---
title: Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Informazioni su come identificare i diversi tipi di attesa può essere messa in una cassetta postale di Office 365. Questi tipi di conservazioni includono i criteri di conservazione Office 365, esenzioni eDiscovery e conservazione per controversia legale. È inoltre possibile determinare se un utente è stato escluso da un criterio di conservazione a livello di organizzazione
ms.openlocfilehash: 1572b34d3f9abef2fb922fc9b01d1f5a27fcdf7b
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026513"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online

In questo articolo viene illustrato come identificare le esenzioni effettuate sulle cassette postali di Exchange Online in Office 365.

Office 365 sono disponibili diversi modi in cui l'organizzazione può impedire che contenuto delle cassette postali vengono eliminati definitivamente. Consente all'organizzazione di conservare il contenuto per soddisfare regulars conformità o per la durata dell'ufficio legale o altri tipi di indagini. Ecco un elenco delle funzionalità conservazione (anche denominato *contiene*) di Office 365:

- **Conservazione per controversia legale** - esenzioni applicate a cassette postali degli utenti in Exchange Online.

- **conservazione eDiscovery** - esenzioni associati a un caso eDiscovery nel centro conformità sicurezza. eDiscovery esenzioni applicabili alle cassette postali utente e la corrispondente cassetta postale per gruppi di Office 365 e Microsoft Teams.

- **In-Place Hold** - esenzioni applicate a cassette postali degli utenti tramite la ricerca eDiscovery In dello strumento di conservazione in Exchange admin center in Exchange Online.

- **Criterio di conservazione di office 365** - consente di conservare il contenuto nelle cassette postali utente in Exchange Online e la corrispondente cassetta postale per gruppi di Office 365 e Microsoft Teams. È possibile creare una conservazione criteri mantiene Skype per le conversazioni di Business, che vengono archiviati in cassette postali degli utenti.

  Esistono due tipi di criteri di conservazione di Office 365 che possono essere assegnati alle cassette postali.

    - **I criteri di conservazione posizione specifica** - queste sono i criteri assegnati per i percorsi di contenuto di utenti specifici. Utilizzare il cmdlet **Get-Mailbox** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione assegnati a determinate cassette postali.

    - **I criteri di conservazione a livello di organizzazione** - si tratta di criteri che sono assegnati a tutti i percorsi di contenuti nell'organizzazione. Utilizzare il cmdlet **Get-OrganizationConfig** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione a livello di organizzazione. Per ulteriori informazioni, vedere la sezione "Applicazione criteri di conservazione per un'intera organizzazione o percorsi specifici" di [criteri di conservazione Panoramica di Office 365](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

- **Le etichette di conservazione di office 365** - se un utente si applica un'etichetta di conservazione di Office 365 (uno configurato per conservare il contenuto o mantenere ed eliminare contenuto) a *qualsiasi* cartella o un elemento nella cassetta postale, di un'esenzione viene effettuata nella cassetta postale come se la cassetta postale è stata inserita nella conservazione per controversia legale o assegnati a un criterio di conservazione di Office 365. Per ulteriori informazioni, vedere la sezione [identificazione cassette postali in attesa perché un'etichetta di conservazione è stata applicata a una cartella o un elemento](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item) in questo articolo.

Per gestire le cassette postali in attesa, potrebbe essere necessario identificare il tipo di attesa viene messa in una cassetta postale in modo che sia possibile eseguire le attività, ad esempio se si modifica la durata di attesa, temporaneamente o permanentemente la rimozione dell'esenzione o ad eccezione di una cassetta postale da un criterio di conservazione di Office 365. In questi casi, il primo passaggio consiste per identificare il tipo di attesa effettuata nella cassetta postale. E, in quanto più esenzioni (e diversi tipi di conservazioni) possono essere inseriti in una singola cassetta postale, sarà necessario identificare tutte le esenzioni messa in una cassetta postale se si desidera rimuovere o modificare le esenzioni.

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>Passaggio 1: Ottenere il GUID di esenzioni messa in una cassetta postale

È possibile eseguire i due cmdlet seguente in Exchange Online PowerShell per ottenere il GUID delle esenzioni effettuate su una cassetta postale. Dopo avere ottenuto un GUID, è utilizzare per identificare l'esenzione specifico nel passaggio 2. Si noti che contiene controversia legale non sono identificati da un GUID. Esenzioni controversia sono attivati o disattivati per una cassetta postale.

- **Get-Mailbox** - utilizzo contiene questo cmdlet per determinare se conservazione per controversia legale è abilitata per una cassetta postale e per ottenere il GUID di eDiscovery, archiviazioni sul posto e i criteri di conservazione di Office 365 specificamente assegnati a una cassetta postale. L'output di questo cmdlet viene indicato anche se una cassetta postale è stata esclusa in modo esplicito da un criterio di conservazione a livello di organizzazione.

- **Get-OrganizationConfig** - utilizzare questo cmdlet per ottenere il GUID per i criteri di conservazione a livello di organizzazione.

Per connettersi a Exchange Online PowerShell, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Eseguire il comando seguente per ottenere informazioni sulle esenzioni e Office 365 i criteri di conservazione applicati a una cassetta postale.

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se non esistono troppi valori nella proprietà InPlaceHolds e non tutti gli elementi visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ciascun GUID su una riga distinta.

Nella tabella seguente descrive come identificare i diversi tipi di conservazioni in base ai valori nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox** .


|Tipo di blocco  |Valore di esempio  |Come identificare la conservazione  |
|---------|---------|---------|
|Conservazione in caso di dispute     |    `True`     |     Conservazione per controversia legale è abilitata per una cassetta postale se la proprietà *LitigationHoldEnabled* è impostata su `True`.    |
|esenzione di eDiscovery     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *proprietà InPlaceHolds* contiene il GUID di qualsiasi sospensione associata a un caso eDiscovery nel centro conformità sicurezza. È possibile sapere si tratta di un'esenzione di eDiscovery in quanto il GUID inizia con la `UniH` prefisso (che indica una conservazione unificata).      |
|Blocco sul posto     |     `c0ba3ce811b6432a8751430937152491` <br/> oppure <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La proprietà *InPlaceHolds* contiene il GUID In-Place Hold che viene inserito nella cassetta postale. È possibile sapere tratta an In-Place Hold perché sia il GUID non inizia con un prefisso, inizia con la `cld` prefisso.     |
|Criterio di conservazione di Office 365 in modo specifico applicato alla cassetta postale     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oppure <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La proprietà InPlaceHolds contiene i GUID qualsiasi posizione specifica dei criteri di conservazione applicato alla cassetta postale. È possibile identificare i criteri di conservazione in quanto il GUID inizia con la `mbx` o `skp` prefisso. Il `skp` prefisso indica che viene applicato il criterio di conservazione Skype per le conversazioni Business nella cassetta postale dell'utente.    |
|Escluso da un criterio di conservazione a livello di organizzazione Office 365     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se una cassetta postale è escluso da un criterio di conservazione a livello di organizzazione Office 365, il GUID per il criterio di conservazione della cassetta postale viene escluso dal viene visualizzato nella proprietà InPlaceHolds e identificato dal `-mbx` prefisso.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è ancora possibile uno o più a livello di organizzazione Office 365 criteri di conservazione applicati alla cassetta postale. Eseguire il seguente comando in Exchange Online PowerShell per ottenere un elenco di GUID di criteri di conservazione a livello di organizzazione Office 365.

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se non esistono troppi valori nella proprietà InPlaceHolds e non tutti gli elementi visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ciascun GUID su una riga distinta.

Nella tabella seguente vengono descritti i diversi tipi di archiviazione a livello di organizzazione e come identificare ogni tipo di base i GUID contenuti nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-OrganizationConfig** .


|Tipo di blocco  |Valore di esempio  |Descrizione  |
|---------|---------|---------|
|I criteri di conservazione 365 Office applicato alle cassette postali di Exchange, cartelle pubbliche di Exchange e team di chat    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Criteri di conservazione a livello di organizzazione applicati alle cassette postali di Exchange, cartelle pubbliche di Exchange, e le chat di 1xN Teams Microsoft vengono identificate in base ai GUID che iniziano con la `mbx` prefisso. Si noti che 1xN chat vengono archiviate nella cassetta postale di partecipanti alla chat singoli.      |
|Criterio di conservazione 365 Office applicata ai messaggi di canale di gruppi di Office 365 e team     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Criteri di conservazione a livello di organizzazione applicati ai gruppi di Office 365 e i messaggi di canale in Microsoft Teams vengono identificati in base ai GUID che iniziano con la `grp` prefisso. Si noti che i messaggi di canale sono archiviati nella cassetta postale di gruppo associato a un Team di Microsoft.     |

Per ulteriori informazioni applicati criteri di conservazione Teams Microsoft, vedere la sezione "Location team" [Panoramica dei criteri di conservazione](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Informazioni sul formato del valore InPlaceHolds per i criteri di conservazione

Oltre il prefisso (mbx, skp o gruppo) che identifica un elemento nella proprietà InPlaceHolds come criterio di conservazione di Office 365, il valore contiene inoltre un suffisso che identifica il tipo di azione di conservazione è configurato per il criterio. Ad esempio, il suffisso di azione è evidenziato in grassetto negli esempi seguenti:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

Nella tabella seguente vengono definiti i tre azioni di conservazione possibili:

|Valore  |Descrizione  |
|---------|---------|
|**1**     | Indica che il criterio di conservazione è configurato per eliminare gli elementi. il criterio non conservazione degli elementi.        |
|**2**    |    Indica che il criterio di conservazione è configurato per contenere dati. il criterio non elimina gli elementi dopo la scadenza del periodo di conservazione.     |
|**3**     |   Indica che il criterio di conservazione è configurato per conservare gli elementi e quindi eliminarli dopo la scadenza del periodo di conservazione.      |

Per ulteriori informazioni sulle azioni di conservazione, vedere la sezione "Mantenimento del contenuto per un determinato periodo di tempo" in [Panoramica di criteri di conservazione](retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>Passaggio 2: Utilizzando il GUID per identificare l'attesa

Dopo avere ottenuto il GUID di un'esenzione che viene applicato a una cassetta postale, il passaggio successivo è utilizzare tale GUID per identificare l'attesa. Nelle sezioni seguenti viene illustrato come identificare il nome dell'esenzione (e altre informazioni) utilizzando il GUID di attesa.

### <a name="ediscovery-holds"></a>esenzioni eDiscovery

Eseguire i seguenti comandi in sicurezza e conformità centro PowerShell per identificare un'esenzione di eDiscovery applicato alla cassetta postale. Utilizzare il GUID (non includendo il prefisso UniH) per eDiscovery attesa identificato nel passaggio 1. Il primo comando crea una variabile contenente informazioni sulla conservazione; Questa variabile viene utilizzata in altri comandi. Il secondo comando viene visualizzato il nome del caso di eDiscovery che è associato all'esenzione. Il terzo comando viene visualizzato il nome dell'esenzione e un elenco delle cassette postali a che si applica l'esenzione.

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

Per connettersi a PowerShell centro conformità e sicurezza, vedere [Connect to Office 365 Security & PowerShell centro conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Blocchi sul posto

Eseguire il seguente comando in Exchange Online PowerShell per identificare In-Place Hold applicato alla cassetta postale. Utilizzare il GUID per l'archiviazione sul posto identificato nel passaggio 1. Il comando Visualizza il nome dell'esenzione e un elenco delle cassette postali a che si applica l'esenzione.

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
Si noti che se il GUID per l'archiviazione sul posto inizia con la `cld` prefix, è necessario includere il prefisso quando si esegue il comando precedente.

### <a name="office-365-retention-policies"></a>Criteri di conservazione di Office 365

Eseguire il comando seguente in sicurezza e conformità centro PowerShell all'identità il criterio di conservazione di Office 365 (livello di organizzazione o specifico il percorso) che viene applicato alla cassetta postale. Utilizzare il GUID (non includendo il prefisso mbx, skp o gruppo oppure il suffisso di azione) identificato nel passaggio 1.

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificazione delle cassette postali in attesa perché un'etichetta di conservazione è stata applicata a una cartella o un elemento

Ogni volta che un utente applica un'etichetta di conservazione è configurata per conservare il contenuto o mantenere e quindi eliminare il contenuto di una cartella o un elemento nella propria cassetta postale, le proprietà della cassetta postale *ComplianceTagHoldApplied* è impostata su **True**. In questo caso, la cassetta postale è considerata da in attesa, come se è stata inserita nella conservazione per controversia legale o assegnato a un criterio di conservazione di Office 365. Quando la proprietà *ComplianceTagHoldApplied* è impostata su **True**, possono verificarsi le operazioni seguenti:

- Se viene eliminata la cassetta postale o account utente di Office 365 dell'utente, la cassetta postale diventa una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md).
- Non sarà in grado di disabilitare la cassetta postale (la cassetta postale principale o la cassetta postale di archiviazione, se abilitato).
- Gli elementi nella cassetta postale possono essere conservati più del previsto. Perché la cassetta postale è in attesa e pertanto nessun elemento verrà eliminato (cancellati).

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il seguente comando in Exchange Online PowerShell:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Per ulteriori informazioni su etichette di conservazione, vedere [Panoramica di Office 365 le etichette di conservazione](labels.md).

## <a name="managing-mailboxes-on-delay-hold"></a>Gestione delle cassette postali in ritardo attesa

Dopo la rimozione di qualsiasi tipo di attesa da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* è impostato su **True**. Questa operazione viene eseguita la volta successiva l'Assistente cartelle gestite elaborata la cassetta postale e rileva che è stata rimossa un'esenzione. Questo viene chiamato un *ritardo di conservazione* e significa che la rimozione effettiva dell'esenzione ha un ritardo per 30 giorni impedire che i dati vengano rimossi definitivamente dalla cassetta postale. In questo modo gli amministratori la possibilità di cercare o il ripristino di elementi delle cassette postali che verranno cancellati dopo la sospensione viene effettivamente rimosso. Quando un'esenzione ritardo viene effettuata nella cassetta postale, la cassetta postale è ancora considerata in attesa per un periodo illimitato come se la cassetta postale è stata controversie legali. Dopo 30 giorni, scade la conservazione di ritardo e Office 365 verrà automaticamente tenta di rimuovere la conservazione di ritardo (impostando la proprietà *DelayHoldApplied* su **False**) in modo che esenzione vengono effettivamente rimosse. Dopo la proprietà *DelayHoldApplied* su **False**, verranno eliminati gli elementi contrassegnati per la rimozione della cassetta postale viene elaborato dall'Assistente cartelle gestite.

Per visualizzare il valore della proprietà *DelayHoldApplied* per una cassetta postale, eseguire il seguente comando in Exchange Online PowerShell.

```
Get-Mailbox <username> | FL DelayHoldApplied
```

Per rimuovere la conservazione di ritardo prima della scadenza, è possibile eseguire il seguente comando in Exchange Online PowerShell: 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
Si noti che è necessario appartenere al ruolo giudiziari di Exchange Online utilizzare il parametro *RemoveDelayHoldApplied* 

Per rimuovere il blocco di ritardo per una cassetta postale inattiva, eseguire il seguente comando in Exchange Online PowerShell:

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> Il modo migliore per specificare una cassetta postale inattiva nel comando precedente consiste nell'utilizzare il relativo valore il nome distinto o il GUID di Exchange. Utilizzando uno dei seguenti valori aiuta a prevenire accidentalmente specificare la cassetta postale di un problema. 

## <a name="next-steps"></a>Passaggi successivi

Dopo aver identificato le conservazioni che vengono applicate a una cassetta postale, è possibile eseguire le attività, ad esempio modifica la durata della conservazione, temporaneamente o rimuovere in modo permanente la conservazione o nel caso di criteri di conservazione di Office 365, ad eccezione di una cassetta postale inattiva dal criterio. Per ulteriori informazioni sull'esecuzione di attività relative alle esenzioni, vedere uno degli argomenti seguenti:

- Eseguire il [RetentionCompliancePolicy Set - AddExchangeLocationException \<cassetta postale utente >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in sicurezza e conformità centro PowerShell per escludere una cassetta postale da un criterio di conservazione a livello di organizzazione Office 365. Si noti che questo comando può essere utilizzato solo per i criteri di conservazione dove il valore della proprietà *ExchangeLocation* è uguale a `All`.

- Eseguire il [Set-Mailbox - ExcludeFromOrgHolds \<contenere GUID senza prefisso o suffisso >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) comando in Exchange Online PowerShell per escludere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione Office 365.

- [Modificare la durata dell'attesa di una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

- [Eliminare gli elementi nella cartella Elementi recuperabili delle cassette postali basate su cloud con blocchi](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
