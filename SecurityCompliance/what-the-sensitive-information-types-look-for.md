---
title: Tipi di informazioni riservate disponibili da cercare
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: 55fa8b6855a9a5bf2c84f6555dd8c8227a2ad9cf
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455268"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="8450f-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="8450f-104">What the sensitive information types look for</span></span>

<span data-ttu-id="8450f-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="8450f-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="8450f-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="8450f-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="8450f-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="8450f-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="8450f-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="8450f-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="8450f-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="8450f-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="8450f-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="8450f-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-111">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-111">Format</span></span>

<span data-ttu-id="8450f-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="8450f-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-113">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-113">Pattern</span></span>

<span data-ttu-id="8450f-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-114">Formatted:</span></span>
- <span data-ttu-id="8450f-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="8450f-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="8450f-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-116">A hyphen</span></span>
- <span data-ttu-id="8450f-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-117">Four digits</span></span>
- <span data-ttu-id="8450f-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-118">A hyphen</span></span>
- <span data-ttu-id="8450f-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-119">A digit</span></span>

<span data-ttu-id="8450f-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="8450f-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="8450f-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-121">Checksum</span></span>

<span data-ttu-id="8450f-122">No</span><span class="sxs-lookup"><span data-stu-id="8450f-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-123">Definition</span></span>

<span data-ttu-id="8450f-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="8450f-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="8450f-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="8450f-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="8450f-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="8450f-129">ABA</span><span class="sxs-lookup"><span data-stu-id="8450f-129">aba</span></span>
- <span data-ttu-id="8450f-130">aba #</span><span class="sxs-lookup"><span data-stu-id="8450f-130">aba #</span></span>
- <span data-ttu-id="8450f-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="8450f-131">aba routing #</span></span>
- <span data-ttu-id="8450f-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="8450f-132">aba routing number</span></span>
- <span data-ttu-id="8450f-133">ABA</span><span class="sxs-lookup"><span data-stu-id="8450f-133">aba#</span></span>
- <span data-ttu-id="8450f-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="8450f-134">abarouting#</span></span>
- <span data-ttu-id="8450f-135">aba number</span><span class="sxs-lookup"><span data-stu-id="8450f-135">aba number</span></span>
- <span data-ttu-id="8450f-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-136">abaroutingnumber</span></span>
- <span data-ttu-id="8450f-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="8450f-137">american bank association routing #</span></span>
- <span data-ttu-id="8450f-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="8450f-138">american bank association routing number</span></span>
- <span data-ttu-id="8450f-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="8450f-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="8450f-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="8450f-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="8450f-141">bank routing number</span></span>
- <span data-ttu-id="8450f-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="8450f-142">bankrouting#</span></span>
- <span data-ttu-id="8450f-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-143">bankroutingnumber</span></span>
- <span data-ttu-id="8450f-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="8450f-144">routing transit number</span></span>
- <span data-ttu-id="8450f-145">RTN</span><span class="sxs-lookup"><span data-stu-id="8450f-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="8450f-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="8450f-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-147">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-147">Format</span></span>

<span data-ttu-id="8450f-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="8450f-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-149">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-149">Pattern</span></span>

<span data-ttu-id="8450f-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-150">Eight digits:</span></span>
- <span data-ttu-id="8450f-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-151">Two digits</span></span>
- <span data-ttu-id="8450f-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-152">A period</span></span>
- <span data-ttu-id="8450f-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-153">Three digits</span></span>
- <span data-ttu-id="8450f-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-154">A period</span></span>
- <span data-ttu-id="8450f-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-156">Checksum</span></span>

<span data-ttu-id="8450f-157">No</span><span class="sxs-lookup"><span data-stu-id="8450f-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-158">Definition</span></span>

<span data-ttu-id="8450f-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="8450f-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="8450f-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="8450f-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="8450f-165">Identità</span><span class="sxs-lookup"><span data-stu-id="8450f-165">Identity</span></span> 
- <span data-ttu-id="8450f-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="8450f-167">DNI</span><span class="sxs-lookup"><span data-stu-id="8450f-167">DNI</span></span> 
- <span data-ttu-id="8450f-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="8450f-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="8450f-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="8450f-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="8450f-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="8450f-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="8450f-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="8450f-171">Identidad</span></span> 
- <span data-ttu-id="8450f-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="8450f-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="8450f-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8450f-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-174">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-174">Format</span></span>

<span data-ttu-id="8450f-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="8450f-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-176">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-176">Pattern</span></span>

<span data-ttu-id="8450f-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="8450f-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="8450f-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="8450f-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="8450f-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-179">Three digits</span></span> 
- <span data-ttu-id="8450f-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-180">A hyphen</span></span> 
- <span data-ttu-id="8450f-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-182">Checksum</span></span>

<span data-ttu-id="8450f-183">No</span><span class="sxs-lookup"><span data-stu-id="8450f-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-184">Definition</span></span>

<span data-ttu-id="8450f-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="8450f-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="8450f-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="8450f-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="8450f-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="8450f-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8450f-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="8450f-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="8450f-194">swift bank code</span></span>
- <span data-ttu-id="8450f-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="8450f-195">correspondent bank</span></span>
- <span data-ttu-id="8450f-196">base currency</span><span class="sxs-lookup"><span data-stu-id="8450f-196">base currency</span></span>
- <span data-ttu-id="8450f-197">usa account</span><span class="sxs-lookup"><span data-stu-id="8450f-197">usa account</span></span>
- <span data-ttu-id="8450f-198">holder address</span><span class="sxs-lookup"><span data-stu-id="8450f-198">holder address</span></span>
- <span data-ttu-id="8450f-199">bank address</span><span class="sxs-lookup"><span data-stu-id="8450f-199">bank address</span></span>
- <span data-ttu-id="8450f-200">information account</span><span class="sxs-lookup"><span data-stu-id="8450f-200">information account</span></span>
- <span data-ttu-id="8450f-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="8450f-201">fund transfers</span></span>
- <span data-ttu-id="8450f-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="8450f-202">bank charges</span></span>
- <span data-ttu-id="8450f-203">bank details</span><span class="sxs-lookup"><span data-stu-id="8450f-203">bank details</span></span>
- <span data-ttu-id="8450f-204">banking information</span><span class="sxs-lookup"><span data-stu-id="8450f-204">banking information</span></span>
- <span data-ttu-id="8450f-205">full names</span><span class="sxs-lookup"><span data-stu-id="8450f-205">full names</span></span>
- <span data-ttu-id="8450f-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="8450f-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="8450f-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-208">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-208">Format</span></span>

<span data-ttu-id="8450f-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="8450f-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-210">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-210">Pattern</span></span>

<span data-ttu-id="8450f-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="8450f-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="8450f-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-213">Two digits</span></span> 
- <span data-ttu-id="8450f-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="8450f-215">O</span><span class="sxs-lookup"><span data-stu-id="8450f-215">OR</span></span>

- <span data-ttu-id="8450f-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-217">4-9 digits</span></span>

<span data-ttu-id="8450f-218">O</span><span class="sxs-lookup"><span data-stu-id="8450f-218">OR</span></span>

- <span data-ttu-id="8450f-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-220">Checksum</span></span>

<span data-ttu-id="8450f-221">No</span><span class="sxs-lookup"><span data-stu-id="8450f-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-222">Definition</span></span>

<span data-ttu-id="8450f-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="8450f-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="8450f-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="8450f-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8450f-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="8450f-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="8450f-229">international driving permits</span></span>
- <span data-ttu-id="8450f-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="8450f-230">australian automobile association</span></span>
- <span data-ttu-id="8450f-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="8450f-231">international driving permit</span></span>
- <span data-ttu-id="8450f-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-232">DriverLicence</span></span>
- <span data-ttu-id="8450f-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-233">DriverLicences</span></span>
- <span data-ttu-id="8450f-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-234">Driver Lic</span></span>
- <span data-ttu-id="8450f-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-235">Driver Licence</span></span>
- <span data-ttu-id="8450f-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-236">Driver Licences</span></span>
- <span data-ttu-id="8450f-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8450f-237">DriversLic</span></span>
- <span data-ttu-id="8450f-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-238">DriversLicence</span></span>
- <span data-ttu-id="8450f-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-239">DriversLicences</span></span>
- <span data-ttu-id="8450f-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-240">Drivers Lic</span></span>
- <span data-ttu-id="8450f-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-241">Drivers Lics</span></span>
- <span data-ttu-id="8450f-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-242">Drivers Licence</span></span>
- <span data-ttu-id="8450f-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-243">Drivers Licences</span></span>
- <span data-ttu-id="8450f-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-244">Driver'Lic</span></span>
- <span data-ttu-id="8450f-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-245">Driver'Lics</span></span>
- <span data-ttu-id="8450f-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-246">Driver'Licence</span></span>
- <span data-ttu-id="8450f-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-247">Driver'Licences</span></span>
- <span data-ttu-id="8450f-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-248">Driver' Lic</span></span>
- <span data-ttu-id="8450f-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-249">Driver' Lics</span></span>
- <span data-ttu-id="8450f-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-250">Driver' Licence</span></span>
- <span data-ttu-id="8450f-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-251">Driver' Licences</span></span>
- <span data-ttu-id="8450f-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="8450f-252">Driver'sLic</span></span>
- <span data-ttu-id="8450f-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="8450f-253">Driver'sLics</span></span>
- <span data-ttu-id="8450f-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-254">Driver'sLicence</span></span>
- <span data-ttu-id="8450f-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-255">Driver'sLicences</span></span>
- <span data-ttu-id="8450f-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-256">Driver's Lic</span></span>
- <span data-ttu-id="8450f-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-257">Driver's Lics</span></span>
- <span data-ttu-id="8450f-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-258">Driver's Licence</span></span>
- <span data-ttu-id="8450f-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-259">Driver's Licences</span></span>
- <span data-ttu-id="8450f-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-260">DriverLic#</span></span>
- <span data-ttu-id="8450f-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-261">DriverLics#</span></span>
- <span data-ttu-id="8450f-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-262">DriverLicence#</span></span>
- <span data-ttu-id="8450f-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-263">DriverLicences#</span></span>
- <span data-ttu-id="8450f-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-264">Driver Lic#</span></span>
- <span data-ttu-id="8450f-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-265">Driver Lics#</span></span>
- <span data-ttu-id="8450f-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-266">Driver Licence#</span></span>
- <span data-ttu-id="8450f-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-267">Driver Licences#</span></span>
- <span data-ttu-id="8450f-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-268">DriversLic#</span></span>
- <span data-ttu-id="8450f-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-269">DriversLics#</span></span>
- <span data-ttu-id="8450f-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-270">DriversLicence#</span></span>
- <span data-ttu-id="8450f-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-271">DriversLicences#</span></span>
- <span data-ttu-id="8450f-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-272">Drivers Lic#</span></span>
- <span data-ttu-id="8450f-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-273">Drivers Lics#</span></span>
- <span data-ttu-id="8450f-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-274">Drivers Licence#</span></span>
- <span data-ttu-id="8450f-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-275">Drivers Licences#</span></span>
- <span data-ttu-id="8450f-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="8450f-276">Driver'Lic#</span></span>
- <span data-ttu-id="8450f-277">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-277">Driver'Lics#</span></span>
- <span data-ttu-id="8450f-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="8450f-278">Driver'Licence#</span></span>
- <span data-ttu-id="8450f-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="8450f-279">Driver'Licences#</span></span>
- <span data-ttu-id="8450f-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-280">Driver' Lic#</span></span>
- <span data-ttu-id="8450f-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-281">Driver' Lics#</span></span>
- <span data-ttu-id="8450f-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-282">Driver' Licence#</span></span>
- <span data-ttu-id="8450f-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-283">Driver' Licences#</span></span>
- <span data-ttu-id="8450f-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-284">Driver'sLic#</span></span>
- <span data-ttu-id="8450f-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-285">Driver'sLics#</span></span>
- <span data-ttu-id="8450f-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-286">Driver'sLicence#</span></span>
- <span data-ttu-id="8450f-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-287">Driver'sLicences#</span></span>
- <span data-ttu-id="8450f-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-288">Driver's Lic#</span></span>
- <span data-ttu-id="8450f-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-289">Driver's Lics#</span></span>
- <span data-ttu-id="8450f-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-290">Driver's Licence#</span></span>
- <span data-ttu-id="8450f-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="8450f-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="8450f-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="8450f-293">AAA</span><span class="sxs-lookup"><span data-stu-id="8450f-293">aaa</span></span>
- <span data-ttu-id="8450f-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-294">DriverLicense</span></span>
- <span data-ttu-id="8450f-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-295">DriverLicenses</span></span>
- <span data-ttu-id="8450f-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="8450f-296">Driver License</span></span>
- <span data-ttu-id="8450f-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-297">Driver Licenses</span></span>
- <span data-ttu-id="8450f-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-298">DriversLicense</span></span>
- <span data-ttu-id="8450f-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-299">DriversLicenses</span></span>
- <span data-ttu-id="8450f-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8450f-300">Drivers License</span></span>
- <span data-ttu-id="8450f-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-301">Drivers Licenses</span></span>
- <span data-ttu-id="8450f-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-302">Driver'License</span></span>
- <span data-ttu-id="8450f-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-303">Driver'Licenses</span></span>
- <span data-ttu-id="8450f-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8450f-304">Driver' License</span></span>
- <span data-ttu-id="8450f-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-305">Driver' Licenses</span></span>
- <span data-ttu-id="8450f-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-306">Driver'sLicense</span></span>
- <span data-ttu-id="8450f-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-307">Driver'sLicenses</span></span>
- <span data-ttu-id="8450f-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8450f-308">Driver's License</span></span>
- <span data-ttu-id="8450f-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-309">Driver's Licenses</span></span>
- <span data-ttu-id="8450f-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-310">DriverLicense#</span></span>
- <span data-ttu-id="8450f-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-311">DriverLicenses#</span></span>
- <span data-ttu-id="8450f-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8450f-312">Driver License#</span></span>
- <span data-ttu-id="8450f-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-313">Driver Licenses#</span></span>
- <span data-ttu-id="8450f-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-314">DriversLicense#</span></span>
- <span data-ttu-id="8450f-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-315">DriversLicenses#</span></span>
- <span data-ttu-id="8450f-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8450f-316">Drivers License#</span></span>
- <span data-ttu-id="8450f-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-317">Drivers Licenses#</span></span>
- <span data-ttu-id="8450f-318">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-318">Driver'License#</span></span>
- <span data-ttu-id="8450f-319">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-319">Driver'Licenses#</span></span>
- <span data-ttu-id="8450f-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8450f-320">Driver' License#</span></span>
- <span data-ttu-id="8450f-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-321">Driver' Licenses#</span></span>
- <span data-ttu-id="8450f-322">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-322">Driver'sLicense#</span></span>
- <span data-ttu-id="8450f-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="8450f-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8450f-324">Driver's License#</span></span>
- <span data-ttu-id="8450f-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="8450f-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="8450f-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-327">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-327">Format</span></span>

<span data-ttu-id="8450f-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-329">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-329">Pattern</span></span>

<span data-ttu-id="8450f-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-330">10-11 digits:</span></span>
- <span data-ttu-id="8450f-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="8450f-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="8450f-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="8450f-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="8450f-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="8450f-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="8450f-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-335">Checksum</span></span>

<span data-ttu-id="8450f-336">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-337">Definition</span></span>

<span data-ttu-id="8450f-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="8450f-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="8450f-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-341">The checksum passes.</span></span>

<span data-ttu-id="8450f-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-344">The checksum passes.</span></span>

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="8450f-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="8450f-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="8450f-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="8450f-347">bank account details</span></span>
- <span data-ttu-id="8450f-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="8450f-348">medicare payments</span></span>
- <span data-ttu-id="8450f-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="8450f-349">mortgage account</span></span>
- <span data-ttu-id="8450f-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="8450f-350">bank payments</span></span>
- <span data-ttu-id="8450f-351">information branch</span><span class="sxs-lookup"><span data-stu-id="8450f-351">information branch</span></span>
- <span data-ttu-id="8450f-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="8450f-352">credit card loan</span></span>
- <span data-ttu-id="8450f-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="8450f-353">department of human services</span></span>
- <span data-ttu-id="8450f-354">local service</span><span class="sxs-lookup"><span data-stu-id="8450f-354">local service</span></span>
- <span data-ttu-id="8450f-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="8450f-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="8450f-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-357">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-357">Format</span></span>

<span data-ttu-id="8450f-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-359">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-359">Pattern</span></span>

<span data-ttu-id="8450f-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-361">Checksum</span></span>

<span data-ttu-id="8450f-362">No</span><span class="sxs-lookup"><span data-stu-id="8450f-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-363">Definition</span></span>

<span data-ttu-id="8450f-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="8450f-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="8450f-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-368">Keyword_passport</span></span>

- <span data-ttu-id="8450f-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8450f-369">Passport Number</span></span>
- <span data-ttu-id="8450f-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="8450f-370">Passport No</span></span>
- <span data-ttu-id="8450f-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="8450f-371">Passport #</span></span>
- <span data-ttu-id="8450f-372">Passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-372">Passport#</span></span>
- <span data-ttu-id="8450f-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="8450f-373">PassportID</span></span>
- <span data-ttu-id="8450f-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="8450f-374">Passportno</span></span>
- <span data-ttu-id="8450f-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-375">passportnumber</span></span>
- <span data-ttu-id="8450f-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-376">パスポート</span></span>
- <span data-ttu-id="8450f-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-377">パスポート番号</span></span>
- <span data-ttu-id="8450f-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-378">パスポートのNum</span></span>
- <span data-ttu-id="8450f-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="8450f-379">パスポート ＃</span></span> 
- <span data-ttu-id="8450f-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-380">Numéro de passeport</span></span>
- <span data-ttu-id="8450f-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8450f-381">Passeport n °</span></span>
- <span data-ttu-id="8450f-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8450f-382">Passeport Non</span></span>
- <span data-ttu-id="8450f-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8450f-383">Passeport #</span></span>
- <span data-ttu-id="8450f-384">Passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-384">Passeport#</span></span>
- <span data-ttu-id="8450f-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8450f-385">PasseportNon</span></span>
- <span data-ttu-id="8450f-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8450f-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="8450f-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="8450f-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="8450f-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-388">passport</span></span>
- <span data-ttu-id="8450f-389">passport details</span><span class="sxs-lookup"><span data-stu-id="8450f-389">passport details</span></span>
- <span data-ttu-id="8450f-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="8450f-390">immigration and citizenship</span></span>
- <span data-ttu-id="8450f-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="8450f-391">commonwealth of australia</span></span>
- <span data-ttu-id="8450f-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="8450f-392">department of immigration</span></span>
- <span data-ttu-id="8450f-393">residential address</span><span class="sxs-lookup"><span data-stu-id="8450f-393">residential address</span></span>
- <span data-ttu-id="8450f-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="8450f-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="8450f-395">esempio</span><span class="sxs-lookup"><span data-stu-id="8450f-395">visa</span></span>
- <span data-ttu-id="8450f-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="8450f-396">national identity card</span></span>
- <span data-ttu-id="8450f-397">passport number</span><span class="sxs-lookup"><span data-stu-id="8450f-397">passport number</span></span>
- <span data-ttu-id="8450f-398">travel document</span><span class="sxs-lookup"><span data-stu-id="8450f-398">travel document</span></span>
- <span data-ttu-id="8450f-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="8450f-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="8450f-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="8450f-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-401">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-401">Format</span></span>

<span data-ttu-id="8450f-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-403">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-403">Pattern</span></span>

<span data-ttu-id="8450f-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8450f-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="8450f-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-405">Three digits</span></span> 
- <span data-ttu-id="8450f-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="8450f-406">An optional space</span></span> 
- <span data-ttu-id="8450f-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-407">Three digits</span></span> 
- <span data-ttu-id="8450f-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="8450f-408">An optional space</span></span> 
- <span data-ttu-id="8450f-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-410">Checksum</span></span>

<span data-ttu-id="8450f-411">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-412">Definition</span></span>

<span data-ttu-id="8450f-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="8450f-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="8450f-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-416">The checksum passes.</span></span>

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="8450f-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="8450f-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="8450f-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="8450f-419">australian business number</span></span>
- <span data-ttu-id="8450f-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="8450f-420">marginal tax rate</span></span>
- <span data-ttu-id="8450f-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="8450f-421">medicare levy</span></span>
- <span data-ttu-id="8450f-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="8450f-422">portfolio number</span></span>
- <span data-ttu-id="8450f-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="8450f-423">service veterans</span></span>
- <span data-ttu-id="8450f-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="8450f-424">withholding tax</span></span>
- <span data-ttu-id="8450f-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="8450f-425">individual tax return</span></span>
- <span data-ttu-id="8450f-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="8450f-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="8450f-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="8450f-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="8450f-428">00000000</span><span class="sxs-lookup"><span data-stu-id="8450f-428">00000000</span></span>
- <span data-ttu-id="8450f-429">11111111</span><span class="sxs-lookup"><span data-stu-id="8450f-429">11111111</span></span>
- <span data-ttu-id="8450f-430">22222222</span><span class="sxs-lookup"><span data-stu-id="8450f-430">22222222</span></span>
- <span data-ttu-id="8450f-431">33333333</span><span class="sxs-lookup"><span data-stu-id="8450f-431">33333333</span></span>
- <span data-ttu-id="8450f-432">44444444</span><span class="sxs-lookup"><span data-stu-id="8450f-432">44444444</span></span>
- <span data-ttu-id="8450f-433">55555555</span><span class="sxs-lookup"><span data-stu-id="8450f-433">55555555</span></span>
- <span data-ttu-id="8450f-434">66666666</span><span class="sxs-lookup"><span data-stu-id="8450f-434">66666666</span></span>
- <span data-ttu-id="8450f-435">77777777</span><span class="sxs-lookup"><span data-stu-id="8450f-435">77777777</span></span>
- <span data-ttu-id="8450f-436">88888888</span><span class="sxs-lookup"><span data-stu-id="8450f-436">88888888</span></span>
- <span data-ttu-id="8450f-437">99999999</span><span class="sxs-lookup"><span data-stu-id="8450f-437">99999999</span></span>
- <span data-ttu-id="8450f-438">000000000</span><span class="sxs-lookup"><span data-stu-id="8450f-438">000000000</span></span>
- <span data-ttu-id="8450f-439">111111111</span><span class="sxs-lookup"><span data-stu-id="8450f-439">111111111</span></span>
- <span data-ttu-id="8450f-440">222222222</span><span class="sxs-lookup"><span data-stu-id="8450f-440">222222222</span></span>
- <span data-ttu-id="8450f-441">333333333</span><span class="sxs-lookup"><span data-stu-id="8450f-441">333333333</span></span>
- <span data-ttu-id="8450f-442">444444444</span><span class="sxs-lookup"><span data-stu-id="8450f-442">444444444</span></span>
- <span data-ttu-id="8450f-443">555555555</span><span class="sxs-lookup"><span data-stu-id="8450f-443">555555555</span></span>
- <span data-ttu-id="8450f-444">666666666</span><span class="sxs-lookup"><span data-stu-id="8450f-444">666666666</span></span>
- <span data-ttu-id="8450f-445">777777777</span><span class="sxs-lookup"><span data-stu-id="8450f-445">777777777</span></span>
- <span data-ttu-id="8450f-446">888888888</span><span class="sxs-lookup"><span data-stu-id="8450f-446">888888888</span></span>
- <span data-ttu-id="8450f-447">999999999</span><span class="sxs-lookup"><span data-stu-id="8450f-447">999999999</span></span>
- <span data-ttu-id="8450f-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="8450f-448">0000000000</span></span>
- <span data-ttu-id="8450f-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="8450f-449">1111111111</span></span>
- <span data-ttu-id="8450f-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="8450f-450">2222222222</span></span>
- <span data-ttu-id="8450f-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="8450f-451">3333333333</span></span>
- <span data-ttu-id="8450f-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="8450f-452">4444444444</span></span>
- <span data-ttu-id="8450f-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="8450f-453">5555555555</span></span>
- <span data-ttu-id="8450f-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="8450f-454">6666666666</span></span>
- <span data-ttu-id="8450f-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="8450f-455">7777777777</span></span>
- <span data-ttu-id="8450f-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="8450f-456">8888888888</span></span>
- <span data-ttu-id="8450f-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="8450f-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="8450f-458">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-459">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-459">Format</span></span>

<span data-ttu-id="8450f-460">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="8450f-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-461">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-461">Pattern</span></span>

<span data-ttu-id="8450f-462">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="8450f-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="8450f-463">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="8450f-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="8450f-464">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-464">A hyphen</span></span> 
- <span data-ttu-id="8450f-465">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="8450f-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="8450f-466">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-466">A period</span></span> 
- <span data-ttu-id="8450f-467">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-468">Checksum</span></span>

<span data-ttu-id="8450f-469">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-470">Definition</span></span>

<span data-ttu-id="8450f-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-472">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-473">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="8450f-474">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-475">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="8450f-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="8450f-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="8450f-477">Identità</span><span class="sxs-lookup"><span data-stu-id="8450f-477">Identity</span></span>
- <span data-ttu-id="8450f-478">Registrazione</span><span class="sxs-lookup"><span data-stu-id="8450f-478">Registration</span></span>
- <span data-ttu-id="8450f-479">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-479">Identification</span></span> 
- <span data-ttu-id="8450f-480">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-480">ID</span></span> 
- <span data-ttu-id="8450f-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="8450f-481">Identiteitskaart</span></span>
- <span data-ttu-id="8450f-482">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="8450f-482">Registratie nummer</span></span> 
- <span data-ttu-id="8450f-483">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="8450f-483">Identificatie nummer</span></span> 
- <span data-ttu-id="8450f-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="8450f-484">Identiteit</span></span>
- <span data-ttu-id="8450f-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="8450f-485">Registratie</span></span>
- <span data-ttu-id="8450f-486">Identificatie</span><span class="sxs-lookup"><span data-stu-id="8450f-486">Identificatie</span></span> 
- <span data-ttu-id="8450f-487">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="8450f-487">Carte d’identité</span></span> 
- <span data-ttu-id="8450f-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="8450f-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="8450f-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="8450f-489">numéro d'identification</span></span>
- <span data-ttu-id="8450f-490">identité</span><span class="sxs-lookup"><span data-stu-id="8450f-490">identité</span></span> 
- <span data-ttu-id="8450f-491">iscrizione</span><span class="sxs-lookup"><span data-stu-id="8450f-491">inscription</span></span> 
- <span data-ttu-id="8450f-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="8450f-492">Identifikation</span></span>
- <span data-ttu-id="8450f-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="8450f-493">Identifizierung</span></span>
- <span data-ttu-id="8450f-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-494">Identifikationsnummer</span></span>
- <span data-ttu-id="8450f-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8450f-495">Personalausweis</span></span>
- <span data-ttu-id="8450f-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="8450f-496">Registrierung</span></span>
- <span data-ttu-id="8450f-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="8450f-498">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="8450f-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-499">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-499">Format</span></span>

<span data-ttu-id="8450f-500">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="8450f-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-501">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-501">Pattern</span></span>

<span data-ttu-id="8450f-502">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-502">Formatted:</span></span>
- <span data-ttu-id="8450f-503">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-503">Three digits</span></span> 
- <span data-ttu-id="8450f-504">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-504">A period</span></span> 
- <span data-ttu-id="8450f-505">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-505">Three digits</span></span> 
- <span data-ttu-id="8450f-506">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-506">A period</span></span> 
- <span data-ttu-id="8450f-507">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-507">Three digits</span></span> 
- <span data-ttu-id="8450f-508">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-508">A hyphen</span></span> 
- <span data-ttu-id="8450f-509">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-509">Two digits which are check digits</span></span>

<span data-ttu-id="8450f-510">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-510">Unformatted:</span></span>
- <span data-ttu-id="8450f-511">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-512">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-512">Checksum</span></span>

<span data-ttu-id="8450f-513">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-514">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-514">Definition</span></span>

<span data-ttu-id="8450f-515">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-516">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-517">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="8450f-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="8450f-518">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-518">The checksum passes.</span></span>

<span data-ttu-id="8450f-519">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-520">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-521">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-521">The checksum passes.</span></span>

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-522">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="8450f-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="8450f-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="8450f-524">CPF</span><span class="sxs-lookup"><span data-stu-id="8450f-524">CPF</span></span>
- <span data-ttu-id="8450f-525">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-525">Identification</span></span>
- <span data-ttu-id="8450f-526">Registrazione</span><span class="sxs-lookup"><span data-stu-id="8450f-526">Registration</span></span>
- <span data-ttu-id="8450f-527">Entrate</span><span class="sxs-lookup"><span data-stu-id="8450f-527">Revenue</span></span>
- <span data-ttu-id="8450f-528">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="8450f-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="8450f-529">Imposto</span><span class="sxs-lookup"><span data-stu-id="8450f-529">Imposto</span></span> 
- <span data-ttu-id="8450f-530">Identificação</span><span class="sxs-lookup"><span data-stu-id="8450f-530">Identificação</span></span> 
- <span data-ttu-id="8450f-531">Inscrição</span><span class="sxs-lookup"><span data-stu-id="8450f-531">Inscrição</span></span> 
- <span data-ttu-id="8450f-532">Receita</span><span class="sxs-lookup"><span data-stu-id="8450f-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="8450f-533">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8450f-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-534">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-534">Format</span></span>

