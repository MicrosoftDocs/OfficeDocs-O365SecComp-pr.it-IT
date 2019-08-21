---
title: Creare un tipo di informazioni sensibili personalizzato con Exact Data Match
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match.
ms.openlocfilehash: 3c2b7cbabc77328f7d907927008e93606d40eded
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478195"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="5955d-103">Creare tipi di informazioni sensibili personalizzati con classificazione esatta basata su Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="5955d-103">See Create a custom sensitive information type with Exact Data Match based classification (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="5955d-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5955d-104">Overview</span></span>

<span data-ttu-id="5955d-105">
  [Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/it-IT/office365/securitycompliance/custom-sensitive-info-types)  vengono usati per impedire la condivisione accidentale o inappropriata di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="5955d-105">[Custom sensitive information types](https://docs.microsoft.com/en-us/office365/securitycompliance/custom-sensitive-info-types) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="5955d-106">Gli amministratori possono usare il  [Centro sicurezza e conformità](https://docs.microsoft.com/it-IT/office365/securitycompliance/create-a-custom-sensitive-information-type) o [PowerShell](https://docs.microsoft.com/it-IT/office365/securitycompliance/create-a-custom-sensitive-information-type-in-scc-powershell)  per definire un tipo di informazioni sensibili personalizzato in base a modelli, evidenza (parole chiave come  *dipendente*,  *badge*,  *ID* e così via), vicinanza tra caratteri (quant'è vicina l'evidenza ai caratteri in un determinato modello) e livelli di probabilità.</span><span class="sxs-lookup"><span data-stu-id="5955d-106">As an administrator, you can use the [Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/create-a-custom-sensitive-information-type) or [PowerShell](https://docs.microsoft.com/en-us/office365/securitycompliance/create-a-custom-sensitive-information-type-in-scc-powershell) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="5955d-107">Questi tipi di informazioni sensibili personalizzati soddisfano le esigenze aziendali di molte organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5955d-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="5955d-108">Ma cosa succede se si vuole un tipo di informazioni sensibili personalizzato che usi valori di dati esatti, anziché modelli generici basati solo sulla corrispondenza?</span><span class="sxs-lookup"><span data-stu-id="5955d-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="5955d-109">Con la classificazione basata su Exact Data Match (EDM) è possibile creare un tipo di informazioni sensibili personalizzato che sia progettato per:</span><span class="sxs-lookup"><span data-stu-id="5955d-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="5955d-110">essere dinamico e aggiornabile;</span><span class="sxs-lookup"><span data-stu-id="5955d-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="5955d-111">offrire maggiore scalabilità;</span><span class="sxs-lookup"><span data-stu-id="5955d-111">be more scalable;</span></span>
- <span data-ttu-id="5955d-112">produrre meno falsi positivi;</span><span class="sxs-lookup"><span data-stu-id="5955d-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="5955d-113">usare dati sensibili strutturati;</span><span class="sxs-lookup"><span data-stu-id="5955d-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="5955d-114">gestire le informazioni sensibili in modo più sicuro; e</span><span class="sxs-lookup"><span data-stu-id="5955d-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="5955d-115">essere usato con più servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5955d-115">be used with several Microsoft cloud services.</span></span>

![Classificazione basata su EDM](media/EDMClassification.png)

<span data-ttu-id="5955d-117">La classificazione basata su EDM consente di creare tipi di informazioni sensibili personalizzati che fanno riferimento a valori esatti in un database di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="5955d-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="5955d-118">Il database può essere aggiornato giornalmente o settimanalmente e può contenere un massimo di 10 milioni di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="5955d-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="5955d-119">I dipendenti, i pazienti o i clienti vanno e vengono e i record cambiano, i tipi di informazioni sensibili personalizzati rimangono aggiornati e disponibili.</span><span class="sxs-lookup"><span data-stu-id="5955d-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="5955d-120">È anche possibile usare una classificazione basata su EDM con criteri, ad esempio i  [criteri di prevenzione della perdita dei dati ](https://docs.microsoft.com/it-IT/office365/securitycompliance/data-loss-prevention-policies) (DLP) o i  [criteri dei file di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="5955d-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="5955d-121">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="5955d-121">Required licenses and permissions</span></span>

<span data-ttu-id="5955d-122">È necessario essere un amministratore globale, di conformità o di Exchange Online per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5955d-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="5955d-123">Per ulteriori informazioni sulle autorizzazioni DLP, vedere  [Autorizzazioni](https://docs.microsoft.com/it-IT/office365/securitycompliance/data-loss-prevention-policies#permissions).</span><span class="sxs-lookup"><span data-stu-id="5955d-123">To learn more about DLP permissions, see [Permissions](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#permissions).</span></span>

<span data-ttu-id="5955d-124">Quando disponibile a livello generale, la classificazione basata su EDM sarà inclusa negli abbonamenti</span><span class="sxs-lookup"><span data-stu-id="5955d-124">When generally available, EDM-based classification will be included in these subscriptions</span></span>

- <span data-ttu-id="5955d-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5955d-125">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="5955d-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5955d-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="5955d-127">Conformità e protezione delle informazioni di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5955d-127">Microsoft 365 Information Protection and Compliance</span></span>
- <span data-ttu-id="5955d-128">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="5955d-128">Office 365 Advanced Compliance</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="5955d-129">Flusso di lavoro in breve</span><span class="sxs-lookup"><span data-stu-id="5955d-129">The work flow at a glance</span></span>

|<span data-ttu-id="5955d-130">Fase</span><span class="sxs-lookup"><span data-stu-id="5955d-130">Phase</span></span>  |<span data-ttu-id="5955d-131">Cosa serve</span><span class="sxs-lookup"><span data-stu-id="5955d-131">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="5955d-132">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-132">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="5955d-133">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="5955d-133">(As needed)</span></span><br/><span data-ttu-id="5955d-134">- [Modificare lo schema del database](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="5955d-134">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="5955d-135">- [Rimuovere lo schema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="5955d-135">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="5955d-136">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-136">- Read access to the sensitive data</span></span><br/><span data-ttu-id="5955d-137">- Schema del database nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="5955d-137">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="5955d-138">- Pacchetto delle regole nel formato .xml (esempio fornito)</span><span class="sxs-lookup"><span data-stu-id="5955d-138">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="5955d-139">- Autorizzazioni di amministratore al Centro sicurezza e conformità (utilizzando PowerShell)</span><span class="sxs-lookup"><span data-stu-id="5955d-139">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="5955d-140">Parte 2: indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-140">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="5955d-141">(In base alle esigenze)</span><span class="sxs-lookup"><span data-stu-id="5955d-141">(As needed)</span></span><br/>[<span data-ttu-id="5955d-142">Aggiornare i dati</span><span class="sxs-lookup"><span data-stu-id="5955d-142">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="5955d-143">- Gruppo di sicurezza personalizzato e account utente</span><span class="sxs-lookup"><span data-stu-id="5955d-143">- Custom security group and user account</span></span><br/><span data-ttu-id="5955d-144">- Accesso come amministratore locale al computer con l’Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-144">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="5955d-145">- Accesso in lettura ai dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-145">- Read access to the sensitive data</span></span><br/><span data-ttu-id="5955d-146">- Procedura e programmazione per l'aggiornamento dei dati</span><span class="sxs-lookup"><span data-stu-id="5955d-146">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="5955d-147">Parte 3: usare la classificazione basata su EDM con i servizi Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="5955d-147">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="5955d-148">- Abbonamento a Office 365 con DLP</span><span class="sxs-lookup"><span data-stu-id="5955d-148">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="5955d-149">- Funzionalità della classificazione basata su EDM abilitata</span><span class="sxs-lookup"><span data-stu-id="5955d-149">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="5955d-150">Parte 1: impostazione della classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-150">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="5955d-151">L’impostazione e la configurazione della classificazione basata su EDM implicano il salvataggio di dati sensibili in formato .csv, la definizione di uno schema per il database delle informazioni sensibili, la creazione di un pacchetto di regole e il caricamento del dello schema e del pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="5955d-151">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="5955d-152">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-152">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="5955d-153">Identificare le informazioni sensibili da usare.</span><span class="sxs-lookup"><span data-stu-id="5955d-153">Identify the KPIs that you want to use.</span></span> <span data-ttu-id="5955d-154">Esportare i dati in un'app, come Microsoft Excel e salvare il file in formato .csv.</span><span class="sxs-lookup"><span data-stu-id="5955d-154">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="5955d-155">Il file di dati può includere al massimo:</span><span class="sxs-lookup"><span data-stu-id="5955d-155">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="5955d-156">Fino a 10 milioni di righe di dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-156">Up to 10 million rows of sensitive data</span></span>
      - <span data-ttu-id="5955d-157">Fino a 32 colonne (campi) per origine dati</span><span class="sxs-lookup"><span data-stu-id="5955d-157">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="5955d-158">Fino a 5 colonne (campi) contrassegnate come ricercabile</span><span class="sxs-lookup"><span data-stu-id="5955d-158">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="5955d-159">Strutturare i dati sensibili nel file .csv in modo che la prima riga includa i nomi dei campi usati per la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-159">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="5955d-160">Nel file .csv potrebbero essere presenti nomi di campo, come "ssn", "birthdate", "firstname", "lastname" e così via.</span><span class="sxs-lookup"><span data-stu-id="5955d-160">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="5955d-161">Ad esempio, il file .csv è denominato  *PatientRecords.csv* e le relative colonne sono  *PatientID*,  *MRN*,  *LastName*,  *FirstName*,  *SSN*  e così via.</span><span class="sxs-lookup"><span data-stu-id="5955d-161">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="5955d-162">Definire lo schema per il database delle informazioni sensibili nel formato .xml (come riportato nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="5955d-162">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="5955d-163">Assegnare un nome al file dello schema edm.xml e configurarlo in modo che per ogni colonna del database sia presente una linea che usi la sintassi \<Field name="" searchable=""/\>.</span><span class="sxs-lookup"><span data-stu-id="5955d-163">Name this schema file edm.xml, and configure it such that for each column in the database, there is a line that uses the syntax \<Field name="" searchable=""/\>.</span></span>

      - <span data-ttu-id="5955d-164">Usare i nomi delle colonne per i valori  *Field name* .</span><span class="sxs-lookup"><span data-stu-id="5955d-164">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="5955d-165">Usare  *searchable="true"*  per un massimo di 5 campi che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="5955d-165">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="5955d-166">È necessario specificare almeno un campo come ricercabile.</span><span class="sxs-lookup"><span data-stu-id="5955d-166">You must designate a minimum of one field as searchable.</span></span>

<span data-ttu-id="5955d-167">Ad esempio, il seguente file .xml definisce lo schema per un database dei record dei pazienti, con cinque campi specificati come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="5955d-167">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

<span data-ttu-id="5955d-168">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="5955d-168">(You can copy, modify, and use our example.)</span></span>

 ```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records" version="1">
            <Field name="PatientID" searchable="true" />
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</EdmSchema>
```

4. <span data-ttu-id="5955d-169">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="5955d-169">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

5. <span data-ttu-id="5955d-170">Per caricare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="5955d-170">To upload the database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="5955d-171">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5955d-171">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="5955d-172">Conferma</span><span class="sxs-lookup"><span data-stu-id="5955d-172">Confirm</span></span>
>
> <span data-ttu-id="5955d-173">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="5955d-173">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="5955d-174">Viene importato il nuovo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="5955d-174">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
>
> <span data-ttu-id="5955d-175">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="5955d-175">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="5955d-176">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 5, usare questo cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="5955d-176">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="5955d-177">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-177">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="5955d-178">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-178">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="5955d-179">Ora che lo schema del database delle informazioni riservate è definito, il passaggio successivo consiste nel configurare un pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="5955d-179">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="5955d-180">Passare alla sezione  [Configurare un pacchetto di regole](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="5955d-180">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="5955d-181">Modificare lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-181">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="5955d-182">Se si vogliono apportare modifiche al file edm.xml, ad esempio modificare i campi usati per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="5955d-182">If you want to make changes to your edm.xml file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="5955d-183">Modificare il file edm.xml (il file descritto nella sezione  [Definisci lo schema](#define-the-schema-for-your-database-of-sensitive-information)  di questo articolo).</span><span class="sxs-lookup"><span data-stu-id="5955d-183">Edit your edm.xml file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="5955d-184">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="5955d-184">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

3. <span data-ttu-id="5955d-185">Per aggiornare lo schema di database, eseguire i cmdlet seguenti, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="5955d-185">To update your database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="5955d-186">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5955d-186">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="5955d-187">Conferma</span><span class="sxs-lookup"><span data-stu-id="5955d-187">Confirm</span></span>
>
> <span data-ttu-id="5955d-188">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="5955d-188">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="5955d-189">Viene aggiornato lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="5955d-189">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
>
> <span data-ttu-id="5955d-190">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="5955d-190">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="5955d-191">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 3, usare questo cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="5955d-191">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="5955d-192">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-192">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="5955d-193">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-193">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="5955d-194">Rimuovere lo schema per la classificazione basata su EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-194">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="5955d-195">(Se necessario) Se si vuole rimuovere lo schema usato per la classificazione basata su EDM, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="5955d-195">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="5955d-196">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="5955d-196">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)</span></span>

2. <span data-ttu-id="5955d-197">Eseguire i cmdlet di PowerShell seguenti, sostituendo il nome dell'archivio dati di "patientrecords" con quello che si vuole rimuovere:</span><span class="sxs-lookup"><span data-stu-id="5955d-197">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

```powershell
Remove-DlpEdmSchema -Identity patientrecords
```

<span data-ttu-id="5955d-198">Verrà richiesto di confermare, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5955d-198">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="5955d-199">Conferma</span><span class="sxs-lookup"><span data-stu-id="5955d-199">Confirm</span></span>
>
> <span data-ttu-id="5955d-200">Eseguire questa azione?</span><span class="sxs-lookup"><span data-stu-id="5955d-200">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="5955d-201">Viene rimosso lo schema EDM per l'archivio dati 'patientrecords'.</span><span class="sxs-lookup"><span data-stu-id="5955d-201">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
>
> <span data-ttu-id="5955d-202">\[Y\] Sì \[A\] Sì, tutti \[N\] No \[L\] No, tutti \[?\] Guida (l'impostazione predefinita è "Y"):</span><span class="sxs-lookup"><span data-stu-id="5955d-202">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
>  <span data-ttu-id="5955d-203">Se si vuole che le modifiche vengano eseguite senza conferma, al passaggio 2, usare questo cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="5955d-203">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="5955d-204">Configurare un pacchetto di regole</span><span class="sxs-lookup"><span data-stu-id="5955d-204">Set up a rule package</span></span>

1. <span data-ttu-id="5955d-205">Creare un pacchetto di regole nel formato .xml (con codifica Unicode), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5955d-205">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="5955d-206">(È possibile copiare, modificare e usare l'esempio.)</span><span class="sxs-lookup"><span data-stu-id="5955d-206">(You can copy, modify, and use our example.)</span></span>

<span data-ttu-id="5955d-207">Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file .csv e al file edm.xml.</span><span class="sxs-lookup"><span data-stu-id="5955d-207">When you set up your rule package, make sure to correctly reference your .csv file and edm.xml file.</span></span> <span data-ttu-id="5955d-208">È possibile copiare, modificare e usare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="5955d-208">You can copy, modify, and use our example.</span></span> <span data-ttu-id="5955d-209">In questo XML di esempio è necessario personalizzare i campi seguenti per creare un tipo di informazioni sensibili di EDM:</span><span class="sxs-lookup"><span data-stu-id="5955d-209">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

- <span data-ttu-id="5955d-210">
  \*\*RulePack id & ExactMatch id\*\*: usare  [New-GUID](https://docs.microsoft.com/it-IT/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6)  per generare un GUID.</span><span class="sxs-lookup"><span data-stu-id="5955d-210">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

- <span data-ttu-id="5955d-211">**Datastore**: questo campo specifica l'archivio dati di ricerca EDM da usare.</span><span class="sxs-lookup"><span data-stu-id="5955d-211">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="5955d-212">È possibile specificare il nome di un'origine dati di uno schema EDM configurato.</span><span class="sxs-lookup"><span data-stu-id="5955d-212">You provide a data source name of a configured EDM Schema.</span></span>

- <span data-ttu-id="5955d-213">**idMatch**: questo campo punta all'elemento primario per EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-213">**idMatch**: This field points to the primary element for EDM.</span></span>
  - <span data-ttu-id="5955d-214">Matches: specifica il campo da usare nella ricerca esatta.</span><span class="sxs-lookup"><span data-stu-id="5955d-214">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="5955d-215">È possibile specificare il nome campo ricercabile nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="5955d-215">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
  - <span data-ttu-id="5955d-216">Classificazione: questo campo specifica la corrispondenza del tipo di informazioni sensibili che attiva la ricerca EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-216">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="5955d-217">È possibile specificare il nome o il GUID di una classificazione predefinita o personalizzata esistente.</span><span class="sxs-lookup"><span data-stu-id="5955d-217">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

- <span data-ttu-id="5955d-218">**Match:** questo campo indica altre evidenze disponibili in prossimità di idMatch.</span><span class="sxs-lookup"><span data-stu-id="5955d-218">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
  - <span data-ttu-id="5955d-219">Matches: è possibile specificare qualsiasi nome campo nello schema EDM per DataStore.</span><span class="sxs-lookup"><span data-stu-id="5955d-219">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
- <span data-ttu-id="5955d-220">**Resource:** questa sezione specifica il nome e la descrizione per il tipo di informazioni sensibili in più impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="5955d-220">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
  - <span data-ttu-id="5955d-221">idRef: è possibile specificare il GUID per l'ID ExactMatch.</span><span class="sxs-lookup"><span data-stu-id="5955d-221">idRef: You provide GUID for ExactMatch id.</span></span>
  - <span data-ttu-id="5955d-222">Name & des Editing the schema criptions: personalizzare come necessario.</span><span class="sxs-lookup"><span data-stu-id="5955d-222">Name & des Editing the schema criptions: customize as required.</span></span>

```xml
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

1. <span data-ttu-id="5955d-223">Per caricare il pacchetto di regole, eseguire i seguenti cmdlet di PowerShell, uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="5955d-223">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

```powershell
$rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
```

<span data-ttu-id="5955d-224">A questo punto è stata configurata la classificazione basata su EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-224">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="5955d-225">Il passaggio successivo consiste nell'indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="5955d-225">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="5955d-226">Usare la procedura precedente in cui lo schema di PatientRecords definisce cinque campi come ricercabili:  *PatientID*,  *MRN*,  *SSN*,  *Phone* e  *DOB*.</span><span class="sxs-lookup"><span data-stu-id="5955d-226">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="5955d-227">Il pacchetto di regole di esempio include questi campi e fa riferimento al file schema di database (edm.xml), con un unico elemento  *ExactMatch*  per ogni campo ricercabile.</span><span class="sxs-lookup"><span data-stu-id="5955d-227">Our example rule package includes those fields and references the database schema file (edm.xml), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="5955d-228">Considerare l'elemento ExactMatch seguente:</span><span class="sxs-lookup"><span data-stu-id="5955d-228">Consider the following ExactMatch item:</span></span>

```xml
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
```

<span data-ttu-id="5955d-229">Utilizzando l'esempio proposto, osservare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5955d-229">In this example, note the following:</span></span>

- <span data-ttu-id="5955d-230">Il nome dataStore fa riferimento al file .csv creato in precedenza:  **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="5955d-230">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="5955d-231">Il valore idMatch fa riferimento a un campo ricercabile elencato nel file dello schema del database:  **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="5955d-231">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="5955d-232">Il valore di classificazione fa riferimento a un tipo di informazioni sensibili esistente o personalizzato:  **classification = "U.S. Social Security Number (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="5955d-232">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="5955d-233">In questo caso, viene usato il tipo di informazioni sensibili esistente del Numero di previdenza sociale degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="5955d-233">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="5955d-234">L'aggiornamento dello schema EDM impiega tra i 10 e i 60 minuti con aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-234">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="5955d-235">Completare l'aggiornamento prima di eseguire i passaggi che usano le aggiunte.</span><span class="sxs-lookup"><span data-stu-id="5955d-235">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="5955d-236">Parte 2: indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-236">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="5955d-237">In questa fase è possibile impostare un gruppo di sicurezza personalizzato e un account utente e configurare lo strumento Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-237">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="5955d-238">Successivamente, è possibile usare lo strumento per indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="5955d-238">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="5955d-239">Impostare il gruppo di sicurezza e l'account utente</span><span class="sxs-lookup"><span data-stu-id="5955d-239">Set up the security group and user account</span></span>

1. <span data-ttu-id="5955d-240">Come amministratore globale, passare all'interfaccia di amministrazione ([https://admin.microsoft.com](https://admin.microsoft.com/)) e  [creare un gruppo di sicurezza](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)  denominato EDM\_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="5955d-240">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com/)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called EDM\_DataUploaders.</span></span>

2. <span data-ttu-id="5955d-241">Aggiungere uno o più utenti al gruppo di sicurezza  *EDM\_DataUploaders* .</span><span class="sxs-lookup"><span data-stu-id="5955d-241">Add one or more users to the *EDM\_DataUploaders* security group.</span></span> <span data-ttu-id="5955d-242">(Questi utenti gestiranno il database delle informazioni sensibili.)</span><span class="sxs-lookup"><span data-stu-id="5955d-242">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="5955d-243">Assicurarsi che ogni utente che gestisce i dati sensibili sia un amministratore locale nel computer usato per l'Agente di caricamento di EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-243">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="5955d-244">Impostare l'Agente di caricamento di EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-244">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="5955d-245">Prima di iniziare questa procedura, verificare di essere un membro del gruppo di sicurezza  *EDM\_DataUploaders*  e un amministratore locale nel computer.</span><span class="sxs-lookup"><span data-stu-id="5955d-245">Before you begin this procedure, make sure that you are a member of the *EDM\_DataUploaders* security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="5955d-246">Scaricare e installare l'[Agente di caricamento di EDM](https://go.microsoft.com/fwlink/?linkid=2088639).</span><span class="sxs-lookup"><span data-stu-id="5955d-246">Download and install the [EDM Upload Agent](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="5955d-247">Per impostazione predefinita, il percorso di installazione deve essere C:\\Programmi\\Microsoft\\EdmUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="5955d-247">By default, the installation location should be C:\\Program Files\\Microsoft\\EdmUploadAgent.</span></span>

2. <span data-ttu-id="5955d-248">Per autorizzare l'Agente di caricamento di EDM, aprire il prompt dei comandi di Windows (come amministratore) e quindi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5955d-248">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="5955d-249">Accedere con l'account aziendale o dell'istituto di istruzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5955d-249">Sign in with your Office 365 work or school account.</span></span>

<span data-ttu-id="5955d-250">Il passaggio successivo consiste nell'usare l’Agente di caricamento di EDM per indicizzare i dati sensibili e poi di caricarli.</span><span class="sxs-lookup"><span data-stu-id="5955d-250">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="5955d-251">Indicizzare e caricare i dati sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-251">Index and upload the sensitive data</span></span>

<span data-ttu-id="5955d-252">Salvare il file di dati sensibili (richiamare l'esempio  *PatientRecords.csv*) nell'unità locale del computer.</span><span class="sxs-lookup"><span data-stu-id="5955d-252">Save the sensitive data file (recall our example is *PatientRecords.csv*) to the local drive on the machine.</span></span> <span data-ttu-id="5955d-253">(Il file di esempio  *PatientRecords.csv*  è stato salvato in  C:\\Edm\\Data.)</span><span class="sxs-lookup"><span data-stu-id="5955d-253">(We saved our example *PatientRecords.csv* file to C:\\Edm\\Data.)</span></span>

<span data-ttu-id="5955d-254">Per indicizzare e caricare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="5955d-254">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="5955d-255">Esempio: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="5955d-255">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="5955d-256">Per separare e indicizzare i dati sensibili in un ambiente isolato, eseguire le operazioni di indicizzazione e caricamento separatamente.</span><span class="sxs-lookup"><span data-stu-id="5955d-256">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="5955d-257">Per indicizzare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="5955d-257">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="5955d-258">Esempio: **EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="5955d-258">Example: **EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="5955d-259">Per caricare i dati sensibili, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="5955d-259">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="5955d-260">Esempio: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="5955d-260">Example: **EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="5955d-261">Per verificare che i dati sensibili siano stati caricati, eseguire il seguente comando nel prompt dei comandi di Windows:</span><span class="sxs-lookup"><span data-stu-id="5955d-261">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="5955d-262">Viene visualizzato un elenco degli archivi dati e la data dell'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5955d-262">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="5955d-263">Procedere alla configurazione della procedura e della programmazione per  [Aggiornare il database delle informazioni sensibili](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="5955d-263">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="5955d-264">A questo punto si è pronti a usare la classificazione basata su EDM con i servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5955d-264">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="5955d-265">Ad esempio, è possibile  [impostare un criterio DLP con la classificazione basata su EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="5955d-265">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="5955d-266">Aggiornare il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="5955d-266">Refreshing your sensitive information database</span></span>

<span data-ttu-id="5955d-267">È possibile aggiornare il database delle informazioni sensibili giornalmente o settimanalmente e lo strumento di caricamento di EDM può reindicizzare i dati sensibili e quindi ricaricarli.</span><span class="sxs-lookup"><span data-stu-id="5955d-267">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="5955d-268">Determinare la procedura e la frequenza (giornaliera o settimanale) dell’aggiornamento del database delle informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="5955d-268">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="5955d-269">Esportare di nuovo i dati sensibili in un'app, come Microsoft Excel e salvare il file in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="5955d-269">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="5955d-270">Mantenere il nome e il percorso del file usati dopo aver seguito la procedura descritta in  [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="5955d-270">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

> [!NOTE]
> <span data-ttu-id="5955d-271">Se non sono state apportate modifiche alla struttura (nomi dei campi) del file CSV, non è necessario apportare modifiche al file dello schema del database quando si aggiornano i dati.</span><span class="sxs-lookup"><span data-stu-id="5955d-271">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="5955d-272">Tuttavia, se è necessario apportare modifiche, accertarsi di modificare di conseguenza lo schema del database e il pacchetto delle regole.</span><span class="sxs-lookup"><span data-stu-id="5955d-272">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="5955d-273">Usare l' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page)  per automatizzare i passaggi 2 e 3 nella procedura  [Indicizzare e caricare i dati sensibili](#index-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="5955d-273">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="5955d-274">È possibile pianificare le attività in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="5955d-274">You can schedule tasks using several methods:</span></span>

| <span data-ttu-id="5955d-275">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="5955d-275">**Method**</span></span>             | <span data-ttu-id="5955d-276">**Procedura**</span><span class="sxs-lookup"><span data-stu-id="5955d-276">**What to do if rule processing fails**.</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5955d-277">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5955d-277">Windows PowerShell</span></span>     | <span data-ttu-id="5955d-278">Consultare la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps)  e lo  [script di PowerShell di esempio](#example-powershell-script-for-task-scheduler)  illustrato in questo articolo</span><span class="sxs-lookup"><span data-stu-id="5955d-278">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
| <span data-ttu-id="5955d-279">API dell'Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="5955d-279">Task Scheduler API</span></span>     | <span data-ttu-id="5955d-280">Vedere la documentazione dell' [Utilità di pianificazione](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="5955d-280">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
| <span data-ttu-id="5955d-281">Interfaccia utente Windows</span><span class="sxs-lookup"><span data-stu-id="5955d-281">Windows user interface</span></span> | <span data-ttu-id="5955d-282">In Windows, fare clic su  **Start** e digitare Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5955d-282">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="5955d-283">Quindi, nell'elenco dei risultati, fare clic con il pulsante destro del mouse sull' **Utilità di pianificazione** e scegliere  **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="5955d-283">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="5955d-284">Esempio di script di PowerShell per Utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="5955d-284">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="5955d-285">Questa sezione include uno script di PowerShell di esempio che è possibile usare per pianificare le attività di indicizzazione dei dati e il caricamento dei dati indicizzati:</span><span class="sxs-lookup"><span data-stu-id="5955d-285">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="5955d-286">Per pianificare l'indicizzazione e il caricamento in un passaggio combinato</span><span class="sxs-lookup"><span data-stu-id="5955d-286">To schedule index and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ‘ /HashLocation’ + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="5955d-287">Per pianificare l'indicizzazione e il caricamento in passaggi separati</span><span class="sxs-lookup"><span data-stu-id="5955d-287">To schedule index and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="5955d-288">Parte 3: usare la classificazione basata su EDM con i servizi cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="5955d-288">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="5955d-289">Office 365 DLP per Exchange Online (posta elettronica), OneDrive for Business (file), Microsoft Teams (conversazioni) e i criteri DLP di Microsoft Cloud App Security supportano i tipi di informazioni sensibili EDM.</span><span class="sxs-lookup"><span data-stu-id="5955d-289">Office 365 DLP for Exchange Online (email), OneDrive for Business (files), Microsoft Teams (conversations) and Microsoft Cloud App Security DLP policies will support EDM sensitive information types.</span></span>

<span data-ttu-id="5955d-290">I tipi di informazioni sensibili EDM per gli scenari seguenti sono in fase di sviluppo e non sono ancora disponibili:</span><span class="sxs-lookup"><span data-stu-id="5955d-290">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="5955d-291">Office 365 DLP per SharePoint (file)</span><span class="sxs-lookup"><span data-stu-id="5955d-291">Office 365 DLP for SharePoint (files)</span></span>
- <span data-ttu-id="5955d-292">Classificazione automatica di etichette di riservatezza ed etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="5955d-292">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="5955d-293">Creazione di un criterio DLP con EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-293">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="5955d-294">Passare al Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com/)).</span><span class="sxs-lookup"><span data-stu-id="5955d-294">Go to the Security & Compliance Center</span></span>

2. <span data-ttu-id="5955d-295">Scegliere  **Prevenzione della perdita dei dati** \> **Criteri**.</span><span class="sxs-lookup"><span data-stu-id="5955d-295">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="5955d-296">Scegliere  **Crea un criterio** \> **Personalizzato** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-296">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="5955d-297">Nella scheda  **Nome criterio** , specificare un nome e una descrizione, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-297">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="5955d-298">Nella scheda  **Scegli posizioni** , selezionare  **Consenti di scegliere posizioni specifiche**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-298">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="5955d-299">Nella colonna  **Stato** , selezionare  **Posta elettronica di Exchange, Account di OneDrive, Chat di Teams e Messaggio del canale** , quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-299">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span> <span data-ttu-id="5955d-300">Nota: EDM al momento non è supportato nei siti di SharePoint e i criteri DLP non vengono rilevati in SharePoint per EDM</span><span class="sxs-lookup"><span data-stu-id="5955d-300">(Note: EDM is currently not supported in SharePoint sites and DLP policy will not detect files in Sharepoint for EDM)</span></span>

7. <span data-ttu-id="5955d-301">Nella scheda  **Impostazioni criterio** , scegliere  **Usa impostazioni avanzate**, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-301">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="5955d-302">Scegliere  **+ Nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="5955d-302">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="5955d-303">Nella sezione  **Nome** , specificare un nome e una descrizione per la regola.</span><span class="sxs-lookup"><span data-stu-id="5955d-303">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="5955d-304">Nella sezione  **Condizioni** , nell'elenco  **+ Aggiungi una condizione** , scegliere  **Il contenuto include il tipo di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="5955d-304">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="5955d-305">![Il contenuto include il tipo di informazioni sensibili](media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="5955d-305">![Content contains sensitive info types](media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="5955d-306">Cercare il tipo di informazioni sensibili creato quando si configura il pacchetto delle regole, quindi scegliere  **+ Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="5955d-306">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="5955d-307">Quindi scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="5955d-307">Then choose **Done**.</span></span>

12. <span data-ttu-id="5955d-308">Infine selezionare le opzioni per la regola, come  **Notifiche utente**,  **Personalizzazioni utente**,  **Report degli eventi** e così via, quindi scegliere  **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5955d-308">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="5955d-309">Nella scheda  **Impostazioni criterio** , esaminare le regole, quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-309">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="5955d-310">Specificare se attivare subito il criterio, testarlo o mantenerlo disattivato.</span><span class="sxs-lookup"><span data-stu-id="5955d-310">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="5955d-311">Quindi scegliere  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5955d-311">Then choose **Next**.</span></span>

15. <span data-ttu-id="5955d-312">Nella scheda  **Esamina le impostazioni** , esaminare il criterio.</span><span class="sxs-lookup"><span data-stu-id="5955d-312">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="5955d-313">Apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="5955d-313">Make any needed changes.</span></span> <span data-ttu-id="5955d-314">Al termine, scegliere  **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5955d-314">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="5955d-315">Il nuovo criterio DLP sarà attivo nel centro dati dopo circa un'ora.</span><span class="sxs-lookup"><span data-stu-id="5955d-315">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5955d-316">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="5955d-316">Related articles</span></span>

<span data-ttu-id="5955d-317">
  [Tipi di informazioni sensibili integrati e cosa individuano](https://docs.microsoft.com/it-IT/office365/securitycompliance/what-the-sensitive-information-types-look-for)</span><span class="sxs-lookup"><span data-stu-id="5955d-317">[Built-in sensitive information types and what they look for](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for)</span></span>

<span data-ttu-id="5955d-318">
  [Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/it-IT/office365/securitycompliance/custom-sensitive-info-types)</span><span class="sxs-lookup"><span data-stu-id="5955d-318">[Custom sensitive information types](https://docs.microsoft.com/en-us/office365/securitycompliance/custom-sensitive-info-types)</span></span>

<span data-ttu-id="5955d-319">
  [Panoramica sui criteri di DLP](https://docs.microsoft.com/it-IT/office365/securitycompliance/data-loss-prevention-policies)</span><span class="sxs-lookup"><span data-stu-id="5955d-319">[Overview of DLP policies](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies)</span></span>

[<span data-ttu-id="5955d-320">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5955d-320">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

<span data-ttu-id="5955d-321">
  [New-DlpEdmSchema](https://docs.microsoft.com/it-IT/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="5955d-321">[New-DlpEdmSchema](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)</span></span>

## <a name="feedback"></a><span data-ttu-id="5955d-322">Feedback</span><span class="sxs-lookup"><span data-stu-id="5955d-322">Feedback</span></span>
<span data-ttu-id="5955d-323">I feedback su GitHub sono abilitati, ma è possibile aggiungere domande solo nel sito pubblico.</span><span class="sxs-lookup"><span data-stu-id="5955d-323">GitHub feedback is enabled, but adding issues is only available on the public site.</span></span>
