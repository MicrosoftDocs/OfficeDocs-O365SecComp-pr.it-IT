---
title: Progettare uno schema di classificazione per i dati personali
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
ms.service: o365-solutions
localization_priority: Priority
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: Determinare se l'organizzazione implementerà etichette nell'ambito del piano RGPD.
ms.openlocfilehash: 82eec50284f0aa4b0b74346c9fbbfc717dc08d07
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272251"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="3535c-103">Progettare uno schema di classificazione per i dati personali</span><span class="sxs-lookup"><span data-stu-id="3535c-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="3535c-p101">I precedenti articoli di questa serie si focalizzano sull'uso dei tipi di informazioni riservate per identificare i dati personali soggetti all'RGPD. I tipi di informazioni riservate sono una forma di classificazione. Potrebbero rappresentare tutta la classificazione necessaria all'utente. Tuttavia, molte organizzazioni implementano una strategia di governance dei dati più ampia mediante le etichette. Consultare questo argomento per decidere se si desidera implementare anche le etichette nell'ambito del piano RGPD. Se sì, in questo argomento sono disponibili informazioni dettagliate ed esempi.</span><span class="sxs-lookup"><span data-stu-id="3535c-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="3535c-p102">Nota: definire uno schema di classificazione per un'organizzazione e configurare criteri, etichette e condizioni richiede una pianificazione attenta. È importante comprendere che non si tratta di una procedura IT. Accertarsi di collaborare con il proprio team legale e della conformità per sviluppare una classificazione e uno schema di etichette appropriati per i dati della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3535c-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It is important to realize that this is not an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization’s data.</span></span>

## <a name="decide-if-you-are-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="3535c-113">Decidere se utilizzare le etichette oltre ai tipi di dati riservati</span><span class="sxs-lookup"><span data-stu-id="3535c-113">Decide if you are using labels in addition to sensitive data types</span></span>

<span data-ttu-id="3535c-p103">È possibile adottare uno dei due approcci di classificazione in Office 365 per le informazioni personali. Ciascuno di essi può essere utilizzato per la protezione RGPD. Se si decide di usare solo i tipi di informazioni riservate per la classificazione, è possibile ignorare il resto di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3535c-p103">You can take one of two approaches for classification in Office 365 for personal information. Either of these can be used for GDPR protection. If decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="3535c-117">Scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="3535c-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-office-365-sensitive-information-types"></a><span data-ttu-id="3535c-118">Opzione 1: usare solo tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="3535c-118">Option 1: Use only Office 365 sensitive information types</span></span>

-   <span data-ttu-id="3535c-119">I tipi di informazioni riservate sono utili per identificare e proteggere i dati personali soggetti a RGPD e altri tipi di normative.</span><span class="sxs-lookup"><span data-stu-id="3535c-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

-   <span data-ttu-id="3535c-120">Sono più facili da usare se l'organizzazione non dispone o non intende implementare un piano di governance dei dati più ampio con le etichette.</span><span class="sxs-lookup"><span data-stu-id="3535c-120">These are simpler to use if your organization doesn’t already have or plan to implement a broader data governance plan using labels.</span></span>

-   <span data-ttu-id="3535c-121">Funzionano con le regole DLP (come le etichette di Office).</span><span class="sxs-lookup"><span data-stu-id="3535c-121">These work with DLP rules (so do Office labels).</span></span>

-   <span data-ttu-id="3535c-122">In futuro, saranno compatibili con Cloud App Security per consentire agli utenti di rilevare le informazioni riservate in altre app SaaS.</span><span class="sxs-lookup"><span data-stu-id="3535c-122">In the future these will work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--office-labels"></a><span data-ttu-id="3535c-123">Opzione 2: usare tipi di informazioni riservate + etichette di Office</span><span class="sxs-lookup"><span data-stu-id="3535c-123">Option 2: Use sensitive information types + Office labels</span></span>

-   <span data-ttu-id="3535c-124">I tipi di informazioni riservate dovranno applicare automaticamente le etichette ai dati personali soggetti a RGPD, quindi rappresentano un prerequisito.</span><span class="sxs-lookup"><span data-stu-id="3535c-124">You’ll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

-   <span data-ttu-id="3535c-125">L'uso delle etichette di Office consente di includere dati personali soggetti a RGPD in un piano di governance dei dati più ampio per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3535c-125">Using Office labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