<span data-ttu-id="8450f-535">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="8450f-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-536">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-536">Pattern</span></span>
<span data-ttu-id="8450f-537">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="8450f-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="8450f-538">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-538">Two digits</span></span> 
- <span data-ttu-id="8450f-539">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-539">A period</span></span> 
- <span data-ttu-id="8450f-540">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-540">Three digits</span></span> 
- <span data-ttu-id="8450f-541">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-541">A period</span></span> 
- <span data-ttu-id="8450f-542">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="8450f-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="8450f-543">Una barra</span><span class="sxs-lookup"><span data-stu-id="8450f-543">A forward slash</span></span> 
- <span data-ttu-id="8450f-544">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="8450f-544">Four-digit branch number</span></span> 
- <span data-ttu-id="8450f-545">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-545">A hyphen</span></span> 
- <span data-ttu-id="8450f-546">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-547">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-547">Checksum</span></span>

<span data-ttu-id="8450f-548">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-549">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-549">Definition</span></span>

<span data-ttu-id="8450f-550">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-551">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-552">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="8450f-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="8450f-553">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-553">The checksum passes.</span></span>

<span data-ttu-id="8450f-554">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-555">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-556">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-556">The checksum passes.</span></span>

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-557">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="8450f-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="8450f-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="8450f-559">CNPJ</span><span class="sxs-lookup"><span data-stu-id="8450f-559">CNPJ</span></span> 
- <span data-ttu-id="8450f-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="8450f-560">CNPJ/MF</span></span> 
- <span data-ttu-id="8450f-561">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="8450f-561">CNPJ-MF</span></span> 
- <span data-ttu-id="8450f-562">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="8450f-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="8450f-563">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="8450f-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="8450f-564">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="8450f-564">Legal entity</span></span> 
- <span data-ttu-id="8450f-565">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="8450f-565">Legal entities</span></span> 
- <span data-ttu-id="8450f-566">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="8450f-566">Registration Status</span></span> 
- <span data-ttu-id="8450f-567">Business</span><span class="sxs-lookup"><span data-stu-id="8450f-567">Business</span></span> 
- <span data-ttu-id="8450f-568">Company</span><span class="sxs-lookup"><span data-stu-id="8450f-568">Company</span></span>
- <span data-ttu-id="8450f-569">CNPJ</span><span class="sxs-lookup"><span data-stu-id="8450f-569">CNPJ</span></span> 
- <span data-ttu-id="8450f-570">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="8450f-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="8450f-571">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="8450f-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="8450f-572">CGC</span><span class="sxs-lookup"><span data-stu-id="8450f-572">CGC</span></span> 
- <span data-ttu-id="8450f-573">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="8450f-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="8450f-574">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="8450f-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="8450f-575">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="8450f-575">Situação cadastral</span></span> 
- <span data-ttu-id="8450f-576">Inscrição</span><span class="sxs-lookup"><span data-stu-id="8450f-576">Inscrição</span></span> 
- <span data-ttu-id="8450f-577">Empresa</span><span class="sxs-lookup"><span data-stu-id="8450f-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="8450f-578">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="8450f-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-579">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-579">Format</span></span>

<span data-ttu-id="8450f-580">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="8450f-581">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-582">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-582">Pattern</span></span>

<span data-ttu-id="8450f-583">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="8450f-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="8450f-584">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-584">Two digits</span></span> 
- <span data-ttu-id="8450f-585">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-585">A period</span></span> 
- <span data-ttu-id="8450f-586">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-586">Three digits</span></span> 
- <span data-ttu-id="8450f-587">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-587">A period</span></span> 
- <span data-ttu-id="8450f-588">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-588">Three digits</span></span> 
- <span data-ttu-id="8450f-589">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-589">A hyphen</span></span> 
- <span data-ttu-id="8450f-590">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-590">One digit which is a check digit</span></span>

<span data-ttu-id="8450f-591">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="8450f-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="8450f-592">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-592">10 digits</span></span> 
- <span data-ttu-id="8450f-593">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-593">A hyphen</span></span> 
- <span data-ttu-id="8450f-594">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-595">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-595">Checksum</span></span>

<span data-ttu-id="8450f-596">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-597">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-597">Definition</span></span>

<span data-ttu-id="8450f-598">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-599">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-600">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="8450f-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="8450f-601">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-601">The checksum passes.</span></span>

<span data-ttu-id="8450f-602">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-603">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-604">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-604">The checksum passes.</span></span>

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-605">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="8450f-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="8450f-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="8450f-607">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="8450f-608">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8450f-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-609">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-609">Format</span></span>

<span data-ttu-id="8450f-610">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-611">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-611">Pattern</span></span>

<span data-ttu-id="8450f-612">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="8450f-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="8450f-613">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="8450f-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="8450f-614">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-614">Five digits</span></span> 
- <span data-ttu-id="8450f-615">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-615">A hyphen</span></span> 
- <span data-ttu-id="8450f-616">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="8450f-616">Three digits OR</span></span>
- <span data-ttu-id="8450f-617">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="8450f-617">A zero "0"</span></span> 
- <span data-ttu-id="8450f-618">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-619">Checksum</span></span>

<span data-ttu-id="8450f-620">No</span><span class="sxs-lookup"><span data-stu-id="8450f-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-621">Definition</span></span>

<span data-ttu-id="8450f-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-623">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-624">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="8450f-625">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="8450f-626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-627">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-628">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-629">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="8450f-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8450f-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="8450f-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="8450f-631">canada savings bonds</span></span>
- <span data-ttu-id="8450f-632">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="8450f-632">canada revenue agency</span></span>
- <span data-ttu-id="8450f-633">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="8450f-633">canadian financial institution</span></span>
- <span data-ttu-id="8450f-634">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="8450f-634">direct deposit form</span></span>
- <span data-ttu-id="8450f-635">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="8450f-635">canadian citizen</span></span>
- <span data-ttu-id="8450f-636">legal representative</span><span class="sxs-lookup"><span data-stu-id="8450f-636">legal representative</span></span>
- <span data-ttu-id="8450f-637">notary public</span><span class="sxs-lookup"><span data-stu-id="8450f-637">notary public</span></span>
- <span data-ttu-id="8450f-638">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="8450f-638">commissioner for oaths</span></span>
- <span data-ttu-id="8450f-639">child care benefit</span><span class="sxs-lookup"><span data-stu-id="8450f-639">child care benefit</span></span>
- <span data-ttu-id="8450f-640">universal child care</span><span class="sxs-lookup"><span data-stu-id="8450f-640">universal child care</span></span>
- <span data-ttu-id="8450f-641">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="8450f-641">canada child tax benefit</span></span>
- <span data-ttu-id="8450f-642">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="8450f-642">income tax benefit</span></span>
- <span data-ttu-id="8450f-643">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="8450f-643">harmonized sales tax</span></span>
- <span data-ttu-id="8450f-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8450f-644">social insurance number</span></span>
- <span data-ttu-id="8450f-645">income tax refund</span><span class="sxs-lookup"><span data-stu-id="8450f-645">income tax refund</span></span>
- <span data-ttu-id="8450f-646">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="8450f-646">child tax benefit</span></span>
- <span data-ttu-id="8450f-647">territorial payments</span><span class="sxs-lookup"><span data-stu-id="8450f-647">territorial payments</span></span>
- <span data-ttu-id="8450f-648">institution number</span><span class="sxs-lookup"><span data-stu-id="8450f-648">institution number</span></span>
- <span data-ttu-id="8450f-649">deposit request</span><span class="sxs-lookup"><span data-stu-id="8450f-649">deposit request</span></span>
- <span data-ttu-id="8450f-650">banking information</span><span class="sxs-lookup"><span data-stu-id="8450f-650">banking information</span></span>
- <span data-ttu-id="8450f-651">direct deposit</span><span class="sxs-lookup"><span data-stu-id="8450f-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="8450f-652">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-653">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-653">Format</span></span>

<span data-ttu-id="8450f-654">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="8450f-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-655">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-655">Pattern</span></span>

<span data-ttu-id="8450f-656">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="8450f-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-657">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-657">Checksum</span></span>

<span data-ttu-id="8450f-658">No</span><span class="sxs-lookup"><span data-stu-id="8450f-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-659">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-659">Definition</span></span>

<span data-ttu-id="8450f-660">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-661">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-662">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="8450f-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8450f-663">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-664">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="8450f-665">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="8450f-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="8450f-666">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="8450f-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="8450f-667">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="8450f-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="8450f-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8450f-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="8450f-669">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-669">DL</span></span>
- <span data-ttu-id="8450f-670">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-670">DLS</span></span>
- <span data-ttu-id="8450f-671">CDL</span><span class="sxs-lookup"><span data-stu-id="8450f-671">CDL</span></span>
- <span data-ttu-id="8450f-672">CDLS</span><span class="sxs-lookup"><span data-stu-id="8450f-672">CDLS</span></span>
- <span data-ttu-id="8450f-673">DriverLic</span><span class="sxs-lookup"><span data-stu-id="8450f-673">DriverLic</span></span>
- <span data-ttu-id="8450f-674">DriverLics</span><span class="sxs-lookup"><span data-stu-id="8450f-674">DriverLics</span></span>
- <span data-ttu-id="8450f-675">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-675">DriverLicense</span></span>
- <span data-ttu-id="8450f-676">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-676">DriverLicenses</span></span>
- <span data-ttu-id="8450f-677">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-677">DriverLicence</span></span>
- <span data-ttu-id="8450f-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-678">DriverLicences</span></span>
- <span data-ttu-id="8450f-679">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-679">Driver Lic</span></span>
- <span data-ttu-id="8450f-680">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-680">Driver Lics</span></span>
- <span data-ttu-id="8450f-681">Driver License</span><span class="sxs-lookup"><span data-stu-id="8450f-681">Driver License</span></span>
- <span data-ttu-id="8450f-682">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-682">Driver Licenses</span></span>
- <span data-ttu-id="8450f-683">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-683">Driver Licence</span></span>
- <span data-ttu-id="8450f-684">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-684">Driver Licences</span></span>
- <span data-ttu-id="8450f-685">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8450f-685">DriversLic</span></span>
- <span data-ttu-id="8450f-686">DriversLics</span><span class="sxs-lookup"><span data-stu-id="8450f-686">DriversLics</span></span>
- <span data-ttu-id="8450f-687">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-687">DriversLicence</span></span>
- <span data-ttu-id="8450f-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-688">DriversLicences</span></span>
- <span data-ttu-id="8450f-689">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-689">DriversLicense</span></span>
- <span data-ttu-id="8450f-690">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-690">DriversLicenses</span></span>
- <span data-ttu-id="8450f-691">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-691">Drivers Lic</span></span>
- <span data-ttu-id="8450f-692">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-692">Drivers Lics</span></span>
- <span data-ttu-id="8450f-693">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8450f-693">Drivers License</span></span>
- <span data-ttu-id="8450f-694">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-694">Drivers Licenses</span></span>
- <span data-ttu-id="8450f-695">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-695">Drivers Licence</span></span>
- <span data-ttu-id="8450f-696">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-696">Drivers Licences</span></span>
- <span data-ttu-id="8450f-697">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-697">Driver'Lic</span></span>
- <span data-ttu-id="8450f-698">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-698">Driver'Lics</span></span>
- <span data-ttu-id="8450f-699">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-699">Driver'License</span></span>
- <span data-ttu-id="8450f-700">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-700">Driver'Licenses</span></span>
- <span data-ttu-id="8450f-701">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-701">Driver'Licence</span></span>
- <span data-ttu-id="8450f-702">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-702">Driver'Licences</span></span>
- <span data-ttu-id="8450f-703">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-703">Driver' Lic</span></span>
- <span data-ttu-id="8450f-704">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-704">Driver' Lics</span></span>
- <span data-ttu-id="8450f-705">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8450f-705">Driver' License</span></span>
- <span data-ttu-id="8450f-706">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-706">Driver' Licenses</span></span>
- <span data-ttu-id="8450f-707">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-707">Driver' Licence</span></span>
- <span data-ttu-id="8450f-708">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-708">Driver' Licences</span></span>
- <span data-ttu-id="8450f-709">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="8450f-709">Driver'sLic</span></span>
- <span data-ttu-id="8450f-710">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="8450f-710">Driver'sLics</span></span>
- <span data-ttu-id="8450f-711">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-711">Driver'sLicense</span></span>
- <span data-ttu-id="8450f-712">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-712">Driver'sLicenses</span></span>
- <span data-ttu-id="8450f-713">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="8450f-713">Driver'sLicence</span></span>
- <span data-ttu-id="8450f-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="8450f-714">Driver'sLicences</span></span>
- <span data-ttu-id="8450f-715">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-715">Driver's Lic</span></span>
- <span data-ttu-id="8450f-716">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-716">Driver's Lics</span></span>
- <span data-ttu-id="8450f-717">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8450f-717">Driver's License</span></span>
- <span data-ttu-id="8450f-718">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-718">Driver's Licenses</span></span>
- <span data-ttu-id="8450f-719">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-719">Driver's Licence</span></span>
- <span data-ttu-id="8450f-720">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-720">Driver's Licences</span></span>
- <span data-ttu-id="8450f-721">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="8450f-721">Permis de Conduire</span></span>
- <span data-ttu-id="8450f-722">id</span><span class="sxs-lookup"><span data-stu-id="8450f-722">id</span></span>
- <span data-ttu-id="8450f-723">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-723">ids</span></span>
- <span data-ttu-id="8450f-724">idcard number</span><span class="sxs-lookup"><span data-stu-id="8450f-724">idcard number</span></span>
- <span data-ttu-id="8450f-725">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-725">idcard numbers</span></span>
- <span data-ttu-id="8450f-726">idcard #</span><span class="sxs-lookup"><span data-stu-id="8450f-726">idcard #</span></span>
- <span data-ttu-id="8450f-727">idcard #s</span><span class="sxs-lookup"><span data-stu-id="8450f-727">idcard #s</span></span>
- <span data-ttu-id="8450f-728">idcard card</span><span class="sxs-lookup"><span data-stu-id="8450f-728">idcard card</span></span>
- <span data-ttu-id="8450f-729">idcard cards</span><span class="sxs-lookup"><span data-stu-id="8450f-729">idcard cards</span></span>
- <span data-ttu-id="8450f-730">IDcard</span><span class="sxs-lookup"><span data-stu-id="8450f-730">idcard</span></span>
- <span data-ttu-id="8450f-731">identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-731">identification number</span></span>
- <span data-ttu-id="8450f-732">identification numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-732">identification numbers</span></span>
- <span data-ttu-id="8450f-733">identification #</span><span class="sxs-lookup"><span data-stu-id="8450f-733">identification #</span></span>
- <span data-ttu-id="8450f-734">identification #s</span><span class="sxs-lookup"><span data-stu-id="8450f-734">identification #s</span></span>
- <span data-ttu-id="8450f-735">identification card</span><span class="sxs-lookup"><span data-stu-id="8450f-735">identification card</span></span>
- <span data-ttu-id="8450f-736">identification cards</span><span class="sxs-lookup"><span data-stu-id="8450f-736">identification cards</span></span>
- <span data-ttu-id="8450f-737">identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-737">identification</span></span> 
- <span data-ttu-id="8450f-738">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-738">DL#</span></span>
- <span data-ttu-id="8450f-739">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-739">DLS#</span></span> 
- <span data-ttu-id="8450f-740">CDL</span><span class="sxs-lookup"><span data-stu-id="8450f-740">CDL#</span></span> 
- <span data-ttu-id="8450f-741">CDLS</span><span class="sxs-lookup"><span data-stu-id="8450f-741">CDLS#</span></span> 
- <span data-ttu-id="8450f-742">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-742">DriverLic#</span></span> 
- <span data-ttu-id="8450f-743">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-743">DriverLics#</span></span> 
- <span data-ttu-id="8450f-744">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-744">DriverLicense#</span></span> 
- <span data-ttu-id="8450f-745">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-745">DriverLicenses#</span></span> 
- <span data-ttu-id="8450f-746">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-746">DriverLicence#</span></span> 
- <span data-ttu-id="8450f-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-747">DriverLicences#</span></span> 
- <span data-ttu-id="8450f-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-748">Driver Lic#</span></span>
- <span data-ttu-id="8450f-749">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-749">Driver Lics#</span></span> 
- <span data-ttu-id="8450f-750">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8450f-750">Driver License#</span></span> 
- <span data-ttu-id="8450f-751">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-751">Driver Licenses#</span></span> 
- <span data-ttu-id="8450f-752">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8450f-752">Driver License#</span></span> 
- <span data-ttu-id="8450f-753">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-753">Driver Licences#</span></span> 
- <span data-ttu-id="8450f-754">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-754">DriversLic#</span></span> 
- <span data-ttu-id="8450f-755">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-755">DriversLics#</span></span> 
- <span data-ttu-id="8450f-756">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-756">DriversLicense#</span></span> 
- <span data-ttu-id="8450f-757">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-757">DriversLicenses#</span></span> 
- <span data-ttu-id="8450f-758">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-758">DriversLicence#</span></span> 
- <span data-ttu-id="8450f-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-759">DriversLicences#</span></span> 
- <span data-ttu-id="8450f-760">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-760">Drivers Lic#</span></span> 
- <span data-ttu-id="8450f-761">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-761">Drivers Lics#</span></span> 
- <span data-ttu-id="8450f-762">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8450f-762">Drivers License#</span></span> 
- <span data-ttu-id="8450f-763">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="8450f-764">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-764">Drivers Licence#</span></span> 
- <span data-ttu-id="8450f-765">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-765">Drivers Licences#</span></span> 
- <span data-ttu-id="8450f-766">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="8450f-766">Driver'Lic#</span></span> 
- <span data-ttu-id="8450f-767">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-767">Driver'Lics#</span></span> 
- <span data-ttu-id="8450f-768">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-768">Driver'License#</span></span> 
- <span data-ttu-id="8450f-769">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="8450f-770">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="8450f-770">Driver'Licence#</span></span> 
- <span data-ttu-id="8450f-771">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="8450f-771">Driver'Licences#</span></span> 
- <span data-ttu-id="8450f-772">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-772">Driver' Lic#</span></span> 
- <span data-ttu-id="8450f-773">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-773">Driver' Lics#</span></span> 
- <span data-ttu-id="8450f-774">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8450f-774">Driver' License#</span></span> 
- <span data-ttu-id="8450f-775">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="8450f-776">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-776">Driver' Licence#</span></span> 
- <span data-ttu-id="8450f-777">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-777">Driver' Licences#</span></span> 
- <span data-ttu-id="8450f-778">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-778">Driver'sLic#</span></span> 
- <span data-ttu-id="8450f-779">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-779">Driver'sLics#</span></span> 
- <span data-ttu-id="8450f-780">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="8450f-781">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="8450f-782">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="8450f-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="8450f-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="8450f-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="8450f-784">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-784">Driver's Lic#</span></span> 
- <span data-ttu-id="8450f-785">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-785">Driver's Lics#</span></span> 
- <span data-ttu-id="8450f-786">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8450f-786">Driver's License#</span></span> 
- <span data-ttu-id="8450f-787">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="8450f-788">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="8450f-788">Driver's Licence#</span></span> 
- <span data-ttu-id="8450f-789">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="8450f-789">Driver's Licences#</span></span> 
- <span data-ttu-id="8450f-790">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="8450f-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="8450f-791">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-791">id#</span></span> 
- <span data-ttu-id="8450f-792">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-792">ids#</span></span> 
- <span data-ttu-id="8450f-793">idcard card#</span><span class="sxs-lookup"><span data-stu-id="8450f-793">idcard card#</span></span> 
- <span data-ttu-id="8450f-794">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="8450f-794">idcard cards#</span></span> 
- <span data-ttu-id="8450f-795">IDcard #</span><span class="sxs-lookup"><span data-stu-id="8450f-795">idcard#</span></span> 
- <span data-ttu-id="8450f-796">identification card#</span><span class="sxs-lookup"><span data-stu-id="8450f-796">identification card#</span></span> 
- <span data-ttu-id="8450f-797">identification cards#</span><span class="sxs-lookup"><span data-stu-id="8450f-797">identification cards#</span></span> 
- <span data-ttu-id="8450f-798">identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="8450f-799">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="8450f-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-800">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-800">Format</span></span>

<span data-ttu-id="8450f-801">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-802">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-802">Pattern</span></span>

<span data-ttu-id="8450f-803">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-804">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-804">Checksum</span></span>

<span data-ttu-id="8450f-805">No</span><span class="sxs-lookup"><span data-stu-id="8450f-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-806">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-806">Definition</span></span>

<span data-ttu-id="8450f-807">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-808">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-809">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-810">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="8450f-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="8450f-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="8450f-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="8450f-812">personal health number</span></span>
- <span data-ttu-id="8450f-813">patient information</span><span class="sxs-lookup"><span data-stu-id="8450f-813">patient information</span></span>
- <span data-ttu-id="8450f-814">health services</span><span class="sxs-lookup"><span data-stu-id="8450f-814">health services</span></span>
- <span data-ttu-id="8450f-815">speciality services</span><span class="sxs-lookup"><span data-stu-id="8450f-815">speciality services</span></span>
- <span data-ttu-id="8450f-816">automobile accident</span><span class="sxs-lookup"><span data-stu-id="8450f-816">automobile accident</span></span>
- <span data-ttu-id="8450f-817">patient hospital</span><span class="sxs-lookup"><span data-stu-id="8450f-817">patient hospital</span></span>
- <span data-ttu-id="8450f-818">psichiatra</span><span class="sxs-lookup"><span data-stu-id="8450f-818">psychiatrist</span></span>
- <span data-ttu-id="8450f-819">workers compensation</span><span class="sxs-lookup"><span data-stu-id="8450f-819">workers compensation</span></span>
- <span data-ttu-id="8450f-820">Disability</span><span class="sxs-lookup"><span data-stu-id="8450f-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="8450f-821">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-822">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-822">Format</span></span>

<span data-ttu-id="8450f-823">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-824">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-824">Pattern</span></span>

<span data-ttu-id="8450f-825">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-826">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-826">Checksum</span></span>

<span data-ttu-id="8450f-827">No</span><span class="sxs-lookup"><span data-stu-id="8450f-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-828">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-828">Definition</span></span>

<span data-ttu-id="8450f-829">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-830">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-831">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-832">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="8450f-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="8450f-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="8450f-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="8450f-834">canadian citizenship</span></span>
- <span data-ttu-id="8450f-835">canadian passport</span><span class="sxs-lookup"><span data-stu-id="8450f-835">canadian passport</span></span>
- <span data-ttu-id="8450f-836">passport application</span><span class="sxs-lookup"><span data-stu-id="8450f-836">passport application</span></span>
- <span data-ttu-id="8450f-837">passport photos</span><span class="sxs-lookup"><span data-stu-id="8450f-837">passport photos</span></span>
- <span data-ttu-id="8450f-838">certified translator</span><span class="sxs-lookup"><span data-stu-id="8450f-838">certified translator</span></span>
- <span data-ttu-id="8450f-839">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="8450f-839">canadian citizens</span></span>
- <span data-ttu-id="8450f-840">processing times</span><span class="sxs-lookup"><span data-stu-id="8450f-840">processing times</span></span>
- <span data-ttu-id="8450f-841">renewal application</span><span class="sxs-lookup"><span data-stu-id="8450f-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="8450f-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-842">Keyword_passport</span></span>

- <span data-ttu-id="8450f-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8450f-843">Passport Number</span></span>
- <span data-ttu-id="8450f-844">Passport No</span><span class="sxs-lookup"><span data-stu-id="8450f-844">Passport No</span></span>
- <span data-ttu-id="8450f-845">Passport#</span><span class="sxs-lookup"><span data-stu-id="8450f-845">Passport #</span></span>
- <span data-ttu-id="8450f-846">Passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-846">Passport#</span></span>
- <span data-ttu-id="8450f-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="8450f-847">PassportID</span></span>
- <span data-ttu-id="8450f-848">Passportno</span><span class="sxs-lookup"><span data-stu-id="8450f-848">Passportno</span></span>
- <span data-ttu-id="8450f-849">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-849">passportnumber</span></span>
- <span data-ttu-id="8450f-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-850">パスポート</span></span>
- <span data-ttu-id="8450f-851">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-851">パスポート番号</span></span>
- <span data-ttu-id="8450f-852">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-852">パスポートのNum</span></span>
- <span data-ttu-id="8450f-853">パスポート #</span><span class="sxs-lookup"><span data-stu-id="8450f-853">パスポート＃</span></span>
- <span data-ttu-id="8450f-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-854">Numéro de passeport</span></span>
- <span data-ttu-id="8450f-855">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8450f-855">Passeport n °</span></span>
- <span data-ttu-id="8450f-856">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8450f-856">Passeport Non</span></span>
- <span data-ttu-id="8450f-857">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8450f-857">Passeport #</span></span>
- <span data-ttu-id="8450f-858">Passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-858">Passeport#</span></span>
- <span data-ttu-id="8450f-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8450f-859">PasseportNon</span></span>
- <span data-ttu-id="8450f-860">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8450f-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="8450f-861">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="8450f-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-862">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-862">Format</span></span>

<span data-ttu-id="8450f-863">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-864">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-864">Pattern</span></span>

<span data-ttu-id="8450f-865">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-866">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-866">Checksum</span></span>

<span data-ttu-id="8450f-867">No</span><span class="sxs-lookup"><span data-stu-id="8450f-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-868">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-868">Definition</span></span>

<span data-ttu-id="8450f-869">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-869">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-870">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="8450f-870">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-871">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="8450f-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="8450f-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="8450f-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8450f-873">social insurance number</span></span>
- <span data-ttu-id="8450f-874">health information act</span><span class="sxs-lookup"><span data-stu-id="8450f-874">health information act</span></span>
- <span data-ttu-id="8450f-875">income tax information</span><span class="sxs-lookup"><span data-stu-id="8450f-875">income tax information</span></span>
- <span data-ttu-id="8450f-876">manitoba health</span><span class="sxs-lookup"><span data-stu-id="8450f-876">manitoba health</span></span>
- <span data-ttu-id="8450f-877">health registration</span><span class="sxs-lookup"><span data-stu-id="8450f-877">health registration</span></span>
- <span data-ttu-id="8450f-878">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="8450f-878">prescription purchases</span></span>
- <span data-ttu-id="8450f-879">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="8450f-879">benefit eligibility</span></span>
- <span data-ttu-id="8450f-880">personal health</span><span class="sxs-lookup"><span data-stu-id="8450f-880">personal health</span></span>
- <span data-ttu-id="8450f-881">power of attorney</span><span class="sxs-lookup"><span data-stu-id="8450f-881">power of attorney</span></span>
- <span data-ttu-id="8450f-882">registration number</span><span class="sxs-lookup"><span data-stu-id="8450f-882">registration number</span></span>
- <span data-ttu-id="8450f-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="8450f-883">personal health number</span></span>
- <span data-ttu-id="8450f-884">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="8450f-884">practitioner referral</span></span>
- <span data-ttu-id="8450f-885">wellness professional</span><span class="sxs-lookup"><span data-stu-id="8450f-885">wellness professional</span></span>
- <span data-ttu-id="8450f-886">patient referral</span><span class="sxs-lookup"><span data-stu-id="8450f-886">patient referral</span></span>
- <span data-ttu-id="8450f-887">health and wellness</span><span class="sxs-lookup"><span data-stu-id="8450f-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="8450f-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="8450f-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="8450f-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="8450f-889">Nunavut</span></span>
- <span data-ttu-id="8450f-890">Quebec</span><span class="sxs-lookup"><span data-stu-id="8450f-890">Quebec</span></span>
- <span data-ttu-id="8450f-891">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="8450f-891">Northwest Territories</span></span>
- <span data-ttu-id="8450f-892">Ontario</span><span class="sxs-lookup"><span data-stu-id="8450f-892">Ontario</span></span>
- <span data-ttu-id="8450f-893">British Columbia</span><span class="sxs-lookup"><span data-stu-id="8450f-893">British Columbia</span></span>
- <span data-ttu-id="8450f-894">Filippa</span><span class="sxs-lookup"><span data-stu-id="8450f-894">Alberta</span></span>
- <span data-ttu-id="8450f-895">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="8450f-895">Saskatchewan</span></span>
- <span data-ttu-id="8450f-896">Manitoba</span><span class="sxs-lookup"><span data-stu-id="8450f-896">Manitoba</span></span>
- <span data-ttu-id="8450f-897">Yukon</span><span class="sxs-lookup"><span data-stu-id="8450f-897">Yukon</span></span>
- <span data-ttu-id="8450f-898">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="8450f-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="8450f-899">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="8450f-899">New Brunswick</span></span>
- <span data-ttu-id="8450f-900">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="8450f-900">Nova Scotia</span></span>
- <span data-ttu-id="8450f-901">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="8450f-901">Prince Edward Island</span></span>
- <span data-ttu-id="8450f-902">Canada</span><span class="sxs-lookup"><span data-stu-id="8450f-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="8450f-903">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-904">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-904">Format</span></span>

