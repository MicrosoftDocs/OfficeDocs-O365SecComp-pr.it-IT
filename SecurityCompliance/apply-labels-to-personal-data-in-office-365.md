---
title: Applicare le etichette ai dati personali in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come utilizzare le etichette di Office per il piano di protezione RGPD.
ms.openlocfilehash: e31cd420fe476ace8031fc2c6e52158762814c7a
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789431"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="75644-103">Applicare le etichette ai dati personali in Office 365</span><span class="sxs-lookup"><span data-stu-id="75644-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="75644-104">Consultare questo argomento se si usano etichette di classificazione per il piano di protezione GDPR.</span><span class="sxs-lookup"><span data-stu-id="75644-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="75644-105">Se si usano etichette per la protezione dei dati personali in Office 365, Microsoft consiglia di iniziare con le [etichette di conservazione](labels.md).</span><span class="sxs-lookup"><span data-stu-id="75644-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="75644-106">Con le etichette di conservazione è possibile:</span><span class="sxs-lookup"><span data-stu-id="75644-106">With retention labels, you can:</span></span>
- <span data-ttu-id="75644-107">Usare Advanced Data Governance per applicare automaticamente le etichette in base ai tipi di informazioni sensibili o ad altri criteri.</span><span class="sxs-lookup"><span data-stu-id="75644-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
-  <span data-ttu-id="75644-108">Usare le etichette di conservazione con la prevenzione della perdita dei dati per applicare la protezione.</span><span class="sxs-lookup"><span data-stu-id="75644-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="75644-109">Usare le etichette con eDiscovery e Ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="75644-109">Use labels with eDiscovery and Content Search.</span></span> 
- <span data-ttu-id="75644-110">Usare etichette e tipi di informazioni sensibili con Cloud App Security per monitorare i dati personali che si trovano in altre app SaaS.</span><span class="sxs-lookup"><span data-stu-id="75644-110">Use both labels and sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="75644-111">Le [etichette di riservatezza](sensitivity-labels.md) sono attualmente consigliate per l'applicazione di etichette a file locali e in altri provider e servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="75644-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="75644-112">Sono consigliate anche per file in Office 365 che richiedono la crittografia di Azure Information Protection per la protezione dei dati, ad esempio file contenenti segreti commerciali.</span><span class="sxs-lookup"><span data-stu-id="75644-112">These are also recommended for files in Office 365 that require Azure Information Protection (AIP) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="75644-113">Al momento, l'uso di Azure Information Protection per applicare la crittografia non è consigliabile per i file in Office 365 contenenti dati soggetti al GDPR.</span><span class="sxs-lookup"><span data-stu-id="75644-113">At this time, using Azure Information Protection to apply Azure RMS encryption is not recommended for files in Office 365 with data that is subject to the GDPR. Office 365 services currently cannot read into RMS-encrypted files. Therefore, the service can’t find sensitive data in these files.</span></span> <span data-ttu-id="75644-114">I servizi di Office 365 attualmente non possono leggere nei file con crittografia AIP.</span><span class="sxs-lookup"><span data-stu-id="75644-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="75644-115">Di conseguenza, il servizio non trova i dati sensibili in questi file.</span><span class="sxs-lookup"><span data-stu-id="75644-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="75644-116">Le etichette di riservatezza possono essere applicate ai messaggi di posta elettronica in Exchange Online e queste etichette funzionano con la prevenzione della perdita dei dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="75644-116">Sensitivity labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Le etichette di Office 365 e di Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="75644-118">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="75644-118">In the illustration:</span></span>