-   <span data-ttu-id="3535c-126">In un secondo momento, le etichette di Office diventeranno le etichette di Azure Information Protection nell'ambito di un motore di classificazione e assegnazione di etichette unificato.</span><span class="sxs-lookup"><span data-stu-id="3535c-126">Later, Office labels will converge with Azure Information Protection labels into a unified classification and labeling engine.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="3535c-127">Sviluppare uno schema di etichette che include dati personali</span><span class="sxs-lookup"><span data-stu-id="3535c-127">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="3535c-p104">Prima di utilizzare funzioni tecniche per applicare etichette e protezione, è opportuno esaminare l'organizzazione per definire uno schema di classificazione. L'organizzazione dovrebbe già avere uno schema di classificazione che semplifica l'aggiunta di dati personali. Questo argomento include uno schema di classificazione di esempio. È possibile utilizzarlo come punto di partenza, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3535c-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="3535c-132">Introduzione</span><span class="sxs-lookup"><span data-stu-id="3535c-132">Getting started</span></span>

<span data-ttu-id="3535c-p105">Iniziare decidendo la quantità e i nomi delle etichette da implementare. Eseguire questa operazione senza pensare alla tecnologia da usare e alla modalità di applicazione delle etichette. Applicare questo schema a livello globale nell'organizzazione, includendo i dati in locale e in altri servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="3535c-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="3535c-136">Consigli</span><span class="sxs-lookup"><span data-stu-id="3535c-136">Recommendations</span></span> 

<span data-ttu-id="3535c-137">Durante la progettazione e l'implementazione di criteri, etichette e condizioni, seguire questi suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="3535c-137">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

-   <span data-ttu-id="3535c-p106">Utilizzare lo schema di classificazione esistente (se disponibile): molte organizzazioni già utilizzano la classificazione dei dati in qualche modo. Esaminare attentamente lo schema di assegnazione delle etichette esistente e, se possibile, usarlo così com'è. La scelta sarà influenzata dall'utilizzo di etichette note agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="3535c-p106">Use existing classification schema (if any) — Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end-user will drive adoption.</span></span>

-   <span data-ttu-id="3535c-p107">Iniziare con criteri ed etichette predefiniti: tutte le soluzioni sono dotate di un set di criteri ed etichette predefiniti. Esaminarli attentamente nell'ambito dei requisiti aziendali e legali dell'organizzazione e scegliere di usare quelli, anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="3535c-p107">Start with default policies and labels — All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organizations legal and business requirements and consider using them instead of creating new ones.</span></span>

-   <span data-ttu-id="3535c-p108">Iniziare con poche etichette: potenzialmente non ci sono limiti alla quantità di etichette che è possibile creare. Tuttavia, un gran numero di etichette e etichette secondarie influirà in modo negativo sull'adozione. Un numero eccessivo di scelte spesso è sinonimo di nessuna scelta.</span><span class="sxs-lookup"><span data-stu-id="3535c-p108">Start small — There is virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often means no choice at all.</span></span>

-   <span data-ttu-id="3535c-146">Utilizzare scenari e casi d'uso: identificare casi d'uso comuni all'interno dell'organizzazione e scenari derivati da RGPD per verificare se la configurazione pianificata per la classificazione e l'assegnazione di etichette è efficace.</span><span class="sxs-lookup"><span data-stu-id="3535c-146">Use scenarios and use cases — Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

-   <span data-ttu-id="3535c-p109">Per ogni richiesta di nuova etichetta, è opportuno chiedersi: tutti gli scenari o i casi d'uso necessitano realmente di una nuova etichetta o è possibile utilizzare quelle già disponibili? Mantenere il numero di etichette al minimo migliora l'adozione.</span><span class="sxs-lookup"><span data-stu-id="3535c-p109">Question every request for a new label, does every scenario or use case really need a new label or can we use what we already have? Keeping the number of labels to a minimum improves adoption.</span></span>

-   <span data-ttu-id="3535c-p110">Utilizzare etichette secondarie per i reparti chiave, alcuni reparti hanno esigenze specifiche che richiedono etichette specifiche. Definire queste etichette come secondarie rispetto a un'etichetta esistente e utilizzare criteri con ambito assegnati a gruppi di utenti, anziché a livello globale.</span><span class="sxs-lookup"><span data-stu-id="3535c-p110">Use sub-labels for key departments, some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

-   <span data-ttu-id="3535c-p111">Prendere in considerazione i criteri con ambito, criteri destinati a sottoinsiemi di utenti che impediscono un "sovraccarico di etichette". Un criterio con ambito consente di abilitare l'assegnazione di etichette (secondarie) specifiche per ruoli o reparti solo ai dipendenti che lavorano per un determinato reparto.</span><span class="sxs-lookup"><span data-stu-id="3535c-p111">Consider scoped policies, polices targeted at subsets of users will prevent "label overload". A scoped policy enables assigning role or department specific (sub-)labels to just employees that work for that specific department.</span></span>

