---
title: Applicare le etichette ai dati personali in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come utilizzare le etichette di Office per il piano di protezione RGPD.
ms.openlocfilehash: d92d132190296e2243bf7ea00c3c0dba4e38930f
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223155"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="54b34-103">Applicare le etichette ai dati personali in Office 365</span><span class="sxs-lookup"><span data-stu-id="54b34-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="54b34-p101">Utilizzare questo argomento se si utilizzano le etichette per il piano di protezione RGPD. Oggi è possibile creare le etichette nel Centro sicurezza e conformità di Office 365 e in Azure Information Protection. Nel corso del tempo queste tecnologie convergeranno in un'esperienza di classificazione e creazione delle etichette unificata e sarà possibile aggiungerne anche altre.</span><span class="sxs-lookup"><span data-stu-id="54b34-p101">Use this topic if you are using Office labels as part of your GDPR protection plan. Today labels can be created in the Office 365 Security & Compliance Center and in Azure Information Protection. Over time these technologies will converge into a unified labeling and classification experience and you will be able to achieve even more.</span></span>

<span data-ttu-id="54b34-p102">Se si utilizzano le etichette per la protezione dei dati personali in Office 365, Microsoft suggerisce di iniziare con le etichette di Office. È possibile utilizzare Advanced Data Governance per applicare automaticamente le etichette in base ai tipi di informazioni riservate o altri criteri. È possibile utilizzare le etichette di Office con la prevenzione della perdita di dati per applicare la protezione. È inoltre possibile usarle con eDiscovery e Ricerca contenuto. Presto sarà possibile usare le etichette e i tipi di informazioni riservate con Cloud App Security per monitorare i dati personali che si trovano in altre applicazioni SaaS.</span><span class="sxs-lookup"><span data-stu-id="54b34-p102">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with Office labels. You can use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria. You can use Office labels with data loss prevention to apply protection. You can also use labels with eDiscovery and Content Search. You’ll soon be able to use both labels and sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="54b34-p103">Le etichette di Azure Information Protection al momento sono consigliate per l'applicazione di etichette ai file in locale e in altri servizi e provider cloud. Sono consigliate anche per i file in Office 365 che richiedono la crittografia di Azure Rights Management (Azure RMS) per la protezione dei dati, come file contenenti segreti commerciali.</span><span class="sxs-lookup"><span data-stu-id="54b34-p103">Azure Information Protection labels are currently recommended for applying labels to files on premises and in other cloud services and providers. These are also recommended for files in Office 365 that require Azure Rights Management (Azure RMS) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="54b34-p104">Al momento, l'uso di Azure Information Protection per applicare la crittografia di Azure RMS non è consigliabile per i file in Office 365 contenti dati soggetti all'RGPD. I servizi di Office 365 attualmente non possono leggere i file crittografati con RMS. Di conseguenza, il servizio non può trovare i dati sensibili in questi file.</span><span class="sxs-lookup"><span data-stu-id="54b34-p104">At this time, using Azure Information Protection to apply Azure RMS encryption is not recommended for files in Office 365 with data that is subject to the GDPR. Office 365 services currently cannot read into RMS-encrypted files. Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="54b34-p105">Le etichette di Azure Information Protection possono essere applicate alla posta in Exchange Online e funzionano con la prevenzione della perdita di dati di Office 365. Prossimamente, con il motore unificato per la classificazione e la creazione delle etichette, sarà possibile usare le stesse etichette per i messaggi di posta elettronica e i file; sarà anche possibile creare le etichette e proteggere i messaggi di posta elettronica in transito.
</span><span class="sxs-lookup"><span data-stu-id="54b34-p105">Azure Information Protection labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention. Coming soon with the unified classification and labeling engine you will be able to use the same labels for email and files, including automatically labeling and protecting email in transit.</span></span>