<span data-ttu-id="8450f-905">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="8450f-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-906">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-906">Pattern</span></span>

<span data-ttu-id="8450f-907">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-907">Formatted:</span></span>
- <span data-ttu-id="8450f-908">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-908">Three digits</span></span> 
- <span data-ttu-id="8450f-909">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="8450f-909">A hyphen or space</span></span> 
- <span data-ttu-id="8450f-910">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-910">Three digits</span></span> 
- <span data-ttu-id="8450f-911">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="8450f-911">A hyphen or space</span></span> 
- <span data-ttu-id="8450f-912">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-912">Three digits</span></span>

<span data-ttu-id="8450f-913">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-914">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-914">Checksum</span></span>

<span data-ttu-id="8450f-915">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-916">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-916">Definition</span></span>

<span data-ttu-id="8450f-917">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-918">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-919">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="8450f-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="8450f-920">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="8450f-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="8450f-921">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="8450f-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="8450f-922">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8450f-923">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-923">The checksum passes.</span></span>

<span data-ttu-id="8450f-924">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-925">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-926">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="8450f-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="8450f-927">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-927">The checksum passes.</span></span>

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-928">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="8450f-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="8450f-929">Keyword_sin</span></span>

- <span data-ttu-id="8450f-930">sin</span><span class="sxs-lookup"><span data-stu-id="8450f-930">sin</span></span> 
- <span data-ttu-id="8450f-931">social insurance</span><span class="sxs-lookup"><span data-stu-id="8450f-931">social insurance</span></span> 
- <span data-ttu-id="8450f-932">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="8450f-933">peccati</span><span class="sxs-lookup"><span data-stu-id="8450f-933">sins</span></span> 
- <span data-ttu-id="8450f-934">SSN</span><span class="sxs-lookup"><span data-stu-id="8450f-934">ssn</span></span> 
- <span data-ttu-id="8450f-935">SNSS</span><span class="sxs-lookup"><span data-stu-id="8450f-935">ssns</span></span> 
- <span data-ttu-id="8450f-936">social security</span><span class="sxs-lookup"><span data-stu-id="8450f-936">social security</span></span> 
- <span data-ttu-id="8450f-937">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="8450f-937">numero d'assurance social</span></span> 
- <span data-ttu-id="8450f-938">national identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-938">national identification number</span></span> 
- <span data-ttu-id="8450f-939">national id</span><span class="sxs-lookup"><span data-stu-id="8450f-939">national id</span></span> 
- <span data-ttu-id="8450f-940">sin</span><span class="sxs-lookup"><span data-stu-id="8450f-940">sin#</span></span> 
- <span data-ttu-id="8450f-941">soc ins</span><span class="sxs-lookup"><span data-stu-id="8450f-941">soc ins</span></span> 
- <span data-ttu-id="8450f-942">social ins</span><span class="sxs-lookup"><span data-stu-id="8450f-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="8450f-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="8450f-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="8450f-944">driver's license</span><span class="sxs-lookup"><span data-stu-id="8450f-944">driver's license</span></span> 
- <span data-ttu-id="8450f-945">drivers license</span><span class="sxs-lookup"><span data-stu-id="8450f-945">drivers license</span></span> 
- <span data-ttu-id="8450f-946">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8450f-946">driver's licence</span></span> 
- <span data-ttu-id="8450f-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8450f-947">drivers licence</span></span> 
- <span data-ttu-id="8450f-948">DOB</span><span class="sxs-lookup"><span data-stu-id="8450f-948">DOB</span></span> 
- <span data-ttu-id="8450f-949">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-949">Birthdate</span></span> 
- <span data-ttu-id="8450f-950">Compleanno</span><span class="sxs-lookup"><span data-stu-id="8450f-950">Birthday</span></span> 
- <span data-ttu-id="8450f-951">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8450f-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="8450f-952">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-953">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-953">Format</span></span>

<span data-ttu-id="8450f-954">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="8450f-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-955">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-955">Pattern</span></span>

<span data-ttu-id="8450f-956">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="8450f-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="8450f-957">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-957">1-2 digits</span></span> 
- <span data-ttu-id="8450f-958">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-958">A period</span></span> 
- <span data-ttu-id="8450f-959">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-959">Three digits</span></span> 
- <span data-ttu-id="8450f-960">Un punto </span><span class="sxs-lookup"><span data-stu-id="8450f-960">A period</span></span> 
- <span data-ttu-id="8450f-961">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-961">Three digits</span></span> 
- <span data-ttu-id="8450f-962">Un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-962">A dash</span></span> 
- <span data-ttu-id="8450f-963">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-964">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-964">Checksum</span></span>

<span data-ttu-id="8450f-965">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-966">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-966">Definition</span></span>

<span data-ttu-id="8450f-967">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-968">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-969">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="8450f-970">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-970">The checksum passes.</span></span>

<span data-ttu-id="8450f-971">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-972">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-973">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-973">The checksum passes.</span></span>

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-974">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="8450f-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="8450f-976">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="8450f-976">National Identification Number</span></span> 
- <span data-ttu-id="8450f-977">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-977">Identity card</span></span> 
- <span data-ttu-id="8450f-978">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-978">ID</span></span> 
- <span data-ttu-id="8450f-979">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-979">Identification</span></span> 
- <span data-ttu-id="8450f-980">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="8450f-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="8450f-981">Correre</span><span class="sxs-lookup"><span data-stu-id="8450f-981">RUN</span></span> 
- <span data-ttu-id="8450f-982">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="8450f-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="8450f-983">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="8450f-983">RUT</span></span> 
- <span data-ttu-id="8450f-984">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="8450f-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="8450f-985">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="8450f-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="8450f-986">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="8450f-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="8450f-987">Identificación</span><span class="sxs-lookup"><span data-stu-id="8450f-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="8450f-988">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="8450f-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-989">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-989">Format</span></span>

<span data-ttu-id="8450f-990">18 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-991">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-991">Pattern</span></span>

<span data-ttu-id="8450f-992">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-992">18 digits:</span></span>
- <span data-ttu-id="8450f-993">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="8450f-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="8450f-994">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="8450f-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8450f-995">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="8450f-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="8450f-996">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-997">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-997">Checksum</span></span>

<span data-ttu-id="8450f-998">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-999">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-999">Definition</span></span>

<span data-ttu-id="8450f-1000">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1001">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1002">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="8450f-1003">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1003">The checksum passes.</span></span>

<span data-ttu-id="8450f-1004">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1005">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1006">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1006">The checksum passes.</span></span>

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1007">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="8450f-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="8450f-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="8450f-1009">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="8450f-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="8450f-1010">RPC</span><span class="sxs-lookup"><span data-stu-id="8450f-1010">PRC</span></span> 
- <span data-ttu-id="8450f-1011">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="8450f-1011">National Identification Card</span></span> 
- <span data-ttu-id="8450f-1012">身份证</span><span class="sxs-lookup"><span data-stu-id="8450f-1012">身份证</span></span> 
- <span data-ttu-id="8450f-1013">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="8450f-1013">居民 身份证</span></span> 
- <span data-ttu-id="8450f-1014">居民身份证</span><span class="sxs-lookup"><span data-stu-id="8450f-1014">居民身份证</span></span> 
- <span data-ttu-id="8450f-1015">鉴定</span><span class="sxs-lookup"><span data-stu-id="8450f-1015">鉴定</span></span> 
- <span data-ttu-id="8450f-1016">身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-1016">身分證</span></span> 
- <span data-ttu-id="8450f-1017">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-1017">居民 身份證</span></span>
- <span data-ttu-id="8450f-1018">鑑定</span><span class="sxs-lookup"><span data-stu-id="8450f-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="8450f-1019">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="8450f-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1020">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1020">Format</span></span>

<span data-ttu-id="8450f-1021">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="8450f-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1022">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1022">Pattern</span></span>

<span data-ttu-id="8450f-1023">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="8450f-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1024">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1024">Checksum</span></span>

<span data-ttu-id="8450f-1025">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="8450f-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1026">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1026">Definition</span></span>

<span data-ttu-id="8450f-1027">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1028">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1029">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1029">One of the following is true:</span></span>
    - <span data-ttu-id="8450f-1030">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="8450f-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="8450f-1031">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="8450f-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="8450f-1032">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8450f-1033">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1033">The checksum passes.</span></span>

<span data-ttu-id="8450f-1034">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1035">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1036">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1036">The checksum passes.</span></span>

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1037">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="8450f-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="8450f-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="8450f-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="8450f-1039">card verification</span></span>
- <span data-ttu-id="8450f-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-1040">card identification number</span></span>
- <span data-ttu-id="8450f-1041">CVN</span><span class="sxs-lookup"><span data-stu-id="8450f-1041">cvn</span></span>
- <span data-ttu-id="8450f-1042">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-1042">cid</span></span>
- <span data-ttu-id="8450f-1043">CVC2</span><span class="sxs-lookup"><span data-stu-id="8450f-1043">cvc2</span></span>
- <span data-ttu-id="8450f-1044">CVV2</span><span class="sxs-lookup"><span data-stu-id="8450f-1044">cvv2</span></span>
- <span data-ttu-id="8450f-1045">pin block</span><span class="sxs-lookup"><span data-stu-id="8450f-1045">pin block</span></span>
- <span data-ttu-id="8450f-1046">security code</span><span class="sxs-lookup"><span data-stu-id="8450f-1046">security code</span></span>
- <span data-ttu-id="8450f-1047">security number</span><span class="sxs-lookup"><span data-stu-id="8450f-1047">security number</span></span>
- <span data-ttu-id="8450f-1048">security no</span><span class="sxs-lookup"><span data-stu-id="8450f-1048">security no</span></span>
- <span data-ttu-id="8450f-1049">issue number</span><span class="sxs-lookup"><span data-stu-id="8450f-1049">issue number</span></span>
- <span data-ttu-id="8450f-1050">issue no</span><span class="sxs-lookup"><span data-stu-id="8450f-1050">issue no</span></span>
- <span data-ttu-id="8450f-1051">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="8450f-1051">cryptogramme</span></span>
- <span data-ttu-id="8450f-1052">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="8450f-1052">numéro de sécurité</span></span>
- <span data-ttu-id="8450f-1053">numero de securite</span><span class="sxs-lookup"><span data-stu-id="8450f-1053">numero de securite</span></span>
- <span data-ttu-id="8450f-1054">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="8450f-1055">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="8450f-1056">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="8450f-1056">prüfziffer</span></span>
- <span data-ttu-id="8450f-1057">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="8450f-1057">prufziffer</span></span>
- <span data-ttu-id="8450f-1058">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="8450f-1058">sicherheits Kode</span></span>
- <span data-ttu-id="8450f-1059">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="8450f-1059">sicherheitscode</span></span>
- <span data-ttu-id="8450f-1060">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="8450f-1061">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1061">verfalldatum</span></span>
- <span data-ttu-id="8450f-1062">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="8450f-1062">codice di verifica</span></span>
- <span data-ttu-id="8450f-1063">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1063">cod.</span></span> <span data-ttu-id="8450f-1064">sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1064">sicurezza</span></span>
- <span data-ttu-id="8450f-1065">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1065">cod sicurezza</span></span>
- <span data-ttu-id="8450f-1066">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8450f-1066">n autorizzazione</span></span>
- <span data-ttu-id="8450f-1067">Código</span><span class="sxs-lookup"><span data-stu-id="8450f-1067">código</span></span>
- <span data-ttu-id="8450f-1068">Codigo</span><span class="sxs-lookup"><span data-stu-id="8450f-1068">codigo</span></span>
- <span data-ttu-id="8450f-1069">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1069">cod.</span></span> <span data-ttu-id="8450f-1070">SEG</span><span class="sxs-lookup"><span data-stu-id="8450f-1070">seg</span></span>
- <span data-ttu-id="8450f-1071">cod seg</span><span class="sxs-lookup"><span data-stu-id="8450f-1071">cod seg</span></span>
- <span data-ttu-id="8450f-1072">código de segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1072">código de segurança</span></span>
- <span data-ttu-id="8450f-1073">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1073">codigo de seguranca</span></span>
- <span data-ttu-id="8450f-1074">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1074">codigo de segurança</span></span>
- <span data-ttu-id="8450f-1075">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1075">código de seguranca</span></span>
- <span data-ttu-id="8450f-1076">cód.</span><span class="sxs-lookup"><span data-stu-id="8450f-1076">cód.</span></span> <span data-ttu-id="8450f-1077">Segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1077">segurança</span></span>
- <span data-ttu-id="8450f-1078">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1078">cod.</span></span> <span data-ttu-id="8450f-1079">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1079">seguranca cod.</span></span> <span data-ttu-id="8450f-1080">Segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1080">segurança</span></span>
- <span data-ttu-id="8450f-1081">cód.</span><span class="sxs-lookup"><span data-stu-id="8450f-1081">cód.</span></span> <span data-ttu-id="8450f-1082">seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1082">seguranca</span></span>
- <span data-ttu-id="8450f-1083">cód segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1083">cód segurança</span></span>
- <span data-ttu-id="8450f-1084">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="8450f-1085">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1085">cód seguranca</span></span>
- <span data-ttu-id="8450f-1086">número de verificação</span><span class="sxs-lookup"><span data-stu-id="8450f-1086">número de verificação</span></span>
- <span data-ttu-id="8450f-1087">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="8450f-1087">numero de verificacao</span></span>
- <span data-ttu-id="8450f-1088">Ablauf</span><span class="sxs-lookup"><span data-stu-id="8450f-1088">ablauf</span></span>
- <span data-ttu-id="8450f-1089">gültig bis</span><span class="sxs-lookup"><span data-stu-id="8450f-1089">gültig bis</span></span>
- <span data-ttu-id="8450f-1090">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="8450f-1091">gultig bis</span><span class="sxs-lookup"><span data-stu-id="8450f-1091">gultig bis</span></span>
- <span data-ttu-id="8450f-1092">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="8450f-1093">scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1093">scadenza</span></span>
- <span data-ttu-id="8450f-1094">data scad</span><span class="sxs-lookup"><span data-stu-id="8450f-1094">data scad</span></span>
- <span data-ttu-id="8450f-1095">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="8450f-1095">fecha de expiracion</span></span>
- <span data-ttu-id="8450f-1096">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="8450f-1096">fecha de venc</span></span>
- <span data-ttu-id="8450f-1097">vencimiento</span><span class="sxs-lookup"><span data-stu-id="8450f-1097">vencimiento</span></span>
- <span data-ttu-id="8450f-1098">válido hasta</span><span class="sxs-lookup"><span data-stu-id="8450f-1098">válido hasta</span></span>
- <span data-ttu-id="8450f-1099">valido hasta</span><span class="sxs-lookup"><span data-stu-id="8450f-1099">valido hasta</span></span>
- <span data-ttu-id="8450f-1100">VTO</span><span class="sxs-lookup"><span data-stu-id="8450f-1100">vto</span></span>
- <span data-ttu-id="8450f-1101">data de expiração</span><span class="sxs-lookup"><span data-stu-id="8450f-1101">data de expiração</span></span>
- <span data-ttu-id="8450f-1102">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="8450f-1102">data de expiracao</span></span>
- <span data-ttu-id="8450f-1103">data em que expira</span><span class="sxs-lookup"><span data-stu-id="8450f-1103">data em que expira</span></span>
- <span data-ttu-id="8450f-1104">validade</span><span class="sxs-lookup"><span data-stu-id="8450f-1104">validade</span></span>
- <span data-ttu-id="8450f-1105">Valor</span><span class="sxs-lookup"><span data-stu-id="8450f-1105">valor</span></span>
- <span data-ttu-id="8450f-1106">vencimento</span><span class="sxs-lookup"><span data-stu-id="8450f-1106">vencimento</span></span>
- <span data-ttu-id="8450f-1107">Venc</span><span class="sxs-lookup"><span data-stu-id="8450f-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="8450f-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="8450f-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="8450f-1109">Amex</span><span class="sxs-lookup"><span data-stu-id="8450f-1109">amex</span></span>
- <span data-ttu-id="8450f-1110">american express</span><span class="sxs-lookup"><span data-stu-id="8450f-1110">american express</span></span>
- <span data-ttu-id="8450f-1111">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="8450f-1111">americanexpress</span></span>
- <span data-ttu-id="8450f-1112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8450f-1112">Visa</span></span>
- <span data-ttu-id="8450f-1113">Mastercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1113">mastercard</span></span>
- <span data-ttu-id="8450f-1114">master card</span><span class="sxs-lookup"><span data-stu-id="8450f-1114">master card</span></span>
- <span data-ttu-id="8450f-1115">MC</span><span class="sxs-lookup"><span data-stu-id="8450f-1115">mc</span></span> 
- <span data-ttu-id="8450f-1116">Mastercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1116">mastercards</span></span>
- <span data-ttu-id="8450f-1117">master cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1117">master cards</span></span>
- <span data-ttu-id="8450f-1118">diner's Club</span><span class="sxs-lookup"><span data-stu-id="8450f-1118">diner's Club</span></span>
- <span data-ttu-id="8450f-1119">diners club</span><span class="sxs-lookup"><span data-stu-id="8450f-1119">diners club</span></span>
- <span data-ttu-id="8450f-1120">DinersClub</span><span class="sxs-lookup"><span data-stu-id="8450f-1120">dinersclub</span></span>
- <span data-ttu-id="8450f-1121">discover card</span><span class="sxs-lookup"><span data-stu-id="8450f-1121">discover card</span></span>
- <span data-ttu-id="8450f-1122">discovercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1122">discovercard</span></span>
- <span data-ttu-id="8450f-1123">discover cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1123">discover cards</span></span>
- <span data-ttu-id="8450f-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="8450f-1124">JCB</span></span>
- <span data-ttu-id="8450f-1125">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="8450f-1125">japanese card bureau</span></span>
- <span data-ttu-id="8450f-1126">carte blanche</span><span class="sxs-lookup"><span data-stu-id="8450f-1126">carte blanche</span></span>
- <span data-ttu-id="8450f-1127">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="8450f-1127">carteblanche</span></span>
- <span data-ttu-id="8450f-1128">credit card</span><span class="sxs-lookup"><span data-stu-id="8450f-1128">credit card</span></span>
- <span data-ttu-id="8450f-1129">CC</span><span class="sxs-lookup"><span data-stu-id="8450f-1129">cc#</span></span>
- <span data-ttu-id="8450f-1130">CC #:</span><span class="sxs-lookup"><span data-stu-id="8450f-1130">cc#:</span></span>
- <span data-ttu-id="8450f-1131">expiration date</span><span class="sxs-lookup"><span data-stu-id="8450f-1131">expiration date</span></span>
- <span data-ttu-id="8450f-1132">exp date</span><span class="sxs-lookup"><span data-stu-id="8450f-1132">exp date</span></span>
- <span data-ttu-id="8450f-1133">expiry date</span><span class="sxs-lookup"><span data-stu-id="8450f-1133">expiry date</span></span>
- <span data-ttu-id="8450f-1134">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="8450f-1134">date d’expiration</span></span>
- <span data-ttu-id="8450f-1135">date d'exp</span><span class="sxs-lookup"><span data-stu-id="8450f-1135">date d'exp</span></span>
- <span data-ttu-id="8450f-1136">date expiration</span><span class="sxs-lookup"><span data-stu-id="8450f-1136">date expiration</span></span>
- <span data-ttu-id="8450f-1137">bank card</span><span class="sxs-lookup"><span data-stu-id="8450f-1137">bank card</span></span>
- <span data-ttu-id="8450f-1138">Bankcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1138">bankcard</span></span>
- <span data-ttu-id="8450f-1139">card number</span><span class="sxs-lookup"><span data-stu-id="8450f-1139">card number</span></span>
- <span data-ttu-id="8450f-1140">card num</span><span class="sxs-lookup"><span data-stu-id="8450f-1140">card num</span></span>
- <span data-ttu-id="8450f-1141">CardNumber</span><span class="sxs-lookup"><span data-stu-id="8450f-1141">cardnumber</span></span>
- <span data-ttu-id="8450f-1142">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1142">cardnumbers</span></span>
- <span data-ttu-id="8450f-1143">card numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1143">card numbers</span></span>
- <span data-ttu-id="8450f-1144">CreditCard</span><span class="sxs-lookup"><span data-stu-id="8450f-1144">creditcard</span></span>
- <span data-ttu-id="8450f-1145">credit cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1145">credit cards</span></span>
- <span data-ttu-id="8450f-1146">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="8450f-1146">creditcards</span></span>
- <span data-ttu-id="8450f-1147">Ccn</span><span class="sxs-lookup"><span data-stu-id="8450f-1147">ccn</span></span>
- <span data-ttu-id="8450f-1148">card holder</span><span class="sxs-lookup"><span data-stu-id="8450f-1148">card holder</span></span>
- <span data-ttu-id="8450f-1149">titolare</span><span class="sxs-lookup"><span data-stu-id="8450f-1149">cardholder</span></span>
- <span data-ttu-id="8450f-1150">card holders</span><span class="sxs-lookup"><span data-stu-id="8450f-1150">card holders</span></span>
- <span data-ttu-id="8450f-1151">titolari</span><span class="sxs-lookup"><span data-stu-id="8450f-1151">cardholders</span></span>
- <span data-ttu-id="8450f-1152">check card</span><span class="sxs-lookup"><span data-stu-id="8450f-1152">check card</span></span>
- <span data-ttu-id="8450f-1153">checkcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1153">checkcard</span></span>
- <span data-ttu-id="8450f-1154">check cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1154">check cards</span></span>
- <span data-ttu-id="8450f-1155">checkcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1155">checkcards</span></span>
- <span data-ttu-id="8450f-1156">debit card</span><span class="sxs-lookup"><span data-stu-id="8450f-1156">debit card</span></span>
- <span data-ttu-id="8450f-1157">debitcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1157">debitcard</span></span>
- <span data-ttu-id="8450f-1158">debit cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1158">debit cards</span></span>
- <span data-ttu-id="8450f-1159">debitcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1159">debitcards</span></span>
- <span data-ttu-id="8450f-1160">atm card</span><span class="sxs-lookup"><span data-stu-id="8450f-1160">atm card</span></span>
- <span data-ttu-id="8450f-1161">atmcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1161">atmcard</span></span>
- <span data-ttu-id="8450f-1162">atm cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1162">atm cards</span></span>
- <span data-ttu-id="8450f-1163">atmcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1163">atmcards</span></span>
- <span data-ttu-id="8450f-1164">Enroute</span><span class="sxs-lookup"><span data-stu-id="8450f-1164">enroute</span></span>
- <span data-ttu-id="8450f-1165">en route</span><span class="sxs-lookup"><span data-stu-id="8450f-1165">en route</span></span>
- <span data-ttu-id="8450f-1166">card type</span><span class="sxs-lookup"><span data-stu-id="8450f-1166">card type</span></span>
- <span data-ttu-id="8450f-1167">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="8450f-1167">carte bancaire</span></span>
- <span data-ttu-id="8450f-1168">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="8450f-1168">carte de crédit</span></span>
- <span data-ttu-id="8450f-1169">carte de credit</span><span class="sxs-lookup"><span data-stu-id="8450f-1169">carte de credit</span></span>
- <span data-ttu-id="8450f-1170">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1170">numéro de carte</span></span>
- <span data-ttu-id="8450f-1171">numero de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1171">numero de carte</span></span>
- <span data-ttu-id="8450f-1172">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1172">nº de la carte</span></span>
- <span data-ttu-id="8450f-1173">nº de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1173">nº de carte</span></span>
- <span data-ttu-id="8450f-1174">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="8450f-1174">kreditkarte</span></span>
- <span data-ttu-id="8450f-1175">Karte</span><span class="sxs-lookup"><span data-stu-id="8450f-1175">karte</span></span>
- <span data-ttu-id="8450f-1176">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="8450f-1176">karteninhaber</span></span>
- <span data-ttu-id="8450f-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="8450f-1177">karteninhabers</span></span>
- <span data-ttu-id="8450f-1178">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="8450f-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="8450f-1179">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="8450f-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="8450f-1180">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="8450f-1180">kreditkartentyp</span></span>
- <span data-ttu-id="8450f-1181">eigentümername</span><span class="sxs-lookup"><span data-stu-id="8450f-1181">eigentümername</span></span>
- <span data-ttu-id="8450f-1182">kartennr</span><span class="sxs-lookup"><span data-stu-id="8450f-1182">kartennr</span></span> 
- <span data-ttu-id="8450f-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1183">kartennummer</span></span>
- <span data-ttu-id="8450f-1184">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1184">kreditkartennummer</span></span>
- <span data-ttu-id="8450f-1185">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="8450f-1186">carta di credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1186">carta di credito</span></span>
- <span data-ttu-id="8450f-1187">carta credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1187">carta credito</span></span>
- <span data-ttu-id="8450f-1188">carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1188">carta</span></span>
- <span data-ttu-id="8450f-1189">n carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1189">n carta</span></span>
- <span data-ttu-id="8450f-1190">Nr.</span><span class="sxs-lookup"><span data-stu-id="8450f-1190">nr.</span></span> <span data-ttu-id="8450f-1191">carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1191">carta</span></span>
- <span data-ttu-id="8450f-1192">nr carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1192">nr carta</span></span>
- <span data-ttu-id="8450f-1193">numero carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1193">numero carta</span></span>
- <span data-ttu-id="8450f-1194">numero della carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1194">numero della carta</span></span>
- <span data-ttu-id="8450f-1195">numero di carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1195">numero di carta</span></span>
- <span data-ttu-id="8450f-1196">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1196">tarjeta credito</span></span>
- <span data-ttu-id="8450f-1197">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1197">tarjeta de credito</span></span>
- <span data-ttu-id="8450f-1198">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1198">tarjeta crédito</span></span>
- <span data-ttu-id="8450f-1199">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="8450f-1200">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="8450f-1200">tarjeta de atm</span></span>
- <span data-ttu-id="8450f-1201">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="8450f-1201">tarjeta atm</span></span>
- <span data-ttu-id="8450f-1202">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1202">tarjeta debito</span></span>
- <span data-ttu-id="8450f-1203">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1203">tarjeta de debito</span></span>
- <span data-ttu-id="8450f-1204">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1204">tarjeta débito</span></span>
- <span data-ttu-id="8450f-1205">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1205">tarjeta de débito</span></span>
- <span data-ttu-id="8450f-1206">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1206">nº de tarjeta</span></span>
- <span data-ttu-id="8450f-1207">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1207">no.</span></span> <span data-ttu-id="8450f-1208">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1208">de tarjeta</span></span>
- <span data-ttu-id="8450f-1209">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1209">no de tarjeta</span></span>
- <span data-ttu-id="8450f-1210">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1210">numero de tarjeta</span></span>
- <span data-ttu-id="8450f-1211">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1211">número de tarjeta</span></span>
- <span data-ttu-id="8450f-1212">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="8450f-1212">tarjeta no</span></span>
- <span data-ttu-id="8450f-1213">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="8450f-1213">tarjetahabiente</span></span>
- <span data-ttu-id="8450f-1214">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1214">cartão de crédito</span></span>
- <span data-ttu-id="8450f-1215">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1215">cartão de credito</span></span>
- <span data-ttu-id="8450f-1216">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1216">cartao de crédito</span></span>
- <span data-ttu-id="8450f-1217">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1217">cartao de credito</span></span>
- <span data-ttu-id="8450f-1218">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1218">cartão de débito</span></span>
- <span data-ttu-id="8450f-1219">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1219">cartao de débito</span></span>
- <span data-ttu-id="8450f-1220">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1220">cartão de debito</span></span>
- <span data-ttu-id="8450f-1221">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1221">cartao de debito</span></span>
- <span data-ttu-id="8450f-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="8450f-1222">débito automático</span></span>
- <span data-ttu-id="8450f-1223">debito automatico</span><span class="sxs-lookup"><span data-stu-id="8450f-1223">debito automatico</span></span>
- <span data-ttu-id="8450f-1224">número do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1224">número do cartão</span></span>
- <span data-ttu-id="8450f-1225">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1225">numero do cartão</span></span> 
- <span data-ttu-id="8450f-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1226">número do cartao</span></span>
- <span data-ttu-id="8450f-1227">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1227">numero do cartao</span></span>
- <span data-ttu-id="8450f-1228">número de cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1228">número de cartão</span></span>
- <span data-ttu-id="8450f-1229">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1229">numero de cartão</span></span>
- <span data-ttu-id="8450f-1230">número de cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1230">número de cartao</span></span>
- <span data-ttu-id="8450f-1231">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1231">numero de cartao</span></span>
- <span data-ttu-id="8450f-1232">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1232">nº do cartão</span></span>
- <span data-ttu-id="8450f-1233">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1233">nº do cartao</span></span>
- <span data-ttu-id="8450f-1234">n º.</span><span class="sxs-lookup"><span data-stu-id="8450f-1234">nº.</span></span> <span data-ttu-id="8450f-1235">do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1235">do cartão</span></span>
- <span data-ttu-id="8450f-1236">no do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1236">no do cartão</span></span>
- <span data-ttu-id="8450f-1237">no do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1237">no do cartao</span></span>
- <span data-ttu-id="8450f-1238">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1238">no.</span></span> <span data-ttu-id="8450f-1239">do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1239">do cartão</span></span>
- <span data-ttu-id="8450f-1240">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1240">no.</span></span> <span data-ttu-id="8450f-1241">do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1241">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="8450f-1242">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="8450f-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1243">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1243">Format</span></span>

