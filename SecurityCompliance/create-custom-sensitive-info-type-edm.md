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
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification-preview"></a><span data-ttu-id="879a1-103">Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match (Anteprima)</span><span class="sxs-lookup"><span data-stu-id="879a1-103">See Create a custom sensitive information type with Exact Data Match based classification (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="879a1-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="879a1-104">Overview</span></span>

<span data-ttu-id="879a1-105">[Tipi di informazioni sensibili personalizzati](custom-sensitive-info-types.md) vengono usati per impedire la condivisione accidentale o inappropriata di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="879a1-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="879a1-106">Gli amministratori possono usare il [centro sicurezza e conformità](create-a-custom-sensitive-information-type.md) o [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per definire un tipo di informazioni sensibili personalizzato in base a modelli, evidenza (parole chiave come *dipendente*, *badge*, *ID* e così via), vicinanza tra caratteri (quant’è vicina l’evidenza ai caratteri in un determinato modello) e livelli di probabilità. </span><span class="sxs-lookup"><span data-stu-id="879a1-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="879a1-107">Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="879a1-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="879a1-108">Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché modelli e vicinanza?</span><span class="sxs-lookup"><span data-stu-id="879a1-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of patterns and proximity?</span></span> <span data-ttu-id="879a1-109">Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che si progettato per:</span><span class="sxs-lookup"><span data-stu-id="879a1-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>
- <span data-ttu-id="879a1-110">essere dinamico e aggiornabile;</span><span class="sxs-lookup"><span data-stu-id="879a1-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="879a1-111">offrire maggiore scalabilità;</span><span class="sxs-lookup"><span data-stu-id="879a1-111">be more scalable;</span></span>
- <span data-ttu-id="879a1-112">produrre meno falsi positivi;</span><span class="sxs-lookup"><span data-stu-id="879a1-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="879a1-113">usare dati sensibili strutturati;</span><span class="sxs-lookup"><span data-stu-id="879a1-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="879a1-114">gestire le informazioni sensibili in modo più sicuro; e</span><span class="sxs-lookup"><span data-stu-id="879a1-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="879a1-115">essere usato con più servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="879a1-115">be used with several Microsoft cloud services.</span></span>

![Classificazione basata su EDM](media/EDMClassification.png)

<span data-ttu-id="879a1-117">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="879a1-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="879a1-118">Il database può essere aggiornato giornalmente o settimanalmente e può contenere un massimo di 10 milioni di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="879a1-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="879a1-119">I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili.</span><span class="sxs-lookup"><span data-stu-id="879a1-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="879a1-120">È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) (DLP) o i [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="879a1-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="879a1-121">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="879a1-121">Required licenses and permissions</span></span>

- <span data-ttu-id="879a1-122">È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="879a1-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="879a1-123">Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="879a1-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

- <span data-ttu-id="879a1-124">Quando disponibile a livello generale, la classificazione basata su EDM sarà inclusa nei seguenti abbonamenti:</span><span class="sxs-lookup"><span data-stu-id="879a1-124">When generally available, EDM-based classification will be included in the following subscriptions:</span></span>
    - <span data-ttu-id="879a1-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="879a1-125">Office 365 Enterprise E5</span></span>
    - <span data-ttu-id="879a1-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="879a1-126">Microsoft 365 E5</span></span>
    - <span data-ttu-id="879a1-127">Conformità e protezione delle informazioni di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="879a1-127">Microsoft 365 Information Protection and Compliance</span></span>
    - <span data-ttu-id="879a1-128">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="879a1-128">Office 365 Advanced Compliance</span></span>

