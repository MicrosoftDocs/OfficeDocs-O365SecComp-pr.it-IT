---
title: Configurare il filtro delle autorizzazioni per la ricerca di contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Utilizzare il filtro per consentire un gestore di eDiscovery solo un sottoinsieme delle cassette postali e i siti di ricerca nell'organizzazione Office 365 le autorizzazioni di ricerca del contenuto.
ms.openlocfilehash: 2b6968a097e7abe5943a84b9ceb9b6d126057cc2
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258624"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Configurare il filtro delle autorizzazioni per la ricerca di contenuto

È possibile utilizzare le autorizzazioni di ricerca il filtro per consentire un gestore di eDiscovery solo un sottoinsieme delle cassette postali e i siti di ricerca nell'organizzazione Office 365. È inoltre possibile utilizzare le autorizzazioni di filtro per consentire di eDiscovery stesso responsabile ricercare solo per il contenuto delle cassette postali o un sito che soddisfa i criteri di ricerca specifici. Ad esempio, può consentire un manager eDiscovery ricerca solo le cassette postali degli utenti in una posizione specifica o un reparto. Ottenere questo risultato creando un filtro che utilizza un filtro destinatari supportato per limitare quali cassette postali possono essere ricercate. È inoltre possibile creare un filtro che specifica il contenuto delle cassette postali può essere ricercato. Questa operazione viene eseguita mediante la creazione di un filtro che utilizza una proprietà del messaggio supportano la ricerca. Allo stesso modo, si può consentire un manager eDiscovery solo dei siti di SharePoint specifici all'interno dell'organizzazione. Ottenere questo risultato creando un filtro che limita i siti possono essere ricercati. È inoltre possibile creare un filtro che specifica il contenuto del sito può essere ricercato. Questa operazione viene eseguita mediante la creazione di un filtro che utilizza una proprietà del sito disponibili per le ricerche.

È inoltre possibile utilizzare il filtro per creare i confini logici (denominati *dei limiti di conformità*) all'interno dell'organizzazione Office 365 che controllano i percorsi di contenuti utente (ad esempio le cassette postali, i siti di SharePoint e gli account OneDrive) le autorizzazioni di ricerca che responsabili di eDiscovery specifico possono eseguire ricerche. Per ulteriori informazioni, vedere [impostare i limiti di conformità per ricerche eDiscovery in Office 365](set-up-compliance-boundaries.md).
  
Autorizzazioni di ricerca il filtro è supportata dalla funzionalità di ricerca del contenuto in Office 365 Security &amp; centro conformità. Quattro cmdlet che consentono di configurare e gestire i filtri di ricerca permisisons:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire i cmdlet di filtro di protezione di conformità, è necessario essere membri del gruppo di ruoli Gestione organizzazione in sicurezza &amp; centro conformità. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
    
- È necessario essere connessi Windows PowerShell per la protezione sia &amp; centro conformità e dell'organizzazione Exchange Online per utilizzare i cmdlet di filtro di protezione conformità. Questo è necessario perché questi cmdlet richiedono l'accesso alle proprietà della cassetta postale, pertanto è necessario connettersi a Exchange Online. Vedere la procedura illustrata nella sezione successiva. 
    