<span data-ttu-id="8450f-1244">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1245">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1245">Pattern</span></span>

<span data-ttu-id="8450f-1246">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1247">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1247">Checksum</span></span>

<span data-ttu-id="8450f-1248">No</span><span class="sxs-lookup"><span data-stu-id="8450f-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1249">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1249">Definition</span></span>

<span data-ttu-id="8450f-1250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1251">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1252">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="8450f-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="8450f-1255">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="8450f-1255">Croatian identity card</span></span>
- <span data-ttu-id="8450f-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="8450f-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="8450f-1257">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="8450f-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1258">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1258">Format</span></span>

<span data-ttu-id="8450f-1259">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1260">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1260">Pattern</span></span>

<span data-ttu-id="8450f-1261">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-1261">11 digits:</span></span>
- <span data-ttu-id="8450f-1262">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1262">10 digits</span></span> 
- <span data-ttu-id="8450f-1263">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="8450f-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1264">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1264">Checksum</span></span>

<span data-ttu-id="8450f-1265">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1266">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1266">Definition</span></span>

<span data-ttu-id="8450f-1267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1268">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1269">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="8450f-1270">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1270">The checksum passes.</span></span>

<span data-ttu-id="8450f-1271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1272">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1273">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1273">The checksum passes.</span></span>

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1274">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="8450f-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="8450f-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="8450f-1276">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="8450f-1276">Personal Identification Number</span></span>
- <span data-ttu-id="8450f-1277">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="8450f-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="8450f-1278">OIB</span><span class="sxs-lookup"><span data-stu-id="8450f-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="8450f-1279">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="8450f-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1280">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1280">Format</span></span>

<span data-ttu-id="8450f-1281">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="8450f-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1282">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1282">Pattern</span></span>

<span data-ttu-id="8450f-1283">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="8450f-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="8450f-1284">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1284">Nine digits</span></span>

<span data-ttu-id="8450f-1285">O</span><span class="sxs-lookup"><span data-stu-id="8450f-1285">OR</span></span>

- <span data-ttu-id="8450f-1286">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="8450f-1287">Una barra</span><span class="sxs-lookup"><span data-stu-id="8450f-1287">A forward slash</span></span>
- <span data-ttu-id="8450f-1288">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1288">Three digits</span></span>

<span data-ttu-id="8450f-1289">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="8450f-1289">10 digits (new format):</span></span>
- <span data-ttu-id="8450f-1290">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1290">10 digits</span></span>

<span data-ttu-id="8450f-1291">O</span><span class="sxs-lookup"><span data-stu-id="8450f-1291">OR</span></span>

- <span data-ttu-id="8450f-1292">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="8450f-1293">Una barra</span><span class="sxs-lookup"><span data-stu-id="8450f-1293">A forward slash</span></span> 
- <span data-ttu-id="8450f-1294">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1295">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1295">Checksum</span></span>

<span data-ttu-id="8450f-1296">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1297">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1297">Definition</span></span>

<span data-ttu-id="8450f-1298">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1298">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-1299">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-1299">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="8450f-1300">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1300">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="8450f-1301">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1301">Keywords</span></span>

- <span data-ttu-id="8450f-1302">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="8450f-1302">czech personal identity number</span></span>
- <span data-ttu-id="8450f-1303">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="8450f-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="8450f-1304">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="8450f-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1305">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1305">Format</span></span>

<span data-ttu-id="8450f-1306">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1307">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1307">Pattern</span></span>

<span data-ttu-id="8450f-1308">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-1308">10 digits:</span></span>
- <span data-ttu-id="8450f-1309">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8450f-1310">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-1310">A hyphen</span></span> 
- <span data-ttu-id="8450f-1311">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1312">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1312">Checksum</span></span>

<span data-ttu-id="8450f-1313">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1314">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1314">Definition</span></span>

<span data-ttu-id="8450f-1315">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-1316">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-1316">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="8450f-1317">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1317">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1318">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="8450f-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="8450f-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="8450f-1320">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="8450f-1320">Personal Identification Number</span></span>
- <span data-ttu-id="8450f-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="8450f-1321">CPR</span></span>
- <span data-ttu-id="8450f-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="8450f-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="8450f-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="8450f-1324">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="8450f-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1325">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1325">Format</span></span>

<span data-ttu-id="8450f-1326">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1327">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1327">Pattern</span></span>

<span data-ttu-id="8450f-1328">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8450f-1329">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="8450f-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="8450f-1330">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="8450f-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="8450f-1331">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1332">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1332">Checksum</span></span>

<span data-ttu-id="8450f-1333">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1334">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1334">Definition</span></span>

<span data-ttu-id="8450f-1335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1336">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1337">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1338">Keywords</span></span>

<span data-ttu-id="8450f-1339">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8450f-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="8450f-1340">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1341">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1341">Format</span></span>

<span data-ttu-id="8450f-1342">16 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1343">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1343">Pattern</span></span>

<span data-ttu-id="8450f-1344">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="8450f-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1345">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1345">Checksum</span></span>

<span data-ttu-id="8450f-1346">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1347">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1347">Definition</span></span>

<span data-ttu-id="8450f-1348">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1349">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1350">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="8450f-1351">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="8450f-1352">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="8450f-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="8450f-1353">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="8450f-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="8450f-1354">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="8450f-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="8450f-1355">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8450f-1356">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1356">The checksum passes.</span></span>

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1357">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="8450f-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="8450f-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="8450f-1359">account number</span><span class="sxs-lookup"><span data-stu-id="8450f-1359">account number</span></span> 
- <span data-ttu-id="8450f-1360">card number</span><span class="sxs-lookup"><span data-stu-id="8450f-1360">card number</span></span> 
- <span data-ttu-id="8450f-1361">card no.</span><span class="sxs-lookup"><span data-stu-id="8450f-1361">card no.</span></span> 
- <span data-ttu-id="8450f-1362">security number</span><span class="sxs-lookup"><span data-stu-id="8450f-1362">security number</span></span> 
- <span data-ttu-id="8450f-1363">CC</span><span class="sxs-lookup"><span data-stu-id="8450f-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="8450f-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8450f-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="8450f-1365">acct nbr</span><span class="sxs-lookup"><span data-stu-id="8450f-1365">acct nbr</span></span> 
- <span data-ttu-id="8450f-1366">acct num</span><span class="sxs-lookup"><span data-stu-id="8450f-1366">acct num</span></span> 
- <span data-ttu-id="8450f-1367">acct no</span><span class="sxs-lookup"><span data-stu-id="8450f-1367">acct no</span></span> 
- <span data-ttu-id="8450f-1368">american express</span><span class="sxs-lookup"><span data-stu-id="8450f-1368">american express</span></span> 
- <span data-ttu-id="8450f-1369">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="8450f-1369">americanexpress</span></span> 
- <span data-ttu-id="8450f-1370">americano espresso</span><span class="sxs-lookup"><span data-stu-id="8450f-1370">americano espresso</span></span> 
- <span data-ttu-id="8450f-1371">Amex</span><span class="sxs-lookup"><span data-stu-id="8450f-1371">amex</span></span> 
- <span data-ttu-id="8450f-1372">atm card</span><span class="sxs-lookup"><span data-stu-id="8450f-1372">atm card</span></span> 
- <span data-ttu-id="8450f-1373">atm cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1373">atm cards</span></span> 
- <span data-ttu-id="8450f-1374">atm kaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1374">atm kaart</span></span> 
- <span data-ttu-id="8450f-1375">atmcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1375">atmcard</span></span> 
- <span data-ttu-id="8450f-1376">atmcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1376">atmcards</span></span> 
- <span data-ttu-id="8450f-1377">atmkaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1377">atmkaart</span></span> 
- <span data-ttu-id="8450f-1378">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="8450f-1378">atmkaarten</span></span> 
- <span data-ttu-id="8450f-1379">Bancontact</span><span class="sxs-lookup"><span data-stu-id="8450f-1379">bancontact</span></span> 
- <span data-ttu-id="8450f-1380">bank card</span><span class="sxs-lookup"><span data-stu-id="8450f-1380">bank card</span></span> 
- <span data-ttu-id="8450f-1381">bankkaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1381">bankkaart</span></span> 
- <span data-ttu-id="8450f-1382">card holder</span><span class="sxs-lookup"><span data-stu-id="8450f-1382">card holder</span></span> 
- <span data-ttu-id="8450f-1383">card holders</span><span class="sxs-lookup"><span data-stu-id="8450f-1383">card holders</span></span> 
- <span data-ttu-id="8450f-1384">card num</span><span class="sxs-lookup"><span data-stu-id="8450f-1384">card num</span></span> 
- <span data-ttu-id="8450f-1385">card number</span><span class="sxs-lookup"><span data-stu-id="8450f-1385">card number</span></span> 
- <span data-ttu-id="8450f-1386">card numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1386">card numbers</span></span> 
- <span data-ttu-id="8450f-1387">card type</span><span class="sxs-lookup"><span data-stu-id="8450f-1387">card type</span></span> 
- <span data-ttu-id="8450f-1388">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="8450f-1388">cardano numerico</span></span> 
- <span data-ttu-id="8450f-1389">titolare</span><span class="sxs-lookup"><span data-stu-id="8450f-1389">cardholder</span></span> 
- <span data-ttu-id="8450f-1390">titolari</span><span class="sxs-lookup"><span data-stu-id="8450f-1390">cardholders</span></span> 
- <span data-ttu-id="8450f-1391">CardNumber</span><span class="sxs-lookup"><span data-stu-id="8450f-1391">cardnumber</span></span> 
- <span data-ttu-id="8450f-1392">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1392">cardnumbers</span></span> 
- <span data-ttu-id="8450f-1393">carta bianca</span><span class="sxs-lookup"><span data-stu-id="8450f-1393">carta bianca</span></span> 
- <span data-ttu-id="8450f-1394">carta credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1394">carta credito</span></span> 
- <span data-ttu-id="8450f-1395">carta di credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1395">carta di credito</span></span> 
- <span data-ttu-id="8450f-1396">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1396">cartao de credito</span></span> 
- <span data-ttu-id="8450f-1397">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1397">cartao de crédito</span></span> 
- <span data-ttu-id="8450f-1398">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1398">cartao de debito</span></span> 
- <span data-ttu-id="8450f-1399">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1399">cartao de débito</span></span> 
- <span data-ttu-id="8450f-1400">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="8450f-1400">carte bancaire</span></span> 
- <span data-ttu-id="8450f-1401">carte blanche</span><span class="sxs-lookup"><span data-stu-id="8450f-1401">carte blanche</span></span> 
- <span data-ttu-id="8450f-1402">carte bleue</span><span class="sxs-lookup"><span data-stu-id="8450f-1402">carte bleue</span></span> 
- <span data-ttu-id="8450f-1403">carte de credit</span><span class="sxs-lookup"><span data-stu-id="8450f-1403">carte de credit</span></span> 
- <span data-ttu-id="8450f-1404">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="8450f-1404">carte de crédit</span></span> 
- <span data-ttu-id="8450f-1405">carte di credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1405">carte di credito</span></span> 
- <span data-ttu-id="8450f-1406">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="8450f-1406">carteblanche</span></span> 
- <span data-ttu-id="8450f-1407">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1407">cartão de credito</span></span> 
- <span data-ttu-id="8450f-1408">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="8450f-1408">cartão de crédito</span></span> 
- <span data-ttu-id="8450f-1409">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1409">cartão de debito</span></span> 
- <span data-ttu-id="8450f-1410">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="8450f-1410">cartão de débito</span></span> 
- <span data-ttu-id="8450f-1411">CB</span><span class="sxs-lookup"><span data-stu-id="8450f-1411">cb</span></span> 
- <span data-ttu-id="8450f-1412">Ccn</span><span class="sxs-lookup"><span data-stu-id="8450f-1412">ccn</span></span> 
- <span data-ttu-id="8450f-1413">check card</span><span class="sxs-lookup"><span data-stu-id="8450f-1413">check card</span></span> 
- <span data-ttu-id="8450f-1414">check cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1414">check cards</span></span> 
- <span data-ttu-id="8450f-1415">checkcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1415">checkcard</span></span>
- <span data-ttu-id="8450f-1416">checkcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1416">checkcards</span></span> 
- <span data-ttu-id="8450f-1417">chequekaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1417">chequekaart</span></span> 
- <span data-ttu-id="8450f-1418">Cirrus</span><span class="sxs-lookup"><span data-stu-id="8450f-1418">cirrus</span></span> 
- <span data-ttu-id="8450f-1419">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="8450f-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="8450f-1420">controlekaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1420">controlekaart</span></span> 
- <span data-ttu-id="8450f-1421">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="8450f-1421">controlekaarten</span></span> 
- <span data-ttu-id="8450f-1422">credit card</span><span class="sxs-lookup"><span data-stu-id="8450f-1422">credit card</span></span> 
- <span data-ttu-id="8450f-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1423">credit cards</span></span> 
- <span data-ttu-id="8450f-1424">CreditCard</span><span class="sxs-lookup"><span data-stu-id="8450f-1424">creditcard</span></span> 
- <span data-ttu-id="8450f-1425">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="8450f-1425">creditcards</span></span> 
- <span data-ttu-id="8450f-1426">debetkaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1426">debetkaart</span></span> 
- <span data-ttu-id="8450f-1427">carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1427">debetkaarten</span></span> 
- <span data-ttu-id="8450f-1428">debit card</span><span class="sxs-lookup"><span data-stu-id="8450f-1428">debit card</span></span> 
- <span data-ttu-id="8450f-1429">debit cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1429">debit cards</span></span> 
- <span data-ttu-id="8450f-1430">debitcard</span><span class="sxs-lookup"><span data-stu-id="8450f-1430">debitcard</span></span> 
- <span data-ttu-id="8450f-1431">debitcards</span><span class="sxs-lookup"><span data-stu-id="8450f-1431">debitcards</span></span> 
- <span data-ttu-id="8450f-1432">debito automatico</span><span class="sxs-lookup"><span data-stu-id="8450f-1432">debito automatico</span></span> 
- <span data-ttu-id="8450f-1433">diners club</span><span class="sxs-lookup"><span data-stu-id="8450f-1433">diners club</span></span> 
- <span data-ttu-id="8450f-1434">DinersClub</span><span class="sxs-lookup"><span data-stu-id="8450f-1434">dinersclub</span></span> 
- <span data-ttu-id="8450f-1435">individuare</span><span class="sxs-lookup"><span data-stu-id="8450f-1435">discover</span></span> 
- <span data-ttu-id="8450f-1436">discover card</span><span class="sxs-lookup"><span data-stu-id="8450f-1436">discover card</span></span> 
- <span data-ttu-id="8450f-1437">discover cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1437">discover cards</span></span> 
- <span data-ttu-id="8450f-1438">discovercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1438">discovercard</span></span> 
- <span data-ttu-id="8450f-1439">discovercards</span><span class="sxs-lookup"><span data-stu-id="8450f-1439">discovercards</span></span> 
- <span data-ttu-id="8450f-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="8450f-1440">débito automático</span></span>
- <span data-ttu-id="8450f-1441">EDC</span><span class="sxs-lookup"><span data-stu-id="8450f-1441">edc</span></span> 
- <span data-ttu-id="8450f-1442">eigentümername</span><span class="sxs-lookup"><span data-stu-id="8450f-1442">eigentümername</span></span> 
- <span data-ttu-id="8450f-1443">european debit card</span><span class="sxs-lookup"><span data-stu-id="8450f-1443">european debit card</span></span> 
- <span data-ttu-id="8450f-1444">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1444">hoofdkaart</span></span> 
- <span data-ttu-id="8450f-1445">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="8450f-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="8450f-1446">in viaggio</span><span class="sxs-lookup"><span data-stu-id="8450f-1446">in viaggio</span></span> 
- <span data-ttu-id="8450f-1447">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="8450f-1447">japanese card bureau</span></span> 
- <span data-ttu-id="8450f-1448">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="8450f-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="8450f-1449">JCB</span><span class="sxs-lookup"><span data-stu-id="8450f-1449">jcb</span></span> 
- <span data-ttu-id="8450f-1450">kaart</span><span class="sxs-lookup"><span data-stu-id="8450f-1450">kaart</span></span> 
- <span data-ttu-id="8450f-1451">kaart num</span><span class="sxs-lookup"><span data-stu-id="8450f-1451">kaart num</span></span> 
- <span data-ttu-id="8450f-1452">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="8450f-1452">kaartaantal</span></span> 
- <span data-ttu-id="8450f-1453">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="8450f-1453">kaartaantallen</span></span> 
- <span data-ttu-id="8450f-1454">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="8450f-1454">kaarthouder</span></span> 
- <span data-ttu-id="8450f-1455">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="8450f-1455">kaarthouders</span></span> 
- <span data-ttu-id="8450f-1456">Karte</span><span class="sxs-lookup"><span data-stu-id="8450f-1456">karte</span></span>  
- <span data-ttu-id="8450f-1457">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="8450f-1457">karteninhaber</span></span> 
- <span data-ttu-id="8450f-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="8450f-1458">karteninhabers</span></span>
- <span data-ttu-id="8450f-1459">kartennr</span><span class="sxs-lookup"><span data-stu-id="8450f-1459">kartennr</span></span> 
- <span data-ttu-id="8450f-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1460">kartennummer</span></span> 
- <span data-ttu-id="8450f-1461">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="8450f-1461">kreditkarte</span></span> 
- <span data-ttu-id="8450f-1462">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="8450f-1463">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="8450f-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="8450f-1464">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="8450f-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="8450f-1465">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="8450f-1466">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="8450f-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="8450f-1467">Maestro</span><span class="sxs-lookup"><span data-stu-id="8450f-1467">maestro</span></span> 
- <span data-ttu-id="8450f-1468">master card</span><span class="sxs-lookup"><span data-stu-id="8450f-1468">master card</span></span> 
- <span data-ttu-id="8450f-1469">master cards</span><span class="sxs-lookup"><span data-stu-id="8450f-1469">master cards</span></span> 
- <span data-ttu-id="8450f-1470">Mastercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1470">mastercard</span></span> 
- <span data-ttu-id="8450f-1471">Mastercard</span><span class="sxs-lookup"><span data-stu-id="8450f-1471">mastercards</span></span> 
- <span data-ttu-id="8450f-1472">MC</span><span class="sxs-lookup"><span data-stu-id="8450f-1472">mc</span></span> 
- <span data-ttu-id="8450f-1473">mister cash</span><span class="sxs-lookup"><span data-stu-id="8450f-1473">mister cash</span></span> 
- <span data-ttu-id="8450f-1474">n carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1474">n carta</span></span> 
- <span data-ttu-id="8450f-1475">carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1475">carta</span></span> 
- <span data-ttu-id="8450f-1476">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1476">no de tarjeta</span></span> 
- <span data-ttu-id="8450f-1477">no do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1477">no do cartao</span></span> 
- <span data-ttu-id="8450f-1478">no do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1478">no do cartão</span></span> 
- <span data-ttu-id="8450f-1479">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1479">no.</span></span> <span data-ttu-id="8450f-1480">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1480">de tarjeta</span></span> 
- <span data-ttu-id="8450f-1481">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1481">no.</span></span> <span data-ttu-id="8450f-1482">do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1482">do cartao</span></span> 
- <span data-ttu-id="8450f-1483">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1483">no.</span></span> <span data-ttu-id="8450f-1484">do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1484">do cartão</span></span> 
- <span data-ttu-id="8450f-1485">nr carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1485">nr carta</span></span> 
- <span data-ttu-id="8450f-1486">Nr.</span><span class="sxs-lookup"><span data-stu-id="8450f-1486">nr.</span></span> <span data-ttu-id="8450f-1487">carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1487">carta</span></span> 
- <span data-ttu-id="8450f-1488">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1488">numeri di scheda</span></span> 
- <span data-ttu-id="8450f-1489">numero carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1489">numero carta</span></span> 
- <span data-ttu-id="8450f-1490">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1490">numero de cartao</span></span> 
- <span data-ttu-id="8450f-1491">numero de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1491">numero de carte</span></span> 
- <span data-ttu-id="8450f-1492">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1492">numero de cartão</span></span> 
- <span data-ttu-id="8450f-1493">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1493">numero de tarjeta</span></span>
- <span data-ttu-id="8450f-1494">numero della carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1494">numero della carta</span></span> 
- <span data-ttu-id="8450f-1495">numero di carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1495">numero di carta</span></span> 
- <span data-ttu-id="8450f-1496">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1496">numero di scheda</span></span> 
- <span data-ttu-id="8450f-1497">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1497">numero do cartao</span></span> 
- <span data-ttu-id="8450f-1498">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1498">numero do cartão</span></span> 
- <span data-ttu-id="8450f-1499">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1499">numéro de carte</span></span> 
- <span data-ttu-id="8450f-1500">nº carta</span><span class="sxs-lookup"><span data-stu-id="8450f-1500">nº carta</span></span> 
- <span data-ttu-id="8450f-1501">nº de carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1501">nº de carte</span></span> 
- <span data-ttu-id="8450f-1502">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="8450f-1502">nº de la carte</span></span> 
- <span data-ttu-id="8450f-1503">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="8450f-1504">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1504">nº do cartao</span></span> 
- <span data-ttu-id="8450f-1505">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1505">nº do cartão</span></span> 
- <span data-ttu-id="8450f-1506">n º.</span><span class="sxs-lookup"><span data-stu-id="8450f-1506">nº.</span></span> <span data-ttu-id="8450f-1507">do cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1507">do cartão</span></span> 
- <span data-ttu-id="8450f-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1508">número de cartao</span></span> 
- <span data-ttu-id="8450f-1509">número de cartão</span><span class="sxs-lookup"><span data-stu-id="8450f-1509">número de cartão</span></span> 
- <span data-ttu-id="8450f-1510">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="8450f-1510">número de tarjeta</span></span> 
- <span data-ttu-id="8450f-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="8450f-1511">número do cartao</span></span> 
- <span data-ttu-id="8450f-1512">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="8450f-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="8450f-1513">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8450f-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="8450f-1514">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8450f-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="8450f-1515">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="8450f-1515">scheda della banca</span></span> 
- <span data-ttu-id="8450f-1516">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1516">scheda di controllo</span></span> 
- <span data-ttu-id="8450f-1517">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1517">scheda di debito</span></span> 
- <span data-ttu-id="8450f-1518">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="8450f-1518">scheda matrice</span></span> 
- <span data-ttu-id="8450f-1519">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="8450f-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="8450f-1520">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1520">schede di controllo</span></span> 
- <span data-ttu-id="8450f-1521">schede di debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1521">schede di debito</span></span> 
- <span data-ttu-id="8450f-1522">schede matrici</span><span class="sxs-lookup"><span data-stu-id="8450f-1522">schede matrici</span></span> 
- <span data-ttu-id="8450f-1523">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="8450f-1524">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="8450f-1524">scoprono le schede</span></span> 
- <span data-ttu-id="8450f-1525">solo</span><span class="sxs-lookup"><span data-stu-id="8450f-1525">solo</span></span> 
- <span data-ttu-id="8450f-1526">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1526">supporti di scheda</span></span> 
- <span data-ttu-id="8450f-1527">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1527">supporto di scheda</span></span> 
- <span data-ttu-id="8450f-1528">opzione</span><span class="sxs-lookup"><span data-stu-id="8450f-1528">switch</span></span> 
- <span data-ttu-id="8450f-1529">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="8450f-1529">tarjeta atm</span></span> 
- <span data-ttu-id="8450f-1530">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1530">tarjeta credito</span></span> 
- <span data-ttu-id="8450f-1531">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="8450f-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="8450f-1532">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="8450f-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="8450f-1533">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="8450f-1534">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="8450f-1534">tarjeta debito</span></span> 
- <span data-ttu-id="8450f-1535">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="8450f-1535">tarjeta no</span></span>
- <span data-ttu-id="8450f-1536">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="8450f-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="8450f-1537">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1537">tipo della scheda</span></span> 
- <span data-ttu-id="8450f-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="8450f-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="8450f-1539">scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1539">scheda</span></span> 
- <span data-ttu-id="8450f-1540">v pay</span><span class="sxs-lookup"><span data-stu-id="8450f-1540">v pay</span></span> 
- <span data-ttu-id="8450f-1541">v-pay</span><span class="sxs-lookup"><span data-stu-id="8450f-1541">v-pay</span></span> 
- <span data-ttu-id="8450f-1542">esempio</span><span class="sxs-lookup"><span data-stu-id="8450f-1542">visa</span></span> 
- <span data-ttu-id="8450f-1543">visa plus</span><span class="sxs-lookup"><span data-stu-id="8450f-1543">visa plus</span></span> 
- <span data-ttu-id="8450f-1544">visa electron</span><span class="sxs-lookup"><span data-stu-id="8450f-1544">visa electron</span></span> 
- <span data-ttu-id="8450f-1545">visto</span><span class="sxs-lookup"><span data-stu-id="8450f-1545">visto</span></span> 
- <span data-ttu-id="8450f-1546">Visum</span><span class="sxs-lookup"><span data-stu-id="8450f-1546">visum</span></span> 
- <span data-ttu-id="8450f-1547">vpay</span><span class="sxs-lookup"><span data-stu-id="8450f-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="8450f-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8450f-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="8450f-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-1549">card identification number</span></span>
- <span data-ttu-id="8450f-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="8450f-1550">card verification</span></span> 
- <span data-ttu-id="8450f-1551">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="8450f-1551">cardi la verifica</span></span> 
- <span data-ttu-id="8450f-1552">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-1552">cid</span></span> 
- <span data-ttu-id="8450f-1553">cod seg</span><span class="sxs-lookup"><span data-stu-id="8450f-1553">cod seg</span></span> 
- <span data-ttu-id="8450f-1554">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1554">cod seguranca</span></span> 
- <span data-ttu-id="8450f-1555">cod segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1555">cod segurança</span></span> 
- <span data-ttu-id="8450f-1556">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1556">cod sicurezza</span></span> 
- <span data-ttu-id="8450f-1557">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1557">cod.</span></span> <span data-ttu-id="8450f-1558">SEG</span><span class="sxs-lookup"><span data-stu-id="8450f-1558">seg</span></span> 
- <span data-ttu-id="8450f-1559">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1559">cod.</span></span> <span data-ttu-id="8450f-1560">seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1560">seguranca</span></span> 
- <span data-ttu-id="8450f-1561">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1561">cod.</span></span> <span data-ttu-id="8450f-1562">Segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1562">segurança</span></span> 
- <span data-ttu-id="8450f-1563">Cod.</span><span class="sxs-lookup"><span data-stu-id="8450f-1563">cod.</span></span> <span data-ttu-id="8450f-1564">sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1564">sicurezza</span></span> 
- <span data-ttu-id="8450f-1565">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="8450f-1566">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="8450f-1566">codice di verifica</span></span> 
- <span data-ttu-id="8450f-1567">Codigo</span><span class="sxs-lookup"><span data-stu-id="8450f-1567">codigo</span></span> 
- <span data-ttu-id="8450f-1568">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="8450f-1569">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1569">codigo de segurança</span></span> 
- <span data-ttu-id="8450f-1570">crittogramma</span><span class="sxs-lookup"><span data-stu-id="8450f-1570">crittogramma</span></span> 
- <span data-ttu-id="8450f-1571">crittogramma</span><span class="sxs-lookup"><span data-stu-id="8450f-1571">cryptogram</span></span> 
- <span data-ttu-id="8450f-1572">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="8450f-1572">cryptogramme</span></span> 
- <span data-ttu-id="8450f-1573">CV2</span><span class="sxs-lookup"><span data-stu-id="8450f-1573">cv2</span></span> 
- <span data-ttu-id="8450f-1574">CVC</span><span class="sxs-lookup"><span data-stu-id="8450f-1574">cvc</span></span> 
- <span data-ttu-id="8450f-1575">CVC2</span><span class="sxs-lookup"><span data-stu-id="8450f-1575">cvc2</span></span> 
- <span data-ttu-id="8450f-1576">CVN</span><span class="sxs-lookup"><span data-stu-id="8450f-1576">cvn</span></span> 
- <span data-ttu-id="8450f-1577">CVV</span><span class="sxs-lookup"><span data-stu-id="8450f-1577">cvv</span></span> 
- <span data-ttu-id="8450f-1578">CVV2</span><span class="sxs-lookup"><span data-stu-id="8450f-1578">cvv2</span></span> 
- <span data-ttu-id="8450f-1579">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1579">cód seguranca</span></span> 
- <span data-ttu-id="8450f-1580">cód segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1580">cód segurança</span></span> 
- <span data-ttu-id="8450f-1581">cód.</span><span class="sxs-lookup"><span data-stu-id="8450f-1581">cód.</span></span> <span data-ttu-id="8450f-1582">seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1582">seguranca</span></span> 
- <span data-ttu-id="8450f-1583">cód.</span><span class="sxs-lookup"><span data-stu-id="8450f-1583">cód.</span></span> <span data-ttu-id="8450f-1584">Segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1584">segurança</span></span> 
- <span data-ttu-id="8450f-1585">Código</span><span class="sxs-lookup"><span data-stu-id="8450f-1585">código</span></span> 
- <span data-ttu-id="8450f-1586">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="8450f-1586">código de seguranca</span></span> 
- <span data-ttu-id="8450f-1587">código de segurança</span><span class="sxs-lookup"><span data-stu-id="8450f-1587">código de segurança</span></span> 
- <span data-ttu-id="8450f-1588">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="8450f-1588">de kaart controle</span></span> 
- <span data-ttu-id="8450f-1589">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="8450f-1589">geeft nr uit</span></span> 
- <span data-ttu-id="8450f-1590">issue no</span><span class="sxs-lookup"><span data-stu-id="8450f-1590">issue no</span></span> 
- <span data-ttu-id="8450f-1591">issue number</span><span class="sxs-lookup"><span data-stu-id="8450f-1591">issue number</span></span> 
- <span data-ttu-id="8450f-1592">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="8450f-1593">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="8450f-1594">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="8450f-1595">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="8450f-1595">kwestieaantal</span></span> 
- <span data-ttu-id="8450f-1596">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1596">no.</span></span> <span data-ttu-id="8450f-1597">Dell'Edizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1597">dell'edizione</span></span> 
- <span data-ttu-id="8450f-1598">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1598">no.</span></span> <span data-ttu-id="8450f-1599">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1599">di sicurezza</span></span> 
- <span data-ttu-id="8450f-1600">numero de securite</span><span class="sxs-lookup"><span data-stu-id="8450f-1600">numero de securite</span></span> 
- <span data-ttu-id="8450f-1601">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="8450f-1601">numero de verificacao</span></span> 
- <span data-ttu-id="8450f-1602">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="8450f-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="8450f-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="8450f-1604">scheda</span><span class="sxs-lookup"><span data-stu-id="8450f-1604">scheda</span></span> 
- <span data-ttu-id="8450f-1605">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="8450f-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="8450f-1606">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="8450f-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="8450f-1607">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="8450f-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="8450f-1608">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8450f-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="8450f-1609">número de verificação</span><span class="sxs-lookup"><span data-stu-id="8450f-1609">número de verificação</span></span> 
- <span data-ttu-id="8450f-1610">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="8450f-1610">perno il blocco</span></span> 
- <span data-ttu-id="8450f-1611">pin block</span><span class="sxs-lookup"><span data-stu-id="8450f-1611">pin block</span></span> 
- <span data-ttu-id="8450f-1612">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="8450f-1612">prufziffer</span></span> 
- <span data-ttu-id="8450f-1613">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="8450f-1613">prüfziffer</span></span> 
- <span data-ttu-id="8450f-1614">security code</span><span class="sxs-lookup"><span data-stu-id="8450f-1614">security code</span></span> 
- <span data-ttu-id="8450f-1615">security no</span><span class="sxs-lookup"><span data-stu-id="8450f-1615">security no</span></span> 
- <span data-ttu-id="8450f-1616">security number</span><span class="sxs-lookup"><span data-stu-id="8450f-1616">security number</span></span> 
- <span data-ttu-id="8450f-1617">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="8450f-1617">sicherheits kode</span></span> 
- <span data-ttu-id="8450f-1618">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="8450f-1618">sicherheitscode</span></span> 
- <span data-ttu-id="8450f-1619">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="8450f-1620">speldblok</span><span class="sxs-lookup"><span data-stu-id="8450f-1620">speldblok</span></span> 
- <span data-ttu-id="8450f-1621">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1621">veiligheid nr</span></span> 
- <span data-ttu-id="8450f-1622">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="8450f-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="8450f-1623">Veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="8450f-1623">veiligheidscode</span></span> 
- <span data-ttu-id="8450f-1624">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="8450f-1625">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="8450f-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="8450f-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="8450f-1627">Ablauf</span><span class="sxs-lookup"><span data-stu-id="8450f-1627">ablauf</span></span> 
- <span data-ttu-id="8450f-1628">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="8450f-1628">data de expiracao</span></span> 
- <span data-ttu-id="8450f-1629">data de expiração</span><span class="sxs-lookup"><span data-stu-id="8450f-1629">data de expiração</span></span> 
- <span data-ttu-id="8450f-1630">data del exp</span><span class="sxs-lookup"><span data-stu-id="8450f-1630">data del exp</span></span> 
- <span data-ttu-id="8450f-1631">data di exp</span><span class="sxs-lookup"><span data-stu-id="8450f-1631">data di exp</span></span> 
- <span data-ttu-id="8450f-1632">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1632">data di scadenza</span></span> 
- <span data-ttu-id="8450f-1633">data em que expira</span><span class="sxs-lookup"><span data-stu-id="8450f-1633">data em que expira</span></span> 
- <span data-ttu-id="8450f-1634">data scad</span><span class="sxs-lookup"><span data-stu-id="8450f-1634">data scad</span></span> 
- <span data-ttu-id="8450f-1635">data scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1635">data scadenza</span></span> 
- <span data-ttu-id="8450f-1636">date de validité</span><span class="sxs-lookup"><span data-stu-id="8450f-1636">date de validité</span></span> 
- <span data-ttu-id="8450f-1637">datum afloop</span><span class="sxs-lookup"><span data-stu-id="8450f-1637">datum afloop</span></span> 
- <span data-ttu-id="8450f-1638">datum van exp</span><span class="sxs-lookup"><span data-stu-id="8450f-1638">datum van exp</span></span> 
- <span data-ttu-id="8450f-1639">de afloop</span><span class="sxs-lookup"><span data-stu-id="8450f-1639">de afloop</span></span> 
- <span data-ttu-id="8450f-1640">espira</span><span class="sxs-lookup"><span data-stu-id="8450f-1640">espira</span></span> 
- <span data-ttu-id="8450f-1641">espira</span><span class="sxs-lookup"><span data-stu-id="8450f-1641">espira</span></span> 
- <span data-ttu-id="8450f-1642">exp date</span><span class="sxs-lookup"><span data-stu-id="8450f-1642">exp date</span></span> 
- <span data-ttu-id="8450f-1643">exp datum</span><span class="sxs-lookup"><span data-stu-id="8450f-1643">exp datum</span></span> 
- <span data-ttu-id="8450f-1644">scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1644">expiration</span></span> 
- <span data-ttu-id="8450f-1645">scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1645">expire</span></span> 
- <span data-ttu-id="8450f-1646">scade</span><span class="sxs-lookup"><span data-stu-id="8450f-1646">expires</span></span> 
- <span data-ttu-id="8450f-1647">scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1647">expiry</span></span> 
- <span data-ttu-id="8450f-1648">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="8450f-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="8450f-1649">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="8450f-1649">fecha de venc</span></span> 
- <span data-ttu-id="8450f-1650">gultig bis</span><span class="sxs-lookup"><span data-stu-id="8450f-1650">gultig bis</span></span> 
- <span data-ttu-id="8450f-1651">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="8450f-1652">gültig bis</span><span class="sxs-lookup"><span data-stu-id="8450f-1652">gültig bis</span></span> 
- <span data-ttu-id="8450f-1653">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="8450f-1654">la scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1654">la scadenza</span></span> 
- <span data-ttu-id="8450f-1655">scadenza</span><span class="sxs-lookup"><span data-stu-id="8450f-1655">scadenza</span></span> 
- <span data-ttu-id="8450f-1656">valable</span><span class="sxs-lookup"><span data-stu-id="8450f-1656">valable</span></span> 
- <span data-ttu-id="8450f-1657">validade</span><span class="sxs-lookup"><span data-stu-id="8450f-1657">validade</span></span> 
- <span data-ttu-id="8450f-1658">valido hasta</span><span class="sxs-lookup"><span data-stu-id="8450f-1658">valido hasta</span></span> 
- <span data-ttu-id="8450f-1659">Valor</span><span class="sxs-lookup"><span data-stu-id="8450f-1659">valor</span></span> 
- <span data-ttu-id="8450f-1660">venc</span><span class="sxs-lookup"><span data-stu-id="8450f-1660">venc</span></span> 
- <span data-ttu-id="8450f-1661">vencimento</span><span class="sxs-lookup"><span data-stu-id="8450f-1661">vencimento</span></span> 
- <span data-ttu-id="8450f-1662">vencimiento</span><span class="sxs-lookup"><span data-stu-id="8450f-1662">vencimiento</span></span> 
- <span data-ttu-id="8450f-1663">verloopt</span><span class="sxs-lookup"><span data-stu-id="8450f-1663">verloopt</span></span> 
- <span data-ttu-id="8450f-1664">vervaldag</span><span class="sxs-lookup"><span data-stu-id="8450f-1664">vervaldag</span></span> 
- <span data-ttu-id="8450f-1665">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1665">vervaldatum</span></span> 
- <span data-ttu-id="8450f-1666">VTO</span><span class="sxs-lookup"><span data-stu-id="8450f-1666">vto</span></span> 
- <span data-ttu-id="8450f-1667">válido hasta</span><span class="sxs-lookup"><span data-stu-id="8450f-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="8450f-1668">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="8450f-1668">EU Driver's License Number</span></span>

