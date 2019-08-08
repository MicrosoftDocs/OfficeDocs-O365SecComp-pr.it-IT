---
title: Creare un tipo di informazioni sensibili personalizzato con Exact Data Match
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 05/15/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match.
ms.openlocfilehash: be86f22ec20d36aaf12ae253028d0896f885267e
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230840"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification-preview"></a>Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match (Anteprima)

## <a name="overview"></a>Panoramica

[Tipi di informazioni sensibili personalizzati](custom-sensitive-info-types.md) vengono usati per impedire la condivisione accidentale o inappropriata di informazioni riservate. Gli amministratori possono usare il [centro sicurezza e conformità](create-a-custom-sensitive-information-type.md) o [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per definire un tipo di informazioni sensibili personalizzato in base a modelli, evidenza (parole chiave come *dipendente*, *badge*, *ID* e così via), vicinanza tra caratteri (quant’è vicina l’evidenza ai caratteri in un determinato modello) e livelli di probabilità.  Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.

Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché modelli e vicinanza? Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che si progettato per:
- essere dinamico e aggiornabile;
- offrire maggiore scalabilità;
- produrre meno falsi positivi;
- usare dati sensibili strutturati;
- gestire le informazioni sensibili in modo più sicuro; e
- essere usato con più servizi cloud Microsoft.

![Classificazione basata su EDM](media/EDMClassification.png)

La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili. Il database può essere aggiornato giornalmente o settimanalmente e può contenere un massimo di 10 milioni di righe di dati. I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili. È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) (DLP) o i [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

- È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo. Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

- Quando disponibile a livello generale, la classificazione basata su EDM sarà inclusa nei seguenti abbonamenti:
    - Office 365 E5
    - Microsoft 365 E5
    - Conformità e protezione delle informazioni di Microsoft 365
    - Office 365 Advanced Compliance

> [!NOTE]
> **La classificazione basata su EDM è attualmente disponibile in anteprima ** per [DLP in Office 365](data-loss-prevention-policies.md) (con Exchange Online e Microsoft teams) e [Cloud App Security](https://docs.microsoft.com/cloud-app-security). Se l'organizzazione dispone di [funzionalità DLP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), è possibile provare la classificazione basata su EDM. Se non si sta già partecipando all'anteprima, [contattare Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) per iniziare. 

## <a name="the-work-flow-at-a-glance"></a>Un’occhiata al flusso di lavoro

|Fase  |Cosa serve  |
|---------|---------|
|[Parte 1: impostazione della classificazione basata su EDM](#part-1-set-up-edm-based-classification)<br/><br/>(In base alle esigenze)<br/>- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification) <br/>- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification) |- Accesso in lettura ai dati sensibili<br/>- Schema del database nel formato .xml (esempio fornito)<br/>- Pacchetto delle regole nel formato .xml (esempio fornito)<br/>- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell) |
|[Parte 2: indicizzare e caricare i dati sensibili](#part-2-index-and-upload-the-sensitive-data)<br/><br/>(In base alle esigenze)<br/>[Aggiornare i dati](#refreshing-your-sensitive-information-database) |- Gruppo di sicurezza personalizzato e account utente<br/>- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM<br/>- Accesso in lettura ai dati sensibili<br/>- Procedura e programmazione per l'aggiornamento dei dati|
|[Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |- Abbonamento a Office 365 con DLP<br/>- Funzionalità della classificazione basata su EDM abilitata (in anteprima) |

## <a name="part-1-set-up-edm-based-classification"></a>Parte 1: impostazione della classificazione basata su EDM

L’impostazione e la configurazione della classificazione basata su EDM implicano il salvataggio di dati sensibili in formato .csv, la definizione di uno schema per il database delle informazioni sensibili, la creazione di un pacchetto di regole e il caricamento del dello schema e del pacchetto di regole.

### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>Definire lo schema per il database delle informazioni sensibili

1. Identificare le informazioni sensibili da usare. Esportare i dati in un'app, come Microsoft Excel, e salvare il file in formato .csv. Il file di dati può includere:

    - Fino a 10 milioni di righe di dati sensibili
    - Fino a 32 colonne (campi) per origine dati

2. Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM. Nel file .csv potrebbero essere presenti nomi di campo, come “cf”, "data di nascita", "nome", "cognome" e così via. Ad esempio, il file .csv è denominato *RecordPazienti.csv* e le relative colonne sono *IDPaziente*, *MRN*, *Cognome*, *Nome*, *CF* e così via.

3. Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente). Assegnare un nome al file dello schema`edm.xml` e configurarlo in modo che per ogni colonna del database sia presente una linea che usi la sintassi `<Field name="" unique="" searchable=""/>`. 

    - Usare i nomi delle colonne per i valori dei *nomi dei campi*.
    - Usare *unique="true"* per i campi che contengono valori univoci (numeri di previdenza sociale, numeri di identificazione e così via); altrimenti usare *unique="false"*.
    - Usare *searchable="true"* per i campi che si desidera cercare. Non specificare più di cinque campi da cercare per database. Tutti gli altri campi devono essere *searchable="false"*.  

    Ad esempio, il seguente file .xml definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili: *IDPaziente*, *MRN*, *CF*, * Telefono* e *Data nasc.*. 
    
    (È possibile copiare, modificare e usare l’esempio.)
    
    ```<?xml version="1.0" encoding="utf-8"?>
    <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
        <DataStore name="PatientRecords" description="Schema for patient records" version="1">
            <Field name="PatientID" unique="false" searchable="true" />
            <Field name="MRN" unique="false" searchable="true" />
            <Field name="FirstName" unique="false" searchable="false" />
            <Field name="LastName" unique="false" searchable="false" />
            <Field name="SSN" unique="false" searchable="true" />
            <Field name="Phone" unique="false" searchable="true" />
            <Field name="DOB" unique="false" searchable="true" />
            <Field name="Gender" unique="false" searchable="false" />
            <Field name="Address" unique="false" searchable="false" />
        </DataStore>
    </EdmSchema>
    ```

4. [Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

5. Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    Verrà richiesto di confermare, come illustrato di seguito:

       Confirm
       Are you sure you want to perform this action?
       New EDM Schema for the data store 'patientrecords' will be imported.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: `New-DlpEdmSchema -FileData $edmSchemaXml`
    
Ora che lo schema del database delle informazioni riservate è definito, il passaggio successivo consiste nel configurare un pacchetto di regole. Passare alla sezione [Configurare un pacchetto di regole](#set-up-a-rule-package).

#### <a name="editing-the-schema-for-edm-based-classification"></a>Modificare lo schema per la classificazione basata su EDM 

(Se necessario) Se si vogliono apportare modifiche al file edm.xml, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:

1. Modificare il file edm.xml (il file descritto nella sezione [Definisci lo schema](#define-the-schema-for-your-database-of-sensitive-information) di questo articolo).

2. [Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

3. Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    Verrà richiesto di confermare, come illustrato di seguito:

       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be updated.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: `Set-DlpEdmSchema -FileData $edmSchemaXml`

#### <a name="removing-the-schema-for-edm-based-classification"></a>Rimuovere lo schema per la classificazione basata su EDM

(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:

1. [Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

2. Eseguire il cmdlet di PowerShell seguente, sostituendo il nome dell'archivio dati di "patientrecords" con quello che si vuole rimuovere:

    `Remove-DlpEdmSchema -Identity patientrecords`

     Verrà richiesto di confermare, come illustrato di seguito:
    
       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be removed.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
    
    > [!TIP]
    > Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`

### <a name="set-up-a-rule-package"></a>Configurare un pacchetto di regole

1. Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente. (È possibile copiare, modificare e usare l’esempio.) 

   Ricordarsi della procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili: *PatientID *, *MRN*, *SSN*, *Telefono* e*DOB*. Il pacchetto di regole di esempio include questi campi e fa riferimento al file schema di database (edm.xml), con un unico elemento *ExactMatch* per ogni campo ricercabile. Si prenda in considerazione l’elemento ExactMatch seguente:

   ```
    <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
    </ExactMatch>
   ```

    Utilizzando l'esempio proposto, osservare quanto segue:

    - Il nome del dataStore fa riferimento al file .csv creato in precedenza: **dataStore = "PatientRecords"**.
    - Il valore idMatch fa riferimento a un campo ricercabile elencato nel file di schema del database: **idMatch matches = "SSN"**.
    - Il valore di classificazione fa riferimento a un tipo di informazioni riservate esistente o personalizzato: **classificazione = "Stati Uniti - Numero di previdenza sociale (SSN)”**. (In questo caso, viene usato il tipo di informazioni riservate esistente del Numero di previdenza sociale degli Stati Uniti.

    Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file edm.xml. (È possibile copiare, modificare e usare l’esempio.) 

    ```<?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
      <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
        <Version build="0" major="2" minor="0" revision="0" />
        <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
        <Details defaultLangCode="en-us">
          <LocalizedDetails langcode="en-us">
            <PublisherName>IP DLP</PublisherName>
            <Name>Health Care EDM Rulepack</Name>
            <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
          </LocalizedDetails>
        </Details>
      </RulePack>
      <Rules>
        <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
          <Pattern confidenceLevel="65">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            <Any minMatches ="3" maxMatches ="100">
              <match matches="PatientID" />
              <match matches="MRN"/>
              <match matches="FirstName"/>
              <match matches="LastName"/>
              <match matches="Phone"/>
              <match matches="DOB"/>
            </Any>
          </Pattern>
        </ExactMatch>
        <LocalizedStrings>
          <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
            <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
            <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
          </Resource>
        </LocalizedStrings>
      </Rules>
    </RulePackage>
    ```
    
2. Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:

    `$rulepack=Get-Content .\rulepack.xml -Encoding Byte -ReadCount 0`

    `New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack`

A questo punto è stata configurata la classificazione basata su EDM. Il passaggio successivo consiste nell'indicizzare i dati sensibili e poi di caricarli. 

## <a name="part-2-index-and-upload-the-sensitive-data"></a>Parte 2: indicizzare e caricare i dati sensibili

In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM. Successivamente, è possibile usare lo strumento per indicizzare i dati sensibili e poi di caricarli.

### <a name="set-up-the-security-group-and-user-account"></a>Impostare il gruppo di sicurezza e l’account utente

1. Come amministratore globale, andare all’interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) e [creare un gruppo di sicurezza](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominato `EDM_DataUploaders`. 

2. Aggiungere uno o più utenti al gruppo di sicurezza *EDM_DataUploaders*. (Questi utenti gestiranno il database delle informazioni sensibili).

3. Assicurarsi che ogni utente che gestisce i dati sensibili sia un amministratore locale nel computer usato per l'Agente di caricamento di EDM.

### <a name="set-up-the-edm-upload-agent"></a>Impostare l'agente di caricamento di EDM

> [!NOTE]
> Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza *EDM_DataUploaders* e un amministratore locale nel computer.

1. Scaricare e installare l'Agente di caricamento di EDM in [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639). Per impostazione predefinita, il percorso di installazione deve essere `C:\Program Files\Microsoft\EdmUploadAgent`. 

2. Per autorizzare l'Agente di caricamento di EDM, aprire il prompt dei comandi di Windows (come amministratore) e quindi eseguire il comando seguente:

    `EdmUploadAgent.exe /Authorize`

3. Accedere con l'account aziendale o dell'istituto di istruzione di Office 365.

Il passaggio successivo consiste nell'usare l’Agente di caricamento di EDM per indicizzare i dati sensibili e poi di caricarli.

### <a name="index-and-upload-the-sensitive-data"></a>Indicizzare e caricare i dati sensibili

1. Salvare il file di dati sensibili, ossia l’esempio *RecordPazienti.csv*, nell'unità locale del computer. (Il file d’esempio *RecordPazienti.csv* è stato salvato in `C:\Edm\Data`.)

2. Per indicizzare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:

    `EdmUploadAgent.exe /CreateHash /DataStoreName <DataStoreName> /DataFile <DataFilePath> /HashLocation <HashedFileLocation>`

    Esempio: **EdmUploadAgent.exe /CreateHash /DataStoreName RecordPazienti /DataFile C:\Edm\Data\RecordPazienti.csv /HashLocation C:\Edm\Hash** 

3. Per caricare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:

    `EdmUploadAgent.exe /UploadHash /DataStoreName <DataStoreName> /HashFile <HashedSourceFilePath>`

    Esempio: **EdmUploadAgent.exe /UploadHash /DataStoreName RecordPazienti /HashFile C:\Edm\Hash\RecordPazienti.EdmHash** 

4. Per verificare che i dati sensibili siano stati caricati, eseguire il seguente comando nel prompt dei comandi di Windows:

    `EdmUploadAgent.exe /GetDataStore`

    Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento, in modo simile al seguente: <br/>![Esempio di cmdlet e risultati di GetDataStore](media/EDM-GetDataStore-example.png)

5. Procedere alla configurazione della procedura e della programmazione per [Aggiornamento del database delle informazioni sensibili](#refreshing-your-sensitive-information-database).

A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft. Ad esempio, è possibile [impostare un criterio di DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm). 

### <a name="refreshing-your-sensitive-information-database"></a>Aggiornare il database delle informazioni sensibili

È possibile aggiornare il database delle informazioni sensibili giornalmente o settimanalmente e lo strumento di caricamento di EDM può reindicizzare i dati sensibili e quindi ricaricarli. 

1. Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.

2. Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel, e salvare il file in formato .csv. Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data).

    > [!NOTE]
    > Se non sono state apportate modifiche alla struttura (nomi dei campi) del file .csv, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati. Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo [schema del database](#editing-the-schema-for-edm-based-classification) e [il pacchetto delle regole](#set-up-a-rule-package).        

3. Usare [l'Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) per automatizzare i passaggi 2 e 3 nella procedura [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data). È possibile pianificare le attività in diversi modi:
    
    |Metodo  |Soluzione  |
    |---------|---------|
    |Windows PowerShell     |Consultare la documentazione dell’[Utilità di pianificazione](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) e [gli script di PowerShell di esempio](#example-powershell-script-for-task-scheduler) illustrati in questo articolo|
    |API dell’Utilità di pianificazione |Consultare la documentazione dell’[Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) |
    |Interfaccia utente Windows     |In Windows, fare clic su **Start** e digitare `Task Scheduler`. Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull’**Utilità di pianificazione** e scegliere **Esegui come amministratore**.          |

#### <a name="example-powershell-script-for-task-scheduler"></a>Esempio di script di PowerShell per Utilità di pianificazione

Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di indicizzazione dei dati e il caricamento dei dati indicizzati:

```powershell
param([string]$dataStoreName,[string]$fileLocation)
# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\$env:USERNAME"
$edminstallpath = 'C:\Program Files\Microsoft\EdmUploadAgent\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\$dataStoreName$csvext"
$hashFile = "$fileLocation\$dataStoreName$edmext"
# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($creds.Password))
# Register the scheduled task
$taskName = 'EDMUpload_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```
## <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft

È anche possibile usare la classificazione basata su EDM con le funzionalità di protezione delle informazioni, come i [criteri di DLP di Office 365](data-loss-prevention-policies.md) e i [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies). La seguente procedura descrive come usare EDM con un criterio di DLP creato nel centro sicurezza e conformità di Office 365.

### <a name="to-create-a-dlp-policy-with-edm"></a>Creazione di un criterio di DLP con EDM

1. Andare al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).

2. Scegliere **Prevenzione della perdita dei dati** > **Criteri**.

3. Scegliere **Crea un criterio** > **Personalizzato** > **Avanti**.

4. Nella scheda **Nome criterio**, specificare un nome e una descrizione, quindi scegliere **Avanti**.

5. Nella scheda **Scegli posizioni**, selezionare **Consenti di scegliere posizioni specifiche** e poi **Avanti**.<br/>![Opzione Seleziona posizioni](media/DLP-EDM-newpolicy-chooselocations.png)<br/>

6. Nella colonna **Stato**, selezionare solo **posta elettronica di Exchange** e poi **Avanti**. <br/>![Criterio di EDM con solo Exchange](media/EDM-DLPpolicy-ExchangeOnly.png)<br/>

7. Nella scheda **Impostazioni criterio**, scegliere **Usa impostazioni avanzate** e poi **Avanti**.<br/>![Usare le impostazioni avanzate](media/edm-dlp-policy-advancedsettings.png)<br/>

8. Scegliere **+ Nuova regola**.<br/>![Creare una regola](media/edm-dlp-newrule.png)<br/>

9. Nella sezione **Nome**, specificare un nome e una descrizione per la regola. <br/>![Campi della nuova regola](media/edm-dlp-newruleform.png)<br/>

10. Nella sezione **Condizioni**, nell'elenco **+ Aggiungi una condizione**, scegliere **Il contenuto include il tipo di informazioni sensibili**.<br/>![Il contenuto include il tipo di informazioni sensibili](media/edm-dlp-newrule-conditions.png)<br/>

11. Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole e quindi scegliere **+ Aggiungi.**<br/>![Trovare il tipo di informazioni sensibili](media/edm-dlp-newrulefindsensitiverulepack.png)<br/>Poi scegliere **Fatto**.

12. Infine selezionare le opzioni per la regola, come **Notifiche utente**, **Personalizzazioni utente**, **Report degli eventi** e così via, quindi scegliere **Salva**.

13. Nella scheda **Impostazioni criterio**, esaminare le regole e quindi scegliere **Avanti**.

14. Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato. Quindi scegliere **Avanti**.

15. Nella scheda **Esamina le impostazioni**, controlla il criterio. Apportare le modifiche necessarie. Al termine, scegliere **Crea**.

    > [!NOTE]
    > Il nuovo criterio di DLP sarà attivo nel centro dati dopo circa un’ora.

## <a name="related-articles"></a>Articoli correlati

[Tipi di informazioni sensibili integrati e cosa individuano](what-the-sensitive-information-types-look-for.md)

[Tipi di informazioni sensibili personalizzati](custom-sensitive-info-types.md)

[Panoramica sui criteri di DLP](data-loss-prevention-policies.md)

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)