-   <span data-ttu-id="75644-119">Usare le etichette di conservazione per i dati personali per i file con segreti commerciali e soggetti a normative in SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="75644-119">Use Office 365 labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="75644-120">Usare le etichette di riservatezza per i file con segreti commerciali e soggetti a normative, la posta elettronica di Exchange Online, file in altri servizi SaaS, file in datacenter locali e file in altri provider cloud.</span><span class="sxs-lookup"><span data-stu-id="75644-120">Use Azure Information Protection (AIP) labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="75644-121">Usare le etichette di conservazione e i tipi di informazioni sensibili in Microsoft 365 per la protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="75644-121">Use Office labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="75644-122">La figura seguente mostra come usare le etichette di conservazione e i tipi di informazioni sensibili in criteri di etichetta, criteri di prevenzione della perdita dei dati e i criteri di Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="75644-122">The following illustration shows how Office labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etichette di Office e tipi di informazioni riservate](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="75644-124">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="75644-124">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75644-125"><strong>Elementi di classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="75644-125"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="75644-126"><strong>Criteri delle etichette - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="75644-126"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="75644-127"><strong>Criteri di prevenzione della perdita dei dati - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="75644-127"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="75644-128"><strong>I criteri di Cloud App Security per tutte le app SaaS - 1 esempio</strong></span><span class="sxs-lookup"><span data-stu-id="75644-128"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="75644-129">Etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="75644-129">Retention labels</span></span> <span data-ttu-id="75644-130">Esempi: Personale, Pubblico, Dati cliente, Dati risorse umane, Riservato, Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="75644-130">Office labels. Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="75644-p105">Applicare automaticamente questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="75644-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="75644-134">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="75644-134">Customer data</span></span></p>
<p><span data-ttu-id="75644-p106">... ai documenti che corrispondono a questi tipi di informazioni riservate...</span><span class="sxs-lookup"><span data-stu-id="75644-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="75644-141">&lt;elenco dei tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-141">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="75644-p107">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="75644-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="75644-145">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-145">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="75644-p108">... ai documenti con questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="75644-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="75644-152">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="75644-152">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="75644-p109">Avvisa quando i file con questi attributi...</span><span class="sxs-lookup"><span data-stu-id="75644-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="75644-156">&lt;Attributo PII predefinito oppure espressione personalizzata&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-156">&lt;predefined PII attribute -or- custom expression&gt;</span></span></p>
<p><span data-ttu-id="75644-p110">... in qualsiasi app SaaS approvata vengono condivisi all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="75644-p110">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="75644-p111">Tipi di informazioni riservate. Esempi: Codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese</span><span class="sxs-lookup"><span data-stu-id="75644-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="75644-p112">Pubblicare le etichette per gli utenti da applicare manualmente...</span><span class="sxs-lookup"><span data-stu-id="75644-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="75644-166">&lt;selezionare etichette&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-166">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="75644-p113">... a questi percorsi...</span><span class="sxs-lookup"><span data-stu-id="75644-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="75644-173">&lt;tutte i percorsi oppure percorsi specifici&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-173">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="75644-p114">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="75644-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="75644-177">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-177">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="75644-p115">... ai documenti che corrispondono a questi tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="75644-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"><span data-ttu-id="75644-182">Nota: gli attributi di Cloud App Security presto includeranno i tipi di informazioni riservate di Office 365 e le etichette unificate in Office 365 e Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="75644-182">Note: Attributes coming soon to Cloud App Security include Office 365 sensitive information types and Unified labels across Office 365 and Azure Information Protection.</span></span></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="75644-183">Definire la priorità dei criteri per applicare automaticamente le etichette
</span><span class="sxs-lookup"><span data-stu-id="75644-183">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="75644-p116">Per i dati personali soggetti all'RGPD, Microsoft consiglia di applicare automaticamente le etichette utilizzando le tipologie di informazioni sensibili create per il proprio ambiente. I criteri che applicano automaticamente le etichette devono essere configurati correttamente e occorre testarli per verificare che producano i risultati previsti.
</span><span class="sxs-lookup"><span data-stu-id="75644-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="75644-p117">L'ordine con cui vengono creati i criteri da applicare automaticamente e il fatto che gli utenti applichino o meno queste etichette influisce sul risultato. È quindi importante pianificare attentamente l'implementazione. Ecco cosa serve sapere.</span><span class="sxs-lookup"><span data-stu-id="75644-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="75644-188">Un'etichetta alla volta</span><span class="sxs-lookup"><span data-stu-id="75644-188">One label at a time</span></span>

<span data-ttu-id="75644-189">È possibile assegnare solo un'etichetta a un documento.</span><span class="sxs-lookup"><span data-stu-id="75644-189">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="75644-190">I criteri più vecchi hanno la precedenza
</span><span class="sxs-lookup"><span data-stu-id="75644-190">Older auto-apply policies win</span></span>

<span data-ttu-id="75644-p118">Se sono presenti più regole che assegnano un'etichetta da applicare automaticamente e il contenuto soddisfa le condizioni di più regole, viene assegnata l'etichetta della regola meno recente. Per questo motivo, è importante pianificare con attenzione i criteri delle etichette prima di configurarli. Se un'organizzazione ha l'esigenza di modificare la priorità dei criteri delle etichette, è necessario eliminarli e crearli di nuovo.
</span><span class="sxs-lookup"><span data-stu-id="75644-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="75644-194">Le etichette applicate manualmente dall'utente hanno la precedenza su quelle applicate automaticamente
</span><span class="sxs-lookup"><span data-stu-id="75644-194">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="75644-p119">Le etichette applicate manualmente dall'utente battono quelle applicate automaticamente. I criteri di applicazione automatica non possono sostituire un'etichetta già applicata da un utente. Gli utenti possono sostituire le etichette applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75644-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="75644-198">Le etichette assegnate automaticamente possono essere aggiornate</span><span class="sxs-lookup"><span data-stu-id="75644-198">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="75644-199">Le etichette assegnate automaticamente possono essere aggiornate creando nuovi criteri o aggiornando quelli esistenti.
</span><span class="sxs-lookup"><span data-stu-id="75644-199">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="75644-200">Assicurarsi che il piano di implementazione delle etichette includa:</span><span class="sxs-lookup"><span data-stu-id="75644-200">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="75644-201">Creare i criteri di applicazione automatica secondo l'ordine di priorità.
</span><span class="sxs-lookup"><span data-stu-id="75644-201">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="75644-p120">Allocare il tempo necessario all'applicazione automatica delle etichette prima di consentire agli utenti di applicarle manualmente. Potrebbe essere necessaria anche una settimana per applicare le etichette a tutti i contenuti che corrispondono alle condizioni.
</span><span class="sxs-lookup"><span data-stu-id="75644-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="75644-204">Esempio di priorità per creare i criteri di applicazione automatica
</span><span class="sxs-lookup"><span data-stu-id="75644-204">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75644-205"><strong>Etichette</strong></span><span class="sxs-lookup"><span data-stu-id="75644-205"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="75644-206"><strong>Ordine di priorità per creare criteri da applicare automaticamente</strong></span><span class="sxs-lookup"><span data-stu-id="75644-206"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="75644-207">Risorse umane - Dati dipendenti</span><span class="sxs-lookup"><span data-stu-id="75644-207">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="75644-208">1</span><span class="sxs-lookup"><span data-stu-id="75644-208">1.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="75644-209">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="75644-209">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="75644-210">2</span><span class="sxs-lookup"><span data-stu-id="75644-210">2.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="75644-211">Estremamente riservato
</span><span class="sxs-lookup"><span data-stu-id="75644-211">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="75644-212">3</span><span class="sxs-lookup"><span data-stu-id="75644-212">3.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="75644-213">Risorse umane - Dati sugli stipendi</span><span class="sxs-lookup"><span data-stu-id="75644-213">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="75644-214">4</span><span class="sxs-lookup"><span data-stu-id="75644-214">4.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="75644-215">Riservato</span><span class="sxs-lookup"><span data-stu-id="75644-215">Confidential</span></span></td>
<td align="left"><span data-ttu-id="75644-216">5</span><span class="sxs-lookup"><span data-stu-id="75644-216">5.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="75644-217">Pubblico</span><span class="sxs-lookup"><span data-stu-id="75644-217">Public</span></span></td>
<td align="left"><span data-ttu-id="75644-218">6</span><span class="sxs-lookup"><span data-stu-id="75644-218">6.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="75644-219">Personale</span><span class="sxs-lookup"><span data-stu-id="75644-219">Personal</span></span></td>
<td align="left"><span data-ttu-id="75644-220">Nessun criterio di applicazione automatica</span><span class="sxs-lookup"><span data-stu-id="75644-220">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="75644-221">Creare le etichette e i criteri per applicare le etichette automaticamente
</span><span class="sxs-lookup"><span data-stu-id="75644-221">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="75644-222">Creare le etichette e i criteri nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="75644-222">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75644-223"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="75644-223"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="75644-224"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75644-224"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75644-225">Assegnare autorizzazioni ai membri del team di conformità.</span><span class="sxs-lookup"><span data-stu-id="75644-225">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="75644-p121">I membri del team di conformità che creeranno le etichette necessitano di autorizzazioni per utilizzare il Centro sicurezza e conformità. Andare a Autorizzazioni nel Centro sicurezza e conformità e modificare i membri del gruppo Amministratori di conformità.</span><span class="sxs-lookup"><span data-stu-id="75644-p121">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="75644-228">Vedere <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="75644-228">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75644-229">Creare etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="75644-229">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="75644-230">Passare a Classificazioni in Centro sicurezza e conformità, scegliere Etichette di conservazione e creare le etichette per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="75644-230">Go to Classifications in Security and Compliance Center, choose Labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75644-231">Creare criteri di applicazione automatica per le etichette.</span><span class="sxs-lookup"><span data-stu-id="75644-231">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="75644-p122">Andare a Classificazione nel Centro sicurezza e conformità, scegliere Criteri etichette e creare i criteri di applicazione automatica delle etichette. Assicurarsi di creare questi criteri nell'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="75644-p122">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="75644-234">La figura seguente mostra come creare un'etichetta Dati cliente da applicare automaticamente.
</span><span class="sxs-lookup"><span data-stu-id="75644-234">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Creare e applicare un'etichetta per i dati del cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="75644-236">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="75644-236">In the illustration:</span></span>

-   <span data-ttu-id="75644-237">Viene creata l'etichetta "Dati del cliente".</span><span class="sxs-lookup"><span data-stu-id="75644-237">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="75644-238">I tipi di informazioni riservate desiderate per l'RGPD sono: codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese.</span><span class="sxs-lookup"><span data-stu-id="75644-238">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="75644-239">La creazione di un criterio di applicazione automatica assegna l'etichetta "Dati del cliente" a qualsiasi file che include uno dei tipi di informazioni riservate aggiunto al criterio.</span><span class="sxs-lookup"><span data-stu-id="75644-239">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