![Le etichette di Office 365 e di Azure Information Protection](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="54b34-120">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="54b34-120">In the illustration:</span></span>

-   <span data-ttu-id="54b34-121">Uso delle etichette di Office 365 per i dati personali per i file con segreti commerciali e soggetti a normative in SharePoint Online e OneDrive for Business.
</span><span class="sxs-lookup"><span data-stu-id="54b34-121">Use Office 365 labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="54b34-122">Uso delle etichette di Azure Information Protection (AIP) per i file con segreti commerciali e soggetti a normative, la posta elettronica di Exchange Online, file in altri servizi SaaS, file in datacenter in locale e file in altri provider cloud.
</span><span class="sxs-lookup"><span data-stu-id="54b34-122">Use Azure Information Protection (AIP) labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>

-   <span data-ttu-id="54b34-123">Prossimamente questi due tipi di etichette verranno consolidati per offrire un'unica esperienza di classificazione e creazione di etichette.
</span><span class="sxs-lookup"><span data-stu-id="54b34-123">Coming soon: both types of labels will converge into a unified classification and labeling experience.</span></span>

## <a name="use-office-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="54b34-124">Usare le etichette di Office e i tipi di informazioni riservate in Microsoft 365 per la protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="54b34-124">Use Office labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="54b34-125">La figura seguente mostra come le etichette e le tipologie di informazioni sensibili di Office possono essere utilizzati nei criteri delle etichette, nei criteri di prevenzione della perdita di dati e con i criteri di Cloud App Security.
</span><span class="sxs-lookup"><span data-stu-id="54b34-125">The following illustration shows how Office labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etichette di Office e tipi di informazioni riservate](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="54b34-127">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="54b34-127">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="54b34-128"><strong>Elementi di classificazione</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-128"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="54b34-129"><strong>Criteri delle etichette - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-129"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="54b34-130"><strong>Criteri di prevenzione della perdita dei dati - 2 esempi</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-130"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="54b34-131"><strong>I criteri di Cloud App Security per tutte le app SaaS - 1 esempio</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-131"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="54b34-p106">Etichette di Office. Esempi: Personale, Pubblico, Dati cliente, Dati risorse umane, Riservato, Estremamente riservato
</span><span class="sxs-lookup"><span data-stu-id="54b34-p106">Office labels. Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="54b34-p107">Applicare automaticamente questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="54b34-p107">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="54b34-137">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="54b34-137">Customer data</span></span></p>
<p><span data-ttu-id="54b34-p108">... ai documenti che corrispondono a questi tipi di informazioni riservate...</span><span class="sxs-lookup"><span data-stu-id="54b34-p108">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="54b34-144">&lt;elenco dei tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-144">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="54b34-p109">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="54b34-p109">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="54b34-148">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-148">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="54b34-p110">... ai documenti con questa etichetta...</span><span class="sxs-lookup"><span data-stu-id="54b34-p110">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="54b34-155">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="54b34-155">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="54b34-p111">Avvisa quando i file con questi attributi...</span><span class="sxs-lookup"><span data-stu-id="54b34-p111">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="54b34-159">&lt;Attributo PII predefinito oppure espressione personalizzata&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-159">&lt;predefined PII attribute -or- custom expression&gt;</span></span></p>
<p><span data-ttu-id="54b34-p112">... in qualsiasi app SaaS approvata vengono condivisi all'esterno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="54b34-p112">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="54b34-p113">Tipi di informazioni riservate. Esempi: Codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese</span><span class="sxs-lookup"><span data-stu-id="54b34-p113">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="54b34-p114">Pubblicare le etichette per gli utenti da applicare manualmente...</span><span class="sxs-lookup"><span data-stu-id="54b34-p114">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="54b34-169">&lt;selezionare etichette&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-169">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="54b34-p115">... a questi percorsi...</span><span class="sxs-lookup"><span data-stu-id="54b34-p115">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="54b34-176">&lt;tutte i percorsi oppure percorsi specifici&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-176">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="54b34-p116">Applicare la protezione...</span><span class="sxs-lookup"><span data-stu-id="54b34-p116">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="54b34-180">&lt;definire la protezione&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-180">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="54b34-p117">... ai documenti che corrispondono a questi tipi di informazioni riservate&gt;</span><span class="sxs-lookup"><span data-stu-id="54b34-p117">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"><span data-ttu-id="54b34-185">Nota: gli attributi di Cloud App Security presto includeranno i tipi di informazioni riservate di Office 365 e le etichette unificate in Office 365 e Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="54b34-185">Note: Attributes coming soon to Cloud App Security include Office 365 sensitive information types and Unified labels across Office 365 and Azure Information Protection.</span></span></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="54b34-186">Definire la priorità dei criteri per applicare automaticamente le etichette
</span><span class="sxs-lookup"><span data-stu-id="54b34-186">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="54b34-p118">Per i dati personali soggetti all'RGPD, Microsoft consiglia di applicare automaticamente le etichette utilizzando le tipologie di informazioni sensibili create per il proprio ambiente. I criteri che applicano automaticamente le etichette devono essere configurati correttamente e occorre testarli per verificare che producano i risultati previsti.
</span><span class="sxs-lookup"><span data-stu-id="54b34-p118">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="54b34-p119">L'ordine con cui vengono creati i criteri da applicare automaticamente e il fatto che gli utenti applichino o meno queste etichette influisce sul risultato. È quindi importante pianificare attentamente l'implementazione. Ecco cosa serve sapere.</span><span class="sxs-lookup"><span data-stu-id="54b34-p119">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="54b34-191">Un'etichetta alla volta</span><span class="sxs-lookup"><span data-stu-id="54b34-191">One label at a time</span></span>

<span data-ttu-id="54b34-192">È possibile assegnare solo un'etichetta a un documento.</span><span class="sxs-lookup"><span data-stu-id="54b34-192">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="54b34-193">I criteri più vecchi hanno la precedenza
</span><span class="sxs-lookup"><span data-stu-id="54b34-193">Older auto-apply policies win</span></span>

<span data-ttu-id="54b34-p120">Se sono presenti più regole che assegnano un'etichetta da applicare automaticamente e il contenuto soddisfa le condizioni di più regole, viene assegnata l'etichetta della regola meno recente. Per questo motivo, è importante pianificare con attenzione i criteri delle etichette prima di configurarli. Se un'organizzazione ha l'esigenza di modificare la priorità dei criteri delle etichette, è necessario eliminarli e crearli di nuovo.
</span><span class="sxs-lookup"><span data-stu-id="54b34-p120">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="54b34-197">Le etichette applicate manualmente dall'utente hanno la precedenza su quelle applicate automaticamente
</span><span class="sxs-lookup"><span data-stu-id="54b34-197">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="54b34-p121">Le etichette applicate manualmente dall'utente battono quelle applicate automaticamente. I criteri di applicazione automatica non possono sostituire un'etichetta già applicata da un utente. Gli utenti possono sostituire le etichette applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="54b34-p121">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="54b34-201">Le etichette assegnate automaticamente possono essere aggiornate</span><span class="sxs-lookup"><span data-stu-id="54b34-201">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="54b34-202">Le etichette assegnate automaticamente possono essere aggiornate creando nuovi criteri o aggiornando quelli esistenti.
</span><span class="sxs-lookup"><span data-stu-id="54b34-202">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="54b34-203">Assicurarsi che il piano di implementazione delle etichette includa:</span><span class="sxs-lookup"><span data-stu-id="54b34-203">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="54b34-204">Creare i criteri di applicazione automatica secondo l'ordine di priorità.
</span><span class="sxs-lookup"><span data-stu-id="54b34-204">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="54b34-p122">Allocare il tempo necessario all'applicazione automatica delle etichette prima di consentire agli utenti di applicarle manualmente. Potrebbe essere necessaria anche una settimana per applicare le etichette a tutti i contenuti che corrispondono alle condizioni.
</span><span class="sxs-lookup"><span data-stu-id="54b34-p122">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="54b34-207">Esempio di priorità per creare i criteri di applicazione automatica
</span><span class="sxs-lookup"><span data-stu-id="54b34-207">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="54b34-208"><strong>Etichette</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-208"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="54b34-209"><strong>Ordine di priorità per creare criteri da applicare automaticamente</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-209"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="54b34-210">Risorse umane - Dati dipendenti</span><span class="sxs-lookup"><span data-stu-id="54b34-210">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="54b34-211">1</span><span class="sxs-lookup"><span data-stu-id="54b34-211">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="54b34-212">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="54b34-212">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="54b34-213">2</span><span class="sxs-lookup"><span data-stu-id="54b34-213">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="54b34-214">Estremamente riservato
</span><span class="sxs-lookup"><span data-stu-id="54b34-214">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="54b34-215">3</span><span class="sxs-lookup"><span data-stu-id="54b34-215">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="54b34-216">Risorse umane - Dati sugli stipendi</span><span class="sxs-lookup"><span data-stu-id="54b34-216">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="54b34-217">4</span><span class="sxs-lookup"><span data-stu-id="54b34-217">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="54b34-218">Riservato</span><span class="sxs-lookup"><span data-stu-id="54b34-218">Confidential</span></span></td>
<td align="left"><span data-ttu-id="54b34-219">5</span><span class="sxs-lookup"><span data-stu-id="54b34-219">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="54b34-220">Pubblico</span><span class="sxs-lookup"><span data-stu-id="54b34-220">Public</span></span></td>
<td align="left"><span data-ttu-id="54b34-221">6</span><span class="sxs-lookup"><span data-stu-id="54b34-221">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="54b34-222">Personale</span><span class="sxs-lookup"><span data-stu-id="54b34-222">Personal</span></span></td>
<td align="left"><span data-ttu-id="54b34-223">Nessun criterio di applicazione automatica</span><span class="sxs-lookup"><span data-stu-id="54b34-223">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="54b34-224">Creare le etichette e i criteri per applicare le etichette automaticamente
</span><span class="sxs-lookup"><span data-stu-id="54b34-224">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="54b34-225">Creare le etichette e i criteri nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="54b34-225">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="54b34-226"><strong>Passaggio</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-226"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="54b34-227"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="54b34-227"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="54b34-228">Assegnare autorizzazioni ai membri del team di conformità.</span><span class="sxs-lookup"><span data-stu-id="54b34-228">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="54b34-p123">I membri del team di conformità che creeranno le etichette necessitano di autorizzazioni per utilizzare il Centro sicurezza e conformità. Andare a Autorizzazioni nel Centro sicurezza e conformità e modificare i membri del gruppo Amministratori di conformità.</span><span class="sxs-lookup"><span data-stu-id="54b34-p123">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="54b34-231">Vedere <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="54b34-231">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="54b34-232">Creare etichette di Office</span><span class="sxs-lookup"><span data-stu-id="54b34-232">Create Office labels.</span></span></p></td>
<td align="left"><span data-ttu-id="54b34-233">Andare a Classificazioni in Centro sicurezza e conformità, scegliere Etichette e creare etichette per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="54b34-233">Go to Classifications in Security and Compliance Center, choose Labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="54b34-234">Creare criteri di applicazione automatica per le etichette.</span><span class="sxs-lookup"><span data-stu-id="54b34-234">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="54b34-p124">Andare a Classificazione nel Centro sicurezza e conformità, scegliere Criteri etichette e creare i criteri di applicazione automatica delle etichette. Assicurarsi di creare questi criteri nell'ordine di priorità.</span><span class="sxs-lookup"><span data-stu-id="54b34-p124">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="54b34-237">La figura seguente mostra come creare un'etichetta Dati cliente da applicare automaticamente.
</span><span class="sxs-lookup"><span data-stu-id="54b34-237">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Creare e applicare un'etichetta per i dati del cliente](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="54b34-239">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="54b34-239">In the illustration:</span></span>

-   <span data-ttu-id="54b34-240">Viene creata l'etichetta "Dati del cliente".</span><span class="sxs-lookup"><span data-stu-id="54b34-240">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="54b34-241">I tipi di informazioni riservate desiderate per l'RGPD sono: codice fiscale belga, numero di carta di credito, numero identità Croazia, codice fiscale Finlandese.</span><span class="sxs-lookup"><span data-stu-id="54b34-241">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="54b34-242">La creazione di un criterio di applicazione automatica assegna l'etichetta "Dati del cliente" a qualsiasi file che include uno dei tipi di informazioni riservate aggiunto al criterio.</span><span class="sxs-lookup"><span data-stu-id="54b34-242">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>