> [!NOTE]
> <span data-ttu-id="879a1-129">\*\*La classificazione basata su EDM è attualmente disponibile in anteprima \*\* per [DLP in Office 365](data-loss-prevention-policies.md) (con Exchange Online e Microsoft teams) e [Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="879a1-129">**EDM-based classification is currently in preview** for [DLP in Office 365](data-loss-prevention-policies.md) (with Exchange Online and Microsoft Teams) and [Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="879a1-130">Se l'organizzazione dispone di [funzionalità DLP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), è possibile provare la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="879a1-130">If your organization has [DLP capabilities](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc#data-loss-prevention-dlp), you can try EDM-based classification.</span></span> <span data-ttu-id="879a1-131">Se non si sta già partecipando all'anteprima, [contattare Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) per iniziare.</span><span class="sxs-lookup"><span data-stu-id="879a1-131">If you are not already participating in the preview, [contact Microsoft](https://resources.office.com/us-landing-spe-contactus.html?LCID=EN-US) to get started.</span></span> 

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="879a1-132">Un’occhiata al flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="879a1-132">The work flow at a glance</span></span>

|<span data-ttu-id="879a1-133">Fase</span><span class="sxs-lookup"><span data-stu-id="879a1-133">Phase</span></span>  |<span data-ttu-id="879a1-134">Cosa serve</span><span class="sxs-lookup"><span data-stu-id="879a1-134">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="879a1-135">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-135">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="879a1-136">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="879a1-136">(As needed)</span></span><br/><span data-ttu-id="879a1-137">- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="879a1-137">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="879a1-138">- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="879a1-138">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="879a1-139">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-139">- Read access to the sensitive data</span></span><br/><span data-ttu-id="879a1-140">- Schema del database nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="879a1-140">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="879a1-141">- Pacchetto delle regole nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="879a1-141">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="879a1-142">- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell)</span><span class="sxs-lookup"><span data-stu-id="879a1-142">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="879a1-143">Parte 2: indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-143">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="879a1-144">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="879a1-144">(As needed)</span></span><br/>[<span data-ttu-id="879a1-145">Aggiornare i dati</span><span class="sxs-lookup"><span data-stu-id="879a1-145">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="879a1-146">- Gruppo di sicurezza personalizzato e account utente</span><span class="sxs-lookup"><span data-stu-id="879a1-146">- Custom security group and user account</span></span><br/><span data-ttu-id="879a1-147">- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-147">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="879a1-148">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-148">- Read access to the sensitive data</span></span><br/><span data-ttu-id="879a1-149">- Procedura e programmazione per l'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="879a1-149">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="879a1-150">Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="879a1-150">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="879a1-151">- Abbonamento a Office 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="879a1-151">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="879a1-152">- Funzionalità della classificazione basata su EDM abilitata (in anteprima)</span><span class="sxs-lookup"><span data-stu-id="879a1-152">- EDM-based classification feature enabled (in preview)</span></span> |

## <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="879a1-153">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-153">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="879a1-154">L’impostazione e la configurazione della classificazione basata su EDM implicano il salvataggio di dati sensibili in formato .csv, la definizione di uno schema per il database delle informazioni sensibili, la creazione di un pacchetto di regole e il caricamento del dello schema e del pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="879a1-154">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="879a1-155">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-155">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="879a1-156">Identificare le informazioni sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="879a1-156">Identify the KPIs that you want to use.</span></span> <span data-ttu-id="879a1-157">Esportare i dati in un'app, come Microsoft Excel, e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="879a1-157">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="879a1-158">Il file di dati può includere:</span><span class="sxs-lookup"><span data-stu-id="879a1-158">The data file can include:</span></span>

    - <span data-ttu-id="879a1-159">Fino a 10 milioni di righe di dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-159">Up to 10 million rows of sensitive data</span></span>
    - <span data-ttu-id="879a1-160">Fino a 32 colonne (campi) per origine dati</span><span class="sxs-lookup"><span data-stu-id="879a1-160">Up to 32 columns (fields) per data source</span></span>

2. <span data-ttu-id="879a1-161">Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="879a1-161">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="879a1-162">Nel file .csv potrebbero essere presenti nomi di campo, come “cf”, "data di nascita", "nome", "cognome" e così via.</span><span class="sxs-lookup"><span data-stu-id="879a1-162">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="879a1-163">Ad esempio, il file .csv è denominato *RecordPazienti.csv* e le relative colonne sono *IDPaziente*, *MRN*, *Cognome*, *Nome*, *CF* e così via.</span><span class="sxs-lookup"><span data-stu-id="879a1-163">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *lastname*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="879a1-164">Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="879a1-164">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="879a1-165">Assegnare un nome al file dello schema`edm.xml` e configurarlo in modo che per ogni colonna del database sia presente una linea che usi la sintassi `<Field name="" unique="" searchable=""/>`.</span><span class="sxs-lookup"><span data-stu-id="879a1-165">Name this schema file `edm.xml`, and configure it such that for each column in the database, there is a line that uses the syntax `<Field name="" unique="" searchable=""/>`.</span></span> 

    - <span data-ttu-id="879a1-166">Usare i nomi delle colonne per i valori dei *nomi dei campi*.</span><span class="sxs-lookup"><span data-stu-id="879a1-166">Use column names for *Field name* values.</span></span>
    - <span data-ttu-id="879a1-167">Usare *unique="true"* per i campi che contengono valori univoci (numeri di previdenza sociale, numeri di identificazione e così via); altrimenti usare *unique="false"*.</span><span class="sxs-lookup"><span data-stu-id="879a1-167">Use *unique="true"* for the fields that contain unique values (Social Security numbers, identification numbers, etc.); otherwise, use *unique="false"*.</span></span>
    - <span data-ttu-id="879a1-168">Usare *searchable="true"* per i campi che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="879a1-168">Use *searchable="true"* for the fields that you want to be searchable.</span></span> <span data-ttu-id="879a1-169">Non specificare più di cinque campi da cercare per database.</span><span class="sxs-lookup"><span data-stu-id="879a1-169">Do not specify more than five fields per database to be searchable.</span></span> <span data-ttu-id="879a1-170">Tutti gli altri campi devono essere *searchable="false"*.</span><span class="sxs-lookup"><span data-stu-id="879a1-170">All the rest should have *searchable="false"*.</span></span>  

    <span data-ttu-id="879a1-171">Ad esempio, il seguente file .xml definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili: *IDPaziente*, *MRN*, *CF*, \* Telefono\* e *Data nasc.*.</span><span class="sxs-lookup"><span data-stu-id="879a1-171">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> 
    
    <span data-ttu-id="879a1-172">(È possibile copiare, modificare e usare l’esempio.)</span><span class="sxs-lookup"><span data-stu-id="879a1-172">(You can copy, modify, and use our example.)</span></span>
    
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

4. <span data-ttu-id="879a1-173">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="879a1-173">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

5. <span data-ttu-id="879a1-174">Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="879a1-174">To upload the database schema, run the following cmdlets, one at a time:</span></span>

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    <span data-ttu-id="879a1-175">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="879a1-175">You will be prompted to confirm, as follows:</span></span>

       Confirm
       Are you sure you want to perform this action?
       New EDM Schema for the data store 'patientrecords' will be imported.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > <span data-ttu-id="879a1-176">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: `New-DlpEdmSchema -FileData $edmSchemaXml`</span><span class="sxs-lookup"><span data-stu-id="879a1-176">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: `New-DlpEdmSchema -FileData $edmSchemaXml`</span></span>
    
<span data-ttu-id="879a1-177">Ora che lo schema del database delle informazioni riservate è definito, il passaggio successivo consiste nel configurare un pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="879a1-177">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="879a1-178">Passare alla sezione [Configurare un pacchetto di regole](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="879a1-178">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="879a1-179">Modificare lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-179">Editing the schema for EDM-based classification</span></span> 

<span data-ttu-id="879a1-180">(Se necessario) Se si vogliono apportare modifiche al file edm.xml, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="879a1-180">(As needed) If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="879a1-181">Modificare il file edm.xml (il file descritto nella sezione [Definisci lo schema](#define-the-schema-for-your-database-of-sensitive-information) di questo articolo).</span><span class="sxs-lookup"><span data-stu-id="879a1-181">Edit your edm.mxl file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="879a1-182">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="879a1-182">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

3. <span data-ttu-id="879a1-183">Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="879a1-183">To update your database schema, run the following cmdlets, one at a time:</span></span>

    `$edmSchemaXml=Get-Content .\edm.xml -Encoding Byte -ReadCount 0`

    `Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

    <span data-ttu-id="879a1-184">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="879a1-184">You will be prompted to confirm, as follows:</span></span>

       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be updated.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):

    > [!TIP]
    > <span data-ttu-id="879a1-185">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: `Set-DlpEdmSchema -FileData $edmSchemaXml`</span><span class="sxs-lookup"><span data-stu-id="879a1-185">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: `Set-DlpEdmSchema -FileData $edmSchemaXml`</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="879a1-186">Rimuovere lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-186">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="879a1-187">(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="879a1-187">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="879a1-188">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="879a1-188">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

2. <span data-ttu-id="879a1-189">Eseguire il cmdlet di PowerShell seguente, sostituendo il nome dell'archivio dati di "patientrecords" con quello che si vuole rimuovere:</span><span class="sxs-lookup"><span data-stu-id="879a1-189">Run the following PowerShell cmdlet, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

    `Remove-DlpEdmSchema -Identity patientrecords`

     <span data-ttu-id="879a1-190">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="879a1-190">You will be prompted to confirm, as follows:</span></span>
    
       Confirm
       Are you sure you want to perform this action?
       EDM Schema for the data store 'patientrecords' will be removed.
       [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
    
    > [!TIP]
    > <span data-ttu-id="879a1-191">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`</span><span class="sxs-lookup"><span data-stu-id="879a1-191">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: `Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false`</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="879a1-192">Configurare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="879a1-192">Set up a rule package</span></span>

1. <span data-ttu-id="879a1-193">Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="879a1-193">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="879a1-194">(È possibile copiare, modificare e usare l’esempio.)</span><span class="sxs-lookup"><span data-stu-id="879a1-194">(You can copy, modify, and use our example.)</span></span> 

   <span data-ttu-id="879a1-195">Ricordarsi della procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili: *PatientID *, *MRN*, *SSN*, *Telefono* e*DOB*.</span><span class="sxs-lookup"><span data-stu-id="879a1-195">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="879a1-196">Il pacchetto di regole di esempio include questi campi e fa riferimento al file schema di database (edm.xml), con un unico elemento *ExactMatch* per ogni campo ricercabile.</span><span class="sxs-lookup"><span data-stu-id="879a1-196">Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="879a1-197">Si prenda in considerazione l’elemento ExactMatch seguente:</span><span class="sxs-lookup"><span data-stu-id="879a1-197">Consider the following ExactMatch item:</span></span>

   ```
    <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
    </ExactMatch>
   ```

    <span data-ttu-id="879a1-198">Utilizzando l'esempio proposto, osservare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="879a1-198">In this example, note the following:</span></span>

    - <span data-ttu-id="879a1-199">Il nome del dataStore fa riferimento al file .csv creato in precedenza: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="879a1-199">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>
    - <span data-ttu-id="879a1-200">Il valore idMatch fa riferimento a un campo ricercabile elencato nel file di schema del database: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="879a1-200">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>
    - <span data-ttu-id="879a1-201">Il valore di classificazione fa riferimento a un tipo di informazioni riservate esistente o personalizzato: **classificazione = "Stati Uniti - Numero di previdenza sociale (SSN)”**.</span><span class="sxs-lookup"><span data-stu-id="879a1-201">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="879a1-202">(In questo caso, viene usato il tipo di informazioni riservate esistente del Numero di previdenza sociale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="879a1-202">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

    <span data-ttu-id="879a1-203">Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file edm.xml.</span><span class="sxs-lookup"><span data-stu-id="879a1-203">When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file.</span></span> <span data-ttu-id="879a1-204">(È possibile copiare, modificare e usare l’esempio.)</span><span class="sxs-lookup"><span data-stu-id="879a1-204">(You can copy, modify, and use our example.)</span></span> 

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
    
2. <span data-ttu-id="879a1-205">Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="879a1-205">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

    `$rulepack=Get-Content .\rulepack.xml -Encoding Byte -ReadCount 0`

    `New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack`

<span data-ttu-id="879a1-206">A questo punto è stata configurata la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="879a1-206">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="879a1-207">Il passaggio successivo consiste nell'indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="879a1-207">The next step is to index the sensitive data, and then upload the indexed data.</span></span> 

## <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="879a1-208">Parte 2: indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-208">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="879a1-209">In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="879a1-209">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="879a1-210">Successivamente, è possibile usare lo strumento per indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="879a1-210">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="879a1-211">Impostare il gruppo di sicurezza e l’account utente</span><span class="sxs-lookup"><span data-stu-id="879a1-211">Set up the security group and user account</span></span>

1. <span data-ttu-id="879a1-212">Come amministratore globale, andare all’interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com)) e [creare un gruppo di sicurezza](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) denominato `EDM_DataUploaders`.</span><span class="sxs-lookup"><span data-stu-id="879a1-212">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called `EDM_DataUploaders`.</span></span> 

2. <span data-ttu-id="879a1-213">Aggiungere uno o più utenti al gruppo di sicurezza *EDM_DataUploaders*.</span><span class="sxs-lookup"><span data-stu-id="879a1-213">Add one or more users to the *EDM_DataUploaders* security group.</span></span> <span data-ttu-id="879a1-214">(Questi utenti gestiranno il database delle informazioni sensibili).</span><span class="sxs-lookup"><span data-stu-id="879a1-214">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="879a1-215">Assicurarsi che ogni utente che gestisce i dati sensibili sia un amministratore locale nel computer usato per l'Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="879a1-215">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="879a1-216">Impostare l'agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-216">Set up the EDM Upload Agent</span></span>

> [!NOTE]
> <span data-ttu-id="879a1-217">Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza *EDM_DataUploaders* e un amministratore locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="879a1-217">Before you begin this procedure, make sure that you are a member of the *EDM_DataUploaders* security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="879a1-218">Scaricare e installare l'Agente di caricamento di EDM in [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639).</span><span class="sxs-lookup"><span data-stu-id="879a1-218">Download and install the EDM Upload Agent at [https://go.microsoft.com/fwlink/?linkid=2088639](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="879a1-219">Per impostazione predefinita, il percorso di installazione deve essere `C:\Program Files\Microsoft\EdmUploadAgent`.</span><span class="sxs-lookup"><span data-stu-id="879a1-219">By default, the installation location should be `C:\Program Files\Microsoft\EdmUploadAgent`.</span></span> 

2. <span data-ttu-id="879a1-220">Per autorizzare l'Agente di caricamento di EDM, aprire il prompt dei comandi di Windows (come amministratore) e quindi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="879a1-220">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="879a1-221">Accedere con l'account aziendale o dell'istituto di istruzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="879a1-221">Sign in with your Office 365 work or school account.</span></span>

<span data-ttu-id="879a1-222">Il passaggio successivo consiste nell'usare l’Agente di caricamento di EDM per indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="879a1-222">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="879a1-223">Indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-223">Index and upload the sensitive data</span></span>

1. <span data-ttu-id="879a1-224">Salvare il file di dati sensibili, ossia l’esempio *RecordPazienti.csv*, nell'unità locale del computer.</span><span class="sxs-lookup"><span data-stu-id="879a1-224">Save the sensitive data file (recall our example is *PatientRecords.csv*) to the local drive on the machine.</span></span> <span data-ttu-id="879a1-225">(Il file d’esempio *RecordPazienti.csv* è stato salvato in `C:\Edm\Data`.)</span><span class="sxs-lookup"><span data-stu-id="879a1-225">(We saved our example *PatientRecords.csv* file to `C:\Edm\Data`.)</span></span>

2. <span data-ttu-id="879a1-226">Per indicizzare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="879a1-226">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /CreateHash /DataStoreName <DataStoreName> /DataFile <DataFilePath> /HashLocation <HashedFileLocation>`

    <span data-ttu-id="879a1-227">Esempio: **EdmUploadAgent.exe /CreateHash /DataStoreName RecordPazienti /DataFile C:\Edm\Data\RecordPazienti.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="879a1-227">Example: **EdmUploadAgent.exe /CreateHash /DataStoreName PatientRecords /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span> 

3. <span data-ttu-id="879a1-228">Per caricare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="879a1-228">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /UploadHash /DataStoreName <DataStoreName> /HashFile <HashedSourceFilePath>`

    <span data-ttu-id="879a1-229">Esempio: **EdmUploadAgent.exe /UploadHash /DataStoreName RecordPazienti /HashFile C:\Edm\Hash\RecordPazienti.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="879a1-229">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\Edm\Hash\PatientRecords.EdmHash**</span></span> 

4. <span data-ttu-id="879a1-230">Per verificare che i dati sensibili siano stati caricati, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="879a1-230">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

    `EdmUploadAgent.exe /GetDataStore`

    <span data-ttu-id="879a1-231">Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento, in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="879a1-231">You'll see a list of data stores and when they were last updated, similar to the following:</span></span> <br/>![Esempio di cmdlet e risultati di GetDataStore](media/EDM-GetDataStore-example.png)

5. <span data-ttu-id="879a1-233">Procedere alla configurazione della procedura e della programmazione per [Aggiornamento del database delle informazioni sensibili](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="879a1-233">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="879a1-234">A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="879a1-234">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="879a1-235">Ad esempio, è possibile [impostare un criterio di DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="879a1-235">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span> 

### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="879a1-236">Aggiornare il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="879a1-236">Refreshing your sensitive information database</span></span>

<span data-ttu-id="879a1-237">È possibile aggiornare il database delle informazioni sensibili giornalmente o settimanalmente e lo strumento di caricamento di EDM può reindicizzare i dati sensibili e quindi ricaricarli.</span><span class="sxs-lookup"><span data-stu-id="879a1-237">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span> 

1. <span data-ttu-id="879a1-238">Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="879a1-238">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="879a1-239">Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel, e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="879a1-239">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="879a1-240">Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="879a1-240">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

    > [!NOTE]
    > <span data-ttu-id="879a1-241">Se non sono state apportate modifiche alla struttura (nomi dei campi) del file .csv, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati.</span><span class="sxs-lookup"><span data-stu-id="879a1-241">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="879a1-242">Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo [schema del database](#editing-the-schema-for-edm-based-classification) e [il pacchetto delle regole](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="879a1-242">But if you must make changes, make sure to edit the [database schema](#editing-the-schema-for-edm-based-classification) and your [rule package](#set-up-a-rule-package) accordingly.</span></span>        

3. <span data-ttu-id="879a1-243">Usare [l'Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) per automatizzare i passaggi 2 e 3 nella procedura [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="879a1-243">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="879a1-244">È possibile pianificare le attività in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="879a1-244">You can schedule tasks using several methods:</span></span>
    
    |<span data-ttu-id="879a1-245">Metodo</span><span class="sxs-lookup"><span data-stu-id="879a1-245">Method</span></span>  |<span data-ttu-id="879a1-246">Soluzione</span><span class="sxs-lookup"><span data-stu-id="879a1-246">What to do</span></span>  |
    |---------|---------|
    |<span data-ttu-id="879a1-247">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="879a1-247">Windows PowerShell</span></span>     |<span data-ttu-id="879a1-248">Consultare la documentazione dell’[Utilità di pianificazione](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) e [gli script di PowerShell di esempio](#example-powershell-script-for-task-scheduler) illustrati in questo articolo</span><span class="sxs-lookup"><span data-stu-id="879a1-248">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span>|
    |<span data-ttu-id="879a1-249">API dell’Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="879a1-249">Task Scheduler API</span></span> |<span data-ttu-id="879a1-250">Consultare la documentazione dell’[Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="879a1-250">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span> |
    |<span data-ttu-id="879a1-251">Interfaccia utente Windows</span><span class="sxs-lookup"><span data-stu-id="879a1-251">Windows user interface</span></span>     |<span data-ttu-id="879a1-252">In Windows, fare clic su **Start** e digitare `Task Scheduler`.</span><span class="sxs-lookup"><span data-stu-id="879a1-252">In Windows, click **Start**, and type `Task Scheduler`.</span></span> <span data-ttu-id="879a1-253">Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull’**Utilità di pianificazione** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="879a1-253">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>          |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="879a1-254">Esempio di script di PowerShell per Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="879a1-254">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="879a1-255">Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di indicizzazione dei dati e il caricamento dei dati indicizzati:</span><span class="sxs-lookup"><span data-stu-id="879a1-255">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

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
## <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="879a1-256">Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="879a1-256">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="879a1-257">È anche possibile usare la classificazione basata su EDM con le funzionalità di protezione delle informazioni, come i [criteri di DLP di Office 365](data-loss-prevention-policies.md) e i [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="879a1-257">You can use EDM-based classification with information protection features, such as [Office 365 DLP policies](data-loss-prevention-policies.md) and [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span> <span data-ttu-id="879a1-258">La seguente procedura descrive come usare EDM con un criterio di DLP creato nel centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="879a1-258">The following procedure describes how to use EDM with a DLP policy that is created in the Office 365 Security & Compliance Center.</span></span>

### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="879a1-259">Creazione di un criterio di DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="879a1-259">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="879a1-260">Andare al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="879a1-260">Go to the Security & Compliance Center</span></span>

2. <span data-ttu-id="879a1-261">Scegliere **Prevenzione della perdita dei dati** > **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="879a1-261">Click **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="879a1-262">Scegliere **Crea un criterio** > **Personalizzato** > **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-262">Choose **Create a policy** > **Custom** > **Next**.</span></span>

4. <span data-ttu-id="879a1-263">Nella scheda **Nome criterio**, specificare un nome e una descrizione, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-263">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="879a1-264">Nella scheda **Scegli posizioni**, selezionare **Consenti di scegliere posizioni specifiche** e poi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-264">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="879a1-265">![Opzione Seleziona posizioni](media/DLP-EDM-newpolicy-chooselocations.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-265">![Choose locations option](media/DLP-EDM-newpolicy-chooselocations.png)</span></span><br/>

6. <span data-ttu-id="879a1-266">Nella colonna **Stato**, selezionare solo **posta elettronica di Exchange** e poi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-266">In the **Status** column, select **Exchange email** only, and then choose **Next**.</span></span> <br/><span data-ttu-id="879a1-267">![Criterio di EDM con solo Exchange](media/EDM-DLPpolicy-ExchangeOnly.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-267">![EDM policy with Exchange only](media/EDM-DLPpolicy-ExchangeOnly.png)</span></span><br/>

7. <span data-ttu-id="879a1-268">Nella scheda **Impostazioni criterio**, scegliere **Usa impostazioni avanzate** e poi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-268">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span><br/><span data-ttu-id="879a1-269">![Usare le impostazioni avanzate](media/edm-dlp-policy-advancedsettings.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-269">![Use advanced settings](media/edm-dlp-policy-advancedsettings.png)</span></span><br/>

8. <span data-ttu-id="879a1-270">Scegliere **+ Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="879a1-270">Choose **+ New rule**.</span></span><br/><span data-ttu-id="879a1-271">![Creare una regola](media/edm-dlp-newrule.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-271">![Create a query rule</span></span><br/>

9. <span data-ttu-id="879a1-272">Nella sezione **Nome**, specificare un nome e una descrizione per la regola. </span><span class="sxs-lookup"><span data-stu-id="879a1-272">Use the **Name and Description** section to specify a name and description for the category.</span></span><br/><span data-ttu-id="879a1-273">![Campi della nuova regola](media/edm-dlp-newruleform.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-273">![New rule fields](media/edm-dlp-newruleform.png)</span></span><br/>

10. <span data-ttu-id="879a1-274">Nella sezione **Condizioni**, nell'elenco **+ Aggiungi una condizione**, scegliere **Il contenuto include il tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="879a1-274">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="879a1-275">![Il contenuto include il tipo di informazioni sensibili](media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-275">![Content contains sensitive info types](media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="879a1-276">Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole e quindi scegliere **+ Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="879a1-276">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span><br/><span data-ttu-id="879a1-277">![Trovare il tipo di informazioni sensibili](media/edm-dlp-newrulefindsensitiverulepack.png)</span><span class="sxs-lookup"><span data-stu-id="879a1-277">![Find the sensitive info type](media/edm-dlp-newrulefindsensitiverulepack.png)</span></span><br/><span data-ttu-id="879a1-278">Poi scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="879a1-278">Then choose **Done**.</span></span>

12. <span data-ttu-id="879a1-279">Infine selezionare le opzioni per la regola, come **Notifiche utente**, **Personalizzazioni utente**, **Report degli eventi** e così via, quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="879a1-279">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="879a1-280">Nella scheda **Impostazioni criterio**, esaminare le regole e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-280">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="879a1-281">Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato.</span><span class="sxs-lookup"><span data-stu-id="879a1-281">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="879a1-282">Quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="879a1-282">Then choose **Next**.</span></span>

15. <span data-ttu-id="879a1-283">Nella scheda **Esamina le impostazioni**, controlla il criterio.</span><span class="sxs-lookup"><span data-stu-id="879a1-283">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="879a1-284">Apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="879a1-284">Make any needed changes.</span></span> <span data-ttu-id="879a1-285">Al termine, scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="879a1-285">When you're ready, choose **Create**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="879a1-286">Il nuovo criterio di DLP sarà attivo nel centro dati dopo circa un’ora.</span><span class="sxs-lookup"><span data-stu-id="879a1-286">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="879a1-287">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="879a1-287">Related articles</span></span>

[<span data-ttu-id="879a1-288">Tipi di informazioni sensibili integrati e cosa individuano</span><span class="sxs-lookup"><span data-stu-id="879a1-288">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="879a1-289">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="879a1-289">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="879a1-290">Panoramica sui criteri di DLP</span><span class="sxs-lookup"><span data-stu-id="879a1-290">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="879a1-291">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="879a1-291">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
