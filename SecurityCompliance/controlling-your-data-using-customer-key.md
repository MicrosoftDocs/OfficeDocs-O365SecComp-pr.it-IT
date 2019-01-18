---
title: Controllare i dati in Office 365 con Customer Key
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: Informazioni su come configurare chiave cliente per Office 365 per Exchange Online, Skype per Business, SharePoint Online e OneDrive for Business. Con clienti chiave, controllare le chiavi di crittografia della propria organizzazione e quindi configurare Office 365 per utilizzarli per crittografare i dati statici nei Data Center di Microsoft.
ms.openlocfilehash: c4a59af49efad3bb8539b6c83b9ad9fd1c2d1f43
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723253"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Controllare i dati in Office 365 con Customer Key

Con clienti chiave, controllare le chiavi di crittografia della propria organizzazione e quindi configurare Office 365 per utilizzarli per crittografare i dati statici nei centri dati di Microsoft. Dati statici includono i dati da Exchange Online e Skype for Business archiviati nelle cassette postali e i file archiviati in SharePoint Online e OneDrive for Business.
  
Prima di poter utilizzare chiave cliente per Office 365, è necessario configurare Azure. In questo argomento vengono descritti i passaggi da eseguire per creare e configurare le risorse necessarie Azure e quindi vengono fornite le procedure per la configurazione di chiave cliente in Office 365. Dopo aver eseguito il programma di installazione Azure, determinare quale criterio e conseguenza, le chiavi da assegnare alle cassette postali e i file nella propria organizzazione. Le cassette postali e i file per cui non si assegna un criterio utilizzerà i criteri di crittografia che vengono controllati e gestiti da Microsoft. Per ulteriori informazioni sulla chiave cliente o per una panoramica generale, vedere il [Codice cliente per Office 365 FAQ](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> Si consiglia attenersi alle procedure consigliate in questo argomento. Questi sono definiti come **Suggerimento** e **importante**. Consente di chiave cliente di controllare le chiavi di crittografia principale il cui ambito è possibile specificarne fino a tutta l'organizzazione. Ciò significa che commessi con queste sequenze di tasti possono avere un impatto ampio e potrebbero causare interruzioni del servizio o la perdita definitiva di dati. 
  
## <a name="before-you-begin-setting-up-customer-key"></a>Prima di iniziare la configurazione di chiave cliente
<a name="Beforeyoustart"> </a>

Prima di iniziare, assicurarsi di avere licenze appropriato per l'organizzazione. Chiave cliente in Office 365 è disponibile in Office 365 E5 o SKU di conformità avanzate.
  
Per comprendere i concetti e le procedure in questo argomento, quindi, è consigliabile consultare la documentazione di [Azure chiave cassaforte](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Inoltre, acquisire familiarità con i termini utilizzati in Azure, ad esempio [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Per inviare commenti e suggerimenti sulla chiave dei clienti, inclusa la documentazione, inviare idee, suggerimenti e prospettive a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Panoramica dell'installazione di chiave cliente per Office 365
<a name="Overview"> </a>

Per configurare la chiave cliente verranno completate queste attività. Il resto di questo argomento vengono fornite istruzioni dettagliate per ogni attività o collegamenti fuori a ulteriori informazioni per ogni passaggio del processo.
  
**In Azure e FastTrack Microsoft:**
  
Completare la maggior parte di queste attività tramite la connessione in remoto a Azure PowerShell. Per ottenere risultati migliori, utilizzare la versione 4.4.0 o versione successiva di Azure PowerShell.
  
- [Creare due nuove sottoscrizioni di Azure](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [Registrare le sottoscrizioni Azure per l'utilizzo di un periodo di conservazione obbligatoria](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    La registrazione può richiedere da una a cinque giorni lavorativi.
    
- [Inviare una richiesta per attivare codice cliente per Office 365](controlling-your-data-using-customer-key.md#FastTrack)
    
    Dopo aver creato le due nuove sottoscrizioni Azure, è necessario inviare la richiesta di offerta cliente chiave appropriata per il completamento di un modulo web è ospitato nel portale dei Microsoft FastTrack. **FastTrack il team non fornire assistenza clienti chiave. Office utilizza semplicemente il portale FastTrack per consentono di inviare il modulo e consentiranno di tenere traccia delle offerte pertinenti per clienti chiave**.
  
Dopo l'invio di una proposta di chiave cliente, Microsoft esamina la richiesta e invia una notifica quando è possibile procedere con il resto le attività di configurazione. Questo processo può richiedere fino a cinque giorni lavorativi.
    
- [Creare un premium Azure chiave cassaforte in ogni sottoscrizione](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [Assegnare le autorizzazioni per ogni archivio chiave](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [Abilitare questa impostazione e quindi confermare l'eliminazione temporanea in archivi il chiavi](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [Aggiungere una chiave per ogni archivio chiave sia per la creazione o l'importazione di una chiave](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [Selezionare il livello di ripristino delle chiavi](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [Backup cassaforte chiave Azure](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [Verificare le impostazioni di configurazione di Azure chiave cassaforte](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [Ottenere l'URI per ogni tasto di Azure chiave cassaforte](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**In Office 365:**
  
Exchange Online e Skype for Business:
  
- [Creare un criterio di crittografia dei dati (DEP) per l'utilizzo con Exchange Online e Skype per le aziende](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Assegnare una protezione esecuzione programmi a una cassetta postale](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Convalidare la crittografia delle cassette postali](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online e OneDrive for Business:
  
- [Creare un criterio di crittografia dei dati (DEP) per ogni SharePoint Online e OneDrive per Business geo](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Convalidare la crittografia del gruppo di siti, siti dei Team e OneDrive for Business](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Eseguire le attività in Azure chiave cassaforte e Microsoft FastTrack chiave cliente
<a name="AzureSteps"> </a>

Completare queste attività in Azure chiave cassaforte per impostare la chiave di clienti per Office 365. È necessario completare la procedura seguente indipendentemente dal fatto che si intende configurare chiave cliente per Exchange Online e Skype per le aziende o SharePoint Online e OneDrive for Business o per tutti i servizi supportati in Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Creare due nuove sottoscrizioni di Azure
<a name="Create2newsubs"> </a>

Due sottoscrizioni Azure sono necessari per clienti chiave. Come procedura consigliata, si consiglia di creare nuove sottoscrizioni Azure per l'utilizzo con chiave cliente. Codici tasto cassaforte Azure possono essere autorizzati solo per le applicazioni nello stesso tenant di Azure Active Directory (AAD), è necessario creare le nuove sottoscrizioni utilizzando stesso tenant di Azure Active Directory utilizzato con l'organizzazione Office 365 in cui verrà assegnato il DEPs. Ad esempio, utilizzando l'account di lavoro o della scuola con privilegi di amministratore globale dell'organizzazione Office 365. Per ulteriori informazioni, vedere [iscrizione a Azure come un'organizzazione](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> Chiave cliente richiede due chiavi per ogni criterio di crittografia dei dati (DEP). Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Per una protezione ottimale, è consigliabile avere separati membri della propria organizzazione di configurare una chiave in ogni sottoscrizione. Inoltre, le sottoscrizioni di Azure devono essere utilizzati solo per amministrare le chiavi di crittografia per Office 365. Consente di proteggere l'organizzazione nel caso in cui un l'operatore eliminato accidentalmente, intenzionalmente o manomettere o in caso contrario mismanages i tasti di cui sono responsabili.<br/> È consigliabile configurare nuove sottoscrizioni Azure unicamente utilizzati per la gestione delle risorse di Azure chiave cassaforte per l'utilizzo con clienti chiave. Non esiste alcun limite pratico al numero di sottoscrizioni Azure che è possibile creare per l'organizzazione. Seguendo le procedure consigliate riduce al minimo l'impatto delle risorse umane errore durante il supporto per gestire le risorse utilizzate dalla chiave cliente. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Inviare una richiesta per attivare codice cliente per Office 365
<a name="FastTrack"> </a>

Dopo aver completato i passaggi Azure, è necessario inviare una richiesta di offerta nel [portale dei Microsoft FastTrack](https://fasttrack.microsoft.com/). Dopo avere inviato una richiesta tramite il portale web FastTrack, Microsoft consente di verificare le Azure chiave archivio dati e contatto informazioni di configurazione specificate. Le selezioni eseguite nel formato offerta relativa autorizzati responsabili dell'organizzazione è necessario per il completamento della registrazione chiave cliente e non critici. I responsabili dell'organizzazione selezionato nel modulo sarà utilizzato per garantire l'autenticità del qualsiasi richiesta di revocare e distruggere tutti i tasti utilizzati con un criterio di crittografia dei dati Customer chiave. È necessario eseguire questo passaggio una volta per attivare codice cliente per Exchange Online e Skype per la copertura dell'azienda e una seconda volta attivare codice cliente per SharePoint Online e OneDrive for Business.
  
Per inviare un'offerta per attivare il codice cliente, completare la procedura seguente:
  
1. Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, eseguire l'accesso al [portale dei Microsoft FastTrack](https://fasttrack.microsoft.com/).
    
2. Dopo aver eseguito, individuare il **Dashboard**.
    
3. Scegliere **offre**ed esaminare l'elenco delle offerte in corso.
    
4. Scegliere **Ulteriori informazioni** per la proposta in base alle esigenze: 
    
  - **Exchange Online e Skype per le aziende:** Scegliere **Ulteriori informazioni** su offerta **Cliente chiave di Exchange** . 
    
  - **SharePoint Online e OneDrive for Business:** Scelta di **Informazioni su più** nei offerta **Cliente chiave per SharePoint e OneDrive for Business** . 
    
5. Nella pagina **sono disponibili ulteriori informazioni** , scegliere **Crea richiesta**.
    
6. Compilare tutti i dettagli applicabili e le informazioni richieste nella maschera offerta. Prestare particolare attenzione alle selezioni eseguite per i responsabili dell'organizzazione si desidera autorizzare per approvare l'eliminazione definitiva e irreversibile delle chiavi di crittografia e dati. Dopo aver completato il modulo, scegliere **Invia**.
    
    Questo processo può richiedere fino a cinque giorni lavorativi dopo che Microsoft informato della richiesta.
    
7. Continuare semplicemente la sezione periodo conservazione obbligatoria riportata di seguito.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrare le sottoscrizioni Azure per l'utilizzo di un periodo di conservazione obbligatoria
<a name="RegisterSubsforMRP"> </a>

Perdita temporanea o permanente radice delle chiavi di crittografia può essere molto eccesso o persino irreversibili all'operazione di servizio e può causare la perdita di dati. Per questo motivo, le risorse utilizzate con clienti chiave richiedono la protezione avanzata. Tutte le risorse Azure utilizzati con chiave cliente offrono meccanismi di protezione oltre la configurazione predefinita. Sottoscrizioni Azure possono essere contrassegnate o registrate in modo che impedisce l'annullamento immediato e irrevocabile. Questa operazione viene definita la registrazione per un periodo di conservazione obbligatoria. I passaggi necessari per registrare le sottoscrizioni Azure per un periodo di conservazione obbligatoria richiedono la collaborazione con il team di Office 365. Questo processo può richiedere da una a cinque giorni lavorativi. In precedenza, questa è stata a volte indicata come "Non annullare".
  
Prima di contattare il team di Office 365, è necessario eseguire la procedura seguente per ogni sottoscrizione Azure al cliente chiave:
  
1. Eseguire l'accesso alla sottoscrizione Azure con Azure PowerShell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Eseguire il cmdlet Register-AzureRmProviderFeature per registrare le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatoria.
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Contatta Microsoft per avere il processo di finalizzazione. Per SharePoint e OneDrive per team di Business, contattare [spock@microsoft.com](mailto:spock@microsoft.com). Per Exchange Online e Skype per le aziende, contattare [exock@microsoft.com](mailto:exock@microsoft.com). Service Level Agreement (SLA) per il completamento di questo processo è cinque giorni lavorativi dopo che Microsoft è stata una notifica (e verificato) che si sono registrati sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatoria. Includere quanto segue nella posta elettronica:
    
    **Oggetto**: chiave cliente per \< *nome di dominio completo del tenant*\> 
    
    **Corpo**: ID di sottoscrizione per il quale si desidera avere il periodo finalizzata la conservazione obbligatoria. 
    
4. Dopo aver ricevuto una notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione del eseguendo il cmdlet Get-AzureRmProviderFeature come indicato di seguito:
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Dopo aver verificato che la proprietà **State registrazione** dal cmdlet Get-AzureRmProviderFeature restituisce un valore di **Registered**, eseguire il comando seguente per completare il processo:
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creare un premium Azure chiave cassaforte in ogni sottoscrizione
<a name="CreateKeyVault"> </a>

I passaggi per creare una chiave cassaforte sono documentati nella [Guida introduttiva a Azure chiave cassaforte](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), cui viene descritta la procedura di installazione e lanciare Azure PowerShell, la connessione alla sottoscrizione Azure, la creazione di un gruppo di risorse e la creazione di un archivio principali in cui gruppo di risorse.
  
Quando si crea un archivio di chiavi, è necessario scegliere un SKU: Standard o Premium. SKU Standard consente chiavi Azure chiave cassaforte a essere protetto con - non esiste alcuna protezione chiave Hardware Security Module (HSM) - il software e SKU Premium consente l'utilizzo di HSM per la protezione dei tasti cassaforte chiave. Chiave cliente accetta archivi chiavi che utilizzano uno SKU, anche se si consiglia di utilizzare solo la SKU Premium. Il costo delle operazioni con i tasti di entrambi i tipi è lo stesso, pertanto l'unica differenza dei costi è il costo al mese per ogni tasto protetti da modulo di sicurezza hardware. Per informazioni dettagliate, vedere [chiave cassaforte prezzo](https://azure.microsoft.com/pricing/details/key-vault/) . 
  
> [!IMPORTANT]
> Utilizzare l'archivi chiavi Premium SKU e le chiavi protetti da modulo di sicurezza hardware per i dati di produzione e utilizzare solo gli archivi chiavi SKU Standard e le chiavi per scopi di test e convalida. 
  
Per ogni servizio Office 365 con cui si utilizzerà chiave cliente, creare una chiave cassaforte in ognuna delle due sottoscrizioni Azure creata. Per Exchange Online e Skype per Business solo o SharePoint Online e OneDrive for Business solo, ad esempio, si creerà solo una coppia di archivi. Per abilitare la chiave cliente per Exchange Online e SharePoint Online, verrà creato due coppie di archivi di chiave.
  
Utilizzare una convenzione di denominazione per gli archivi di chiave che indica la modalità di utilizzo della protezione esecuzione programmi a cui associare gli archivi di. Vedere la sezione procedure consigliate di sotto di suggerimenti convenzione di denominazione.
  
Creare un insieme di archivi per ogni criterio di crittografia dei dati separato, accoppiato. Per Exchange Online, l'ambito dei criteri di crittografia dei dati sia selezionata dall'utente quando si assegna il criterio cassetta postale di. Una cassetta postale può avere un solo criterio assegnato ed è possibile creare criteri fino a 50. SharePoint Online è l'ambito dei criteri di tutti i dati all'interno dell'organizzazione in aree geografiche o geo.
  
La creazione di archivi di chiave richiede anche la creazione di gruppi di risorse Azure, in quanto gli archivi di chiave necessario capacità di archiviazione (sebbene dimensioni molto piccole) e cassaforte chiave registrazione, se abilitato, genera inoltre dati memorizzati. Come procedura consigliata è consigliabile utilizzare amministratori diversi per gestire ogni gruppo di risorse con l'amministrazione allineato con il gruppo di amministratori che gestirà tutte le risorse correlate chiave cliente.
  
> [!IMPORTANT]
> Per ottimizzare la disponibilità, il chiavi archivi devono trovarsi in aree di raggiungere il servizio Office 365. Ad esempio, se l'organizzazione Exchange Online in Nord America, effettuare il chiavi archivi in Nord America. Se l'organizzazione Exchange Online in Europa, inserire il chiavi archivi in Europa.<br/>Utilizzare un prefisso comune per gli archivi di chiave e includere una voce di utilizzo e l'ambito dei tasti e cassaforte chiave (ad esempio, per il servizio Contoso SharePoint gli archivi di conterrà in Nord America, una coppia di nomi possibile è Contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. I nomi cassaforte sono stringhe globalmente univoche all'interno di Azure, in modo che potrebbe essere necessario provare le varianti dei nomi desiderati nel caso in cui i nomi desiderati siano già stati richiesti da altri utenti di Azure. A partire da luglio 2017 cassaforte nomi non possono essere modificati, in modo che è consigliabile disporre di un piano scritto dal programma di installazione e l'utilizzo di un secondo utente per verificare che il piano viene eseguito correttamente.<br/>Se possibile, creare le archivi in aree non associata. Aree di Azure accoppiate garantire la disponibilità elevata tra domini di errore del servizio. Di conseguenza, coppie regionali possono essere considerate come area backup di altro. Ciò significa che una risorsa Azure che viene inserita in una regione automaticamente sta per essere la tolleranza di errore tramite l'area accoppiato. Per questo motivo, la scelta di aree per due archivi utilizzati in una protezione esecuzione programmi in cui le aree sono accoppiati significa che solo un totale di due regioni della disponibilità sono in uso. La maggior parte delle aree geografiche hanno a disposizione due aree, in modo che non è ancora possibile selezionare aree non associata. Se possibile, selezionare due aree non associata per gli archivi di due utilizzati con una protezione esecuzione programmi. Il vantaggio da un totale di quattro aree della disponibilità. Per ulteriori informazioni, vedere [Business continuity e ripristino di emergenza (BCDR): Azure accoppiato aree](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente delle coppie regionali. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Assegnare le autorizzazioni per ogni archivio chiave
<a name="KeyVaultPerms"> </a>

Per ogni archivio chiave, sarà necessario definire tre set di autorizzazioni per clienti chiave, a seconda dell'implementazione separati. Ad esempio, è necessario definire un set di autorizzazioni per gli elementi seguenti:
  
- **Gli amministratori cassaforte chiave** che verranno eseguite gestione giornaliera dell'archivio chiave per la propria organizzazione. Queste attività includono backup, creare, ottenere, importano, elencare e ripristino. 
    
    > [!IMPORTANT]
    > Il set di autorizzazioni assegnate agli amministratori di cassaforte chiave non include l'autorizzazione per eliminare le chiavi. Questo comportamento è intenzionale e una procedura importante. Eliminazione delle chiavi di crittografia non viene in genere eseguita, poiché effettuare in modo permanente Elimina dati. Come procedura consigliata, non concedere questa autorizzazione per gli amministratori principali cassaforte per impostazione predefinita. In realtà, questo riservare per i collaboratori cassaforte chiave e solo assegnarlo a un amministratore in base a breve termine una volta che viene considerato comprendere chiaramente le conseguenze. 
  
    Per assegnare le autorizzazioni a un utente nell'organizzazione Office 365, accedere alla sottoscrizione Azure con Azure PowerShell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Ad esempio:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- **I collaboratori cassaforte chiave** che possono modificare le autorizzazioni per l'archivio di chiave Azure stesso. Sarà necessario modificare queste autorizzazioni dipendenti lasciare o partecipare al team o in una situazione molto rara che la chiave di archivio amministratori legittimo necessario disporre dell'autorizzazione per eliminare o ripristinare una chiave. Questa serie di cassaforte principali collaboratori deve essere concesso il ruolo di **Collaboratore** dell'archivio chiave. È possibile assegnare questo ruolo con Gestione risorse di Azure. Per ulteriori informazioni, vedere [Controllo dell'accesso Use Role-Based per gestire l'accesso alle risorse della sottoscrizione di Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). L'amministratore che ha creato una sottoscrizione con questo tipo di accesso in modo implicito, nonché la possibilità di assegnare ad altri amministratori al ruolo di collaboratore.
    
- Se si intende utilizzare chiave cliente con Exchange Online e Skype per le aziende, è necessario concedere l'autorizzazione per Office 365 utilizzino cassaforte chiave per conto di Exchange Online e Skype per le aziende. Analogamente, se si intende utilizzare chiave cliente con SharePoint Online e OneDrive for Business, è necessario aggiungere l'autorizzazione per Office 365 utilizzare l'archivio chiave per conto di SharePoint Online e OneDrive for Business. Per concedere autorizzazioni a Office 365, eseguire il cmdlet **Set-AzureRmKeyVaultAccessPolicy** utilizzando la sintassi seguente: 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Dove:
    
  - *vaultname* è il nome dell'archivio di chiave che è stato creato. 
    
  - Per Exchange Online e Skype per le aziende, sostituire *appID Office 365* con`00000002-0000-0ff1-ce00-000000000000`
    
  - Per SharePoint Online e OneDrive for Business, sostituire *appID Office 365* con`00000003-0000-0ff1-ce00-000000000000`
    
  Esempio: Impostazione delle autorizzazioni per Exchange Online e Skype for Business:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Esempio: Impostazione delle autorizzazioni per SharePoint Online e OneDrive for Business
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Abilitare questa impostazione e quindi confermare l'eliminazione temporanea in archivi il chiavi
<a name="SoftDelete"> </a>

Quando è possibile ripristinare rapidamente le chiavi, hanno meno probabilità di verifica un'interruzione del servizio esteso a causa di chiavi eliminate accidentalmente o da utenti malintenzionati. È necessario attivare questa configurazione, denominata eliminare Soft, prima di poter utilizzare i tasti con clienti chiave. Abilitazione eliminare Soft consente di ripristinare le chiavi o gli archivi di 90 giorni di eliminazione senza la necessità di ripristinarli dal backup.
  
Per abilitare eliminare Soft negli archivi chiavi, completare la procedura seguente:
  
1. Eseguire l'accesso alla sottoscrizione Azure con Windows Powershell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).
    
2. Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . In questo esempio *vaultname* è il nome dell'archivio di chiave per la quale si desidera abilitare l'eliminazione temporanea: 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. Conferma eliminazione temporanea è configurato per l'archivio chiave eseguendo il cmdlet **Get-AzureRmKeyVault** . Se eliminazione temporanea sia configurato correttamente per l'archivio di chiavi, il Soft eliminare Enabled? proprietà restituisce il valore **True**: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Aggiungere una chiave per ogni archivio chiave sia per la creazione o l'importazione di una chiave
<a name="AddKeystoKeyVault"> </a>

Esistono due modi per aggiungere le chiavi a una cassaforte chiave Azure; è possibile creare una chiave direttamente nella chiave cassaforte oppure è possibile importare una chiave. Creazione di una chiave direttamente nella chiave cassaforte è il metodo meno complesso, durante l'importazione di una chiave consente di controllare totale come viene generata la chiave.
  
Per creare una chiave direttamente la chiave cassaforte, eseguire il cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) come indicato di seguito: 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dove:
  
-  *vaultname* è il nome dell'archivio di chiave in cui si desidera creare la chiave. 
    
-  *nome chiave* è il nome che si desidera assegnare alla nuova chiave. 
    
    > [!TIP]
    > Nome chiavi utilizzando la convenzione di denominazione simile, come descritto in precedenza per gli archivi di chiave. In questo modo, negli strumenti che mostra solo il nome della chiave, la stringa self-descritto. 
  
- Se si prevede di proteggere la chiave con un modulo di sicurezza hardware, assicurarsi di specificare **modulo di sicurezza hardware** come valore del parametro _destinazione_ , in caso contrario, specificare **Software**.
    
Ad esempio:
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Per importare una chiave direttamente nell'archivio di chiavi, è necessario disporre di un modulo di sicurezza Hardware di nShield Thales.
  
Alcune aziende preferiscono questo approccio per stabilire provenienza per le chiavi e questo metodo offre inoltre le operazioni seguenti:
  
- Il set di strumenti utilizzati per l'importazione include attestazione da Thales che non sia stato esportabile la chiave di Exchange chiave (KEK) utilizzato per crittografare la chiave che è generare e viene generato all'interno di un modulo di sicurezza autentico hardware che è stata prodotta da Thales.
    
- Il set di strumenti include attestazione da Thales che le funzionalità di sicurezza Azure chiave cassaforte viene generata anche in un modulo di sicurezza hardware autentico prodotto da Thales. Questo tipo di attestazione può rivelarsi a un utente che Microsoft utilizza hardware Thales autentico.
    
Verificare con il gruppo di sicurezza per determinare se sono necessarie che le attestazioni sopra elencate. Per informazioni dettagliate sulla procedura creare una chiave in locale e importarlo in cassaforte la chiave, vedere [come generare e trasferire protetti da modulo di sicurezza hardware chiavi per Azure chiave cassaforte](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Utilizzare le istruzioni Azure per creare una chiave in ogni archivio chiave.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Selezionare il livello di ripristino delle chiavi
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 è necessario che la sottoscrizione cassaforte chiave Azure è impostata su non annullare e che i tasti utilizzati dalla chiave cliente dispongano di eliminazione temporanea abilitato. È possibile verificarlo esaminando a livello di ripristino delle chiavi.
  
Per controllare il livello di ripristino di un tasto, in Azure PowerShell, eseguire il cmdlet Get-AzureKeyVaultKey come indicato di seguito:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

Se la proprietà a _Livello di ripristino_ restituisce un valore diverso da un valore pari a **+ ProtectedSubscription reversibile**, è necessario leggere questo argomento e verificare di aver seguito tutti i passaggi per mettere la sottoscrizione nell'elenco non annullare e di avere eliminazione temporanea abilitato in ognuno degli archivi chiavi.
  
### <a name="backup-azure-key-vault"></a>Backup cassaforte chiave Azure
<a name="BackupAzureKeyVaultkeys"> </a>

Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire il backup e archiviare le copie di backup, online e offline. Copie non in linea dovrebbero essere connessi non a qualsiasi rete, ad esempio in una struttura fisica di archiviazione sicura o commerciale. Almeno una copia di backup deve essere archiviata in un percorso accessibile in caso di emergenza. Gli oggetti BLOB di backup è l'unico mezzo per il ripristino chiave opportuno un codice di tasto cassaforte eliminato in modo permanente o inutilizzabile in caso contrario. Le chiavi sono esterni all'archivio chiave Azure e sono stati importati in Azure chiave archivio non possono essere come backup perché i metadati necessari per clienti chiave da utilizzare la chiave non esiste con la chiave esterna. Consente solo un backup eseguito dall'insieme di credenziali chiave Azure per operazioni di ripristino con clienti chiave. Di conseguenza, è essenziale che un backup dell'archivio di chiave Azure deve essere eseguita dopo una chiave viene caricata o creata.
  
Per creare un backup di una chiave di Azure chiave cassaforte, eseguire il cmdlet [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) come indicato di seguito:
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

Verificare che il file di output viene utilizzato il suffisso `.backup`.
  
File di output risultanti da questo cmdlet viene crittografato e non può essere utilizzato all'esterno di Azure chiave cassaforte. Il backup può essere ripristinato solo per la sottoscrizione Azure da cui è stato eseguito il backup.
  
> [!TIP]
> Il file di output, scegliere una combinazione del nome di archivio e il nome della chiave. Ciò consentirà il file nome self-descrizione. Garantisce inoltre che i nomi di file di backup non sono in conflitto. 
  
Ad esempio:
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Verificare le impostazioni di configurazione di Azure chiave cassaforte
<a name="Validateconfiguration"> </a>

Eseguire la convalida prima di utilizzare chiavi di una protezione esecuzione programmi è facoltativa ma consigliata. In particolare, se si utilizzano passaggi per configurare le chiavi e gli archivi di diversi da quelli descritti in questo argomento, è necessario convalidare l'integrità delle risorse di Azure chiave cassaforte prima di configurare la chiave cliente.
  
Per verificare che le chiavi sono operazioni get, wrapKey e unwrapKey abilitate:
  
Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) come indicato di seguito: 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

Nell'output, osservare per il criterio di accesso e per l'identità (GUID) di Exchange Online o l'identità (GUID) di SharePoint Online nel modo appropriato. Tutti e tre i queste autorizzazioni devono essere visualizzate in autorizzazioni alle chiavi.
  
Se la configurazione dei criteri di accesso non è corretta, eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy come indicato di seguito:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Ad esempio, per Exchange Online e Skype for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Ad esempio, per SharePoint Online e OneDrive for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Per verificare che la data di scadenza non è impostata per le chiavi eseguire il cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) come indicato di seguito: 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

Una chiave scaduta non può essere utilizzata dalla chiave cliente e operazioni tentate con una chiave scaduta avrà esito negativo e anche comportare un'interruzione del servizio. È consigliabile che le chiavi utilizzate con chiave cliente non è una data di scadenza. Una data di scadenza, una volta impostato, non possono essere rimosse, ma può essere modificato in una data diversa. Se una chiave deve essere utilizzata con una data di scadenza impostare, modificare il valore di scadenza per 31/12/9999. Tasti con una data di scadenza per impostato un valore diverso da quello 31/12/9999 non superano la convalida di Office 365.
  
Per modificare una data di scadenza che è stata impostata su un valore diverso da 31/12/9999, eseguire il cmdlet [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) come indicato di seguito: 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Non impostare date di scadenza per le chiavi di crittografia che si utilizza con clienti chiave. 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Ottenere l'URI per ogni tasto di Azure chiave cassaforte
<a name="GetKeyURI"> </a>

Dopo aver completato tutti i passaggi descritti in Azure per impostare il chiavi archivi e aggiungere le chiavi, eseguire il comando seguente per ottenere l'URI della chiave in ogni archivio chiave. È necessario utilizzare questi URI quando si creano e assegnare ciascuna protezione esecuzione programmi in seguito, quindi salvare le informazioni in un luogo sicuro. Ricordarsi di eseguire il comando una sola volta per ogni archivio chiave.
  
In Azure PowerShell:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Impostazione di chiave cliente per Exchange Online e Skype per le aziende
<a name="AzureSteps"> </a>

Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure chiave cassaforte. Per informazioni, vedere [completare le attività in Azure chiave cassaforte e FastTrack Microsoft per la chiave cliente](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Per configurare chiave cliente per Exchange Online e Skype per le aziende, è necessario eseguire la procedura seguente tramite la connessione in remoto a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Creare un criterio di crittografia dei dati (DEP) per l'utilizzo con Exchange Online e Skype per le aziende
<a name="CreateDEP4EXOSkype"> </a>

Una protezione esecuzione programmi sono associata a un set di chiavi archiviate nell'archivio chiave Azure. Per assegnare una protezione esecuzione programmi a una cassetta postale in Office 365. Office 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare i programmi, è necessario gli URI cassaforte chiave ottenuto in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni tasto cassaforte chiave Azure](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
Ricordare! Quando si creano una protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi archivi di chiave di Azure. Verificare che queste chiavi si trovano in due regioni Azure separate per garantire la ridondanza geografica.
  
Per creare i programmi, procedere come segue:
  
1. Nel computer locale, utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, [la connessione a Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) aprire Windows PowerShell ed eseguendo il comando seguente. 
    
   ```
   $UserCredential = Get-Credential
   ```

2. Nella finestra di dialogo richiesta credenziali di Windows PowerShell immettere il proprio lavoro o scuola informazioni sull'account, fare clic su **OK**e quindi immettere il comando seguente. 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Eseguire il comando riportato di seguito.
    
   ```
   Import-PSSession $Session
   ```

4. Per creare una protezione esecuzione programmi, utilizzare il cmdlet New-DataEncryptionPolicy digitando il comando seguente.
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dove:
    
   -  *PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes. 
    
   -  *PolicyDescription* è una descrizione descrittivo del criterio che consenta di ricordare facilmente novità per i criteri. È possibile includere spazi nella descrizione. Ad esempio, principali chiave per le cassette postali degli Stati Uniti e le aree. 
    
   -  *KeyVaultURI1* è l'URI per la prima chiave del criterio. Ad esempio https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01. 
    
   -  *KeyVaultURI2* è l'URI per la seconda chiave del criterio. Ad esempio https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separare i due URI da una virgola e uno spazio. 
    
   Esempio:
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Assegnare una protezione esecuzione programmi a una cassetta postale
<a name="assignDEPtomailbox"> </a>

Assegnare la protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Office 365 possono crittografare la cassetta postale con la chiave designata la protezione esecuzione programmi.
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dove *MailboxIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Convalidare la crittografia delle cassette postali
<a name="validatemailboxencryption"> </a>

Crittografare una cassetta postale può richiedere tempo. Per l'assegnazione di criteri prima volta, la cassetta postale inoltre necessario eseguire lo spostamento da un database a un'altra prima che il servizio può crittografare la cassetta postale. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo che si modificano una protezione esecuzione programmi o la prima volta che è stata assegnata una protezione esecuzione programmi a una cassetta postale.
  
Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale viene crittografata.
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non verrà crittografata. 

Il tempo necessario per completare spostamenti delle cassette postali dipende dal numero di cassette postali a cui si assegna una protezione esecuzione programmi per la prima volta, nonché le dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui sono assegnati i programmi, avviare uno spostamento delle cassette postali per le cassette postali non crittografate tramite il cmdlet New-MoveRequest.

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: Impostazione di chiave cliente per SharePoint Online e OneDrive for Business
<a name="AzureSteps"> </a>

Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure chiave cassaforte. Per informazioni, vedere [completare le attività in Azure chiave cassaforte e FastTrack Microsoft per la chiave cliente](controlling-your-data-using-customer-key.md#AzureSteps) . 
  
Per configurare chiave cliente per SharePoint Online e OneDrive for Business, è necessario eseguire la procedura seguente per una connessione remota in SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Creare un criterio di crittografia dei dati (DEP) per ogni SharePoint Online e OneDrive per Business geo
<a name="CreateDEP4SPOODfB"> </a>

Una protezione esecuzione programmi sono associata a un set di chiavi archiviate nell'archivio chiave Azure. Si applicano una protezione esecuzione programmi per tutti i dati in un'unica posizione geografica, denominata anche un livello geografico. Se si utilizza la funzionalità multi-geo di Office 365 (attualmente in anteprima), è possibile creare una protezione esecuzione programmi per ogni livello geografico. Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi in Office 365 per l'utilizzo con SharePoint Online e OneDrive for Business. Office 365 utilizzerà quindi le chiavi identificate nella protezione esecuzione programmi per crittografare i dati in tale livello geografico. Per creare i programmi, è necessario gli URI cassaforte chiave ottenuto in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni tasto cassaforte chiave Azure](controlling-your-data-using-customer-key.md#GetKeyURI) . 
  
Ricordare! Quando si creano una protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi archivi di chiave di Azure. Verificare che queste chiavi si trovano in due regioni Azure separate per garantire la ridondanza geografica.
  
Per creare una protezione esecuzione programmi, è necessario per la connessione a SharePoint Online in modalità remota tramite Windows PowerShell.
  
1. Nel computer locale, utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, [connettersi a Powershell per SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx).
    
2. In Microsoft SharePoint Online Management Shell, eseguire il cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) come indicato di seguito: 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Quando si registrano i programmi, crittografia inizia dati contenuti nel livello geografico. L'operazione può richiedere alcuni minuti.
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Convalidare la crittografia del gruppo di siti, siti dei Team e OneDrive for Business
<a name="validateencryptionSPO"> </a>

È possibile controllare lo stato di crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

L'output del cmdlet include:
  
- L'URI della chiave primaria.
    
- L'URI della chiave secondaria.
    
- Specifica lo stato di crittografia per il livello geografico. I possibili stati includono:
    
  - **Annullare la registrazione:** La crittografia chiave clienti non è stato ancora applicata. 
    
  - **Registrazione:** È stata applicata la crittografia chiave cliente e i file sono in corso la crittografia. Se il livello geografico questo stato, si verranno anche da visualizzare informazioni su quale percentuale di siti nel geo siano stati completati in modo che è possibile monitorare avanzamento di crittografia. 
    
  - **Registrato:** È stata applicata la crittografia chiave cliente e tutti i file in tutti i siti sono stati crittografati. 
    
  - **In sequenza:** Una chiave (in inglese) è in corso. Se il livello geografico questo stato, si verranno anche da visualizzare informazioni su quale percentuale di siti di aver completato l'operazione roll chiave in modo che è possibile monitorare l'avanzamento delle. 
    
## <a name="managing-customer-key-for-office-365"></a>Gestione dei clienti chiave per Office 365
<a name="ManageCustomerKey"> </a>

Dopo aver configurato chiave cliente per Office 365, è possibile eseguire le altre attività di gestione.
  
- [Ripristinare le chiavi Azure chiave cassaforte](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [Ripristino dello stato o la rotazione di una chiave in Azure chiave cassaforte al cliente chiave](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [Gestire le autorizzazioni cassaforte chiave](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [Determinare la protezione esecuzione programmi assegnato a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Ripristinare le chiavi Azure chiave cassaforte
<a name="RestoreAzureKeyVaultKeys"> </a>

Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione temporanea. Tutti i tasti utilizzati con chiave cliente sono necessari disporre di eliminazione temporanea abilitato. Eliminazione temporanea funge da un Cestino secondario e consente il ripristino fino a 90 giorni senza la necessità di ripristino. Ripristino in genere necessaria solo in casi extreme o insoliti, ad esempio se si perde il tasto o tasto cassaforte. Se è necessario ripristinare una chiave per l'utilizzo con clienti chiave in Azure PowerShell, utilizzare il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Ad esempio:
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se esiste già una chiave con lo stesso nome nell'archivio di chiave, l'operazione di ripristino avrà esito negativo. Ripristino AzureKeyVaultKey Ripristina tutti i metadati per il tasto inclusi il nome della chiave e tutte le versioni principali.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Ripristino dello stato o la rotazione di una chiave in Azure chiave cassaforte al cliente chiave
<a name="RollCKkey"> </a>

In sequenza tasti non è richiesto uno cassaforte chiave Azure o dalla chiave cliente. Tasti protetti con un modulo di sicurezza hardware sono inoltre praticamente a compromessi. Anche se una chiave radice sono in possesso di un attore dannoso non esiste alcun modo realizzabili dell'utilizzo per decrittografare i dati, in quanto solo il codice di Office 365 è in grado di utilizzarlo. Ripristino dello stato di una chiave è tuttavia supportato dalla chiave cliente.
  
> [!CAUTION]
> Solo ripristinare una chiave di crittografia utilizzati con chiave cliente quando è presente un motivo deselezionare tecnico o requisiti di conformità indicano che è necessario ripristinare la chiave. Inoltre, non eliminare eventuali chiavi o sono state associate ai criteri. Quando si esegue rollback le chiavi, non è presente il contenuto crittografato con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno nuovamente crittografate frequentemente, inattivo, le cassette postali disconnesse e su disattivato possono essere crittografate con le chiavi precedenti. SharePoint Online consente di eseguire il backup del contenuto per scopi di ripristino e il ripristino, in modo che potrebbero ancora essere archiviato il contenuto utilizzando le chiavi precedenti.<br/> Per garantire la sicurezza dei dati, SharePoint Online consentirà non più di un'operazione di rollback chiave siano in corso alla volta. Se si desidera ripristinare entrambe le chiavi in un archivio di chiave, è necessario attendere la prima operazione (in inglese) chiave per completa. È consigliabile scaglionare le operazioni (in inglese) chiave intervalli diversi, in modo che questo non è un problema. 
  
Quando si esegue il rollback un tasto, si richiede una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, utilizzare il cmdlet stesso, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la stessa sintassi utilizzata per creare la chiave in primo luogo.
  
Ad esempio:
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

In questo esempio, in quanto non esiste una chiave denominata **Contoso-O365EX-NA-VaultA1-Key001** già nell'archivio di **Contoso-O365EX-NA-VaultA1** , verrà creata una nuova versione chiave. Il metodo aggiunge una nuova versione chiave. Questa operazione consente di mantenere le versioni precedenti chiave nella cronologia delle versioni della chiave, in modo che i dati crittografati in precedenza con tale chiave possono comunque essere decrittografati. Dopo avere completato un tasto qualsiasi associato a una protezione esecuzione programmi di distribuzione, è necessario eseguire un cmdlet aggiuntive per garantire che chiave cliente inizia con la nuova chiave. 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Abilitare Exchange Online e Skype per le aziende utilizzano una nuova chiave dopo aver rollback o ruotato tasti in Azure chiave cassaforte

Quando si ripristina una delle chiavi Azure chiave cassaforte associate a una protezione esecuzione programmi utilizzati con Exchange Online e Skype per le aziende, è necessario eseguire il comando seguente per aggiornare la protezione esecuzione programmi e attivare Office 365 iniziare a utilizzare la nuova chiave.
  
Per indicare a clienti chiave da utilizzare la nuova chiave per crittografare le cassette postali in Office 365, eseguire il cmdlet Set-DataEncryptionPolicy come indicato di seguito:
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

All'interno di 48 ore, le cassette postali attive crittografate tramite il criterio verrà associate il tasto aggiornato. Utilizzare i passaggi descritti in [Determine Protezione esecuzione programmi assegnato a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) per verificare il valore della proprietà DataEncryptionPolicyID per la cassetta postale. Il valore di questa proprietà verrà modificato dopo che è stata applicata la chiave aggiornata. 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Abilitare SharePoint Online e OneDrive for Business utilizzare una nuova chiave dopo aver rollback o ruotato tasti in Azure chiave cassaforte

Quando si ripristina una delle chiavi Azure chiave cassaforte associate a una protezione esecuzione programmi utilizzato con SharePoint Online e OneDrive for Business, è necessario eseguire il cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) per aggiornare la protezione esecuzione programmi e attivare Office 365 iniziare a utilizzare la nuova chiave. 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Verrà avviata l'operazione (in inglese) principali per SharePoint Online e OneDrive for Business. Questa azione non è immediata. Per visualizzare lo stato di avanzamento della chiave di eseguire il rollback operazione, eseguire il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Gestire le autorizzazioni cassaforte chiave
<a name="Managekeyvaultperms"> </a>

Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni cassaforte chiave. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio, quando un dipendente lascia il team.
  
Per visualizzare le autorizzazioni cassaforte chiave, eseguire il cmdlet Get-AzureRmKeyVault:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

Ad esempio:
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Per rimuovere le autorizzazioni dell'amministratore, eseguire il cmdlet Remove-AzureRmKeyVaultAccessPolicy:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

Ad esempio:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinare la protezione esecuzione programmi assegnato a una cassetta postale
<a name="DeterminemailboxDEP"> </a>

Per determinare la protezione esecuzione programmi assegnato a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce l'identificatore univoco (GUID).
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Utilizzare il GUID per trovare il nome descrittivo della protezione esecuzione programmi a cui viene assegnata alla cassetta postale eseguendo il cmdlet seguente.
  
```
Get-DataEncryptionPolicy <GUID>
```

Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente. 
  