- Consultare la sezione [More information](#more-information) per ulteriori informazioni sui filtri delle autorizzazioni di ricerca. 
    
- Autorizzazioni di ricerca il filtro è applicabile alle cassette postali inattive, pertanto è possibile utilizzare cassette postali e contenuto delle cassette postali filtro per limitare la può eseguire ricerche in una cassetta postale inattiva. Vedere la sezione [informazioni](#more-information) per ulteriori informazioni sulle autorizzazioni filtro e delle cassette postali inattive. 
    
-  Autorizzazioni di ricerca filtro non possono essere utilizzate per limitare che possono eseguire ricerche in cartelle pubbliche di Exchange. 
    
- Non esiste alcun limite al numero di filtri di ricerca per le autorizzazioni che possono essere creati in un'organizzazione. Tuttavia, le prestazioni della ricerca inciderà quando sono presenti più di 100 filtri di ricerca per le autorizzazioni. Per mantenere al minimo il numero di filtri di ricerca per le autorizzazioni nell'organizzazione, creare filtri di combinano le regole di Exchange, SharePoint e OneDrive in un singolo filtro quando possibile.
    
## <a name="connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>Connettersi alla protezione &amp; centro conformità ed Exchange Online in una singola sessione di PowerShell remota

1. Salvare il testo seguente in un file di script di Windows PowerShell, utilizzando il suffisso filename. ps1. Ad esempio, è possibile salvare in un file denominato ConnectEXO CC.ps1.
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Nel computer locale, aprire Windows PowerShell, passare alla cartella in cui si trova lo script creato nel passaggio precedente e quindi eseguire lo script. Per esempio:
    
    ```
    .\ConnectEXO-CC.ps1
    ```
 
Come fai a sapere se si ha avuto esito positivo? Dopo aver eseguito lo script, i cmdlet di sicurezza &amp; centro conformità ed Exchange Online vengono importati nella sessione di Windows PowerShell locale. Se non di errori, l'utente connesso correttamente. Una prova veloce consiste nell'eseguire una protezione &amp; cmdlet centro conformità, ad esempio, **Install-UnifiedCompliancePrerequisite** e un cmdlet di Exchange Online, ad esempio **Get-Mailbox**. 
  
Se non vengono visualizzati errori, controllare i requisiti seguenti:
  
- Un problema comune è rappresentato da una password errata. Eseguire di nuovo questi due passaggi e prestare particolare attenzione al nome utente e alla password del passaggio 1.
    
- Verificare che l'account disponga dell'autorizzazione per la protezione dall'accesso di &amp; centro conformità. Per ulteriori informazioni, vedere [Concedi accesso utenti per la protezione &amp; centro conformità](grant-access-to-the-security-and-compliance-center.md).
    
- Per impedire gli attacchi di tipo denial of service (DoS), è possibile aprire massimo tre connessioni PowerShell remote per la protezione &amp; centro conformità.
    
- Windows PowerShell deve essere configurato per poter eseguire gli script. È necessario configurare questa impostazione soltanto una volta sul computer e non ogni volta che si stabilisce una connessione. Per abilitare Windows PowerShell affinché esegua script firmati, eseguire il seguente comando in una finestra di Windows PowerShell elevata (una finestra di Windows PowerShell aperta selezionando **Esegui come amministratore**).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
- Il traffico TCP la porta 80 deve essere aperta tra il computer locale e Office 365. È probabile che aperto, ma è un elemento da considerare se l'organizzazione dispone di un criterio di accesso Internet restrittivo.
    

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter
<a name="New"> </a>

**New-ComplianceSecurityFilter** viene utilizzato per creare un nuovo filtro di autorizzazioni di ricerca. Nella tabella seguente vengono descritti i parametri per questo cmdlet. Tutti i parametri sono necessari per creare un filtro di protezione di conformità. 
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Action_ <br/> | Il parametro _Action_ specifica di azioni di ricerca che il filtro viene applicato a tale tipo. Le azioni di ricerca del contenuto possibili sono:<br/><br/> **Esportare** - il filtro viene applicato durante l'esportazione dei risultati di ricerca.  <br/> **Anteprima** - il filtro viene applicato durante l'anteprima dei risultati della ricerca.  <br/> **Eliminare** - il filtro viene applicato durante l'eliminazione dei risultati di ricerca.  <br/> **Ricerca** - il filtro viene applicato quando si esegue una ricerca.  <br/> **Tutti** : il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _FilterName_ <br/> |Il parametro _FilterName_ specifica il nome del filtro delle autorizzazioni. Questo nome viene utilizzato un filtro all'identità quando si utilizza il cmdlet **Get-ComplianceSecurityFilter**, **Set-ComplianceSecurityFilter** e **Remove-ComplianceSecurityFilter** .<br/> |
| _Filtri_ <br/> | Il parametro _filtri_ specifica i criteri di ricerca per il filtro di protezione di conformità. È possibile creare tre diversi tipo di filtri:<br/><br/> **Il filtraggio della cassetta postale** - questo tipo di filtro consente di specificare le cassette postali gli utenti assegnati (specificati dal parametro _utenti_ ) possono eseguire ricerche. La sintassi di questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per le cassette postali che possono essere ricercate dell'ambito. Ad esempio, il filtro delle cassette postali `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` consente all'utente assegnato a questo filtro per la ricerca solo le cassette postali contenenti il valore "OttawaUsers" nella proprietà CustomAttribute10.<br/>  Qualsiasi proprietà destinatario filtrabili supportati può essere utilizzata per la proprietà _MailboxPropertyName_ . Per un elenco di proprietà supportate, vedere [proprietà filtrabili per il parametro - RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903).<br/><br/> **Il filtro contenuto delle cassette postali** - questo tipo di filtro viene applicato il contenuto che possono essere ricercate. Specifica il contenuto delle cassette postali che possono cercare gli utenti assegnati. La sintassi di questo tipo di filtro è **MailboxContent_** _SearchablePropertyName:value_, dove _SearchablePropertyName_ specifica una proprietà Keyword Query Language (KQL) che è possibile specificare una ricerca di contenuto. Ad esempio, il filtro dei contenuti della cassetta postale `MailboxContent_recipients:contoso.com` consente all'utente assegnato questo filtro per la ricerca solo per i messaggi inviati a destinatari compresi nel dominio contoso.com.<br/>  Per un elenco delle proprietà dei messaggi disponibili per le ricerche, vedere [query con parole chiave e le condizioni di ricerca per la ricerca del contenuto](keyword-queries-and-search-conditions.md).  <br/><br/> **Filtraggio dei siti e contenuto del sito** - vi sono due SharePoint e OneDrive per Business relativa al sito i filtri che è possibile utilizzare per specificare quali siti o contenuto del sito assegnati gli utenti possono eseguire ricerche:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  Questi due filtri sono intercambiabili; ad esempio `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` verranno restituiti gli stessi risultati. Ma che consentono di identificare un filtro esegue, è possibile utilizzare `Site_` per specificare le proprietà relative al sito (ad esempio, un URL del sito) e `SiteContent_` per specificare le proprietà relative al contenuto (ad esempio, tipi di documenti. Ad esempio, il filtro `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` consente all'utente assegnato questo filtro per la ricerca solo per il contenuto di https://contoso.sharepoint.com/sites/doctors raccolta siti. Il filtro `"SiteContent_FileExtension -eq 'docx'"` consente all'utente assegnato questo filtro per la ricerca solo per i documenti di Word (Word 2007 e versioni successive).<br/><br/>  Per un elenco delle proprietà del sito disponibili per le ricerche, vedere [Overview of a ricerca per indicizzazione e proprietà gestite nello SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Proprietà contrassegnati con **Sì** nella * * sottoponibile a query * * colonna può essere utilizzata per creare un sito o un filtro del contenuto del sito.<br/> <br/> **Importante:**  Un filtro di ricerca singolo può avere solo un tipo di filtro. non può contenere un filtro della cassetta postale e un filtro del sito. Analogamente, non può contenere un filtro della cassetta postale e un filtro dei contenuti della cassetta postale. Tuttavia, un filtro può contenere una query più complessa dello stesso tipo. Per esempio`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` <br/><br/> **Importante:** È necessario creare un filtro di autorizzazioni di ricerca per in modo esplicito impedire agli utenti di eseguire la ricerca dei percorsi di contenuti in un servizio specifico di Office 365 (ad esempio, impedendo a un utente di ricerca di qualsiasi cassetta postale di Exchange o qualsiasi sito di SharePoint). In altre parole, la creazione di un filtro di autorizzazioni di ricerca che consente agli utenti di cercare tutti i siti di SharePoint dell'organizzazione non impedisce all'utente la ricerca di cassette postali. Ad esempio, per consentire gli amministratori di SharePoint di cercare solo siti di SharePoint, è necessario creare un filtro che impedisce loro di ricerca di cassette postali. Analogamente, per consentire gli amministratori di Exchange di cercare solo le cassette postali, è necessario creare un filtro che impedisce loro di ricerca di siti.           |
| _Utenti_ <br/> |Il parametro _utenti_ specificare gli utenti che ottenere il filtro applicato per le ricerche di contenuto. Identificare gli utenti in base al alias o l'indirizzo SMTP primario. È possibile specificare più valori separati da virgole oppure è possibile assegnare il filtro a tutti gli utenti utilizzando il valore **tutti**.<br/> È anche possibile utilizzare il parametro _gli utenti_ per specificare un titolo &amp; gruppo di ruoli centro conformità. Consente di creare un gruppo di ruoli personalizzati e quindi assegnare il ruolo group un filtro di autorizzazioni di ricerca. Ad esempio, si supponga che si dispone di un gruppo di ruoli personalizzati per i gestori di eDiscovery per la filiale US di una società multinazionale. È possibile utilizzare il parametro _utenti_ specificare questo gruppo di ruoli (tramite la proprietà Name del gruppo di ruoli) e quindi utilizzare il parametro _Filter_ per consentire solo le cassette postali negli Stati Uniti da cercare.<br/> Non è possibile specificare gruppi di distribuzione con questo parametro.  <br/> |
   

## <a name="examples-of-creating-search-permissions-filters"></a>Esempi di creazione di filtri di ricerca per le autorizzazioni

Di seguito sono riportati esempi di utilizzo del cmdlet **New-ComplianceSecurityFilter** per creare un filtro delle autorizzazioni di ricerca. 
  
In questo esempio l'annb@contoso.com utente eseguire tutte le azioni di ricerca del contenuto solo per le cassette postali in Canada. Il filtro contiene il codice paese numerico di tre cifre per il Canada da ISO 3166-1.

```
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

In questo esempio, gli utenti donh e suzanf possono eseguire le ricerche solo nelle cassette postali che dispongono del valore "Marketing" per la proprietà delle cassette postali CustomAttribute1.

```
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```
   
In questo esempio, i membri del gruppo di ruoli "US Discovery Managers" possono effettuare tutte le azioni di ricerca di contenuto solo nelle cassette postali negli Stati Uniti. Questo filtro contiene il codice numerico a tre cifre per gli Stati Uniti fornito dall'ISO 3166-1.
  
```
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

In questo esempio, i membri del gruppo di ruoli "eDiscovery Manager" possono eseguire le ricerche solo nelle cassette postali dei membri del gruppo di distribuzione "Ottawa Users". 
  
```
$DG = Get-DistributionGroup "Ottawa Users"
```

```
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```
In questo esempio, nessun utente può eliminare i contenuti dalle cassette postali dei membri del gruppo di distribuzione "Executive Team".

```
$DG = Get-DistributionGroup "Executive Team"
```

```
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users all -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```
   
In questo esempio consente ai membri del gruppo di ruoli personalizzati responsabili eDiscovery OneDrive per cercare contenuto solo in OneDrive per i percorsi Business nell'organizzazione.

```
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```
   
> [!NOTE]
> Per limitare gli utenti per la ricerca di siti specifici, utilizzare il filtro `Site_Path`, come illustrato nell'esempio precedente. Utilizzo di `Site_Site` non funzionerà. 
  
In questo esempio, le azioni di ricerca di contenuto di un utente sono limitate solo ai messaggi di posta elettronica inviati durante il 2015.

```
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```
   
Analogamente all'esempio precedente, in questo esempio le azioni di ricerca di contenuto di un utente sono limitate solo ai documenti modificati nel 2015.

```
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```
   
Questo esempio viene impedito che i membri del gruppo di ruoli "Manager dell'individuazione OneDrive" esecuzione di operazioni di ricerca del contenuto su qualsiasi cassetta postale nell'organizzazione. 

```
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```
  
## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** viene utilizzato per restituire un elenco di filtri di ricerca per le autorizzazioni. Utilizzare il parametro _FilterName_ per restituire le informazioni per un filtro di ricerca specifici. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** viene utilizzato per modificare un filtro di autorizzazioni di ricerca esistente. L'unico parametro obbligatorio è _FilterName_. 
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
| _Action_| Il parametro _Action_ specifica di azioni di ricerca che il filtro viene applicato a tale tipo. Le azioni di ricerca del contenuto possibili sono:<br/><br/> **Esportare** - il filtro viene applicato durante l'esportazione dei risultati di ricerca.  <br/> **Anteprima** - il filtro viene applicato durante l'anteprima dei risultati della ricerca.  <br/> **Eliminare** - il filtro viene applicato durante l'eliminazione dei risultati di ricerca.  <br/> **Ricerca** - il filtro viene applicato quando si esegue una ricerca.  <br/> **Tutti** : il filtro viene applicato a tutte le azioni di ricerca.  <br/> |
| _FilterName_|Il parametro _FilterName_ specifica il nome del filtro delle autorizzazioni. |
| _Filtri_| Il parametro _filtri_ specifica i criteri di ricerca per il filtro di protezione di conformità. È possibile creare due tipo diverso di filtri:<br/><br/>**Il filtraggio della cassetta postale** - questo tipo di filtro consente di specificare le cassette postali gli utenti assegnati (specificati dal parametro _utenti_ ) possono eseguire ricerche. La sintassi di questo tipo di filtro è **Mailbox_** _MailboxPropertyName_, dove _MailboxPropertyName_ specifica una proprietà della cassetta postale utilizzata per le cassette postali che possono essere ricercate dell'ambito. Ad esempio, il filtro delle cassette postali `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` consente all'utente assegnato a questo filtro per la ricerca solo le cassette postali contenenti il valore "OttawaUsers" nella proprietà CustomAttribute10.  Qualsiasi proprietà destinatario filtrabili supportati può essere utilizzata per la proprietà _MailboxPropertyName_ . Per un elenco di proprietà supportate, vedere [proprietà filtrabili per il parametro - RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=784903).<br/><br/>**Il filtro contenuto delle cassette postali**- questo tipo di filtro viene applicato il contenuto che possono essere ricercate. Specifica il contenuto delle cassette postali che possono cercare gli utenti assegnati. La sintassi di questo tipo di filtro è **MailboxContent_** _SearchablePropertyName:value_, dove _SearchablePropertyName_ specifica una proprietà Keyword Query Language (KQL) che è possibile specificare una ricerca di contenuto. Ad esempio, il filtro dei contenuti della cassetta postale `MailboxContent_recipients:contoso.com` consente all'utente assegnato questo filtro per la ricerca solo per i messaggi inviati a destinatari compresi nel dominio contoso.com.  Per un elenco delle proprietà dei messaggi disponibili per le ricerche, vedere [query con parole chiave per la ricerca del contenuto](keyword-queries-and-search-conditions.md).<br/><br/>**Filtraggio dei siti e contenuto del sito** Esistono due SharePoint e OneDrive per Business relativa al sito i filtri che è possibile utilizzare per specificare quali siti o contenuto del sito assegnati gli utenti possono eseguire ricerche: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>Questi due filtri sono intercambiabili; ad esempio `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` e `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` verranno restituiti gli stessi risultati. Ma che consentono di identificare un filtro esegue, è possibile utilizzare `Site_` per specificare le proprietà relative al sito (ad esempio, un URL del sito) e `SiteContent_` per specificare le proprietà relative al contenuto (ad esempio, tipi di documenti. Ad esempio, il filtro `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` consente all'utente assegnato questo filtro per la ricerca solo per il contenuto di https://contoso.spoppe.com/sites/doctors raccolta siti. Il filtro `"SiteContent_FileExtension -eq 'docx'"` consente all'utente assegnato questo filtro per la ricerca solo per i documenti di Word (Word 2007 e versioni successive).<br/><br/>Per un elenco delle proprietà del sito disponibili per le ricerche, vedere [Overview of a ricerca per indicizzazione e proprietà gestite nello SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). Proprietà contrassegnate con **Sì** nella colonna **impostazione sottoponibile a query** possono essere utilizzate per creare un sito o un filtro del contenuto del sito.<br/><br/> **Importante:** Un filtro di ricerca singolo può avere solo un tipo di filtro. non può contenere un filtro della cassetta postale e un filtro del sito. Analogamente, non può contenere un filtro della cassetta postale e un filtro dei contenuti della cassetta postale. Tuttavia, un filtro può contenere una query più complessa dello stesso tipo. Per esempio`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`          |
| _Utenti_|Il parametro _utenti_ specificare gli utenti che ottenere il filtro applicato per le ricerche di contenuto. Poiché si tratta di una proprietà multivalore, specificando un utente o gruppo di utenti con il parametro sovrascriverà l'elenco di utenti esistente. Vedere gli esempi seguenti per la sintassi per l'aggiunta e rimozione di utenti selezionati.<br/><br/>È anche possibile utilizzare il parametro _gli utenti_ per specificare un titolo &amp; gruppo di ruoli centro conformità. Consente di creare un gruppo di ruoli personalizzati e quindi assegnare il ruolo group un filtro di autorizzazioni di ricerca. Ad esempio, si supponga che si dispone di un gruppo di ruoli personalizzati per i gestori di eDiscovery per la filiale US di una società multinazionale. È possibile utilizzare il parametro _utenti_ specificare questo gruppo di ruoli (tramite la proprietà Name del gruppo di ruoli) e quindi utilizzare il parametro _Filter_ per consentire solo le cassette postali negli Stati Uniti da cercare.<br/><br/>Non è possibile specificare gruppi di distribuzione con questo parametro. |

## <a name="examples-of-changing-search-permissions-filters"></a>Esempi di filtri di ricerca per le autorizzazioni di modifica

In questi esempi viene illustrano come utilizzare i cmdlet **Get-ComplianceSecurityFilter** e **Set-ComplianceSecurityFilter** per aggiungere o rimuovere un utente a un elenco di utenti ai quali è assegnato il filtro esistente. Quando si aggiunge o rimuovere utenti da un filtro, specificare l'utente utilizzando il proprio indirizzo SMTP. 
  
In questo esempio viene aggiunto un utente al filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```
```
$filterusers.users.add("pilarp@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
   
In questo esempio viene rimosso un utente dal filtro.

```
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```
$filterusers.users.remove("annb@contoso.com")
```

```
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```
  
## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter** viene utilizzato per eliminare un filtro di ricerca. Utilizzare il parametro _FilterName_ consente di specificare il filtro che si desidera eliminare. 
  
## <a name="more-information"></a>Ulteriori informazioni

- **Come ricerca autorizzazioni filtro ufficio?** Il filtro autorizzazioni viene aggiunto alla query di ricerca quando viene eseguita una ricerca di contenuto. Il filtro autorizzazioni essenzialmente appartenente a query di ricerca per l'operatore booleano **AND** . Si supponga, ad esempio, che è necessario un filtro di autorizzazioni che consente di Bob eseguire tutte le azioni di ricerca per le cassette postali dei membri del gruppo di distribuzione lavoratori. Quindi Bob viene eseguita una ricerca di contenuto in tutte le cassette postali nell'organizzazione con query di ricerca `sender:jerry@adatum.com`. Dal momento che il filtro per le autorizzazioni e la query di ricerca vengono unite logicamente da un operatore **AND** , la ricerca restituisce qualsiasi messaggio inviato da jerry@adatum.com ad alcun membro del gruppo di distribuzione lavoratori. 
    
- **Cosa succede se si dispone di più filtri di ricerca per le autorizzazioni?** In una query di ricerca del contenuto più filtri le autorizzazioni vengono combinati **o** operatori booleani. Pertanto i risultati verranno restituiti se i filtri sono true. In una ricerca di contenuto, tutti i filtri (combinati tramite operatori **o** ) vengono quindi combinati dall'operatore **e** con la query di ricerca. Ecco quello precedente, in un filtro di ricerca consente di Bob effettuare la ricerca solo le cassette postali dei membri del gruppo di distribuzione lavoratori. Creiamo quindi un altro filtro che impedisce Bob di ricerca di cassette postali di Phil ("Mailbox_Alias - ne 'Phil'"). Si supponga inoltre che Phil sia un membro del gruppo di dipendenti. Quando Bob viene eseguita una ricerca di contenuto (in base all'esempio precedente) in tutte le cassette postali nell'organizzazione, i risultati della ricerca verranno restituiti per la cassetta postale di Phil anche se è stato applicato filtro per impedire la ricerca delle cassette postali di Phil Bob. Ciò avviene perché il primo filtro, che consente di Bob cercare il gruppo di dipendenti, è true. E poiché Phil è un membro del gruppo di dipendenti, Bob possono eseguire ricerche delle cassette postali di Phil. 
    
- **Ricerca autorizzazioni filtro lavoro per le cassette postali inattive?** Sì, è possibile utilizzare cassette postali e i filtri del contenuto delle cassette postali per limitare che possono eseguire ricerche delle cassette postali inattive all'interno dell'organizzazione. Ad esempio una cassetta postale regolare, una cassetta postale inattiva deve essere configurata tramite la proprietà dei destinatari che consente di creare un filtro di autorizzazioni. Se necessario, è possibile utilizzare il comando **Get-Mailbox InactiveMailboxOnly** per visualizzare le proprietà delle cassette postali inattive. Per ulteriori informazioni, vedere [creare e gestire le cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md).
    
- **Ricerca autorizzazioni filtro lavoro per le cartelle pubbliche?** No. Come indicato in precedenza, la ricerca autorizzazioni filtro non possono essere utilizzate per limitare che può eseguire ricerche in cartelle pubbliche di Exchange. Ad esempio, gli elementi nelle cartelle pubbliche di non sono da escludere dai risultati della ricerca mediante un filtro di autorizzazioni. 
    
- **Agli utenti di cercare tutti i percorsi di contenuti in un servizio specifico inoltre impedire la ricerca di percorsi di contenuti in un altro servizio?** No. Come indicato in precedenza, è necessario creare un filtro di autorizzazioni di ricerca per in modo esplicito impedire agli utenti di eseguire la ricerca dei percorsi di contenuti in un servizio specifico di Office 365 (ad esempio, impedendo a un utente di ricerca di qualsiasi cassetta postale di Exchange o qualsiasi sito di SharePoint). In altre parole, la creazione di un filtro di autorizzazioni di ricerca che consente agli utenti di cercare tutti i siti di SharePoint dell'organizzazione non impedisce all'utente la ricerca di cassette postali. Ad esempio, per consentire gli amministratori di SharePoint di cercare solo siti di SharePoint, è necessario creare un filtro che impedisce loro di ricerca di cassette postali. Analogamente, per consentire gli amministratori di Exchange di cercare solo le cassette postali, è necessario creare un filtro che impedisce loro di ricerca di siti.
