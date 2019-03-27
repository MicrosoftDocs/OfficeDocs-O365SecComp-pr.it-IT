---
title: Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Informazioni su come identificare i diversi tipi di blocco che è possibile inserire in una cassetta postale di Office 365. Questi tipi di esenzioni includono il blocco per controversia legale, eDiscovery holds e i criteri di conservazione di Office 365. È anche possibile determinare se un utente è stato escluso da un criterio di conservazione a livello di organizzazione
ms.openlocfilehash: fa037e4e4f6a0c4b419645bdc3242fdc3d6db7db
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "30900155"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online

In questo articolo viene illustrato come identificare le esenzioni effettuate nelle cassette postali di Exchange online in Office 365.

Office 365 offre diversi modi in cui l'organizzazione può impedire che il contenuto delle cassette postali venga eliminato definitivamente. In questo modo l'organizzazione può conservare il contenuto per soddisfare i requisiti di conformità o per la durata di indagini legali o di altro tipo. Di seguito è indicato un elenco delle caratteristiche di conservazione ( ** denominate anche esenzioni) in Office 365:

- **Esenzioni per controversIa legale** applicate alle cassette postali degli utenti in Exchange Online.

- **eDiscovery Hold** -appigli associati a un caso di eDiscovery nel centro conformità & sicurezza. le esenzioni di eDiscovery possono essere applicate alle cassette postali degli utenti e nella cassetta postale corrispondente per i gruppi di Office 365 e Microsoft teams.

- Archiviazione **sul posto** che vengono applicate alle cassette postali degli utenti utilizzando lo strumento di archiviazione eDiscovery _AMP_ sul posto nell'interfaccia di amministrazione di Exchange in Exchange Online.

- **Criteri di conservazione di office 365** -conserva il contenuto nelle cassette postali degli utenti in Exchange Online e nella cassetta postale corrispondente per i gruppi di Office 365 e Microsoft teams. È possibile creare un criterio di conservazione che contenga conversazioni di Skype for business, archiviate nelle cassette postali degli utenti.

  Sono disponibili due tipi di criteri di conservazione di Office 365 che è possibile assegnare alle cassette postali.

    - **Criteri di conservazione** delle posizioni specifiche: criteri che vengono assegnati ai percorsi di contenuto di utenti specifici. È possibile utilizzare il cmdlet **Get-Mailbox** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione assegnati a cassette postali specifiche.

    - **Criteri di conservazione a livello dell'organizzazione** : criteri che vengono assegnati a tutti i percorsi di contenuto dell'organizzazione. È possibile utilizzare il cmdlet **Get-OrganizationConfig** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione a livello dell'organizzazione.
  Per ulteriori informazioni, vedere la sezione "applicazione di un criterio di conservazione a un'intera organizzazione o a percorsi specifici" in [Overview of Office 365](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)Retention Policies.