-   <span data-ttu-id="3535c-p112">Utilizzare nomi significativi per le etichette (si consiglia di non usare termini specifici, standard o acronimi). Provare a usare nomi familiari agli utenti finali per migliorarne l'adozione. Anziché usare etichette come PII, PCI, HIPAA, LBI, MBI e HBI, scegliere nomi quali Non aziendale, Pubblico, Generale, Riservato ed Estremamente riservato.</span><span class="sxs-lookup"><span data-stu-id="3535c-p112">Use meaningful label names, it is recommended not to use jargon, standards or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI and HBI consider names like Non-Business, Public, General, Confidential and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="3535c-156">Schema di classificazione di esempio</span><span class="sxs-lookup"><span data-stu-id="3535c-156">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3535c-157"><strong>Nome etichetta</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-157"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="3535c-158"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-158"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-159">Personale</span><span class="sxs-lookup"><span data-stu-id="3535c-159">Personal</span></span></td>
<td align="left"><span data-ttu-id="3535c-160">Dati non aziendali, solo per uso personale.</span><span class="sxs-lookup"><span data-stu-id="3535c-160">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-161">Pubblico</span><span class="sxs-lookup"><span data-stu-id="3535c-161">Public</span></span></td>
<td align="left"><span data-ttu-id="3535c-162">Dati aziendali appositamente preparati e approvati per l'utilizzo pubblico.</span><span class="sxs-lookup"><span data-stu-id="3535c-162">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-163">Dati della società</span><span class="sxs-lookup"><span data-stu-id="3535c-163">Customer data</span></span></td>
<td align="left"><span data-ttu-id="3535c-p113">Dati aziendali contenenti informazioni di identificazione personale (ad esempio; numeri di carte di credito, numeri di conto corrente e numeri di previdenza sociale).</span><span class="sxs-lookup"><span data-stu-id="3535c-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-166">Dati sulle risorse umane</span><span class="sxs-lookup"><span data-stu-id="3535c-166">HR data</span></span></td>
<td align="left"><span data-ttu-id="3535c-167">Dati sulle risorse umane sui dipendenti di Contoso, come i dati sulle retribuzioni e sul numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="3535c-167">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-168">Riservato</span><span class="sxs-lookup"><span data-stu-id="3535c-168">Confidential</span></span></td>
<td align="left"><span data-ttu-id="3535c-p114">Dati aziendali riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: contratti, report sulla sicurezza, riepilogo delle previsioni e dati sul conto vendite).</span><span class="sxs-lookup"><span data-stu-id="3535c-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-171">Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="3535c-171">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="3535c-p115">Dati aziendali estremamente riservati che potrebbero causare danni all'azienda qualora fossero condivisi con persone non autorizzate (ad esempio: informazioni su clienti e dipendenti, password, codice sorgente e report finanziari pre-annunciati.</span><span class="sxs-lookup"><span data-stu-id="3535c-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="3535c-174">Definire una tassonomia e criteri di ricerca per ogni etichetta</span><span class="sxs-lookup"><span data-stu-id="3535c-174">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="3535c-p116">Dopo aver sviluppato uno schema di classificazione per l'organizzazione, il passaggio successivo consiste nello sviluppo della tassonomia e dei criteri di ricerca per trovare tali dati. Per i dati personali, questa operazione è già stata completata identificando i tipi di informazioni riservate e personalizzando o creando nuovi tipi di informazioni riservate per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3535c-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you’ve already completed this work by identifying sensitive information types and also by customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="3535c-p117">La tabella seguente fornisce un esempio di schema, tassonomia e criteri di ricerca per un'organizzazione. Le etichette sono ordinate per livello di gravità dalla meno riservata alla più riservata per garantire che ai dati che corrispondono a più condizioni vengano assegnate le etichette corrette.</span><span class="sxs-lookup"><span data-stu-id="3535c-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="3535c-179">Nota: l'esempio di configurazione viene fornito a scopo puramente illustrativo e non è da considerare come una guida o una risorsa di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3535c-179">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="3535c-180">Il punto importante è accertarsi che il lavoro investito nel classificare i dati personali per la conformità all'RGPD sia adatto agli obiettivi dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3535c-180">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="3535c-181">Esempio di schema, tassonomia e criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="3535c-181">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3535c-182"><strong>Etichetta</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-182"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="3535c-183"><strong>Tassonomia</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-183"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="3535c-184"><strong>Metodo</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-184"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="3535c-185"><strong>Sintassi di ricerca</strong></span><span class="sxs-lookup"><span data-stu-id="3535c-185"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-186">Personale</span><span class="sxs-lookup"><span data-stu-id="3535c-186">Personal</span></span></td>
<td align="left"><span data-ttu-id="3535c-187">Documenti personali etichettati manualmente dall'utente finale.</span><span class="sxs-lookup"><span data-stu-id="3535c-187">Documents manually labelled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="3535c-188">Manuale</span><span class="sxs-lookup"><span data-stu-id="3535c-188">Manual</span></span></td>
<td align="left"><span data-ttu-id="3535c-189">Documenti personali etichettati manualmente dall'utente finale.</span><span class="sxs-lookup"><span data-stu-id="3535c-189">Documents manually labelled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-190">Pubblico</span><span class="sxs-lookup"><span data-stu-id="3535c-190">Public</span></span></td>
<td align="left"><span data-ttu-id="3535c-191">Documenti contenenti la frase Approvato per la pubblicazione ##/#### (senza distinzione tra maiuscole/minuscole), dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="3535c-191">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="3535c-192">KQL</span><span class="sxs-lookup"><span data-stu-id="3535c-192">KQL</span></span></p>
<p><span data-ttu-id="3535c-193">RegEx</span><span class="sxs-lookup"><span data-stu-id="3535c-193">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="3535c-194">KQL — Approvato per la pubblicazione\*</span><span class="sxs-lookup"><span data-stu-id="3535c-194">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="3535c-195">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="3535c-195">RegEx — (?i)(\bApproved for Public Release \d{2}\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-196">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="3535c-196">Customer data</span></span></td>
<td align="left"><span data-ttu-id="3535c-197">Tipi di informazioni riservate per i dati dei cittadini dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="3535c-197">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="3535c-198">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="3535c-198">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-199">Risorse umane - Dati dipendenti</span><span class="sxs-lookup"><span data-stu-id="3535c-199">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="3535c-200">Documenti che includono l'id dipendente (con distinzione tra maiuscole/minuscole) nel formato CONTOSO-9#####, dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="3535c-200">Documents that include the case sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="3535c-201">KQL</span><span class="sxs-lookup"><span data-stu-id="3535c-201">KQL</span></span></p>
<p><span data-ttu-id="3535c-202">RegEx</span><span class="sxs-lookup"><span data-stu-id="3535c-202">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="3535c-203">KQL — CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="3535c-203">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="3535c-204">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="3535c-204">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-205">Risorse umane - Dati sugli stipendi</span><span class="sxs-lookup"><span data-stu-id="3535c-205">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="3535c-206">Documenti che includono la parola chiave (senza distinzione tra maiuscole/minuscole) Contoso AND un'altra parola chiave (senza distinzione tra maiuscole/minuscole), Stipendio OR Retribuzione</span><span class="sxs-lookup"><span data-stu-id="3535c-206">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="3535c-207">KQL</span><span class="sxs-lookup"><span data-stu-id="3535c-207">KQL</span></span></p>
<p><span data-ttu-id="3535c-208">RegEx</span><span class="sxs-lookup"><span data-stu-id="3535c-208">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="3535c-209">KQL — Contoso AND (Stipendio OR Retribuzione)</span><span class="sxs-lookup"><span data-stu-id="3535c-209">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="3535c-210">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="3535c-210">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3535c-211">Riservato</span><span class="sxs-lookup"><span data-stu-id="3535c-211">Confidential</span></span></td>
<td align="left"><span data-ttu-id="3535c-212">Documenti contenenti la frase (senza distinzione tra maiuscole/minuscole) Contoso - Riservato.</span><span class="sxs-lookup"><span data-stu-id="3535c-212">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="3535c-213">KQL</span><span class="sxs-lookup"><span data-stu-id="3535c-213">KQL</span></span></p>
<p><span data-ttu-id="3535c-214">RegEx</span><span class="sxs-lookup"><span data-stu-id="3535c-214">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="3535c-215">KQL — Contoso - Riservato</span><span class="sxs-lookup"><span data-stu-id="3535c-215">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="3535c-216">RegEx — (?i)(\bContoso - Riservato\b)</span><span class="sxs-lookup"><span data-stu-id="3535c-216">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3535c-217">Estremamente riservato</span><span class="sxs-lookup"><span data-stu-id="3535c-217">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="3535c-218">Documenti che includono la frase (con distinzione tra maiuscle/minuscole) Contoso Secret o Secret-C####, dove # rappresenta qualsiasi cifra.</span><span class="sxs-lookup"><span data-stu-id="3535c-218">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="3535c-219">KQL</span><span class="sxs-lookup"><span data-stu-id="3535c-219">KQL</span></span></p>
<p><span data-ttu-id="3535c-220">RegEx</span><span class="sxs-lookup"><span data-stu-id="3535c-220">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="3535c-221">KQL — Contoso Secret OR Secret-C\*</span><span class="sxs-lookup"><span data-stu-id="3535c-221">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="3535c-222">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="3535c-222">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