<span data-ttu-id="8450f-1669">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="8450f-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="8450f-1670">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="8450f-1670">EU National Identification Number</span></span>

<span data-ttu-id="8450f-1671">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="8450f-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="8450f-1672">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="8450f-1672">EU Passport Number</span></span>

<span data-ttu-id="8450f-1673">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="8450f-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="8450f-1674">Codice di preVidenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="8450f-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="8450f-1675">Per ulteriori informazioni, vedere [codice di PrevideNza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="8450f-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="8450f-1676">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="8450f-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="8450f-1677">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="8450f-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="8450f-1678">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="8450f-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1679">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1679">Format</span></span>

<span data-ttu-id="8450f-1680">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1681">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1681">Pattern</span></span>

<span data-ttu-id="8450f-1682">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8450f-1683">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="8450f-1684">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="8450f-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="8450f-1685">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="8450f-1686">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1687">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1687">Checksum</span></span>

<span data-ttu-id="8450f-1688">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1689">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1689">Definition</span></span>

<span data-ttu-id="8450f-1690">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1691">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1692">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="8450f-1693">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1694">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1694">Keywords</span></span>

- <span data-ttu-id="8450f-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="8450f-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="8450f-1696">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="8450f-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="8450f-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="8450f-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="8450f-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="8450f-1698">Personbeteckning</span></span>
- <span data-ttu-id="8450f-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="8450f-1700">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-1700">Finland Passport Number</span></span>

<span data-ttu-id="8450f-1701">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1701">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-1702">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-1702">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="8450f-1703"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="8450f-1703"></span></span>
<span data-ttu-id="8450f-1704">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="8450f-1704">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="8450f-1705">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1706">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1706">Format</span></span>

<span data-ttu-id="8450f-1707">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1708">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1708">Pattern</span></span>

<span data-ttu-id="8450f-1709">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="8450f-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1710">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1710">Checksum</span></span>

<span data-ttu-id="8450f-1711">No</span><span class="sxs-lookup"><span data-stu-id="8450f-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1712">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1712">Definition</span></span>

<span data-ttu-id="8450f-1713">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1714">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1715">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="8450f-1716">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="8450f-1717">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-1717">The function Func_eu_date finds a date in the right date format.</span></span>

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1718">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="8450f-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8450f-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="8450f-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1720">drivers licence</span></span>
- <span data-ttu-id="8450f-1721">drivers license</span><span class="sxs-lookup"><span data-stu-id="8450f-1721">drivers license</span></span>
- <span data-ttu-id="8450f-1722">driving licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1722">driving licence</span></span>
- <span data-ttu-id="8450f-1723">driving license</span><span class="sxs-lookup"><span data-stu-id="8450f-1723">driving license</span></span>
- <span data-ttu-id="8450f-1724">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8450f-1724">permis de conduire</span></span>
- <span data-ttu-id="8450f-1725">licence number</span><span class="sxs-lookup"><span data-stu-id="8450f-1725">licence number</span></span>
- <span data-ttu-id="8450f-1726">license number</span><span class="sxs-lookup"><span data-stu-id="8450f-1726">license number</span></span>
- <span data-ttu-id="8450f-1727">licence numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1727">licence numbers</span></span>
- <span data-ttu-id="8450f-1728">license numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="8450f-1729">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="8450f-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1730">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1730">Format</span></span>

<span data-ttu-id="8450f-1731">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1732">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1732">Pattern</span></span>

<span data-ttu-id="8450f-1733">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1734">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1734">Checksum</span></span>

<span data-ttu-id="8450f-1735">No</span><span class="sxs-lookup"><span data-stu-id="8450f-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1736">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1736">Definition</span></span>

<span data-ttu-id="8450f-1737">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1738">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1739">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1739">Keywords</span></span>

<span data-ttu-id="8450f-1740">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8450f-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="8450f-1741">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1742">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1742">Format</span></span>

<span data-ttu-id="8450f-1743">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1744">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1744">Pattern</span></span>

<span data-ttu-id="8450f-1745">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="8450f-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="8450f-1746">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1746">Two digits</span></span> 
- <span data-ttu-id="8450f-1747">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-1748">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1749">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1749">Checksum</span></span>

<span data-ttu-id="8450f-1750">No</span><span class="sxs-lookup"><span data-stu-id="8450f-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1751">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1751">Definition</span></span>

<span data-ttu-id="8450f-1752">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1753">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1754">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1755">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="8450f-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-1756">Keyword_passport</span></span>

- <span data-ttu-id="8450f-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8450f-1757">Passport Number</span></span>
- <span data-ttu-id="8450f-1758">Passport No</span><span class="sxs-lookup"><span data-stu-id="8450f-1758">Passport No</span></span>
- <span data-ttu-id="8450f-1759">Passport#</span><span class="sxs-lookup"><span data-stu-id="8450f-1759">Passport #</span></span>
- <span data-ttu-id="8450f-1760">Passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-1760">Passport#</span></span>
- <span data-ttu-id="8450f-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="8450f-1761">PassportID</span></span>
- <span data-ttu-id="8450f-1762">Passportno</span><span class="sxs-lookup"><span data-stu-id="8450f-1762">Passportno</span></span>
- <span data-ttu-id="8450f-1763">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-1763">passportnumber</span></span>
- <span data-ttu-id="8450f-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-1764">パスポート</span></span>
- <span data-ttu-id="8450f-1765">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-1765">パスポート番号</span></span>
- <span data-ttu-id="8450f-1766">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-1766">パスポートのNum</span></span>
- <span data-ttu-id="8450f-1767">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="8450f-1767">パスポート ＃</span></span> 
- <span data-ttu-id="8450f-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-1768">Numéro de passeport</span></span>
- <span data-ttu-id="8450f-1769">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8450f-1769">Passeport n °</span></span>
- <span data-ttu-id="8450f-1770">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8450f-1770">Passeport Non</span></span>
- <span data-ttu-id="8450f-1771">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8450f-1771">Passeport #</span></span>
- <span data-ttu-id="8450f-1772">Passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-1772">Passeport#</span></span>
- <span data-ttu-id="8450f-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8450f-1773">PasseportNon</span></span>
- <span data-ttu-id="8450f-1774">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8450f-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="8450f-1775">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="8450f-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1776">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1776">Format</span></span>

<span data-ttu-id="8450f-1777">15 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1778">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1778">Pattern</span></span>

<span data-ttu-id="8450f-1779">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="8450f-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="8450f-1780">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="8450f-1781">oppure</span><span class="sxs-lookup"><span data-stu-id="8450f-1781">or</span></span>
- <span data-ttu-id="8450f-1782">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1783">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1783">Checksum</span></span>

<span data-ttu-id="8450f-1784">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1785">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1785">Definition</span></span>

<span data-ttu-id="8450f-1786">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1787">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1788">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="8450f-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="8450f-1789">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1789">The checksum passes.</span></span>

<span data-ttu-id="8450f-1790">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1791">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1792">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="8450f-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="8450f-1793">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1793">The checksum passes.</span></span>

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1794">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="8450f-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="8450f-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="8450f-1796">INSEE</span><span class="sxs-lookup"><span data-stu-id="8450f-1796">insee</span></span>
- <span data-ttu-id="8450f-1797">securité sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-1797">securité sociale</span></span>
- <span data-ttu-id="8450f-1798">securite sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-1798">securite sociale</span></span>
- <span data-ttu-id="8450f-1799">national id</span><span class="sxs-lookup"><span data-stu-id="8450f-1799">national id</span></span>
- <span data-ttu-id="8450f-1800">national identification</span><span class="sxs-lookup"><span data-stu-id="8450f-1800">national identification</span></span>
- <span data-ttu-id="8450f-1801">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="8450f-1801">numéro d'identité</span></span>
- <span data-ttu-id="8450f-1802">no d'identité</span><span class="sxs-lookup"><span data-stu-id="8450f-1802">no d'identité</span></span>
- <span data-ttu-id="8450f-1803">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1803">no.</span></span> <span data-ttu-id="8450f-1804">d'identité</span><span class="sxs-lookup"><span data-stu-id="8450f-1804">d'identité</span></span>
- <span data-ttu-id="8450f-1805">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="8450f-1805">numero d'identite</span></span>
- <span data-ttu-id="8450f-1806">no d'identite</span><span class="sxs-lookup"><span data-stu-id="8450f-1806">no d'identite</span></span>
- <span data-ttu-id="8450f-1807">No.</span><span class="sxs-lookup"><span data-stu-id="8450f-1807">no.</span></span> <span data-ttu-id="8450f-1808">d'identite</span><span class="sxs-lookup"><span data-stu-id="8450f-1808">d'identite</span></span>
- <span data-ttu-id="8450f-1809">social security number</span><span class="sxs-lookup"><span data-stu-id="8450f-1809">social security number</span></span>
- <span data-ttu-id="8450f-1810">social security code</span><span class="sxs-lookup"><span data-stu-id="8450f-1810">social security code</span></span>
- <span data-ttu-id="8450f-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="8450f-1811">social insurance number</span></span>
- <span data-ttu-id="8450f-1812">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="8450f-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="8450f-1813">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="8450f-1813">d'identité nationale</span></span>
- <span data-ttu-id="8450f-1814">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="8450f-1815">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="8450f-1816">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="8450f-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="8450f-1817">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="8450f-1817">numéro de sécu</span></span>
- <span data-ttu-id="8450f-1818">code sécu</span><span class="sxs-lookup"><span data-stu-id="8450f-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="8450f-1819">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1820">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1820">Format</span></span>

<span data-ttu-id="8450f-1821">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1822">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1822">Pattern</span></span>

<span data-ttu-id="8450f-1823">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="8450f-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="8450f-1824">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="8450f-1824">A digit or letter</span></span> 
- <span data-ttu-id="8450f-1825">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1825">Two digits</span></span> 
- <span data-ttu-id="8450f-1826">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-1826">Six digits or letters</span></span> 
- <span data-ttu-id="8450f-1827">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-1827">A digit</span></span> 
- <span data-ttu-id="8450f-1828">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="8450f-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1829">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1829">Checksum</span></span>

<span data-ttu-id="8450f-1830">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1831">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1831">Definition</span></span>

<span data-ttu-id="8450f-1832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1833">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1834">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="8450f-1835">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="8450f-1836">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="8450f-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="8450f-1837">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="8450f-1838">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1838">The checksum passes.</span></span>

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1839">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="8450f-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8450f-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="8450f-1841">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1841">Führerschein</span></span>
- <span data-ttu-id="8450f-1842">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1842">Fuhrerschein</span></span>
- <span data-ttu-id="8450f-1843">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1843">Fuehrerschein</span></span>
- <span data-ttu-id="8450f-1844">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="8450f-1845">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="8450f-1846">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="8450f-1847">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="8450f-1847">Führerschein-</span></span> 
- <span data-ttu-id="8450f-1848">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="8450f-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="8450f-1849">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="8450f-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="8450f-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="8450f-1851">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="8450f-1852">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="8450f-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="8450f-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="8450f-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="8450f-1856">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="8450f-1857">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="8450f-1858">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="8450f-1859">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="8450f-1860">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="8450f-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="8450f-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="8450f-1863">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="8450f-1864">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="8450f-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="8450f-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8450f-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8450f-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="8450f-1868">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="8450f-1869">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="8450f-1870">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="8450f-1871">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="8450f-1872">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="8450f-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="8450f-1874">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-1874">DL</span></span> 
- <span data-ttu-id="8450f-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-1875">DLS</span></span>
- <span data-ttu-id="8450f-1876">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-1876">Driv Lic</span></span> 
- <span data-ttu-id="8450f-1877">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="8450f-1877">Driv Licen</span></span> 
- <span data-ttu-id="8450f-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="8450f-1878">Driv License</span></span>
- <span data-ttu-id="8450f-1879">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-1879">Driv Licenses</span></span> 
- <span data-ttu-id="8450f-1880">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1880">Driv Licence</span></span> 
- <span data-ttu-id="8450f-1881">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-1881">Driv Licences</span></span> 
- <span data-ttu-id="8450f-1882">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-1882">Driv Lic</span></span> 
- <span data-ttu-id="8450f-1883">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="8450f-1883">Driver Licen</span></span> 
- <span data-ttu-id="8450f-1884">Driver License</span><span class="sxs-lookup"><span data-stu-id="8450f-1884">Driver License</span></span> 
- <span data-ttu-id="8450f-1885">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-1885">Driver Licenses</span></span> 
- <span data-ttu-id="8450f-1886">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1886">Driver Licence</span></span> 
- <span data-ttu-id="8450f-1887">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-1887">Driver Licences</span></span> 
- <span data-ttu-id="8450f-1888">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-1888">Drivers Lic</span></span> 
- <span data-ttu-id="8450f-1889">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="8450f-1889">Drivers Licen</span></span> 
- <span data-ttu-id="8450f-1890">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8450f-1890">Drivers License</span></span> 
- <span data-ttu-id="8450f-1891">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="8450f-1892">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1892">Drivers Licence</span></span> 
- <span data-ttu-id="8450f-1893">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-1893">Drivers Licences</span></span> 
- <span data-ttu-id="8450f-1894">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-1894">Driver's Lic</span></span> 
- <span data-ttu-id="8450f-1895">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="8450f-1895">Driver's Licen</span></span> 
- <span data-ttu-id="8450f-1896">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8450f-1896">Driver's License</span></span> 
- <span data-ttu-id="8450f-1897">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="8450f-1898">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1898">Driver's Licence</span></span> 
- <span data-ttu-id="8450f-1899">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-1899">Driver's Licences</span></span> 
- <span data-ttu-id="8450f-1900">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-1900">Driving Lic</span></span> 
- <span data-ttu-id="8450f-1901">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="8450f-1901">Driving Licen</span></span> 
- <span data-ttu-id="8450f-1902">Driving License</span><span class="sxs-lookup"><span data-stu-id="8450f-1902">Driving License</span></span> 
- <span data-ttu-id="8450f-1903">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-1903">Driving Licenses</span></span> 
- <span data-ttu-id="8450f-1904">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="8450f-1904">Driving Licence</span></span> 
- <span data-ttu-id="8450f-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="8450f-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="8450f-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="8450f-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="8450f-1907">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="8450f-1908">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1909">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="8450f-1910">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1910">No-Führerschein</span></span> 
- <span data-ttu-id="8450f-1911">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1912">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="8450f-1913">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1913">N-Führerschein</span></span> 
- <span data-ttu-id="8450f-1914">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="8450f-1916">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="8450f-1917">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1918">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="8450f-1919">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1919">No-Führerschein</span></span> 
- <span data-ttu-id="8450f-1920">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1921">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="8450f-1922">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1922">N-Führerschein</span></span> 
- <span data-ttu-id="8450f-1923">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="8450f-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="8450f-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="8450f-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8450f-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="8450f-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="8450f-1927">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="8450f-1927">ausstellungsort</span></span>
- <span data-ttu-id="8450f-1928">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="8450f-1928">ausstellende behöde</span></span>
- <span data-ttu-id="8450f-1929">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="8450f-1929">ausstellende behorde</span></span>
- <span data-ttu-id="8450f-1930">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="8450f-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="8450f-1931">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1932">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1932">Format</span></span>

<span data-ttu-id="8450f-1933">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1934">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1934">Pattern</span></span>

<span data-ttu-id="8450f-1935">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="8450f-1936">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="8450f-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="8450f-1937">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1937">Three digits</span></span> 
- <span data-ttu-id="8450f-1938">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="8450f-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="8450f-1939">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1940">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1940">Checksum</span></span>

<span data-ttu-id="8450f-1941">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1942">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1942">Definition</span></span>

<span data-ttu-id="8450f-1943">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1944">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1945">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="8450f-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="8450f-1946">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1946">The checksum passes.</span></span>

<span data-ttu-id="8450f-1947">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1948">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1949">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="8450f-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="8450f-1950">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-1950">The checksum passes.</span></span>

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1951">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="8450f-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="8450f-1953">Reisepass</span><span class="sxs-lookup"><span data-stu-id="8450f-1953">reisepass</span></span>
- <span data-ttu-id="8450f-1954">reisepasse</span><span class="sxs-lookup"><span data-stu-id="8450f-1954">reisepasse</span></span>
- <span data-ttu-id="8450f-1955">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1955">reisepassnummer</span></span>
- <span data-ttu-id="8450f-1956">passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-1956">passport</span></span>
- <span data-ttu-id="8450f-1957">passaporti</span><span class="sxs-lookup"><span data-stu-id="8450f-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="8450f-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="8450f-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="8450f-1959">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1959">geburtsdatum</span></span>
- <span data-ttu-id="8450f-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="8450f-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="8450f-1961">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="8450f-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="8450f-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="8450f-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="8450f-1963">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="8450f-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="8450f-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="8450f-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="8450f-1965">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="8450f-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="8450f-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="8450f-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="8450f-1967">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="8450f-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="8450f-1968">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1969">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1969">Format</span></span>

<span data-ttu-id="8450f-1970">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="8450f-1971">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1972">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1972">Pattern</span></span>

<span data-ttu-id="8450f-1973">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="8450f-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="8450f-1974">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-1975">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1975">Eight digits</span></span>

<span data-ttu-id="8450f-1976">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="8450f-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="8450f-1977">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-1978">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-1978">Checksum</span></span>

<span data-ttu-id="8450f-1979">No</span><span class="sxs-lookup"><span data-stu-id="8450f-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-1980">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-1980">Definition</span></span>

<span data-ttu-id="8450f-1981">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-1982">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-1983">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-1984">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="8450f-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="8450f-1986">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-1986">Identity Card</span></span>
- <span data-ttu-id="8450f-1987">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-1987">ID</span></span>
- <span data-ttu-id="8450f-1988">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-1988">Identification</span></span>
- <span data-ttu-id="8450f-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="8450f-1989">Personalausweis</span></span>
- <span data-ttu-id="8450f-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="8450f-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="8450f-1991">Ausweis</span></span>
- <span data-ttu-id="8450f-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="8450f-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="8450f-1993">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="8450f-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="8450f-1994">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-1994">Format</span></span>

<span data-ttu-id="8450f-1995">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-1996">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-1996">Pattern</span></span>

<span data-ttu-id="8450f-1997">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="8450f-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="8450f-1998">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="8450f-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="8450f-1999">Un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-1999">A dash</span></span> 
- <span data-ttu-id="8450f-2000">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2000">Six digits</span></span>

<span data-ttu-id="8450f-2001">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="8450f-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="8450f-2002">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="8450f-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="8450f-2003">Un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-2003">A dash</span></span> 
- <span data-ttu-id="8450f-2004">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2005">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2005">Checksum</span></span>

<span data-ttu-id="8450f-2006">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2007">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2007">Definition</span></span>

<span data-ttu-id="8450f-2008">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2009">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2010">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2011">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="8450f-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="8450f-2013">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="8450f-2013">Greek identity Card</span></span>
- <span data-ttu-id="8450f-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="8450f-2014">Tautotita</span></span>
- <span data-ttu-id="8450f-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="8450f-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="8450f-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="8450f-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="8450f-2017">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="8450f-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2018">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2018">Format</span></span>

<span data-ttu-id="8450f-2019">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="8450f-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2020">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2020">Pattern</span></span>

<span data-ttu-id="8450f-2021">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="8450f-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="8450f-2022">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2023">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2023">Six digits</span></span> 
- <span data-ttu-id="8450f-2024">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="8450f-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2025">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2025">Checksum</span></span>

<span data-ttu-id="8450f-2026">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2027">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2027">Definition</span></span>

<span data-ttu-id="8450f-2028">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2029">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2030">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="8450f-2031">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2031">The checksum passes.</span></span>

<span data-ttu-id="8450f-2032">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2033">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2034">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2034">The checksum passes.</span></span>

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2035">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="8450f-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="8450f-2037">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="8450f-2037">hong kong identity card</span></span>
- <span data-ttu-id="8450f-2038">HKIDC</span><span class="sxs-lookup"><span data-stu-id="8450f-2038">HKIDC</span></span>
- <span data-ttu-id="8450f-2039">id card</span><span class="sxs-lookup"><span data-stu-id="8450f-2039">id card</span></span>
- <span data-ttu-id="8450f-2040">carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2040">identity card</span></span>
- <span data-ttu-id="8450f-2041">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="8450f-2041">hk identity card</span></span>
- <span data-ttu-id="8450f-2042">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="8450f-2042">hong kong id</span></span>
- <span data-ttu-id="8450f-2043">香港身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2043">香港身份證</span></span>
- <span data-ttu-id="8450f-2044">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="8450f-2045">身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2045">身份證</span></span>
- <span data-ttu-id="8450f-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2046">身份証</span></span>
- <span data-ttu-id="8450f-2047">身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2047">身分證</span></span>
- <span data-ttu-id="8450f-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2048">身分証</span></span>
- <span data-ttu-id="8450f-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2049">香港身份証</span></span>
- <span data-ttu-id="8450f-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2050">香港身分證</span></span>
- <span data-ttu-id="8450f-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2051">香港身分証</span></span>
- <span data-ttu-id="8450f-2052">香港身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2052">香港身份證</span></span>
- <span data-ttu-id="8450f-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2053">香港居民身份證</span></span>
- <span data-ttu-id="8450f-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2054">香港居民身份証</span></span>
- <span data-ttu-id="8450f-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2055">香港居民身分證</span></span>
- <span data-ttu-id="8450f-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2056">香港居民身分証</span></span>
- <span data-ttu-id="8450f-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="8450f-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="8450f-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="8450f-2060">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="8450f-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="8450f-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="8450f-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="8450f-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="8450f-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="8450f-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="8450f-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="8450f-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="8450f-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="8450f-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="8450f-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="8450f-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="8450f-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="8450f-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="8450f-2073">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2074">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2074">Format</span></span>

<span data-ttu-id="8450f-2075">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2076">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2076">Pattern</span></span>

<span data-ttu-id="8450f-2077">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2077">10 letters or digits:</span></span>
- <span data-ttu-id="8450f-2078">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2079">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2079">Four digits</span></span> 
- <span data-ttu-id="8450f-2080">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="8450f-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2081">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2081">Checksum</span></span>

<span data-ttu-id="8450f-2082">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2083">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2083">Definition</span></span>

<span data-ttu-id="8450f-2084">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2085">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2086">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="8450f-2087">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="8450f-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="8450f-2090">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="8450f-2091">PAN</span><span class="sxs-lookup"><span data-stu-id="8450f-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="8450f-2092">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="8450f-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2093">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2093">Format</span></span>

<span data-ttu-id="8450f-2094">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="8450f-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2095">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2095">Pattern</span></span>

<span data-ttu-id="8450f-2096">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2096">12 digits:</span></span>
- <span data-ttu-id="8450f-2097">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2097">Four digits</span></span> 
- <span data-ttu-id="8450f-2098">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="8450f-2098">An optional space or dash</span></span> 
- <span data-ttu-id="8450f-2099">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2099">Four digits</span></span> 
- <span data-ttu-id="8450f-2100">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="8450f-2100">An optional space or dash</span></span> 
- <span data-ttu-id="8450f-2101">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2102">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2102">Checksum</span></span>

<span data-ttu-id="8450f-2103">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2104">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2104">Definition</span></span>

<span data-ttu-id="8450f-2105">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-2106">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="8450f-2106">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="8450f-2107">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2107">The checksum passes.</span></span>
<span data-ttu-id="8450f-2108">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-2109">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2109">The checksum passes.</span></span>
<span data-ttu-id="8450f-2110"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="8450f-2110"></span></span>

### <a name="keywords"></a><span data-ttu-id="8450f-2111">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="8450f-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="8450f-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="8450f-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="8450f-2113">Aadhar</span></span>
- <span data-ttu-id="8450f-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="8450f-2114">Aadhaar</span></span>
- <span data-ttu-id="8450f-2115">UID</span><span class="sxs-lookup"><span data-stu-id="8450f-2115">UID</span></span>
- <span data-ttu-id="8450f-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="8450f-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="8450f-2117">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="8450f-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2118">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2118">Format</span></span>

<span data-ttu-id="8450f-2119">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="8450f-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2120">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2120">Pattern</span></span>

<span data-ttu-id="8450f-2121">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2121">16 digits:</span></span>
- <span data-ttu-id="8450f-2122">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="8450f-2122">Two-digit province code</span></span> 
- <span data-ttu-id="8450f-2123">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="8450f-2123">A period (optional)</span></span> 
- <span data-ttu-id="8450f-2124">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="8450f-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="8450f-2125">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="8450f-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="8450f-2126">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="8450f-2126">A period (optional)</span></span> 
- <span data-ttu-id="8450f-2127">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8450f-2128">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="8450f-2128">A period (optional)</span></span> 
- <span data-ttu-id="8450f-2129">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2130">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2130">Checksum</span></span>

<span data-ttu-id="8450f-2131">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2132">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2132">Definition</span></span>

<span data-ttu-id="8450f-2133">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2134">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2135">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="8450f-2136">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2137">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2138">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="8450f-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="8450f-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="8450f-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="8450f-2140">KTP</span></span>
- <span data-ttu-id="8450f-2141">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="8450f-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="8450f-2142">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="8450f-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="8450f-2143">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2144">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2144">Format</span></span>

<span data-ttu-id="8450f-2145">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="8450f-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2146">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2146">Pattern</span></span>

<span data-ttu-id="8450f-2147">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="8450f-2148">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-2148">Two-letter country code</span></span>
- <span data-ttu-id="8450f-2149">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="8450f-2150">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="8450f-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="8450f-2151">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2151">1-3 letters or digits</span></span>

<span data-ttu-id="8450f-2152">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="8450f-2152">The format for each country is slightly different.</span></span> <span data-ttu-id="8450f-2153">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="8450f-2153">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="8450f-2154">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="8450f-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2155">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2155">Checksum</span></span>

<span data-ttu-id="8450f-2156">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2157">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2157">Definition</span></span>

<span data-ttu-id="8450f-2158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2159">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2160">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2161">Keywords</span></span>

<span data-ttu-id="8450f-2162">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8450f-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="8450f-2163">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="8450f-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2164">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="8450f-2165">IPv4</span><span class="sxs-lookup"><span data-stu-id="8450f-2165">IPv4:</span></span>
<span data-ttu-id="8450f-2166">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="8450f-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="8450f-2167">IPv6</span><span class="sxs-lookup"><span data-stu-id="8450f-2167">IPv6:</span></span>
<span data-ttu-id="8450f-2168">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="8450f-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2169">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2170">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2170">Checksum</span></span>

<span data-ttu-id="8450f-2171">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2172">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2172">Definition</span></span>

<span data-ttu-id="8450f-2173">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2174">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2175">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="8450f-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="8450f-2176">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2177">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2178">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="8450f-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="8450f-2179">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2180">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2181">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="8450f-2181">No keyword from Keyword_ipaddress is found.</span></span>

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2182">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="8450f-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="8450f-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="8450f-2184">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="8450f-2185">ip address</span><span class="sxs-lookup"><span data-stu-id="8450f-2185">ip address</span></span> 
- <span data-ttu-id="8450f-2186">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="8450f-2186">ip addresses</span></span>
- <span data-ttu-id="8450f-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="8450f-2187">internet protocol</span></span>
- <span data-ttu-id="8450f-2188">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="8450f-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="8450f-2189">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8450f-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2190">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2190">Format</span></span>

<span data-ttu-id="8450f-2191">Dizionario</span><span class="sxs-lookup"><span data-stu-id="8450f-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2192">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2192">Pattern</span></span>

<span data-ttu-id="8450f-2193">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2194">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2194">Checksum</span></span>

<span data-ttu-id="8450f-2195">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2196">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2196">Definition</span></span>

<span data-ttu-id="8450f-2197">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2198">Viene trovata una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="8450f-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="8450f-2199">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2199">Keywords</span></span>

<span data-ttu-id="8450f-2200">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_cm, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="8450f-2200">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="8450f-2201">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="8450f-2201">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="8450f-2202">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8450f-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2203">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2203">Format</span></span>

<span data-ttu-id="8450f-2204">Dizionario</span><span class="sxs-lookup"><span data-stu-id="8450f-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2205">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2205">Pattern</span></span>

<span data-ttu-id="8450f-2206">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2207">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2207">Checksum</span></span>

<span data-ttu-id="8450f-2208">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2209">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2209">Definition</span></span>

<span data-ttu-id="8450f-2210">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2211">Viene trovata una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="8450f-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2212">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2212">Keywords</span></span>

<span data-ttu-id="8450f-2213">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_cm, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="8450f-2213">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="8450f-2214">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="8450f-2214">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="8450f-2215">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="8450f-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2216">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2216">Format</span></span>

<span data-ttu-id="8450f-2217">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="8450f-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="8450f-2218">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="8450f-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="8450f-2219">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="8450f-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="8450f-2220">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2221">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2221">Pattern</span></span>

<span data-ttu-id="8450f-2222">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="8450f-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="8450f-2223">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2223">Seven digits</span></span> 
- <span data-ttu-id="8450f-2224">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="8450f-2225">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="8450f-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="8450f-2226">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2226">Seven digits</span></span> 
- <span data-ttu-id="8450f-2227">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="8450f-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="8450f-2228">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2229">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2229">Checksum</span></span>

<span data-ttu-id="8450f-2230">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2231">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2231">Definition</span></span>

<span data-ttu-id="8450f-2232">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2233">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2234">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-2234">One of the following is true:</span></span>
    - <span data-ttu-id="8450f-2235">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="8450f-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="8450f-2236">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="8450f-2237">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2237">The checksum passes.</span></span>

<span data-ttu-id="8450f-2238">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2239">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2240">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2240">The checksum passes.</span></span>

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2241">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="8450f-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="8450f-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="8450f-2243">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="8450f-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="8450f-2244">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="8450f-2244">PPS Number</span></span> 
- <span data-ttu-id="8450f-2245">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="8450f-2245">PPS Num</span></span> 
- <span data-ttu-id="8450f-2246">N° PPS</span><span class="sxs-lookup"><span data-stu-id="8450f-2246">PPS No.</span></span> 
- <span data-ttu-id="8450f-2247">PPS #</span><span class="sxs-lookup"><span data-stu-id="8450f-2247">PPS #</span></span> 
- <span data-ttu-id="8450f-2248">PPS</span><span class="sxs-lookup"><span data-stu-id="8450f-2248">PPS#</span></span> 
- <span data-ttu-id="8450f-2249">PPSN</span><span class="sxs-lookup"><span data-stu-id="8450f-2249">PPSN</span></span> 
- <span data-ttu-id="8450f-2250">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="8450f-2250">Public Services Card</span></span> 
- <span data-ttu-id="8450f-2251">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="8450f-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="8450f-2252">Uimh.</span><span class="sxs-lookup"><span data-stu-id="8450f-2252">Uimh.</span></span> <span data-ttu-id="8450f-2253">PSP</span><span class="sxs-lookup"><span data-stu-id="8450f-2253">PSP</span></span> 
- <span data-ttu-id="8450f-2254">PSP</span><span class="sxs-lookup"><span data-stu-id="8450f-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="8450f-2255">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8450f-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2256">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2256">Format</span></span>

<span data-ttu-id="8450f-2257">13 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2258">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2258">Pattern</span></span>

<span data-ttu-id="8450f-2259">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-2259">Formatted:</span></span>
- <span data-ttu-id="8450f-2260">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2260">Two digits</span></span> 
- <span data-ttu-id="8450f-2261">Un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-2261">A dash</span></span> 
- <span data-ttu-id="8450f-2262">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2262">Three digits</span></span> 
- <span data-ttu-id="8450f-2263">Un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-2263">A dash</span></span> 
- <span data-ttu-id="8450f-2264">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2264">Eight digits</span></span>

<span data-ttu-id="8450f-2265">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-2265">Unformatted:</span></span>
- <span data-ttu-id="8450f-2266">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2267">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2267">Checksum</span></span>

<span data-ttu-id="8450f-2268">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2269">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2269">Definition</span></span>

<span data-ttu-id="8450f-2270">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2271">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2272">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2273">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="8450f-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="8450f-2275">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2275">Bank Account Number</span></span> 
- <span data-ttu-id="8450f-2276">Bank Account</span><span class="sxs-lookup"><span data-stu-id="8450f-2276">Bank Account</span></span> 
- <span data-ttu-id="8450f-2277">Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2277">Account Number</span></span> 
- <span data-ttu-id="8450f-2278">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="8450f-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="8450f-2279">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="8450f-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2280">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2280">Format</span></span>

<span data-ttu-id="8450f-2281">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2282">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2282">Pattern</span></span>

<span data-ttu-id="8450f-2283">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2284">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2284">Checksum</span></span>

<span data-ttu-id="8450f-2285">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2286">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2286">Definition</span></span>

<span data-ttu-id="8450f-2287">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2288">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2289">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="8450f-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="8450f-2290">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2290">The checksum passes.</span></span>

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2291">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="8450f-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="8450f-2293">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="8450f-2293">מספר זהות</span></span> 
- <span data-ttu-id="8450f-2294">National ID Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="8450f-2295">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2296">Format</span></span>

<span data-ttu-id="8450f-2297">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2298">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2298">Pattern</span></span>

- <span data-ttu-id="8450f-2299">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="8450f-2300">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2301">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2302">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="8450f-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="8450f-2303">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2304">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2304">Checksum</span></span>

<span data-ttu-id="8450f-2305">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2306">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2306">Definition</span></span>

<span data-ttu-id="8450f-2307">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2308">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2309">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2310">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="8450f-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="8450f-2312">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="8450f-2313">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="8450f-2314">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8450f-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2315">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2315">Format</span></span>

<span data-ttu-id="8450f-2316">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2317">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2317">Pattern</span></span>

<span data-ttu-id="8450f-2318">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="8450f-2318">Bank account number:</span></span>
- <span data-ttu-id="8450f-2319">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2319">Seven or eight digits</span></span>
- <span data-ttu-id="8450f-2320">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="8450f-2320">Bank account branch code:</span></span>
- <span data-ttu-id="8450f-2321">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2321">Four digits</span></span> 
- <span data-ttu-id="8450f-2322">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="8450f-2323">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2323">Three digits</span></span>

<span data-ttu-id="8450f-2324">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2324">Checksum</span></span>

<span data-ttu-id="8450f-2325">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2326">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2326">Definition</span></span>

<span data-ttu-id="8450f-2327">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2328">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2329">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="8450f-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="8450f-2330">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-2330">One of the following is true:</span></span>
- <span data-ttu-id="8450f-2331">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2332">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="8450f-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="8450f-2333">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2334">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2335">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="8450f-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2336">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="8450f-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="8450f-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="8450f-2338">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2338">Checking Account Number</span></span> 
- <span data-ttu-id="8450f-2339">Checking Account</span><span class="sxs-lookup"><span data-stu-id="8450f-2339">Checking Account</span></span> 
- <span data-ttu-id="8450f-2340">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-2340">Checking Account #</span></span> 
- <span data-ttu-id="8450f-2341">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="8450f-2342">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-2342">Checking Acct #</span></span> 
- <span data-ttu-id="8450f-2343">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="8450f-2344">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2344">Checking Account No.</span></span> 
- <span data-ttu-id="8450f-2345">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2345">Bank Account Number</span></span> 
- <span data-ttu-id="8450f-2346">Bank Account</span><span class="sxs-lookup"><span data-stu-id="8450f-2346">Bank Account</span></span> 
- <span data-ttu-id="8450f-2347">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-2347">Bank Account #</span></span> 
- <span data-ttu-id="8450f-2348">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="8450f-2349">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-2349">Bank Acct #</span></span> 
- <span data-ttu-id="8450f-2350">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="8450f-2351">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2351">Bank Account No.</span></span> 
- <span data-ttu-id="8450f-2352">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2352">Savings Account Number</span></span> 
- <span data-ttu-id="8450f-2353">Savings Account</span><span class="sxs-lookup"><span data-stu-id="8450f-2353">Savings Account</span></span> 
- <span data-ttu-id="8450f-2354">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-2354">Savings Account #</span></span> 
- <span data-ttu-id="8450f-2355">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="8450f-2356">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-2356">Savings Acct #</span></span> 
- <span data-ttu-id="8450f-2357">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="8450f-2358">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2358">Savings Account No.</span></span> 
- <span data-ttu-id="8450f-2359">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2359">Debit Account Number</span></span> 
- <span data-ttu-id="8450f-2360">Debit Account</span><span class="sxs-lookup"><span data-stu-id="8450f-2360">Debit Account</span></span> 
- <span data-ttu-id="8450f-2361">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-2361">Debit Account #</span></span> 
- <span data-ttu-id="8450f-2362">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="8450f-2363">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-2363">Debit Acct #</span></span> 
- <span data-ttu-id="8450f-2364">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="8450f-2365">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2365">Debit Account No.</span></span> 
- <span data-ttu-id="8450f-2366">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="8450f-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="8450f-2367">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="8450f-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="8450f-2368">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="8450f-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="8450f-2369">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="8450f-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="8450f-2370">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="8450f-2370">口座番号の確認</span></span> 
- <span data-ttu-id="8450f-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2371">銀行口座番号</span></span> 
- <span data-ttu-id="8450f-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="8450f-2372">銀行口座</span></span> 
- <span data-ttu-id="8450f-2373">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2373">銀行口座＃</span></span> 
- <span data-ttu-id="8450f-2374">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="8450f-2375">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="8450f-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="8450f-2376">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="8450f-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="8450f-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2377">銀行口座番号</span></span>
- <span data-ttu-id="8450f-2378">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="8450f-2379">預金口座</span><span class="sxs-lookup"><span data-stu-id="8450f-2379">預金口座</span></span> 
- <span data-ttu-id="8450f-2380">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="8450f-2381">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="8450f-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="8450f-2382">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="8450f-2383">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="8450f-2384">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="8450f-2385">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="8450f-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2386">口座番号</span></span> 
- <span data-ttu-id="8450f-2387">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2387">口座番号＃</span></span> 
- <span data-ttu-id="8450f-2388">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="8450f-2389">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="8450f-2390">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="8450f-2391">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="8450f-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="8450f-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="8450f-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="8450f-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="8450f-2394">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2395">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2395">Format</span></span>

<span data-ttu-id="8450f-2396">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2397">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2397">Pattern</span></span>

<span data-ttu-id="8450f-2398">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2399">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2399">Checksum</span></span>

<span data-ttu-id="8450f-2400">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2401">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2401">Definition</span></span>

<span data-ttu-id="8450f-2402">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2403">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2404">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2405">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="8450f-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="8450f-2407">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-2407">dl#</span></span> 
- <span data-ttu-id="8450f-2408">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-2408">DL＃</span></span> 
- <span data-ttu-id="8450f-2409">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-2409">dls#</span></span> 
- <span data-ttu-id="8450f-2410">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-2410">DLS＃</span></span> 
- <span data-ttu-id="8450f-2411">driver license</span><span class="sxs-lookup"><span data-stu-id="8450f-2411">driver license</span></span> 
- <span data-ttu-id="8450f-2412">driver licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-2412">driver licenses</span></span> 
- <span data-ttu-id="8450f-2413">drivers license</span><span class="sxs-lookup"><span data-stu-id="8450f-2413">drivers license</span></span> 
- <span data-ttu-id="8450f-2414">driver's license</span><span class="sxs-lookup"><span data-stu-id="8450f-2414">driver's license</span></span> 
- <span data-ttu-id="8450f-2415">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-2415">drivers licenses</span></span> 
- <span data-ttu-id="8450f-2416">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-2416">driver's licenses</span></span> 
- <span data-ttu-id="8450f-2417">driving licence</span><span class="sxs-lookup"><span data-stu-id="8450f-2417">driving licence</span></span> 
- <span data-ttu-id="8450f-2418">driver'lic</span><span class="sxs-lookup"><span data-stu-id="8450f-2418">lic#</span></span> 
- <span data-ttu-id="8450f-2419">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="8450f-2419">LIC＃</span></span> 
- <span data-ttu-id="8450f-2420">driver'lics</span><span class="sxs-lookup"><span data-stu-id="8450f-2420">lics#</span></span> 
- <span data-ttu-id="8450f-2421">state id</span><span class="sxs-lookup"><span data-stu-id="8450f-2421">state id</span></span> 
- <span data-ttu-id="8450f-2422">state identification</span><span class="sxs-lookup"><span data-stu-id="8450f-2422">state identification</span></span> 
- <span data-ttu-id="8450f-2423">state identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-2423">state identification number</span></span> 
- <span data-ttu-id="8450f-2424">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2424">低所得国＃</span></span> 
- <span data-ttu-id="8450f-2425">免許証</span><span class="sxs-lookup"><span data-stu-id="8450f-2425">免許証</span></span> 
- <span data-ttu-id="8450f-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2426">状態ID</span></span>
- <span data-ttu-id="8450f-2427">状態の識別</span><span class="sxs-lookup"><span data-stu-id="8450f-2427">状態の識別</span></span> 
- <span data-ttu-id="8450f-2428">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2428">状態の識別番号</span></span> 
- <span data-ttu-id="8450f-2429">運転免許</span><span class="sxs-lookup"><span data-stu-id="8450f-2429">運転免許</span></span> 
- <span data-ttu-id="8450f-2430">運転免許証</span><span class="sxs-lookup"><span data-stu-id="8450f-2430">運転免許証</span></span> 
- <span data-ttu-id="8450f-2431">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="8450f-2432">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2433">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2433">Format</span></span>

<span data-ttu-id="8450f-2434">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2435">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2435">Pattern</span></span>

<span data-ttu-id="8450f-2436">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2437">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2437">Checksum</span></span>

<span data-ttu-id="8450f-2438">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2439">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2439">Definition</span></span>

<span data-ttu-id="8450f-2440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2441">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2442">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="8450f-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="8450f-2445">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-2445">パスポート</span></span> 
- <span data-ttu-id="8450f-2446">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2446">パスポート番号</span></span> 
- <span data-ttu-id="8450f-2447">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-2447">パスポートのNum</span></span> 
- <span data-ttu-id="8450f-2448">パスポート #</span><span class="sxs-lookup"><span data-stu-id="8450f-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="8450f-2449">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="8450f-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2450">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2450">Format</span></span>

<span data-ttu-id="8450f-2451">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2452">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2452">Pattern</span></span>

<span data-ttu-id="8450f-2453">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2454">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2454">Checksum</span></span>

<span data-ttu-id="8450f-2455">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2456">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2456">Definition</span></span>

<span data-ttu-id="8450f-2457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2458">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2459">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="8450f-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="8450f-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2462">Resident Registration Number</span></span>
- <span data-ttu-id="8450f-2463">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2463">Resident Register Number</span></span> 
- <span data-ttu-id="8450f-2464">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="8450f-2465">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="8450f-2466">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2466">Resident Register No.</span></span> 
- <span data-ttu-id="8450f-2467">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="8450f-2468">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="8450f-2469">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="8450f-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="8450f-2470">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="8450f-2471">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="8450f-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="8450f-2472">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="8450f-2473">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2474">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2474">Format</span></span>

<span data-ttu-id="8450f-2475">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2476">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2476">Pattern</span></span>

<span data-ttu-id="8450f-2477">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2477">7-12 digits:</span></span>
- <span data-ttu-id="8450f-2478">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2478">Four digits</span></span> 
- <span data-ttu-id="8450f-2479">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="8450f-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="8450f-2480">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="8450f-2480">Six digits OR</span></span>
- <span data-ttu-id="8450f-2481">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2482">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2482">Checksum</span></span>

<span data-ttu-id="8450f-2483">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2484">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2484">Definition</span></span>

<span data-ttu-id="8450f-2485">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2486">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2487">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="8450f-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="8450f-2488">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2489">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2490">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="8450f-2490">A keyword from Keyword_jp_sin is found.</span></span>

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2491">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="8450f-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="8450f-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="8450f-2493">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="8450f-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="8450f-2494">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="8450f-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="8450f-2495">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="8450f-2496">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="8450f-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="8450f-2497">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="8450f-2498">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="8450f-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2499">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2499">Format</span></span>

<span data-ttu-id="8450f-2500">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2501">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2501">Pattern</span></span>

<span data-ttu-id="8450f-2502">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2502">12 letters and digits:</span></span>
- <span data-ttu-id="8450f-2503">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="8450f-2504">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2504">Eight digits</span></span> 
- <span data-ttu-id="8450f-2505">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2506">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2506">Checksum</span></span>

<span data-ttu-id="8450f-2507">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2508">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2508">Definition</span></span>

<span data-ttu-id="8450f-2509">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2510">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2511">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="8450f-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="8450f-2514">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="8450f-2514">Residence card number</span></span>
- <span data-ttu-id="8450f-2515">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="8450f-2515">Residence card no</span></span>
- <span data-ttu-id="8450f-2516">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="8450f-2516">Residence card #</span></span>
- <span data-ttu-id="8450f-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="8450f-2518">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2519">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2519">Format</span></span>

<span data-ttu-id="8450f-2520">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="8450f-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2521">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2521">Pattern</span></span>

<span data-ttu-id="8450f-2522">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2522">12 digits:</span></span>
- <span data-ttu-id="8450f-2523">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8450f-2524">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2524">A dash (optional)</span></span> 
- <span data-ttu-id="8450f-2525">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="8450f-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="8450f-2526">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2526">A dash (optional)</span></span> 
- <span data-ttu-id="8450f-2527">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="8450f-2527">Three random digits</span></span> 
- <span data-ttu-id="8450f-2528">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="8450f-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2529">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2529">Checksum</span></span>

<span data-ttu-id="8450f-2530">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2531">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2531">Definition</span></span>

<span data-ttu-id="8450f-2532">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2533">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2534">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2535">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="8450f-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="8450f-2537">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="8450f-2537">digital application card</span></span>
- <span data-ttu-id="8450f-2538">i/c</span><span class="sxs-lookup"><span data-stu-id="8450f-2538">i/c</span></span>
- <span data-ttu-id="8450f-2539">i/c no</span><span class="sxs-lookup"><span data-stu-id="8450f-2539">i/c no</span></span>
- <span data-ttu-id="8450f-2540">IC</span><span class="sxs-lookup"><span data-stu-id="8450f-2540">ic</span></span>
- <span data-ttu-id="8450f-2541">IC No</span><span class="sxs-lookup"><span data-stu-id="8450f-2541">ic no</span></span>
- <span data-ttu-id="8450f-2542">id card</span><span class="sxs-lookup"><span data-stu-id="8450f-2542">id card</span></span>
- <span data-ttu-id="8450f-2543">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-2543">identification Card</span></span>
- <span data-ttu-id="8450f-2544">carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2544">identity card</span></span>
- <span data-ttu-id="8450f-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="8450f-2545">k/p</span></span>
- <span data-ttu-id="8450f-2546">k/p no</span><span class="sxs-lookup"><span data-stu-id="8450f-2546">k/p no</span></span>
- <span data-ttu-id="8450f-2547">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="8450f-2547">kad akuan diri</span></span>
- <span data-ttu-id="8450f-2548">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="8450f-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="8450f-2549">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="8450f-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="8450f-2550">KP</span><span class="sxs-lookup"><span data-stu-id="8450f-2550">kp</span></span>
- <span data-ttu-id="8450f-2551">KP No</span><span class="sxs-lookup"><span data-stu-id="8450f-2551">kp no</span></span>
- <span data-ttu-id="8450f-2552">MyKad</span><span class="sxs-lookup"><span data-stu-id="8450f-2552">mykad</span></span>
- <span data-ttu-id="8450f-2553">MYKAS</span><span class="sxs-lookup"><span data-stu-id="8450f-2553">mykas</span></span>
- <span data-ttu-id="8450f-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="8450f-2554">mykid</span></span>
- <span data-ttu-id="8450f-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="8450f-2555">mypr</span></span>
- <span data-ttu-id="8450f-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="8450f-2556">mytentera</span></span>
- <span data-ttu-id="8450f-2557">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="8450f-2557">malaysia identity card</span></span>
- <span data-ttu-id="8450f-2558">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="8450f-2558">malaysian identity card</span></span>
- <span data-ttu-id="8450f-2559">NRIC</span><span class="sxs-lookup"><span data-stu-id="8450f-2559">nric</span></span>
- <span data-ttu-id="8450f-2560">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="8450f-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="8450f-2561">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2562">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2562">Format</span></span>

<span data-ttu-id="8450f-2563">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="8450f-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2564">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2564">Pattern</span></span>

<span data-ttu-id="8450f-2565">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2565">8-9 digits:</span></span>
- <span data-ttu-id="8450f-2566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2566">Three digits</span></span> 
- <span data-ttu-id="8450f-2567">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2567">A space (optional)</span></span> 
- <span data-ttu-id="8450f-2568">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2568">Three digits</span></span> 
- <span data-ttu-id="8450f-2569">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-2569">A space (optional)</span></span> 
- <span data-ttu-id="8450f-2570">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2571">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2571">Checksum</span></span>

<span data-ttu-id="8450f-2572">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2573">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2573">Definition</span></span>

<span data-ttu-id="8450f-2574">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2575">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2576">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="8450f-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="8450f-2577">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="8450f-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="8450f-2578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2578">The checksum passes.</span></span>

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="8450f-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="8450f-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="8450f-2581">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="8450f-2581">Citizen service number</span></span> 
- <span data-ttu-id="8450f-2582">BSN</span><span class="sxs-lookup"><span data-stu-id="8450f-2582">BSN</span></span> 
- <span data-ttu-id="8450f-2583">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="8450f-2584">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2584">Sofinummer</span></span> 
- <span data-ttu-id="8450f-2585">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="8450f-2586">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="8450f-2587">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="8450f-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2588">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2588">Format</span></span>

<span data-ttu-id="8450f-2589">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2590">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2590">Pattern</span></span>

<span data-ttu-id="8450f-2591">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2592">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2592">Checksum</span></span>

<span data-ttu-id="8450f-2593">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2594">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2594">Definition</span></span>

<span data-ttu-id="8450f-2595">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2596">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2597">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="8450f-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="8450f-2598">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2598">The checksum passes.</span></span>

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="8450f-2599">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2599">Keywords</span></span>

<span data-ttu-id="8450f-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="8450f-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="8450f-2601">NHI</span><span class="sxs-lookup"><span data-stu-id="8450f-2601">NHI</span></span> 
- <span data-ttu-id="8450f-2602">New Zealand</span><span class="sxs-lookup"><span data-stu-id="8450f-2602">New Zealand</span></span> 
- <span data-ttu-id="8450f-2603">Integrità</span><span class="sxs-lookup"><span data-stu-id="8450f-2603">Health</span></span> 
- <span data-ttu-id="8450f-2604">trattamento</span><span class="sxs-lookup"><span data-stu-id="8450f-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="8450f-2605">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="8450f-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2606">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2606">Format</span></span>

<span data-ttu-id="8450f-2607">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2608">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2608">Pattern</span></span>

<span data-ttu-id="8450f-2609">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2609">11 digits:</span></span>
- <span data-ttu-id="8450f-2610">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="8450f-2611">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="8450f-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="8450f-2612">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="8450f-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2613">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2613">Checksum</span></span>

<span data-ttu-id="8450f-2614">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2615">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2615">Definition</span></span>

<span data-ttu-id="8450f-2616">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2617">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2618">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="8450f-2619">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2619">The checksum passes.</span></span>
- <span data-ttu-id="8450f-2620">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2621">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2622">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2622">The checksum passes.</span></span>

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2623">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="8450f-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="8450f-2625">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="8450f-2625">Personal identification number</span></span>
- <span data-ttu-id="8450f-2626">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="8450f-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="8450f-2627">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="8450f-2627">ID Number</span></span>
- <span data-ttu-id="8450f-2628">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-2628">Identification</span></span>
- <span data-ttu-id="8450f-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2629">Personnummer</span></span>
- <span data-ttu-id="8450f-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="8450f-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="8450f-2631">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="8450f-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2632">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2632">Format</span></span>

<span data-ttu-id="8450f-2633">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="8450f-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2634">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2634">Pattern</span></span>

<span data-ttu-id="8450f-2635">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2635">12 digits:</span></span>
- <span data-ttu-id="8450f-2636">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2636">Four digits</span></span> 
- <span data-ttu-id="8450f-2637">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-2637">A hyphen</span></span> 
- <span data-ttu-id="8450f-2638">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2638">Seven digits</span></span> 
- <span data-ttu-id="8450f-2639">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-2639">A hyphen</span></span> 
- <span data-ttu-id="8450f-2640">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2641">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2641">Checksum</span></span>

<span data-ttu-id="8450f-2642">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2643">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2643">Definition</span></span>

<span data-ttu-id="8450f-2644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2645">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2646">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2647">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="8450f-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="8450f-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="8450f-2649">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="8450f-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="8450f-2650">UMID</span><span class="sxs-lookup"><span data-stu-id="8450f-2650">UMID</span></span> 
- <span data-ttu-id="8450f-2651">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2651">Identity Card</span></span> 
- <span data-ttu-id="8450f-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="8450f-2653">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="8450f-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2654">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2654">Format</span></span>

<span data-ttu-id="8450f-2655">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2656">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2656">Pattern</span></span>

<span data-ttu-id="8450f-2657">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2658">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2658">Checksum</span></span>

<span data-ttu-id="8450f-2659">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2660">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2660">Definition</span></span>

<span data-ttu-id="8450f-2661">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="8450f-2662">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2662">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="8450f-2663">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2663">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2664">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="8450f-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="8450f-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="8450f-2666">Dowód osobisty</span></span>
- <span data-ttu-id="8450f-2667">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8450f-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="8450f-2668">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8450f-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="8450f-2669">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="8450f-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="8450f-2670">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="8450f-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="8450f-2671">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="8450f-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="8450f-2672">Dow.</span><span class="sxs-lookup"><span data-stu-id="8450f-2672">dow.</span></span> <span data-ttu-id="8450f-2673">OS.</span><span class="sxs-lookup"><span data-stu-id="8450f-2673">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="8450f-2674">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="8450f-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2675">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2675">Format</span></span>

<span data-ttu-id="8450f-2676">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2677">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2677">Pattern</span></span>

<span data-ttu-id="8450f-2678">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2679">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2679">Checksum</span></span>

<span data-ttu-id="8450f-2680">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2681">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2681">Definition</span></span>

<span data-ttu-id="8450f-2682">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2683">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2684">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="8450f-2685">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2686">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="8450f-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="8450f-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="8450f-2688">Nr PESEL</span></span>
- <span data-ttu-id="8450f-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="8450f-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="8450f-2690">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="8450f-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2691">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2691">Format</span></span>

<span data-ttu-id="8450f-2692">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2693">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2693">Pattern</span></span>

<span data-ttu-id="8450f-2694">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2695">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2695">Checksum</span></span>

<span data-ttu-id="8450f-2696">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2697">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2697">Definition</span></span>

<span data-ttu-id="8450f-2698">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2699">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2700">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="8450f-2701">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2701">The checksum passes.</span></span>

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2702">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="8450f-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="8450f-2704">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="8450f-2704">Numer paszportu</span></span>
- <span data-ttu-id="8450f-2705">Nr.</span><span class="sxs-lookup"><span data-stu-id="8450f-2705">Nr.</span></span> <span data-ttu-id="8450f-2706">Paszportu</span><span class="sxs-lookup"><span data-stu-id="8450f-2706">Paszportu</span></span>
- <span data-ttu-id="8450f-2707">Paszport</span><span class="sxs-lookup"><span data-stu-id="8450f-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="8450f-2708">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="8450f-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2709">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2709">Format</span></span>

<span data-ttu-id="8450f-2710">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2711">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2711">Pattern</span></span>

<span data-ttu-id="8450f-2712">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2713">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2713">Checksum</span></span>

<span data-ttu-id="8450f-2714">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2715">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2715">Definition</span></span>

<span data-ttu-id="8450f-2716">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2717">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2718">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="8450f-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2719">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="8450f-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="8450f-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="8450f-2721">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="8450f-2721">Citizen Card</span></span>
- <span data-ttu-id="8450f-2722">Carta ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2722">National ID Card</span></span>
- <span data-ttu-id="8450f-2723">CC</span><span class="sxs-lookup"><span data-stu-id="8450f-2723">CC</span></span>
- <span data-ttu-id="8450f-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="8450f-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="8450f-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="8450f-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="8450f-2726">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2727">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2727">Format</span></span>

<span data-ttu-id="8450f-2728">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2729">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2729">Pattern</span></span>

<span data-ttu-id="8450f-2730">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2731">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2731">Checksum</span></span>

<span data-ttu-id="8450f-2732">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2733">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2733">Definition</span></span>

<span data-ttu-id="8450f-2734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2735">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2736">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2737">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="8450f-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="8450f-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="8450f-2739">Identification Card</span><span class="sxs-lookup"><span data-stu-id="8450f-2739">Identification Card</span></span> 
- <span data-ttu-id="8450f-2740">I card number</span><span class="sxs-lookup"><span data-stu-id="8450f-2740">I card number</span></span> 
- <span data-ttu-id="8450f-2741">ID number</span><span class="sxs-lookup"><span data-stu-id="8450f-2741">ID number</span></span> 
- <span data-ttu-id="8450f-2742">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="8450f-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="8450f-2743">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="8450f-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2744">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2744">Format</span></span>

<span data-ttu-id="8450f-2745">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="8450f-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2746">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2746">Pattern</span></span>

- <span data-ttu-id="8450f-2747">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="8450f-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="8450f-2748">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="8450f-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2749">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2749">Seven digits</span></span> 
- <span data-ttu-id="8450f-2750">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="8450f-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2751">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2751">Checksum</span></span>

<span data-ttu-id="8450f-2752">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2753">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2753">Definition</span></span>

<span data-ttu-id="8450f-2754">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2755">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2756">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="8450f-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="8450f-2757">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2757">The checksum passes.</span></span>

<span data-ttu-id="8450f-2758">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2759">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2760">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2760">The checksum passes.</span></span>

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2761">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="8450f-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="8450f-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="8450f-2763">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="8450f-2764">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2764">Identity Card Number</span></span> 
- <span data-ttu-id="8450f-2765">NRIC</span><span class="sxs-lookup"><span data-stu-id="8450f-2765">NRIC</span></span> 
- <span data-ttu-id="8450f-2766">IC</span><span class="sxs-lookup"><span data-stu-id="8450f-2766">IC</span></span> 
- <span data-ttu-id="8450f-2767">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="8450f-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="8450f-2768">FIN</span><span class="sxs-lookup"><span data-stu-id="8450f-2768">FIN</span></span> 
- <span data-ttu-id="8450f-2769">身份证</span><span class="sxs-lookup"><span data-stu-id="8450f-2769">身份证</span></span> 
- <span data-ttu-id="8450f-2770">身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="8450f-2771">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="8450f-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2772">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2772">Format</span></span>

<span data-ttu-id="8450f-2773">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="8450f-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2774">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2774">Pattern</span></span>

<span data-ttu-id="8450f-2775">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2775">13 digits:</span></span>
- <span data-ttu-id="8450f-2776">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8450f-2777">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2777">Four digits</span></span> 
- <span data-ttu-id="8450f-2778">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="8450f-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="8450f-2779">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="8450f-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="8450f-2780">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2781">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2781">Checksum</span></span>

<span data-ttu-id="8450f-2782">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2783">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2783">Definition</span></span>

<span data-ttu-id="8450f-2784">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2785">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2786">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="8450f-2787">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2788">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="8450f-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="8450f-2790">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2790">Identity card</span></span>
- <span data-ttu-id="8450f-2791">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2791">ID</span></span>
- <span data-ttu-id="8450f-2792">Identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="8450f-2793">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="8450f-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2794">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2794">Format</span></span>

<span data-ttu-id="8450f-2795">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="8450f-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2796">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2796">Pattern</span></span>

<span data-ttu-id="8450f-2797">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2797">13 digits:</span></span>
- <span data-ttu-id="8450f-2798">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="8450f-2799">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8450f-2799">A hyphen</span></span> 
- <span data-ttu-id="8450f-2800">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="8450f-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="8450f-2801">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="8450f-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="8450f-2802">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="8450f-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="8450f-2803">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2804">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2804">Checksum</span></span>

<span data-ttu-id="8450f-2805">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2806">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2806">Definition</span></span>

<span data-ttu-id="8450f-2807">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2808">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2809">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="8450f-2810">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2810">The checksum passes.</span></span>

<span data-ttu-id="8450f-2811">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2812">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2813">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2813">The checksum passes.</span></span>

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2814">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="8450f-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="8450f-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="8450f-2816">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="8450f-2816">National ID card</span></span> 
- <span data-ttu-id="8450f-2817">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="8450f-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="8450f-2818">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="8450f-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="8450f-2819">RRN</span><span class="sxs-lookup"><span data-stu-id="8450f-2819">RRN</span></span> 
- <span data-ttu-id="8450f-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="8450f-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="8450f-2821">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2822">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2822">Format</span></span>

<span data-ttu-id="8450f-2823">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2824">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2824">Pattern</span></span>

<span data-ttu-id="8450f-2825">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2825">11-12 digits:</span></span>
- <span data-ttu-id="8450f-2826">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2826">Two digits</span></span> 
- <span data-ttu-id="8450f-2827">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="8450f-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="8450f-2828">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2828">7-8 digits</span></span> 
- <span data-ttu-id="8450f-2829">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="8450f-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="8450f-2830">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2831">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2831">Checksum</span></span>

<span data-ttu-id="8450f-2832">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2833">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2833">Definition</span></span>

<span data-ttu-id="8450f-2834">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2835">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2836">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2837">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2837">Keywords</span></span>

<span data-ttu-id="8450f-2838">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8450f-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="8450f-2839">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2840">Format</span></span>

<span data-ttu-id="8450f-2841">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="8450f-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2842">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2842">Pattern</span></span>

<span data-ttu-id="8450f-2843">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="8450f-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="8450f-2844">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="8450f-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="8450f-2845">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="8450f-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="8450f-2846">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="8450f-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="8450f-2847">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2848">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2848">Checksum</span></span>

<span data-ttu-id="8450f-2849">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2850">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2850">Definition</span></span>

<span data-ttu-id="8450f-2851">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2852">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2853">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2854">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2854">Keywords</span></span>

<span data-ttu-id="8450f-2855">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="8450f-2856">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2857">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2857">Format</span></span>

<span data-ttu-id="8450f-2858">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2859">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2859">Pattern</span></span>

<span data-ttu-id="8450f-2860">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2861">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2861">Checksum</span></span>

<span data-ttu-id="8450f-2862">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2863">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2863">Definition</span></span>

<span data-ttu-id="8450f-2864">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2865">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2866">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-2866">One of the following is true:</span></span>
    - <span data-ttu-id="8450f-2867">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="8450f-2868">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-2868">A keyword from Keyword_sweden_passport is found.</span></span>

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2869">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="8450f-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="8450f-2871">visa requirements</span><span class="sxs-lookup"><span data-stu-id="8450f-2871">visa requirements</span></span> 
- <span data-ttu-id="8450f-2872">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="8450f-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="8450f-2873">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="8450f-2873">Schengen visas</span></span> 
- <span data-ttu-id="8450f-2874">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="8450f-2874">Schengen visa</span></span> 
- <span data-ttu-id="8450f-2875">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="8450f-2875">Visa Processing</span></span> 
- <span data-ttu-id="8450f-2876">Visa Type</span><span class="sxs-lookup"><span data-stu-id="8450f-2876">Visa Type</span></span> 
- <span data-ttu-id="8450f-2877">Single Entry</span><span class="sxs-lookup"><span data-stu-id="8450f-2877">Single Entry</span></span> 
- <span data-ttu-id="8450f-2878">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="8450f-2878">Multiple Entry</span></span> 
- <span data-ttu-id="8450f-2879">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="8450f-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="8450f-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-2880">Keyword_passport</span></span>

- <span data-ttu-id="8450f-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8450f-2881">Passport Number</span></span> 
- <span data-ttu-id="8450f-2882">Passport No</span><span class="sxs-lookup"><span data-stu-id="8450f-2882">Passport No</span></span> 
- <span data-ttu-id="8450f-2883">Passport#</span><span class="sxs-lookup"><span data-stu-id="8450f-2883">Passport #</span></span> 
- <span data-ttu-id="8450f-2884">Passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2884">Passport#</span></span> 
- <span data-ttu-id="8450f-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="8450f-2885">PassportID</span></span> 
- <span data-ttu-id="8450f-2886">Passportno</span><span class="sxs-lookup"><span data-stu-id="8450f-2886">Passportno</span></span> 
- <span data-ttu-id="8450f-2887">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-2887">passportnumber</span></span> 
- <span data-ttu-id="8450f-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-2888">パスポート</span></span> 
- <span data-ttu-id="8450f-2889">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2889">パスポート番号</span></span> 
- <span data-ttu-id="8450f-2890">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-2890">パスポートのNum</span></span> 
- <span data-ttu-id="8450f-2891">パスポート #</span><span class="sxs-lookup"><span data-stu-id="8450f-2891">パスポート＃</span></span> 
- <span data-ttu-id="8450f-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="8450f-2893">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8450f-2893">Passeport n °</span></span> 
- <span data-ttu-id="8450f-2894">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8450f-2894">Passeport Non</span></span> 
- <span data-ttu-id="8450f-2895">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8450f-2895">Passeport #</span></span> 
- <span data-ttu-id="8450f-2896">Passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-2896">Passeport#</span></span> 
- <span data-ttu-id="8450f-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8450f-2897">PasseportNon</span></span> 
- <span data-ttu-id="8450f-2898">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8450f-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="8450f-2899">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="8450f-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2900">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2900">Format</span></span>

<span data-ttu-id="8450f-2901">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2902">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2902">Pattern</span></span>

<span data-ttu-id="8450f-2903">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="8450f-2904">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2905">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="8450f-2905">An optional space</span></span> 
- <span data-ttu-id="8450f-2906">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="8450f-2907">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="8450f-2907">An optional space</span></span> 
- <span data-ttu-id="8450f-2908">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="8450f-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2909">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2909">Checksum</span></span>

<span data-ttu-id="8450f-2910">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2911">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2911">Definition</span></span>

<span data-ttu-id="8450f-2912">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2913">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2914">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="8450f-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2915">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="8450f-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="8450f-2916">Keyword_swift</span></span>

- <span data-ttu-id="8450f-2917">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="8450f-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="8450f-2918">iso 9362</span><span class="sxs-lookup"><span data-stu-id="8450f-2918">iso 9362</span></span> 
- <span data-ttu-id="8450f-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="8450f-2919">iso9362</span></span> 
- <span data-ttu-id="8450f-2920">Swift\#</span><span class="sxs-lookup"><span data-stu-id="8450f-2920">swift\#</span></span> 
- <span data-ttu-id="8450f-2921">swiftcode</span><span class="sxs-lookup"><span data-stu-id="8450f-2921">swiftcode</span></span> 
- <span data-ttu-id="8450f-2922">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-2922">swiftnumber</span></span> 
- <span data-ttu-id="8450f-2923">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="8450f-2924">swift code</span><span class="sxs-lookup"><span data-stu-id="8450f-2924">swift code</span></span> 
- <span data-ttu-id="8450f-2925">swift number #</span><span class="sxs-lookup"><span data-stu-id="8450f-2925">swift number #</span></span> 
- <span data-ttu-id="8450f-2926">swift routing number</span><span class="sxs-lookup"><span data-stu-id="8450f-2926">swift routing number</span></span> 
- <span data-ttu-id="8450f-2927">bic number</span><span class="sxs-lookup"><span data-stu-id="8450f-2927">bic number</span></span> 
- <span data-ttu-id="8450f-2928">bic code</span><span class="sxs-lookup"><span data-stu-id="8450f-2928">bic code</span></span> 
- <span data-ttu-id="8450f-2929">BIC\#</span><span class="sxs-lookup"><span data-stu-id="8450f-2929">bic \#</span></span> 
- <span data-ttu-id="8450f-2930">BIC\#</span><span class="sxs-lookup"><span data-stu-id="8450f-2930">bic\#</span></span> 
- <span data-ttu-id="8450f-2931">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="8450f-2931">bank identifier code</span></span> 
- <span data-ttu-id="8450f-2932">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="8450f-2932">標準化9362</span></span> 
- <span data-ttu-id="8450f-2933">迅速 #</span><span class="sxs-lookup"><span data-stu-id="8450f-2933">迅速＃</span></span> 
- <span data-ttu-id="8450f-2934">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="8450f-2934">SWIFTコード</span></span> 
- <span data-ttu-id="8450f-2935">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2935">SWIFT番号</span></span> 
- <span data-ttu-id="8450f-2936">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="8450f-2937">BIC番号</span><span class="sxs-lookup"><span data-stu-id="8450f-2937">BIC番号</span></span> 
- <span data-ttu-id="8450f-2938">BICコード</span><span class="sxs-lookup"><span data-stu-id="8450f-2938">BICコード</span></span> 
- <span data-ttu-id="8450f-2939">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="8450f-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="8450f-2940">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="8450f-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="8450f-2941">rapide\#</span><span class="sxs-lookup"><span data-stu-id="8450f-2941">rapide \#</span></span> 
- <span data-ttu-id="8450f-2942">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="8450f-2942">code SWIFT</span></span> 
- <span data-ttu-id="8450f-2943">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="8450f-2943">le numéro de swift</span></span> 
- <span data-ttu-id="8450f-2944">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="8450f-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="8450f-2945">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="8450f-2945">le numéro BIC</span></span> 
- <span data-ttu-id="8450f-2946">\#BIC</span><span class="sxs-lookup"><span data-stu-id="8450f-2946">\# BIC</span></span> 
- <span data-ttu-id="8450f-2947">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="8450f-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="8450f-2948">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="8450f-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2949">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2949">Format</span></span>

<span data-ttu-id="8450f-2950">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2951">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2951">Pattern</span></span>

<span data-ttu-id="8450f-2952">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="8450f-2953">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="8450f-2954">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="8450f-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="8450f-2955">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2956">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2956">Checksum</span></span>

<span data-ttu-id="8450f-2957">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2958">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2958">Definition</span></span>

<span data-ttu-id="8450f-2959">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2960">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2961">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="8450f-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="8450f-2962">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2963">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="8450f-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="8450f-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="8450f-2965">身份證字號</span><span class="sxs-lookup"><span data-stu-id="8450f-2965">身份證字號</span></span> 
- <span data-ttu-id="8450f-2966">身份證</span><span class="sxs-lookup"><span data-stu-id="8450f-2966">身份證</span></span> 
- <span data-ttu-id="8450f-2967">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="8450f-2967">身份證號碼</span></span> 
- <span data-ttu-id="8450f-2968">身份證號</span><span class="sxs-lookup"><span data-stu-id="8450f-2968">身份證號</span></span> 
- <span data-ttu-id="8450f-2969">身分證字號</span><span class="sxs-lookup"><span data-stu-id="8450f-2969">身分證字號</span></span> 
- <span data-ttu-id="8450f-2970">身分證</span><span class="sxs-lookup"><span data-stu-id="8450f-2970">身分證</span></span> 
- <span data-ttu-id="8450f-2971">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="8450f-2971">身分證號碼</span></span> 
- <span data-ttu-id="8450f-2972">身份證號</span><span class="sxs-lookup"><span data-stu-id="8450f-2972">身份證號</span></span> 
- <span data-ttu-id="8450f-2973">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="8450f-2973">身分證統一編號</span></span> 
- <span data-ttu-id="8450f-2974">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="8450f-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="8450f-2975">簽名</span><span class="sxs-lookup"><span data-stu-id="8450f-2975">簽名</span></span> 
- <span data-ttu-id="8450f-2976">蓋章</span><span class="sxs-lookup"><span data-stu-id="8450f-2976">蓋章</span></span> 
- <span data-ttu-id="8450f-2977">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="8450f-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="8450f-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="8450f-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="8450f-2979">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-2980">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-2980">Format</span></span>

- <span data-ttu-id="8450f-2981">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="8450f-2982">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-2983">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-2983">Pattern</span></span>
<span data-ttu-id="8450f-2984">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="8450f-2984">Biometric passport number:</span></span>
- <span data-ttu-id="8450f-2985">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="8450f-2985">The digit "3"</span></span> 
- <span data-ttu-id="8450f-2986">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2986">Eight digits</span></span>

<span data-ttu-id="8450f-2987">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="8450f-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="8450f-2988">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-2989">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-2989">Checksum</span></span>

<span data-ttu-id="8450f-2990">No</span><span class="sxs-lookup"><span data-stu-id="8450f-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-2991">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-2991">Definition</span></span>

<span data-ttu-id="8450f-2992">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-2993">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-2994">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-2995">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="8450f-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="8450f-2997">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="8450f-2997">ROC passport number</span></span> 
- <span data-ttu-id="8450f-2998">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2998">Passport number</span></span> 
- <span data-ttu-id="8450f-2999">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-2999">Passport no</span></span> 
- <span data-ttu-id="8450f-3000">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="8450f-3000">Passport Num</span></span> 
- <span data-ttu-id="8450f-3001">Passport #</span><span class="sxs-lookup"><span data-stu-id="8450f-3001">Passport #</span></span> 
- <span data-ttu-id="8450f-3002">护照</span><span class="sxs-lookup"><span data-stu-id="8450f-3002">护照</span></span> 
- <span data-ttu-id="8450f-3003">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="8450f-3003">中華民國護照</span></span> 
- <span data-ttu-id="8450f-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="8450f-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="8450f-3005">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8450f-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3006">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3006">Format</span></span>

<span data-ttu-id="8450f-3007">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3008">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3008">Pattern</span></span>

<span data-ttu-id="8450f-3009">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-3009">10 letters and digits:</span></span>
- <span data-ttu-id="8450f-3010">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="8450f-3011">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3012">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3012">Checksum</span></span>

<span data-ttu-id="8450f-3013">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3014">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3014">Definition</span></span>

<span data-ttu-id="8450f-3015">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3016">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3017">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="8450f-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3018">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="8450f-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="8450f-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="8450f-3020">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="8450f-3020">Resident Certificate</span></span> 
- <span data-ttu-id="8450f-3021">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="8450f-3021">Resident Cert</span></span> 
- <span data-ttu-id="8450f-3022">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="8450f-3022">Resident Cert.</span></span> 
- <span data-ttu-id="8450f-3023">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="8450f-3023">Identification card</span></span> 
- <span data-ttu-id="8450f-3024">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="8450f-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="8450f-3025">ARCO</span><span class="sxs-lookup"><span data-stu-id="8450f-3025">ARC</span></span> 
- <span data-ttu-id="8450f-3026">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="8450f-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="8450f-3027">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="8450f-3027">TARC</span></span> 
- <span data-ttu-id="8450f-3028">居留證</span><span class="sxs-lookup"><span data-stu-id="8450f-3028">居留證</span></span> 
- <span data-ttu-id="8450f-3029">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="8450f-3029">外僑居留證</span></span> 
- <span data-ttu-id="8450f-3030">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="8450f-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="8450f-3031">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="8450f-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3032">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3032">Format</span></span>

<span data-ttu-id="8450f-3033">13 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3034">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3034">Pattern</span></span>

<span data-ttu-id="8450f-3035">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-3035">13 digits:</span></span>
- <span data-ttu-id="8450f-3036">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="8450f-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="8450f-3037">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3038">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3038">Checksum</span></span>

<span data-ttu-id="8450f-3039">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3040">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3040">Definition</span></span>

<span data-ttu-id="8450f-3041">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3042">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3043">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="8450f-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="8450f-3044">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3045">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3046">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="8450f-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="8450f-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="8450f-3048">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="8450f-3048">ID Number</span></span>
- <span data-ttu-id="8450f-3049">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="8450f-3049">Identification Number</span></span>
- <span data-ttu-id="8450f-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8450f-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="8450f-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8450f-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="8450f-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8450f-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="8450f-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="8450f-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="8450f-3054">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="8450f-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3055">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3055">Format</span></span>

<span data-ttu-id="8450f-3056">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3057">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3057">Pattern</span></span>

<span data-ttu-id="8450f-3058">11 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3059">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3059">Checksum</span></span>

<span data-ttu-id="8450f-3060">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3061">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3061">Definition</span></span>

<span data-ttu-id="8450f-3062">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3063">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3064">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="8450f-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="8450f-3065">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3066">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3067">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="8450f-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="8450f-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="8450f-3069">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="8450f-3069">TC Kimlik No</span></span>
- <span data-ttu-id="8450f-3070">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="8450f-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="8450f-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="8450f-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="8450f-3072">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="8450f-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="8450f-p141">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3075">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3075">Format</span></span>

<span data-ttu-id="8450f-3076">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="8450f-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3077">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3077">Pattern</span></span>

<span data-ttu-id="8450f-3078">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-3078">18 letters and digits:</span></span>
- <span data-ttu-id="8450f-3079">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="8450f-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="8450f-3080">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-3080">One digit</span></span> 
- <span data-ttu-id="8450f-3081">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="8450f-3082">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="8450f-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="8450f-3083">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3084">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3084">Checksum</span></span>

<span data-ttu-id="8450f-3085">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3086">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3086">Definition</span></span>

<span data-ttu-id="8450f-3087">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3088">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3089">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="8450f-3090">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3091">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="8450f-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8450f-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="8450f-3093">DVLA</span><span class="sxs-lookup"><span data-stu-id="8450f-3093">DVLA</span></span> 
- <span data-ttu-id="8450f-3094">light vans</span><span class="sxs-lookup"><span data-stu-id="8450f-3094">light vans</span></span> 
- <span data-ttu-id="8450f-3095">quadbikes</span><span class="sxs-lookup"><span data-stu-id="8450f-3095">quadbikes</span></span> 
- <span data-ttu-id="8450f-3096">motor cars</span><span class="sxs-lookup"><span data-stu-id="8450f-3096">motor cars</span></span> 
- <span data-ttu-id="8450f-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="8450f-3097">125cc</span></span> 
- <span data-ttu-id="8450f-3098">sidecar</span><span class="sxs-lookup"><span data-stu-id="8450f-3098">sidecar</span></span> 
- <span data-ttu-id="8450f-3099">tricicli</span><span class="sxs-lookup"><span data-stu-id="8450f-3099">tricycles</span></span> 
- <span data-ttu-id="8450f-3100">moto</span><span class="sxs-lookup"><span data-stu-id="8450f-3100">motorcycles</span></span> 
- <span data-ttu-id="8450f-3101">photocard licence</span><span class="sxs-lookup"><span data-stu-id="8450f-3101">photocard licence</span></span> 
- <span data-ttu-id="8450f-3102">learner drivers</span><span class="sxs-lookup"><span data-stu-id="8450f-3102">learner drivers</span></span> 
- <span data-ttu-id="8450f-3103">licence holder</span><span class="sxs-lookup"><span data-stu-id="8450f-3103">licence holder</span></span> 
- <span data-ttu-id="8450f-3104">licence holders</span><span class="sxs-lookup"><span data-stu-id="8450f-3104">licence holders</span></span> 
- <span data-ttu-id="8450f-3105">driving licences</span><span class="sxs-lookup"><span data-stu-id="8450f-3105">driving licences</span></span> 
- <span data-ttu-id="8450f-3106">driving licence</span><span class="sxs-lookup"><span data-stu-id="8450f-3106">driving licence</span></span> 
- <span data-ttu-id="8450f-3107">dual control car</span><span class="sxs-lookup"><span data-stu-id="8450f-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="8450f-p142">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="8450f-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3110">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3110">Format</span></span>

<span data-ttu-id="8450f-3111">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3112">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3112">Pattern</span></span>

<span data-ttu-id="8450f-3113">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="8450f-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3114">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3114">Checksum</span></span>

<span data-ttu-id="8450f-3115">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3116">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3116">Definition</span></span>

<span data-ttu-id="8450f-3117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3118">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3119">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="8450f-3119">A keyword from Keyword_uk_electoral is found.</span></span>

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="8450f-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="8450f-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="8450f-3122">council nomination</span><span class="sxs-lookup"><span data-stu-id="8450f-3122">council nomination</span></span> 
- <span data-ttu-id="8450f-3123">nomination form</span><span class="sxs-lookup"><span data-stu-id="8450f-3123">nomination form</span></span> 
- <span data-ttu-id="8450f-3124">electoral register</span><span class="sxs-lookup"><span data-stu-id="8450f-3124">electoral register</span></span> 
- <span data-ttu-id="8450f-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="8450f-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="8450f-p143">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="8450f-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3128">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3128">Format</span></span>

<span data-ttu-id="8450f-3129">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="8450f-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3130">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3130">Pattern</span></span>

<span data-ttu-id="8450f-3131">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="8450f-3131">10-17 digits:</span></span>
- <span data-ttu-id="8450f-3132">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="8450f-3133">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="8450f-3133">A space</span></span> 
- <span data-ttu-id="8450f-3134">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3134">Three digits</span></span> 
- <span data-ttu-id="8450f-3135">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="8450f-3135">A space</span></span> 
- <span data-ttu-id="8450f-3136">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3137">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3137">Checksum</span></span>

<span data-ttu-id="8450f-3138">Sì</span><span class="sxs-lookup"><span data-stu-id="8450f-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3139">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3139">Definition</span></span>

<span data-ttu-id="8450f-3140">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3141">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3142">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-3142">One of the following is true:</span></span>
    - <span data-ttu-id="8450f-3143">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="8450f-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="8450f-3144">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="8450f-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="8450f-3145">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="8450f-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="8450f-3146">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8450f-3146">The checksum passes.</span></span>

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3147">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="8450f-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="8450f-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="8450f-3149">national health service</span><span class="sxs-lookup"><span data-stu-id="8450f-3149">national health service</span></span> 
- <span data-ttu-id="8450f-3150">NHS</span><span class="sxs-lookup"><span data-stu-id="8450f-3150">nhs</span></span> 
- <span data-ttu-id="8450f-3151">health services authority</span><span class="sxs-lookup"><span data-stu-id="8450f-3151">health services authority</span></span> 
- <span data-ttu-id="8450f-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="8450f-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="8450f-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="8450f-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="8450f-3154">patient id</span><span class="sxs-lookup"><span data-stu-id="8450f-3154">patient id</span></span> 
- <span data-ttu-id="8450f-3155">patient identification</span><span class="sxs-lookup"><span data-stu-id="8450f-3155">patient identification</span></span> 
- <span data-ttu-id="8450f-3156">patient no</span><span class="sxs-lookup"><span data-stu-id="8450f-3156">patient no</span></span> 
- <span data-ttu-id="8450f-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="8450f-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="8450f-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="8450f-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="8450f-3159">GP</span><span class="sxs-lookup"><span data-stu-id="8450f-3159">GP</span></span> 
- <span data-ttu-id="8450f-3160">DOB</span><span class="sxs-lookup"><span data-stu-id="8450f-3160">DOB</span></span> 
- <span data-ttu-id="8450f-3161">D. O. B</span><span class="sxs-lookup"><span data-stu-id="8450f-3161">D.O.B</span></span> 
- <span data-ttu-id="8450f-3162">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8450f-3162">Date of Birth</span></span> 
- <span data-ttu-id="8450f-3163">Birth Date</span><span class="sxs-lookup"><span data-stu-id="8450f-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="8450f-p144">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="8450f-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3166">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3166">Format</span></span>

<span data-ttu-id="8450f-3167">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="8450f-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3168">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3168">Pattern</span></span>

<span data-ttu-id="8450f-3169">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="8450f-3169">Two possible patterns:</span></span>

- <span data-ttu-id="8450f-3170">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="8450f-3171">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3171">Six digits</span></span>
- <span data-ttu-id="8450f-3172">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8450f-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="8450f-3173">O</span><span class="sxs-lookup"><span data-stu-id="8450f-3173">OR</span></span>

- <span data-ttu-id="8450f-3174">Due lettere</span><span class="sxs-lookup"><span data-stu-id="8450f-3174">Two letters</span></span>
- <span data-ttu-id="8450f-3175">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3175">A space or dash</span></span>
- <span data-ttu-id="8450f-3176">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3176">Two digits</span></span>
- <span data-ttu-id="8450f-3177">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3177">A space or dash</span></span>
- <span data-ttu-id="8450f-3178">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3178">Two digits</span></span>
- <span data-ttu-id="8450f-3179">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3179">A space or dash</span></span>
- <span data-ttu-id="8450f-3180">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3180">Two digits</span></span>
- <span data-ttu-id="8450f-3181">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3181">A space or dash</span></span>
- <span data-ttu-id="8450f-3182">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="8450f-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3183">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3183">Checksum</span></span>

<span data-ttu-id="8450f-3184">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3185">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3185">Definition</span></span>

<span data-ttu-id="8450f-3186">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3187">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3188">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="8450f-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="8450f-3189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3190">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3191">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="8450f-3191">No keyword from Keyword_uk_nino is found.</span></span>

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="8450f-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="8450f-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="8450f-3194">national insurance number</span><span class="sxs-lookup"><span data-stu-id="8450f-3194">national insurance number</span></span> 
- <span data-ttu-id="8450f-3195">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="8450f-3195">national insurance contributions</span></span> 
- <span data-ttu-id="8450f-3196">protection act</span><span class="sxs-lookup"><span data-stu-id="8450f-3196">protection act</span></span> 
- <span data-ttu-id="8450f-3197">Insurance</span><span class="sxs-lookup"><span data-stu-id="8450f-3197">insurance</span></span> 
- <span data-ttu-id="8450f-3198">social security number</span><span class="sxs-lookup"><span data-stu-id="8450f-3198">social security number</span></span> 
- <span data-ttu-id="8450f-3199">insurance application</span><span class="sxs-lookup"><span data-stu-id="8450f-3199">insurance application</span></span> 
- <span data-ttu-id="8450f-3200">medical application</span><span class="sxs-lookup"><span data-stu-id="8450f-3200">medical application</span></span> 
- <span data-ttu-id="8450f-3201">social insurance</span><span class="sxs-lookup"><span data-stu-id="8450f-3201">social insurance</span></span> 
- <span data-ttu-id="8450f-3202">medical attention</span><span class="sxs-lookup"><span data-stu-id="8450f-3202">medical attention</span></span> 
- <span data-ttu-id="8450f-3203">social security</span><span class="sxs-lookup"><span data-stu-id="8450f-3203">social security</span></span> 
- <span data-ttu-id="8450f-3204">great britain</span><span class="sxs-lookup"><span data-stu-id="8450f-3204">great britain</span></span> 
- <span data-ttu-id="8450f-3205">Insurance</span><span class="sxs-lookup"><span data-stu-id="8450f-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="8450f-p145">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3208">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3208">Format</span></span>

<span data-ttu-id="8450f-3209">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3210">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3210">Pattern</span></span>

<span data-ttu-id="8450f-3211">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3212">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3212">Checksum</span></span>

<span data-ttu-id="8450f-3213">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3214">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3214">Definition</span></span>

<span data-ttu-id="8450f-3215">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3216">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3217">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="8450f-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3218">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="8450f-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="8450f-3219">Keyword_passport</span></span>

- <span data-ttu-id="8450f-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3220">Passport Number</span></span> 
- <span data-ttu-id="8450f-3221">Passport No</span><span class="sxs-lookup"><span data-stu-id="8450f-3221">Passport No</span></span> 
- <span data-ttu-id="8450f-3222">Passport#</span><span class="sxs-lookup"><span data-stu-id="8450f-3222">Passport #</span></span> 
- <span data-ttu-id="8450f-3223">Passaporto</span><span class="sxs-lookup"><span data-stu-id="8450f-3223">Passport#</span></span> 
- <span data-ttu-id="8450f-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="8450f-3224">PassportID</span></span> 
- <span data-ttu-id="8450f-3225">Passportno</span><span class="sxs-lookup"><span data-stu-id="8450f-3225">Passportno</span></span> 
- <span data-ttu-id="8450f-3226">passportnumber</span><span class="sxs-lookup"><span data-stu-id="8450f-3226">passportnumber</span></span> 
- <span data-ttu-id="8450f-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="8450f-3227">パスポート</span></span> 
- <span data-ttu-id="8450f-3228">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="8450f-3228">パスポート番号</span></span> 
- <span data-ttu-id="8450f-3229">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="8450f-3229">パスポートのNum</span></span> 
- <span data-ttu-id="8450f-3230">パスポート #</span><span class="sxs-lookup"><span data-stu-id="8450f-3230">パスポート＃</span></span> 
- <span data-ttu-id="8450f-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="8450f-3232">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="8450f-3232">Passeport n °</span></span> 
- <span data-ttu-id="8450f-3233">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="8450f-3233">Passeport Non</span></span> 
- <span data-ttu-id="8450f-3234">Passeport#</span><span class="sxs-lookup"><span data-stu-id="8450f-3234">Passeport #</span></span> 
- <span data-ttu-id="8450f-3235">Passeport</span><span class="sxs-lookup"><span data-stu-id="8450f-3235">Passeport#</span></span> 
- <span data-ttu-id="8450f-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="8450f-3236">PasseportNon</span></span> 
- <span data-ttu-id="8450f-3237">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="8450f-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="8450f-3238">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="8450f-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3239">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3239">Format</span></span>

<span data-ttu-id="8450f-3240">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3241">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3241">Pattern</span></span>

<span data-ttu-id="8450f-3242">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="8450f-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3243">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3243">Checksum</span></span>

<span data-ttu-id="8450f-3244">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3245">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3245">Definition</span></span>

<span data-ttu-id="8450f-3246">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3247">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3248">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="8450f-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3249">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="8450f-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="8450f-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="8450f-3251">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3251">Checking Account Number</span></span> 
- <span data-ttu-id="8450f-3252">Checking Account</span><span class="sxs-lookup"><span data-stu-id="8450f-3252">Checking Account</span></span> 
- <span data-ttu-id="8450f-3253">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-3253">Checking Account #</span></span> 
- <span data-ttu-id="8450f-3254">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="8450f-3255">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-3255">Checking Acct #</span></span> 
- <span data-ttu-id="8450f-3256">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="8450f-3257">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3257">Checking Account No.</span></span> 
- <span data-ttu-id="8450f-3258">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3258">Bank Account Number</span></span> 
- <span data-ttu-id="8450f-3259">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-3259">Bank Account #</span></span> 
- <span data-ttu-id="8450f-3260">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="8450f-3261">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-3261">Bank Acct #</span></span> 
- <span data-ttu-id="8450f-3262">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="8450f-3263">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3263">Bank Account No.</span></span> 
- <span data-ttu-id="8450f-3264">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3264">Savings Account Number</span></span> 
- <span data-ttu-id="8450f-3265">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="8450f-3265">Savings Account.</span></span> 
- <span data-ttu-id="8450f-3266">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-3266">Savings Account #</span></span> 
- <span data-ttu-id="8450f-3267">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="8450f-3268">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-3268">Savings Acct #</span></span> 
- <span data-ttu-id="8450f-3269">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="8450f-3270">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3270">Savings Account No.</span></span> 
- <span data-ttu-id="8450f-3271">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3271">Debit Account Number</span></span> 
- <span data-ttu-id="8450f-3272">Debit Account</span><span class="sxs-lookup"><span data-stu-id="8450f-3272">Debit Account</span></span> 
- <span data-ttu-id="8450f-3273">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="8450f-3273">Debit Account #</span></span> 
- <span data-ttu-id="8450f-3274">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="8450f-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="8450f-3275">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="8450f-3275">Debit Acct #</span></span> 
- <span data-ttu-id="8450f-3276">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="8450f-3277">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="8450f-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="8450f-3278">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8450f-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3279">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3279">Format</span></span>

<span data-ttu-id="8450f-3280">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="8450f-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3281">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3281">Pattern</span></span>

<span data-ttu-id="8450f-3282">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="8450f-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="8450f-3283">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="8450f-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="8450f-3284">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="8450f-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3285">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3285">Checksum</span></span>

<span data-ttu-id="8450f-3286">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3287">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3287">Definition</span></span>

<span data-ttu-id="8450f-3288">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3289">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3290">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="8450f-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8450f-3291">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="8450f-3292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3293">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3294">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="8450f-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="8450f-3295">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="8450f-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="8450f-3296">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="8450f-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3297">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="8450f-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="8450f-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="8450f-3299">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-3299">DL</span></span> 
- <span data-ttu-id="8450f-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-3300">DLS</span></span> 
- <span data-ttu-id="8450f-3301">CDL</span><span class="sxs-lookup"><span data-stu-id="8450f-3301">CDL</span></span> 
- <span data-ttu-id="8450f-3302">CDLS</span><span class="sxs-lookup"><span data-stu-id="8450f-3302">CDLS</span></span> 
- <span data-ttu-id="8450f-3303">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-3303">ID</span></span> 
- <span data-ttu-id="8450f-3304">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-3304">IDs</span></span> 
- <span data-ttu-id="8450f-3305">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-3305">DL#</span></span> 
- <span data-ttu-id="8450f-3306">DLS</span><span class="sxs-lookup"><span data-stu-id="8450f-3306">DLS#</span></span> 
- <span data-ttu-id="8450f-3307">CDL</span><span class="sxs-lookup"><span data-stu-id="8450f-3307">CDL#</span></span> 
- <span data-ttu-id="8450f-3308">CDLS</span><span class="sxs-lookup"><span data-stu-id="8450f-3308">CDLS#</span></span> 
- <span data-ttu-id="8450f-3309">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-3309">ID#</span></span>
- <span data-ttu-id="8450f-3310">ID</span><span class="sxs-lookup"><span data-stu-id="8450f-3310">IDs#</span></span> 
- <span data-ttu-id="8450f-3311">ID number</span><span class="sxs-lookup"><span data-stu-id="8450f-3311">ID number</span></span> 
- <span data-ttu-id="8450f-3312">ID numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-3312">ID numbers</span></span> 
- <span data-ttu-id="8450f-3313">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="8450f-3313">LIC</span></span> 
- <span data-ttu-id="8450f-3314">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="8450f-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="8450f-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="8450f-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="8450f-3316">DriverLic</span><span class="sxs-lookup"><span data-stu-id="8450f-3316">DriverLic</span></span> 
- <span data-ttu-id="8450f-3317">DriverLics</span><span class="sxs-lookup"><span data-stu-id="8450f-3317">DriverLics</span></span> 
- <span data-ttu-id="8450f-3318">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-3318">DriverLicense</span></span> 
- <span data-ttu-id="8450f-3319">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3319">DriverLicenses</span></span> 
- <span data-ttu-id="8450f-3320">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-3320">Driver Lic</span></span> 
- <span data-ttu-id="8450f-3321">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-3321">Driver Lics</span></span> 
- <span data-ttu-id="8450f-3322">Driver License</span><span class="sxs-lookup"><span data-stu-id="8450f-3322">Driver License</span></span> 
- <span data-ttu-id="8450f-3323">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3323">Driver Licenses</span></span> 
- <span data-ttu-id="8450f-3324">DriversLic</span><span class="sxs-lookup"><span data-stu-id="8450f-3324">DriversLic</span></span> 
- <span data-ttu-id="8450f-3325">DriversLics</span><span class="sxs-lookup"><span data-stu-id="8450f-3325">DriversLics</span></span> 
- <span data-ttu-id="8450f-3326">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="8450f-3326">DriversLicense</span></span> 
- <span data-ttu-id="8450f-3327">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3327">DriversLicenses</span></span> 
- <span data-ttu-id="8450f-3328">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-3328">Drivers Lic</span></span> 
- <span data-ttu-id="8450f-3329">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-3329">Drivers Lics</span></span> 
- <span data-ttu-id="8450f-3330">Drivers License</span><span class="sxs-lookup"><span data-stu-id="8450f-3330">Drivers License</span></span> 
- <span data-ttu-id="8450f-3331">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="8450f-3332">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-3332">Driver'Lic</span></span> 
- <span data-ttu-id="8450f-3333">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-3333">Driver'Lics</span></span> 
- <span data-ttu-id="8450f-3334">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-3334">Driver'License</span></span> 
- <span data-ttu-id="8450f-3335">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="8450f-3336">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-3336">Driver' Lic</span></span> 
- <span data-ttu-id="8450f-3337">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-3337">Driver' Lics</span></span> 
- <span data-ttu-id="8450f-3338">Driver' License</span><span class="sxs-lookup"><span data-stu-id="8450f-3338">Driver' License</span></span> 
- <span data-ttu-id="8450f-3339">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3339">Driver' Licenses</span></span>
- <span data-ttu-id="8450f-3340">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="8450f-3340">Driver'sLic</span></span> 
- <span data-ttu-id="8450f-3341">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="8450f-3341">Driver'sLics</span></span> 
- <span data-ttu-id="8450f-3342">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="8450f-3343">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="8450f-3344">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="8450f-3344">Driver's Lic</span></span> 
- <span data-ttu-id="8450f-3345">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="8450f-3345">Driver's Lics</span></span> 
- <span data-ttu-id="8450f-3346">Driver's License</span><span class="sxs-lookup"><span data-stu-id="8450f-3346">Driver's License</span></span> 
- <span data-ttu-id="8450f-3347">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="8450f-3348">identification number</span><span class="sxs-lookup"><span data-stu-id="8450f-3348">identification number</span></span> 
- <span data-ttu-id="8450f-3349">identification numbers</span><span class="sxs-lookup"><span data-stu-id="8450f-3349">identification numbers</span></span> 
- <span data-ttu-id="8450f-3350">identification#</span><span class="sxs-lookup"><span data-stu-id="8450f-3350">identification #</span></span> 
- <span data-ttu-id="8450f-3351">id card</span><span class="sxs-lookup"><span data-stu-id="8450f-3351">id card</span></span> 
- <span data-ttu-id="8450f-3352">id cards</span><span class="sxs-lookup"><span data-stu-id="8450f-3352">id cards</span></span> 
- <span data-ttu-id="8450f-3353">identification card</span><span class="sxs-lookup"><span data-stu-id="8450f-3353">identification card</span></span> 
- <span data-ttu-id="8450f-3354">identification cards</span><span class="sxs-lookup"><span data-stu-id="8450f-3354">identification cards</span></span> 
- <span data-ttu-id="8450f-3355">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-3355">DriverLic#</span></span> 
- <span data-ttu-id="8450f-3356">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-3356">DriverLics#</span></span> 
- <span data-ttu-id="8450f-3357">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-3357">DriverLicense#</span></span> 
- <span data-ttu-id="8450f-3358">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="8450f-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-3359">Driver Lic#</span></span> 
- <span data-ttu-id="8450f-3360">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-3360">Driver Lics#</span></span> 
- <span data-ttu-id="8450f-3361">Driver License#</span><span class="sxs-lookup"><span data-stu-id="8450f-3361">Driver License#</span></span> 
- <span data-ttu-id="8450f-3362">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="8450f-3363">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-3363">DriversLic#</span></span> 
- <span data-ttu-id="8450f-3364">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-3364">DriversLics#</span></span> 
- <span data-ttu-id="8450f-3365">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="8450f-3365">DriversLicense#</span></span> 
- <span data-ttu-id="8450f-3366">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="8450f-3367">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="8450f-3368">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="8450f-3369">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="8450f-3369">Drivers License#</span></span> 
- <span data-ttu-id="8450f-3370">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="8450f-3371">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="8450f-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="8450f-3372">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="8450f-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="8450f-3373">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="8450f-3373">Driver'License#</span></span> 
- <span data-ttu-id="8450f-3374">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="8450f-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="8450f-3375">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="8450f-3376">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="8450f-3377">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="8450f-3377">Driver' License#</span></span> 
- <span data-ttu-id="8450f-3378">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="8450f-3379">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="8450f-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="8450f-3380">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="8450f-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="8450f-3381">Secondola</span><span class="sxs-lookup"><span data-stu-id="8450f-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="8450f-3382">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="8450f-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="8450f-3383">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="8450f-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="8450f-3384">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="8450f-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="8450f-3385">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="8450f-3385">Driver's License#</span></span> 
- <span data-ttu-id="8450f-3386">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="8450f-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="8450f-3387">id card#</span><span class="sxs-lookup"><span data-stu-id="8450f-3387">id card#</span></span> 
- <span data-ttu-id="8450f-3388">id cards#</span><span class="sxs-lookup"><span data-stu-id="8450f-3388">id cards#</span></span> 
- <span data-ttu-id="8450f-3389">identification card#</span><span class="sxs-lookup"><span data-stu-id="8450f-3389">identification card#</span></span> 
- <span data-ttu-id="8450f-3390">identification cards#</span><span class="sxs-lookup"><span data-stu-id="8450f-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="8450f-3391">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="8450f-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="8450f-3392">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="8450f-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="8450f-3393">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="8450f-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="8450f-3394">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="8450f-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3395">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3395">Format</span></span>

<span data-ttu-id="8450f-3396">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8450f-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3397">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3397">Pattern</span></span>

<span data-ttu-id="8450f-3398">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-3398">Formatted:</span></span>
- <span data-ttu-id="8450f-3399">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="8450f-3399">The digit "9"</span></span> 
- <span data-ttu-id="8450f-3400">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3400">Two digits</span></span> 
- <span data-ttu-id="8450f-3401">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3401">A space or dash</span></span> 
- <span data-ttu-id="8450f-3402">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="8450f-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="8450f-3403">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8450f-3403">A digit</span></span> 
- <span data-ttu-id="8450f-3404">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="8450f-3404">A space, or dash</span></span> 
- <span data-ttu-id="8450f-3405">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3405">Four digits</span></span>

<span data-ttu-id="8450f-3406">Formattato</span><span class="sxs-lookup"><span data-stu-id="8450f-3406">Unformatted:</span></span>
- <span data-ttu-id="8450f-3407">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="8450f-3407">The digit "9"</span></span> 
- <span data-ttu-id="8450f-3408">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3408">Two digits</span></span> 
- <span data-ttu-id="8450f-3409">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="8450f-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="8450f-3410">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="8450f-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3411">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3411">Checksum</span></span>

<span data-ttu-id="8450f-3412">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="8450f-3413">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3413">Definition</span></span>

<span data-ttu-id="8450f-3414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3415">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3416">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="8450f-3417">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="8450f-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="8450f-3418">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="8450f-3419">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="8450f-3420">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="8450f-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="8450f-3421">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3422">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3423">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8450f-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="8450f-3424">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="8450f-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="8450f-3425">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="8450f-3426">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="8450f-3426">The function Func_us_date finds a date in the right date format.</span></span>

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3427">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="8450f-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="8450f-3428">Keyword_itin</span></span>

- <span data-ttu-id="8450f-3429">contribuente</span><span class="sxs-lookup"><span data-stu-id="8450f-3429">taxpayer</span></span> 
- <span data-ttu-id="8450f-3430">tax id</span><span class="sxs-lookup"><span data-stu-id="8450f-3430">tax id</span></span> 
- <span data-ttu-id="8450f-3431">tax identification</span><span class="sxs-lookup"><span data-stu-id="8450f-3431">tax identification</span></span> 
- <span data-ttu-id="8450f-3432">Itin</span><span class="sxs-lookup"><span data-stu-id="8450f-3432">itin</span></span> 
- <span data-ttu-id="8450f-3433">SSN</span><span class="sxs-lookup"><span data-stu-id="8450f-3433">ssn</span></span> 
- <span data-ttu-id="8450f-3434">latta</span><span class="sxs-lookup"><span data-stu-id="8450f-3434">tin</span></span> 
- <span data-ttu-id="8450f-3435">social security</span><span class="sxs-lookup"><span data-stu-id="8450f-3435">social security</span></span> 
- <span data-ttu-id="8450f-3436">tax payer</span><span class="sxs-lookup"><span data-stu-id="8450f-3436">tax payer</span></span> 
- <span data-ttu-id="8450f-3437">itins</span><span class="sxs-lookup"><span data-stu-id="8450f-3437">itins</span></span> 
- <span data-ttu-id="8450f-3438">taxid</span><span class="sxs-lookup"><span data-stu-id="8450f-3438">taxid</span></span> 
- <span data-ttu-id="8450f-3439">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="8450f-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="8450f-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="8450f-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="8450f-3441">License</span><span class="sxs-lookup"><span data-stu-id="8450f-3441">License</span></span> 
- <span data-ttu-id="8450f-3442">DL</span><span class="sxs-lookup"><span data-stu-id="8450f-3442">DL</span></span> 
- <span data-ttu-id="8450f-3443">DOB</span><span class="sxs-lookup"><span data-stu-id="8450f-3443">DOB</span></span> 
- <span data-ttu-id="8450f-3444">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="8450f-3444">Birthdate</span></span> 
- <span data-ttu-id="8450f-3445">Compleanno</span><span class="sxs-lookup"><span data-stu-id="8450f-3445">Birthday</span></span> 
- <span data-ttu-id="8450f-3446">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="8450f-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="8450f-3447">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="8450f-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="8450f-3448">Formato</span><span class="sxs-lookup"><span data-stu-id="8450f-3448">Format</span></span>

<span data-ttu-id="8450f-3449">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="8450f-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="8450f-3450">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="8450f-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="8450f-3451">Modello</span><span class="sxs-lookup"><span data-stu-id="8450f-3451">Pattern</span></span>

<span data-ttu-id="8450f-3452">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="8450f-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="8450f-3453">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="8450f-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="8450f-3454">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="8450f-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="8450f-3455">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="8450f-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="8450f-3456">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="8450f-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="8450f-3457">Checksum</span><span class="sxs-lookup"><span data-stu-id="8450f-3457">Checksum</span></span>

<span data-ttu-id="8450f-3458">No</span><span class="sxs-lookup"><span data-stu-id="8450f-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="8450f-3459">Definizione</span><span class="sxs-lookup"><span data-stu-id="8450f-3459">Definition</span></span>

<span data-ttu-id="8450f-3460">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3461">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3462">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="8450f-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="8450f-3463">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3464">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3465">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="8450f-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="8450f-3466">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3467">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3468">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="8450f-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="8450f-3469">La funzione Func_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="8450f-3470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8450f-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="8450f-3471">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="8450f-3472">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="8450f-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="8450f-3473">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="8450f-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="8450f-3474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8450f-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="8450f-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="8450f-3475">Keyword_ssn</span></span>

- <span data-ttu-id="8450f-3476">Social Security</span><span class="sxs-lookup"><span data-stu-id="8450f-3476">Social Security</span></span> 
- <span data-ttu-id="8450f-3477">Social Security#</span><span class="sxs-lookup"><span data-stu-id="8450f-3477">Social Security#</span></span> 
- <span data-ttu-id="8450f-3478">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="8450f-3478">Soc Sec</span></span> 
- <span data-ttu-id="8450f-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="8450f-3479">SSN</span></span> 
- <span data-ttu-id="8450f-3480">SNSS</span><span class="sxs-lookup"><span data-stu-id="8450f-3480">SSNS</span></span> 
- <span data-ttu-id="8450f-3481">SSN</span><span class="sxs-lookup"><span data-stu-id="8450f-3481">SSN#</span></span> 
- <span data-ttu-id="8450f-3482">SS</span><span class="sxs-lookup"><span data-stu-id="8450f-3482">SS#</span></span> 
- <span data-ttu-id="8450f-3483">SSID</span><span class="sxs-lookup"><span data-stu-id="8450f-3483">SSID</span></span> 
   