- **Etichette di conservazione di office 365** -se un utente applica un'etichetta di conservazione di Office 365 (una configurata in modo da conservare il contenuto o conservare e quindi eliminare il contenuto) in *qualsiasi* cartella o elemento della propria cassetta postale, la cassetta postale viene conservata come se la cassetta postale fosse in blocco per controversia legale o assegnato a un criterio di conservazione di Office 365. Per ulteriori informazioni, vedere l' [argomento relativo all'identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o a una](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) sezione di elementi in questo articolo.

Per gestire le cassette postali in blocco, potrebbe essere necessario identificare il tipo di blocco applicato a una cassetta postale, in modo da poter eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o definitiva del blocco o l'esclusione di una cassetta postale da un criterio di conservazione di Office 365. In questi casi, il primo passaggio consiste nell'identificare il tipo di blocco applicato alla cassetta postale. Poiché in una singola cassetta postale è possibile inserire più esenzioni (e tipi diversi di esenzioni), è necessario identificare tutte le esenzioni inserite in una cassetta postale se si desidera rimuovere o modificare tali esenzioni.

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>Passaggio 1: ottenere il GUID per le esenzioni inserite in una cassetta postale

È possibile eseguire i due cmdlet seguenti in PowerShell di Exchange Online per ottenere il GUID delle esenzioni inserite in una cassetta postale. Dopo aver ottenuto un GUID, è possibile utilizzarlo per identificare il blocco specifico nel passaggio 2. Si noti che le esenzioni per controversia legale non sono identificate da un GUID. Le esenzioni per controversia legale sono abilitate o disabilitate per una cassetta postale.

- **Get-Mailbox** -utilizzare questo cmdlet per determinare se la conservazione per controversia legale è abilitata per una cassetta postale e per ottenere i GUID per eDiscovery holds, le stive sul posto e i criteri di riTenzione di Office 365 che sono specificatamente assegnati a una cassetta postale. L'output di questo cmdlet indicherà anche se una cassetta postale è stata esclusa in modo esplicito da un criterio di conservazione a livello dell'organizzazione.

- **Get-OrganizationConfig** -utilizzare questo cmdlet per ottenere i GUID per i criteri di conservazione a livello dell'organizzazione.

Per connettersi a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Eseguire il seguente comando per ottenere informazioni sulle esenzioni e sui criteri di conservazione di Office 365 applicati a una cassetta postale.

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni GUID su una riga distinta.

Nella tabella seguente viene descritto come identificare diversi tipi di esenzioni in base ai valori della proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox** .


|Tipo di blocco  |Valore di esempio  |Come identificare il blocco  |
|---------|---------|---------|
|Conservazione in caso di dispute     |    `True`     |     Il blocco per controversia legale è abilitato per una ** cassetta postale se la proprietà `True`LitigationHoldEnabled è impostata su.    |
|eDiscovery Hold     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *Proprietà InPlaceHolds* contiene il GUID di qualsiasi blocco associato a un caso di eDiscovery nel centro sicurezza & Compliance. Si può dire che si tratta di un blocco eDiscovery perché il GUID inizia `UniH` con il prefisso (che denota una conservazione unitaria).      |
|Blocco sul posto     |     `c0ba3ce811b6432a8751430937152491` <br/> oppure <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La proprietà *InPlaceHolds* contiene il GUID del blocco sul posto applicato alla cassetta postale. Si può dire che si tratta di un blocco sul posto, perché il GUID non inizia con un prefisso o inizia con il `cld` prefisso.     |
|Criteri di conservazione di Office 365 applicati specificamente alla cassetta postale     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oppure <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La proprietà InPlaceHolds contiene GUID di tutti i criteri di conservazione delle posizioni specifici applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia `mbx` con il `skp` prefisso o. Il `skp` prefisso indica che il criterio di conservazione viene applicato alle conversazioni di Skype for business nella cassetta postale dell'utente.    |
|Escluso da un criterio di conservazione di Office 365 a livello di organizzazione     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se una cassetta postale è esclusa da un criterio di conservazione di Office 365 a livello di organizzazione, il GUID del criterio di conservazione a cui viene esclusa la cassetta postale viene visualizzato nella `-mbx` proprietà InPlaceHolds ed è identificato dal prefisso.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è possibile che siano ancora presenti uno o più criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale. Eseguire il seguente comando in PowerShell di Exchange Online per ottenere un elenco di GUID per i criteri di conservazione di Office 365 a livello di organizzazione.

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni GUID su una riga distinta.

Nella tabella seguente vengono descritti i diversi tipi di esenzioni a livello di organizzazione e viene descritto come identificare ogni tipo in base ai GUID contenuti nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-OrganizationConfig** .


|Tipo di blocco  |Valore di esempio  |Descrizione  |
|---------|---------|---------|
|Criteri di conservazione di Office 365 applicati alle cassette postali di Exchange, alle cartelle pubbliche di Exchange e alle chat di Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   I criteri di conservazione a livello di organizzazione applicati alle cassette postali di Exchange, alle cartelle pubbliche di Exchange e alle chat di 1xN in Microsoft teams `mbx` sono identificati da GUID che iniziano con il prefisso. Si noti che le chat di 1xN vengono archiviate nella cassetta postale dei singoli partecipanti alla chat.      |
|Criteri di conservazione di Office 365 applicati ai messaggi di gruppo di Office 365 e ai gruppi di Team     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    I criteri di conservazione a livello di organizzazione applicati ai gruppi di Office 365 e ai messaggi di canale in Microsoft teams sono identificati da GUID che iniziano con il `grp` prefisso. Si noti che i messaggi di canale vengono archiviati nella cassetta postale di gruppo associata a un team di Microsoft.     |

Per ulteriori informazioni sui criteri di conservazione applicati a Microsoft teams, vedere la sezione "percorso team" [Panoramica dei criteri di conservazione](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Informazioni sul formato del valore InPlaceHolds per i criteri di conservazione

Oltre al prefisso (MBX, SKP o GRP) che identifica un elemento nella proprietà InPlaceHolds come criterio di conservazione di Office 365, il valore contiene anche un suffisso che identifica il tipo di azione di conservazione configurata per il criterio. Ad esempio, il suffisso Action è evidenziato in grassetto negli esempi seguenti:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

Nella tabella seguente vengono definite le tre possibili azioni di conservazione:

|Valore  |Descrizione  |
|---------|---------|
|**1**     | Indica che il criterio di conservazione è configurato per eliminare gli elementi; il criterio non conserva gli elementi.        |
|**2**    |    Indica che il criterio di conservazione è configurato per contenere gli elementi; il criterio non elimina gli elementi dopo la scadenza del periodo di conservazione.     |
|**3**     |   Indica che il criterio di conservazione è configurato per contenere gli elementi e quindi eliminarli dopo la scadenza del periodo di conservazione.      |

Per ulteriori informazioni sulle azioni di conservazione, vedere la sezione "conservazione del contenuto per un periodo di tempo specifico" in [Overview of](retention-policies.md#retaining-content-for-a-specific-period-of-time)Retention Policies.
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>Passaggio 2: utilizzo del GUID per identificare il blocco

Dopo aver ottenuto il GUID di un'esenzione applicato a una cassetta postale, il passaggio successivo consiste nell'utilizzare il GUID per identificare il blocco. Nelle sezioni seguenti viene illustrato come identificare il nome del blocco (e altre informazioni) utilizzando il GUID di blocco.

### <a name="ediscovery-holds"></a>eDiscovery contiene

Eseguire i comandi seguenti in PowerShell centro conformità & di sicurezza per identificare un'esenzione di eDiscovery applicata alla cassetta postale. Utilizzare il GUID (escluso il prefisso UniH) per il blocco eDiscovery identificato nel passaggio 1. Il primo comando crea una variabile che contiene informazioni sul blocco. Questa variabile viene utilizzata negli altri comandi. Nel secondo comando viene visualizzato il nome del caso di eDiscovery a cui è associato il blocco. Il terzo comando Visualizza il nome del blocco e un elenco delle cassette postali a cui è applicato il blocco.

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

Per eseguire la connessione a PowerShell centro conformità &, vedere [Connect to Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Archiviazione sul posto

Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco sul posto applicato alla cassetta postale. Utilizzare il GUID per il blocco sul posto identificato nel passaggio 1. Il comando Visualizza il nome del blocco e un elenco delle cassette postali a cui è applicato il blocco.

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
Si noti che se il GUID per il blocco sul posto inizia con il `cld` prefisso, assicurarsi di includere il prefisso quando si esegue il comando precedente.

### <a name="office-365-retention-policies"></a>Criteri di conservazione di Office 365

Eseguire il seguente comando in PowerShell centro conformità di & di sicurezza per identificare i criteri di conservazione di Office 365 (a livello di organizzazione o di posizione specifica) applicati alla cassetta postale. Utilizzare il GUID (che non include il prefisso MBX, SKP o GRP o il suffisso di azione) identificato nel passaggio 1.

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o un elemento

Ogni volta che un utente applica un'etichetta di conservazione configurata per mantenere il contenuto o mantenere e quindi eliminare il contenuto in una cartella o un elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* è impostata su **true**. In questo caso, la cassetta postale viene considerata attiva, come se fosse stata inserita in una conservazione per controversia legale o assegnata a un criterio di ritenzione di Office 365. Quando la proprietà *ComplianceTagHoldApplied* è impostata su **true**, è possibile che si verifichino le seguenti operazioni:

- Se la cassetta postale o l'account utente di Office 365 dell'utente viene eliminato, la cassetta postale diventa una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md).
- Non sarà possibile disabilitare la cassetta postale, ovvero la cassetta postale principale o la cassetta postale di archiviazione, se è abilitata.
- Gli elementi della cassetta postale possono essere mantenuti più a lungo del previsto. Ciò è dovuto al fatto che la cassetta postale è in attesa e pertanto nessun elemento verrà eliminato definitivamente (eliminato).

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il comando seguente in PowerShell di Exchange Online:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Per ulteriori informazioni sulle etichette di conservazione, vedere [Overview of Office 365](labels.md)retention labels.

## <a name="managing-mailboxes-on-delay-hold"></a>Gestione delle cassette postali in attesa del ritardo

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, il valore della proprietà della cassetta postale *DelayHoldApplied* è impostato su **true**. Questo problema si verifica quando l'Assistente cartelle gestite elabora la cassetta postale e rileva che è stata rimossa un'esenzione. Si tratta di un *blocco di ritardo* che indica che la rimozione effettiva del blocco viene posticipata di 30 giorni per evitare che i dati vengano eliminati definitivamente (eliminati) dalla cassetta postale. In questo modo gli amministratori avranno la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo che il blocco è stato effettivamente rimosso. Quando viene immessa una conservazione per la cassetta postale, la cassetta postale è ancora considerata attiva per una durata illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, scade il ritardo e Office 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà *DelayHoldApplied* su **false**) in modo che il blocco venga effettivamente rimosso. Dopo che la proprietà *DelayHoldApplied* è impostata su **false**, gli elementi contrassegnati per la rimozione verranno eliminati alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite.

Per visualizzare il valore della proprietà *DelayHoldApplied* per una cassetta postale, eseguire il comando seguente in PowerShell di Exchange Online.

```
Get-Mailbox <username> | FL DelayHoldApplied
```

Per rimuovere il ritardo di attesa prima della scadenza, è possibile eseguire il comando seguente in PowerShell di Exchange Online: 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
Tenere presente che è necessario essere assegnati al ruolo di blocco legale in Exchange Online per utilizzare il parametro *RemoveDelayHoldApplied* 

Per rimuovere il blocco di ritardo su una cassetta postale inattiva, eseguire il comando seguente in PowerShell di Exchange Online:

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> Il modo migliore per specificare una cassetta postale inattiva nel comando precedente consiste nell'utilizzare il nome distinto o il valore GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 

## <a name="next-steps"></a>Passaggi successivi

Dopo aver identificato le esenzioni applicate a una cassetta postale, è possibile eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o permanente del blocco o nel caso di criteri di conservazione di Office 365, ad esclusione di una cassetta postale inattiva dal criterio. Per ulteriori informazioni sull'esecuzione di attività correlate alle esenzioni, vedere uno dei seguenti argomenti:

- Eseguire il comando di [mailbox> dell'utente \<set-RetentionCompliancePolicy-AddExchangeLocationException](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) nel centro sicurezza & Compliance PowerShell per escludere una cassetta postale da un criterio di conservazione di Office 365 a livello di organizzazione. Si noti che questo comando può essere utilizzato solo per i criteri di conservazione in cui ** il valore della proprietà `All`ExchangeLocation è uguale a.

- Eseguire il [GUID di blocco set- \<Mailbox-ExcludeFromOrgHolds senza prefisso o comando suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) in PowerShell di Exchange Online per escludere una cassetta postale inattiva da un criterio di conservazione di Office 365 a livello di organizzazione.

- [Modificare la durata del blocco per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

- [Eliminare gli elementi nella cartella Elementi recuperabili delle cassette postali basate su cloud con blocchi](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
