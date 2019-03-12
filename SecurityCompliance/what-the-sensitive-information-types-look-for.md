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
ms.openlocfilehash: e9811b285e98a791570dc91e275cb5cead4f8bc9
ms.sourcegitcommit: 6e8e2b43a4bea31c1e835c5b050824651c6a0094
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537643"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="0095d-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="0095d-104">What the sensitive information types look for</span></span>

<span data-ttu-id="0095d-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="0095d-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="0095d-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="0095d-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="0095d-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="0095d-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="0095d-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="0095d-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="0095d-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="0095d-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="0095d-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="0095d-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-111">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-111">Format</span></span>

<span data-ttu-id="0095d-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="0095d-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-113">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-113">Pattern</span></span>

<span data-ttu-id="0095d-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-114">Formatted:</span></span>
- <span data-ttu-id="0095d-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="0095d-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="0095d-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-116">A hyphen</span></span>
- <span data-ttu-id="0095d-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-117">Four digits</span></span>
- <span data-ttu-id="0095d-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-118">A hyphen</span></span>
- <span data-ttu-id="0095d-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-119">A digit</span></span>

<span data-ttu-id="0095d-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="0095d-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="0095d-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-121">Checksum</span></span>

<span data-ttu-id="0095d-122">No</span><span class="sxs-lookup"><span data-stu-id="0095d-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-123">Definition</span></span>

<span data-ttu-id="0095d-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="0095d-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="0095d-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="0095d-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="0095d-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="0095d-129">ABA</span><span class="sxs-lookup"><span data-stu-id="0095d-129">aba</span></span>
- <span data-ttu-id="0095d-130">aba #</span><span class="sxs-lookup"><span data-stu-id="0095d-130">aba #</span></span>
- <span data-ttu-id="0095d-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="0095d-131">aba routing #</span></span>
- <span data-ttu-id="0095d-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="0095d-132">aba routing number</span></span>
- <span data-ttu-id="0095d-133">ABA</span><span class="sxs-lookup"><span data-stu-id="0095d-133">aba#</span></span>
- <span data-ttu-id="0095d-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="0095d-134">abarouting#</span></span>
- <span data-ttu-id="0095d-135">aba number</span><span class="sxs-lookup"><span data-stu-id="0095d-135">aba number</span></span>
- <span data-ttu-id="0095d-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-136">abaroutingnumber</span></span>
- <span data-ttu-id="0095d-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="0095d-137">american bank association routing #</span></span>
- <span data-ttu-id="0095d-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="0095d-138">american bank association routing number</span></span>
- <span data-ttu-id="0095d-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="0095d-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="0095d-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="0095d-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="0095d-141">bank routing number</span></span>
- <span data-ttu-id="0095d-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="0095d-142">bankrouting#</span></span>
- <span data-ttu-id="0095d-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-143">bankroutingnumber</span></span>
- <span data-ttu-id="0095d-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="0095d-144">routing transit number</span></span>
- <span data-ttu-id="0095d-145">RTN</span><span class="sxs-lookup"><span data-stu-id="0095d-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="0095d-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="0095d-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-147">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-147">Format</span></span>

<span data-ttu-id="0095d-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="0095d-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-149">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-149">Pattern</span></span>

<span data-ttu-id="0095d-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-150">Eight digits:</span></span>
- <span data-ttu-id="0095d-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-151">Two digits</span></span>
- <span data-ttu-id="0095d-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-152">A period</span></span>
- <span data-ttu-id="0095d-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-153">Three digits</span></span>
- <span data-ttu-id="0095d-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-154">A period</span></span>
- <span data-ttu-id="0095d-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-156">Checksum</span></span>

<span data-ttu-id="0095d-157">No</span><span class="sxs-lookup"><span data-stu-id="0095d-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-158">Definition</span></span>

<span data-ttu-id="0095d-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="0095d-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="0095d-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="0095d-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="0095d-165">Identità</span><span class="sxs-lookup"><span data-stu-id="0095d-165">Identity</span></span> 
- <span data-ttu-id="0095d-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="0095d-167">DNI</span><span class="sxs-lookup"><span data-stu-id="0095d-167">DNI</span></span> 
- <span data-ttu-id="0095d-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="0095d-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="0095d-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="0095d-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="0095d-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="0095d-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="0095d-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="0095d-171">Identidad</span></span> 
- <span data-ttu-id="0095d-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="0095d-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="0095d-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="0095d-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-174">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-174">Format</span></span>

<span data-ttu-id="0095d-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="0095d-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-176">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-176">Pattern</span></span>

<span data-ttu-id="0095d-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="0095d-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="0095d-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="0095d-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="0095d-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-179">Three digits</span></span> 
- <span data-ttu-id="0095d-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-180">A hyphen</span></span> 
- <span data-ttu-id="0095d-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-182">Checksum</span></span>

<span data-ttu-id="0095d-183">No</span><span class="sxs-lookup"><span data-stu-id="0095d-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-184">Definition</span></span>

<span data-ttu-id="0095d-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="0095d-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="0095d-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="0095d-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="0095d-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="0095d-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="0095d-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="0095d-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="0095d-194">swift bank code</span></span>
- <span data-ttu-id="0095d-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="0095d-195">correspondent bank</span></span>
- <span data-ttu-id="0095d-196">base currency</span><span class="sxs-lookup"><span data-stu-id="0095d-196">base currency</span></span>
- <span data-ttu-id="0095d-197">usa account</span><span class="sxs-lookup"><span data-stu-id="0095d-197">usa account</span></span>
- <span data-ttu-id="0095d-198">holder address</span><span class="sxs-lookup"><span data-stu-id="0095d-198">holder address</span></span>
- <span data-ttu-id="0095d-199">bank address</span><span class="sxs-lookup"><span data-stu-id="0095d-199">bank address</span></span>
- <span data-ttu-id="0095d-200">information account</span><span class="sxs-lookup"><span data-stu-id="0095d-200">information account</span></span>
- <span data-ttu-id="0095d-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="0095d-201">fund transfers</span></span>
- <span data-ttu-id="0095d-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="0095d-202">bank charges</span></span>
- <span data-ttu-id="0095d-203">bank details</span><span class="sxs-lookup"><span data-stu-id="0095d-203">bank details</span></span>
- <span data-ttu-id="0095d-204">banking information</span><span class="sxs-lookup"><span data-stu-id="0095d-204">banking information</span></span>
- <span data-ttu-id="0095d-205">full names</span><span class="sxs-lookup"><span data-stu-id="0095d-205">full names</span></span>
- <span data-ttu-id="0095d-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="0095d-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="0095d-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-208">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-208">Format</span></span>

<span data-ttu-id="0095d-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="0095d-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-210">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-210">Pattern</span></span>

<span data-ttu-id="0095d-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="0095d-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="0095d-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-213">Two digits</span></span> 
- <span data-ttu-id="0095d-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="0095d-215">O</span><span class="sxs-lookup"><span data-stu-id="0095d-215">OR</span></span>

- <span data-ttu-id="0095d-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-217">4-9 digits</span></span>

<span data-ttu-id="0095d-218">O</span><span class="sxs-lookup"><span data-stu-id="0095d-218">OR</span></span>

- <span data-ttu-id="0095d-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-220">Checksum</span></span>

<span data-ttu-id="0095d-221">No</span><span class="sxs-lookup"><span data-stu-id="0095d-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-222">Definition</span></span>

<span data-ttu-id="0095d-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="0095d-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="0095d-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="0095d-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="0095d-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="0095d-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="0095d-229">international driving permits</span></span>
- <span data-ttu-id="0095d-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="0095d-230">australian automobile association</span></span>
- <span data-ttu-id="0095d-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="0095d-231">international driving permit</span></span>
- <span data-ttu-id="0095d-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-232">DriverLicence</span></span>
- <span data-ttu-id="0095d-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-233">DriverLicences</span></span>
- <span data-ttu-id="0095d-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-234">Driver Lic</span></span>
- <span data-ttu-id="0095d-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-235">Driver Licence</span></span>
- <span data-ttu-id="0095d-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-236">Driver Licences</span></span>
- <span data-ttu-id="0095d-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="0095d-237">DriversLic</span></span>
- <span data-ttu-id="0095d-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-238">DriversLicence</span></span>
- <span data-ttu-id="0095d-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-239">DriversLicences</span></span>
- <span data-ttu-id="0095d-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-240">Drivers Lic</span></span>
- <span data-ttu-id="0095d-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-241">Drivers Lics</span></span>
- <span data-ttu-id="0095d-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-242">Drivers Licence</span></span>
- <span data-ttu-id="0095d-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-243">Drivers Licences</span></span>
- <span data-ttu-id="0095d-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-244">Driver'Lic</span></span>
- <span data-ttu-id="0095d-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-245">Driver'Lics</span></span>
- <span data-ttu-id="0095d-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-246">Driver'Licence</span></span>
- <span data-ttu-id="0095d-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-247">Driver'Licences</span></span>
- <span data-ttu-id="0095d-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-248">Driver' Lic</span></span>
- <span data-ttu-id="0095d-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-249">Driver' Lics</span></span>
- <span data-ttu-id="0095d-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-250">Driver' Licence</span></span>
- <span data-ttu-id="0095d-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-251">Driver' Licences</span></span>
- <span data-ttu-id="0095d-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="0095d-252">Driver'sLic</span></span>
- <span data-ttu-id="0095d-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="0095d-253">Driver'sLics</span></span>
- <span data-ttu-id="0095d-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-254">Driver'sLicence</span></span>
- <span data-ttu-id="0095d-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-255">Driver'sLicences</span></span>
- <span data-ttu-id="0095d-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-256">Driver's Lic</span></span>
- <span data-ttu-id="0095d-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-257">Driver's Lics</span></span>
- <span data-ttu-id="0095d-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-258">Driver's Licence</span></span>
- <span data-ttu-id="0095d-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-259">Driver's Licences</span></span>
- <span data-ttu-id="0095d-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-260">DriverLic#</span></span>
- <span data-ttu-id="0095d-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-261">DriverLics#</span></span>
- <span data-ttu-id="0095d-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-262">DriverLicence#</span></span>
- <span data-ttu-id="0095d-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-263">DriverLicences#</span></span>
- <span data-ttu-id="0095d-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-264">Driver Lic#</span></span>
- <span data-ttu-id="0095d-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-265">Driver Lics#</span></span>
- <span data-ttu-id="0095d-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-266">Driver Licence#</span></span>
- <span data-ttu-id="0095d-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-267">Driver Licences#</span></span>
- <span data-ttu-id="0095d-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-268">DriversLic#</span></span>
- <span data-ttu-id="0095d-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-269">DriversLics#</span></span>
- <span data-ttu-id="0095d-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-270">DriversLicence#</span></span>
- <span data-ttu-id="0095d-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-271">DriversLicences#</span></span>
- <span data-ttu-id="0095d-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-272">Drivers Lic#</span></span>
- <span data-ttu-id="0095d-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-273">Drivers Lics#</span></span>
- <span data-ttu-id="0095d-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-274">Drivers Licence#</span></span>
- <span data-ttu-id="0095d-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-275">Drivers Licences#</span></span>
- <span data-ttu-id="0095d-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="0095d-276">Driver'Lic#</span></span>
- <span data-ttu-id="0095d-277">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-277">Driver'Lics#</span></span>
- <span data-ttu-id="0095d-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="0095d-278">Driver'Licence#</span></span>
- <span data-ttu-id="0095d-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="0095d-279">Driver'Licences#</span></span>
- <span data-ttu-id="0095d-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-280">Driver' Lic#</span></span>
- <span data-ttu-id="0095d-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-281">Driver' Lics#</span></span>
- <span data-ttu-id="0095d-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-282">Driver' Licence#</span></span>
- <span data-ttu-id="0095d-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-283">Driver' Licences#</span></span>
- <span data-ttu-id="0095d-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-284">Driver'sLic#</span></span>
- <span data-ttu-id="0095d-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-285">Driver'sLics#</span></span>
- <span data-ttu-id="0095d-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-286">Driver'sLicence#</span></span>
- <span data-ttu-id="0095d-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-287">Driver'sLicences#</span></span>
- <span data-ttu-id="0095d-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-288">Driver's Lic#</span></span>
- <span data-ttu-id="0095d-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-289">Driver's Lics#</span></span>
- <span data-ttu-id="0095d-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-290">Driver's Licence#</span></span>
- <span data-ttu-id="0095d-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="0095d-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="0095d-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="0095d-293">AAA</span><span class="sxs-lookup"><span data-stu-id="0095d-293">aaa</span></span>
- <span data-ttu-id="0095d-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-294">DriverLicense</span></span>
- <span data-ttu-id="0095d-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-295">DriverLicenses</span></span>
- <span data-ttu-id="0095d-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="0095d-296">Driver License</span></span>
- <span data-ttu-id="0095d-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-297">Driver Licenses</span></span>
- <span data-ttu-id="0095d-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-298">DriversLicense</span></span>
- <span data-ttu-id="0095d-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-299">DriversLicenses</span></span>
- <span data-ttu-id="0095d-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="0095d-300">Drivers License</span></span>
- <span data-ttu-id="0095d-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-301">Drivers Licenses</span></span>
- <span data-ttu-id="0095d-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-302">Driver'License</span></span>
- <span data-ttu-id="0095d-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-303">Driver'Licenses</span></span>
- <span data-ttu-id="0095d-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="0095d-304">Driver' License</span></span>
- <span data-ttu-id="0095d-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-305">Driver' Licenses</span></span>
- <span data-ttu-id="0095d-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-306">Driver'sLicense</span></span>
- <span data-ttu-id="0095d-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-307">Driver'sLicenses</span></span>
- <span data-ttu-id="0095d-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="0095d-308">Driver's License</span></span>
- <span data-ttu-id="0095d-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-309">Driver's Licenses</span></span>
- <span data-ttu-id="0095d-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-310">DriverLicense#</span></span>
- <span data-ttu-id="0095d-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-311">DriverLicenses#</span></span>
- <span data-ttu-id="0095d-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="0095d-312">Driver License#</span></span>
- <span data-ttu-id="0095d-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-313">Driver Licenses#</span></span>
- <span data-ttu-id="0095d-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-314">DriversLicense#</span></span>
- <span data-ttu-id="0095d-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-315">DriversLicenses#</span></span>
- <span data-ttu-id="0095d-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="0095d-316">Drivers License#</span></span>
- <span data-ttu-id="0095d-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-317">Drivers Licenses#</span></span>
- <span data-ttu-id="0095d-318">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-318">Driver'License#</span></span>
- <span data-ttu-id="0095d-319">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-319">Driver'Licenses#</span></span>
- <span data-ttu-id="0095d-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="0095d-320">Driver' License#</span></span>
- <span data-ttu-id="0095d-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-321">Driver' Licenses#</span></span>
- <span data-ttu-id="0095d-322">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-322">Driver'sLicense#</span></span>
- <span data-ttu-id="0095d-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="0095d-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="0095d-324">Driver's License#</span></span>
- <span data-ttu-id="0095d-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="0095d-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="0095d-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-327">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-327">Format</span></span>

<span data-ttu-id="0095d-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-329">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-329">Pattern</span></span>

<span data-ttu-id="0095d-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-330">10-11 digits:</span></span>
- <span data-ttu-id="0095d-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="0095d-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="0095d-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="0095d-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="0095d-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="0095d-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="0095d-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-335">Checksum</span></span>

<span data-ttu-id="0095d-336">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-337">Definition</span></span>

<span data-ttu-id="0095d-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="0095d-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="0095d-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-341">The checksum passes.</span></span>

<span data-ttu-id="0095d-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="0095d-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="0095d-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="0095d-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="0095d-347">bank account details</span></span>
- <span data-ttu-id="0095d-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="0095d-348">medicare payments</span></span>
- <span data-ttu-id="0095d-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="0095d-349">mortgage account</span></span>
- <span data-ttu-id="0095d-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="0095d-350">bank payments</span></span>
- <span data-ttu-id="0095d-351">information branch</span><span class="sxs-lookup"><span data-stu-id="0095d-351">information branch</span></span>
- <span data-ttu-id="0095d-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="0095d-352">credit card loan</span></span>
- <span data-ttu-id="0095d-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="0095d-353">department of human services</span></span>
- <span data-ttu-id="0095d-354">local service</span><span class="sxs-lookup"><span data-stu-id="0095d-354">local service</span></span>
- <span data-ttu-id="0095d-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="0095d-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="0095d-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-357">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-357">Format</span></span>

<span data-ttu-id="0095d-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-359">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-359">Pattern</span></span>

<span data-ttu-id="0095d-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-361">Checksum</span></span>

<span data-ttu-id="0095d-362">No</span><span class="sxs-lookup"><span data-stu-id="0095d-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-363">Definition</span></span>

<span data-ttu-id="0095d-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="0095d-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-368">Keyword_passport</span></span>

- <span data-ttu-id="0095d-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="0095d-369">Passport Number</span></span>
- <span data-ttu-id="0095d-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="0095d-370">Passport No</span></span>
- <span data-ttu-id="0095d-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="0095d-371">Passport #</span></span>
- <span data-ttu-id="0095d-372">Passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-372">Passport#</span></span>
- <span data-ttu-id="0095d-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="0095d-373">PassportID</span></span>
- <span data-ttu-id="0095d-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="0095d-374">Passportno</span></span>
- <span data-ttu-id="0095d-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-375">passportnumber</span></span>
- <span data-ttu-id="0095d-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-376">パスポート</span></span>
- <span data-ttu-id="0095d-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-377">パスポート番号</span></span>
- <span data-ttu-id="0095d-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-378">パスポートのNum</span></span>
- <span data-ttu-id="0095d-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="0095d-379">パスポート ＃</span></span> 
- <span data-ttu-id="0095d-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-380">Numéro de passeport</span></span>
- <span data-ttu-id="0095d-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="0095d-381">Passeport n °</span></span>
- <span data-ttu-id="0095d-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="0095d-382">Passeport Non</span></span>
- <span data-ttu-id="0095d-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="0095d-383">Passeport #</span></span>
- <span data-ttu-id="0095d-384">Passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-384">Passeport#</span></span>
- <span data-ttu-id="0095d-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="0095d-385">PasseportNon</span></span>
- <span data-ttu-id="0095d-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="0095d-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="0095d-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="0095d-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="0095d-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-388">passport</span></span>
- <span data-ttu-id="0095d-389">passport details</span><span class="sxs-lookup"><span data-stu-id="0095d-389">passport details</span></span>
- <span data-ttu-id="0095d-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="0095d-390">immigration and citizenship</span></span>
- <span data-ttu-id="0095d-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="0095d-391">commonwealth of australia</span></span>
- <span data-ttu-id="0095d-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="0095d-392">department of immigration</span></span>
- <span data-ttu-id="0095d-393">residential address</span><span class="sxs-lookup"><span data-stu-id="0095d-393">residential address</span></span>
- <span data-ttu-id="0095d-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="0095d-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="0095d-395">esempio</span><span class="sxs-lookup"><span data-stu-id="0095d-395">visa</span></span>
- <span data-ttu-id="0095d-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="0095d-396">national identity card</span></span>
- <span data-ttu-id="0095d-397">passport number</span><span class="sxs-lookup"><span data-stu-id="0095d-397">passport number</span></span>
- <span data-ttu-id="0095d-398">travel document</span><span class="sxs-lookup"><span data-stu-id="0095d-398">travel document</span></span>
- <span data-ttu-id="0095d-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="0095d-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="0095d-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="0095d-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-401">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-401">Format</span></span>

<span data-ttu-id="0095d-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-403">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-403">Pattern</span></span>

<span data-ttu-id="0095d-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0095d-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="0095d-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-405">Three digits</span></span> 
- <span data-ttu-id="0095d-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="0095d-406">An optional space</span></span> 
- <span data-ttu-id="0095d-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-407">Three digits</span></span> 
- <span data-ttu-id="0095d-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="0095d-408">An optional space</span></span> 
- <span data-ttu-id="0095d-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-410">Checksum</span></span>

<span data-ttu-id="0095d-411">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-412">Definition</span></span>

<span data-ttu-id="0095d-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="0095d-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="0095d-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="0095d-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="0095d-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="0095d-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="0095d-419">australian business number</span></span>
- <span data-ttu-id="0095d-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="0095d-420">marginal tax rate</span></span>
- <span data-ttu-id="0095d-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="0095d-421">medicare levy</span></span>
- <span data-ttu-id="0095d-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="0095d-422">portfolio number</span></span>
- <span data-ttu-id="0095d-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="0095d-423">service veterans</span></span>
- <span data-ttu-id="0095d-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="0095d-424">withholding tax</span></span>
- <span data-ttu-id="0095d-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="0095d-425">individual tax return</span></span>
- <span data-ttu-id="0095d-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="0095d-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="0095d-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="0095d-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="0095d-428">00000000</span><span class="sxs-lookup"><span data-stu-id="0095d-428">00000000</span></span>
- <span data-ttu-id="0095d-429">11111111</span><span class="sxs-lookup"><span data-stu-id="0095d-429">11111111</span></span>
- <span data-ttu-id="0095d-430">22222222</span><span class="sxs-lookup"><span data-stu-id="0095d-430">22222222</span></span>
- <span data-ttu-id="0095d-431">33333333</span><span class="sxs-lookup"><span data-stu-id="0095d-431">33333333</span></span>
- <span data-ttu-id="0095d-432">44444444</span><span class="sxs-lookup"><span data-stu-id="0095d-432">44444444</span></span>
- <span data-ttu-id="0095d-433">55555555</span><span class="sxs-lookup"><span data-stu-id="0095d-433">55555555</span></span>
- <span data-ttu-id="0095d-434">66666666</span><span class="sxs-lookup"><span data-stu-id="0095d-434">66666666</span></span>
- <span data-ttu-id="0095d-435">77777777</span><span class="sxs-lookup"><span data-stu-id="0095d-435">77777777</span></span>
- <span data-ttu-id="0095d-436">88888888</span><span class="sxs-lookup"><span data-stu-id="0095d-436">88888888</span></span>
- <span data-ttu-id="0095d-437">99999999</span><span class="sxs-lookup"><span data-stu-id="0095d-437">99999999</span></span>
- <span data-ttu-id="0095d-438">000000000</span><span class="sxs-lookup"><span data-stu-id="0095d-438">000000000</span></span>
- <span data-ttu-id="0095d-439">111111111</span><span class="sxs-lookup"><span data-stu-id="0095d-439">111111111</span></span>
- <span data-ttu-id="0095d-440">222222222</span><span class="sxs-lookup"><span data-stu-id="0095d-440">222222222</span></span>
- <span data-ttu-id="0095d-441">333333333</span><span class="sxs-lookup"><span data-stu-id="0095d-441">333333333</span></span>
- <span data-ttu-id="0095d-442">444444444</span><span class="sxs-lookup"><span data-stu-id="0095d-442">444444444</span></span>
- <span data-ttu-id="0095d-443">555555555</span><span class="sxs-lookup"><span data-stu-id="0095d-443">555555555</span></span>
- <span data-ttu-id="0095d-444">666666666</span><span class="sxs-lookup"><span data-stu-id="0095d-444">666666666</span></span>
- <span data-ttu-id="0095d-445">777777777</span><span class="sxs-lookup"><span data-stu-id="0095d-445">777777777</span></span>
- <span data-ttu-id="0095d-446">888888888</span><span class="sxs-lookup"><span data-stu-id="0095d-446">888888888</span></span>
- <span data-ttu-id="0095d-447">999999999</span><span class="sxs-lookup"><span data-stu-id="0095d-447">999999999</span></span>
- <span data-ttu-id="0095d-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="0095d-448">0000000000</span></span>
- <span data-ttu-id="0095d-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="0095d-449">1111111111</span></span>
- <span data-ttu-id="0095d-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="0095d-450">2222222222</span></span>
- <span data-ttu-id="0095d-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="0095d-451">3333333333</span></span>
- <span data-ttu-id="0095d-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="0095d-452">4444444444</span></span>
- <span data-ttu-id="0095d-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="0095d-453">5555555555</span></span>
- <span data-ttu-id="0095d-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="0095d-454">6666666666</span></span>
- <span data-ttu-id="0095d-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="0095d-455">7777777777</span></span>
- <span data-ttu-id="0095d-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="0095d-456">8888888888</span></span>
- <span data-ttu-id="0095d-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="0095d-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="0095d-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="0095d-459">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-459">Format</span></span>

<span data-ttu-id="0095d-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="0095d-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-461">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-461">Pattern</span></span>

- <span data-ttu-id="0095d-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="0095d-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="0095d-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="0095d-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="0095d-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-467">Checksum</span></span>

<span data-ttu-id="0095d-468">No</span><span class="sxs-lookup"><span data-stu-id="0095d-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-469">Definition</span></span>

<span data-ttu-id="0095d-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-472">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-476">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-476">contoso</span></span>
- <span data-ttu-id="0095d-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-477">fabrikam</span></span>
- <span data-ttu-id="0095d-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-478">northwind</span></span>
- <span data-ttu-id="0095d-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-479">sandbox</span></span>
- <span data-ttu-id="0095d-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-480">onebox</span></span>
- <span data-ttu-id="0095d-481">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-481">localhost</span></span>
- <span data-ttu-id="0095d-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-482">127.0.0.1</span></span>
- <span data-ttu-id="0095d-483">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-483">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-484">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-484">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="0095d-485">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-485">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="0095d-486">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-486">Format</span></span>

<span data-ttu-id="0095d-487">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure. <!--no-hyperlink-->com "o" cloudapp. Azure. <!--no-hyperlink-->NET "o" database. Windows. <!--no-hyperlink-->NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="0095d-487">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.<!--no-hyperlink-->com" or "cloudapp.azure.<!--no-hyperlink-->net" or "database.windows.<!--no-hyperlink-->net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-488">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-488">Pattern</span></span>

- <span data-ttu-id="0095d-489">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="0095d-489">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="0095d-490">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-490">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-491">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-491">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-492">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-492">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-493">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-493">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-494">La stringa "cloudapp. Azure. <!--no-hyperlink-->com "," cloudapp. Azure. <!--no-hyperlink-->NET "o" database. Windows. <!--no-hyperlink-->NET "</span><span class="sxs-lookup"><span data-stu-id="0095d-494">The string "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", or "database.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="0095d-495">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-495">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-496">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="0095d-496">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="0095d-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-498">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-498">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-499">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-499">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-500">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="0095d-500">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="0095d-501">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="0095d-501">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-502">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-502">Checksum</span></span>

<span data-ttu-id="0095d-503">No</span><span class="sxs-lookup"><span data-stu-id="0095d-503">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-504">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-504">Definition</span></span>

<span data-ttu-id="0095d-505">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-505">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-506">L'espressione regolare CEP_Regex_AzureConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-506">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-507">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-507">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-508">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-508">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-509">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-509">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-510">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-510">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-511">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-511">contoso</span></span>
- <span data-ttu-id="0095d-512">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-512">fabrikam</span></span>
- <span data-ttu-id="0095d-513">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-513">northwind</span></span>
- <span data-ttu-id="0095d-514">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-514">sandbox</span></span>
- <span data-ttu-id="0095d-515">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-515">onebox</span></span>
- <span data-ttu-id="0095d-516">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-516">localhost</span></span>
- <span data-ttu-id="0095d-517">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-517">127.0.0.1</span></span>
- <span data-ttu-id="0095d-518">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-518">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-519">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-519">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="0095d-520">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0095d-520">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="0095d-521">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-521">Format</span></span>

<span data-ttu-id="0095d-522">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices. <!--no-hyperlink-->NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="0095d-522">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.<!--no-hyperlink-->net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-523">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-523">Pattern</span></span>

- <span data-ttu-id="0095d-524">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="0095d-524">The string "HostName"</span></span>
- <span data-ttu-id="0095d-525">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-525">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-526">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-526">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-527">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-527">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-528">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-528">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-529">La stringa "Azure-Devices. <!--no-hyperlink-->NET "</span><span class="sxs-lookup"><span data-stu-id="0095d-529">The string "azure-devices.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="0095d-530">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-530">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-531">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="0095d-531">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="0095d-532">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-532">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-533">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-533">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-534">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-534">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-535">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-535">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-536">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-536">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-537">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-537">Checksum</span></span>

<span data-ttu-id="0095d-538">No</span><span class="sxs-lookup"><span data-stu-id="0095d-538">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-539">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-539">Definition</span></span>

<span data-ttu-id="0095d-540">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-540">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-541">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-541">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-542">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-542">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-543">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-543">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-544">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-544">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-545">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-545">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-546">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-546">contoso</span></span>
- <span data-ttu-id="0095d-547">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-547">fabrikam</span></span>
- <span data-ttu-id="0095d-548">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-548">northwind</span></span>
- <span data-ttu-id="0095d-549">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-549">sandbox</span></span>
- <span data-ttu-id="0095d-550">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-550">onebox</span></span>
- <span data-ttu-id="0095d-551">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-551">localhost</span></span>
- <span data-ttu-id="0095d-552">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-552">127.0.0.1</span></span>
- <span data-ttu-id="0095d-553">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-553">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-554">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-554">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="0095d-555">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-555">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="0095d-556">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-556">Format</span></span>

<span data-ttu-id="0095d-557">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="0095d-557">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-558">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-558">Pattern</span></span>

- <span data-ttu-id="0095d-559">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="0095d-559">The string "userpwd="</span></span>
- <span data-ttu-id="0095d-560">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="0095d-560">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="0095d-561">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="0095d-561">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-562">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-562">Checksum</span></span>

<span data-ttu-id="0095d-563">No</span><span class="sxs-lookup"><span data-stu-id="0095d-563">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-564">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-564">Definition</span></span>

<span data-ttu-id="0095d-565">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-565">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-566">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-566">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-567">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-567">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-568">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-568">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-569">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-569">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-570">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-570">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-571">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-571">contoso</span></span>
- <span data-ttu-id="0095d-572">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-572">fabrikam</span></span>
- <span data-ttu-id="0095d-573">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-573">northwind</span></span>
- <span data-ttu-id="0095d-574">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-574">sandbox</span></span>
- <span data-ttu-id="0095d-575">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-575">onebox</span></span>
- <span data-ttu-id="0095d-576">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-576">localhost</span></span>
- <span data-ttu-id="0095d-577">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-577">127.0.0.1</span></span>
- <span data-ttu-id="0095d-578">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-578">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-579">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-579">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="0095d-580">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="0095d-580">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="0095d-581">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-581">Format</span></span>

<span data-ttu-id="0095d-582">La stringa "Redis. cache. Windows. <!--no-hyperlink-->NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="0095d-582">The string "redis.cache.windows.<!--no-hyperlink-->net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-583">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-583">Pattern</span></span>

- <span data-ttu-id="0095d-584">La stringa "Redis. cache. Windows. <!--no-hyperlink-->NET "</span><span class="sxs-lookup"><span data-stu-id="0095d-584">The string "redis.cache.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="0095d-585">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-585">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-586">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="0095d-586">The string "password" or "pwd"</span></span>
- <span data-ttu-id="0095d-587">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-587">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-588">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-588">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-589">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-589">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-590">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-590">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-591">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-591">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-592">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-592">Checksum</span></span>

<span data-ttu-id="0095d-593">No</span><span class="sxs-lookup"><span data-stu-id="0095d-593">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-594">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-594">Definition</span></span>

<span data-ttu-id="0095d-595">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-596">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-596">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="0095d-597">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-597">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-598">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-598">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-599">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-599">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-600">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-600">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-601">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-601">contoso</span></span>
- <span data-ttu-id="0095d-602">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-602">fabrikam</span></span>
- <span data-ttu-id="0095d-603">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-603">northwind</span></span>
- <span data-ttu-id="0095d-604">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-604">sandbox</span></span>
- <span data-ttu-id="0095d-605">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-605">onebox</span></span>
- <span data-ttu-id="0095d-606">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-606">localhost</span></span>
- <span data-ttu-id="0095d-607">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-607">127.0.0.1</span></span>
- <span data-ttu-id="0095d-608">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-608">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-609">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-609">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="0095d-610">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-610">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="0095d-611">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-611">Format</span></span>

<span data-ttu-id="0095d-612">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="0095d-612">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-613">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-613">Pattern</span></span>

- <span data-ttu-id="0095d-614">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="0095d-614">The string "sig"</span></span>
- <span data-ttu-id="0095d-615">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-615">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-616">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-616">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-617">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-617">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-618">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="0095d-618">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="0095d-619">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="0095d-619">The string "%3d"</span></span>
- <span data-ttu-id="0095d-620">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="0095d-620">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-621">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-621">Checksum</span></span>

<span data-ttu-id="0095d-622">No</span><span class="sxs-lookup"><span data-stu-id="0095d-622">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-623">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-623">Definition</span></span>

<span data-ttu-id="0095d-624">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-625">L'espressione regolare CEP_Regex_AzureSAS trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-625">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="0095d-626">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-626">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="0095d-627">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-627">Format</span></span>

<span data-ttu-id="0095d-628">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows. <!--no-hyperlink-->NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="0095d-628">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.<!--no-hyperlink-->net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-629">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-629">Pattern</span></span>

- <span data-ttu-id="0095d-630">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="0095d-630">The string "EndPoint"</span></span>
- <span data-ttu-id="0095d-631">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-631">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-632">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-632">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-633">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-633">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-634">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-634">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-635">La stringa "ServiceBus. Windows. <!--no-hyperlink-->NET "</span><span class="sxs-lookup"><span data-stu-id="0095d-635">The string "servicebus.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="0095d-636">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-636">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-637">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="0095d-637">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="0095d-638">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-638">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-639">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-639">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-640">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-640">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-641">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-641">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-642">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-642">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-643">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-643">Checksum</span></span>

<span data-ttu-id="0095d-644">No</span><span class="sxs-lookup"><span data-stu-id="0095d-644">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-645">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-645">Definition</span></span>

<span data-ttu-id="0095d-646">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-646">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-647">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-647">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="0095d-648">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-648">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-649">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-649">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-650">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-650">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-651">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-651">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-652">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-652">contoso</span></span>
- <span data-ttu-id="0095d-653">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-653">fabrikam</span></span>
- <span data-ttu-id="0095d-654">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-654">northwind</span></span>
- <span data-ttu-id="0095d-655">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-655">sandbox</span></span>
- <span data-ttu-id="0095d-656">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-656">onebox</span></span>
- <span data-ttu-id="0095d-657">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-657">localhost</span></span>
- <span data-ttu-id="0095d-658">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-658">127.0.0.1</span></span>
- <span data-ttu-id="0095d-659">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-659">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-660">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-660">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="0095d-661">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="0095d-661">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="0095d-662">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-662">Format</span></span>

<span data-ttu-id="0095d-663">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="0095d-663">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-664">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-664">Pattern</span></span>

- <span data-ttu-id="0095d-665">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="0095d-665">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="0095d-666">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-666">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-667">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-667">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-668">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-668">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-669">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-669">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-670">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="0095d-670">The string "AccountKey"</span></span>
- <span data-ttu-id="0095d-671">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-671">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-672">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-672">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-673">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-673">0-2 whitespace characters</span></span>
- <span data-ttu-id="0095d-674">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-674">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-675">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-675">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-676">Checksum</span></span>

<span data-ttu-id="0095d-677">No</span><span class="sxs-lookup"><span data-stu-id="0095d-677">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-678">Definition</span></span>

<span data-ttu-id="0095d-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-679">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-680">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-680">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-681">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-681">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-682">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-682">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-683">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-683">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="0095d-684">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="0095d-684">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="0095d-685">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-685">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="0095d-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-687">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-687">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-688">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-688">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-689">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-689">contoso</span></span>
- <span data-ttu-id="0095d-690">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-690">fabrikam</span></span>
- <span data-ttu-id="0095d-691">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-691">northwind</span></span>
- <span data-ttu-id="0095d-692">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-692">sandbox</span></span>
- <span data-ttu-id="0095d-693">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-693">onebox</span></span>
- <span data-ttu-id="0095d-694">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-694">localhost</span></span>
- <span data-ttu-id="0095d-695">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-695">127.0.0.1</span></span>
- <span data-ttu-id="0095d-696">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-696">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-697">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-697">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="0095d-698">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="0095d-698">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-699">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-699">Format</span></span>

<span data-ttu-id="0095d-700">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="0095d-700">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-701">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-701">Pattern</span></span>

- <span data-ttu-id="0095d-702">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="0095d-702">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="0095d-703">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="0095d-703">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="0095d-704">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-704">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="0095d-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-705">Checksum</span></span>

<span data-ttu-id="0095d-706">No</span><span class="sxs-lookup"><span data-stu-id="0095d-706">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-707">Definition</span></span>

<span data-ttu-id="0095d-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-708">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-709">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-709">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="0095d-710">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-710">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-711">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-711">Format</span></span>

<span data-ttu-id="0095d-712">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="0095d-712">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-713">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-713">Pattern</span></span>

<span data-ttu-id="0095d-714">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="0095d-714">11 digits plus delimiters:</span></span>
- <span data-ttu-id="0095d-715">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="0095d-715">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="0095d-716">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-716">A hyphen</span></span> 
- <span data-ttu-id="0095d-717">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="0095d-717">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="0095d-718">Un punto</span><span class="sxs-lookup"><span data-stu-id="0095d-718">A period</span></span> 
- <span data-ttu-id="0095d-719">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-719">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-720">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-720">Checksum</span></span>

<span data-ttu-id="0095d-721">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-721">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-722">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-722">Definition</span></span>

<span data-ttu-id="0095d-723">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-723">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-724">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-724">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-725">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-725">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="0095d-726">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-726">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-727">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-727">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="0095d-728">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="0095d-728">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="0095d-729">Identità</span><span class="sxs-lookup"><span data-stu-id="0095d-729">Identity</span></span>
- <span data-ttu-id="0095d-730">Registrazione</span><span class="sxs-lookup"><span data-stu-id="0095d-730">Registration</span></span>
- <span data-ttu-id="0095d-731">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-731">Identification</span></span> 
- <span data-ttu-id="0095d-732">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-732">ID</span></span> 
- <span data-ttu-id="0095d-733">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="0095d-733">Identiteitskaart</span></span>
- <span data-ttu-id="0095d-734">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="0095d-734">Registratie nummer</span></span> 
- <span data-ttu-id="0095d-735">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="0095d-735">Identificatie nummer</span></span> 
- <span data-ttu-id="0095d-736">Identiteit</span><span class="sxs-lookup"><span data-stu-id="0095d-736">Identiteit</span></span>
- <span data-ttu-id="0095d-737">Registratie</span><span class="sxs-lookup"><span data-stu-id="0095d-737">Registratie</span></span>
- <span data-ttu-id="0095d-738">Identificatie</span><span class="sxs-lookup"><span data-stu-id="0095d-738">Identificatie</span></span> 
- <span data-ttu-id="0095d-739">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="0095d-739">Carte d’identité</span></span> 
- <span data-ttu-id="0095d-740">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="0095d-740">numéro d'immatriculation</span></span>
- <span data-ttu-id="0095d-741">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="0095d-741">numéro d'identification</span></span>
- <span data-ttu-id="0095d-742">identité</span><span class="sxs-lookup"><span data-stu-id="0095d-742">identité</span></span> 
- <span data-ttu-id="0095d-743">iscrizione</span><span class="sxs-lookup"><span data-stu-id="0095d-743">inscription</span></span> 
- <span data-ttu-id="0095d-744">Identifikation</span><span class="sxs-lookup"><span data-stu-id="0095d-744">Identifikation</span></span>
- <span data-ttu-id="0095d-745">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="0095d-745">Identifizierung</span></span>
- <span data-ttu-id="0095d-746">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-746">Identifikationsnummer</span></span>
- <span data-ttu-id="0095d-747">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="0095d-747">Personalausweis</span></span>
- <span data-ttu-id="0095d-748">Registrierung</span><span class="sxs-lookup"><span data-stu-id="0095d-748">Registrierung</span></span>
- <span data-ttu-id="0095d-749">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-749">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="0095d-750">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="0095d-750">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-751">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-751">Format</span></span>

<span data-ttu-id="0095d-752">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="0095d-752">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-753">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-753">Pattern</span></span>

<span data-ttu-id="0095d-754">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-754">Formatted:</span></span>
- <span data-ttu-id="0095d-755">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-755">Three digits</span></span> 
- <span data-ttu-id="0095d-756">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-756">A period</span></span> 
- <span data-ttu-id="0095d-757">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-757">Three digits</span></span> 
- <span data-ttu-id="0095d-758">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-758">A period</span></span> 
- <span data-ttu-id="0095d-759">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-759">Three digits</span></span> 
- <span data-ttu-id="0095d-760">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-760">A hyphen</span></span> 
- <span data-ttu-id="0095d-761">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-761">Two digits which are check digits</span></span>

<span data-ttu-id="0095d-762">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-762">Unformatted:</span></span>
- <span data-ttu-id="0095d-763">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-763">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-764">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-764">Checksum</span></span>

<span data-ttu-id="0095d-765">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-765">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-766">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-766">Definition</span></span>

<span data-ttu-id="0095d-767">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-767">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-768">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-768">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-769">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="0095d-769">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="0095d-770">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-770">The checksum passes.</span></span>

<span data-ttu-id="0095d-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-772">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-772">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-773">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-773">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-774">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="0095d-775">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="0095d-775">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="0095d-776">CPF</span><span class="sxs-lookup"><span data-stu-id="0095d-776">CPF</span></span>
- <span data-ttu-id="0095d-777">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-777">Identification</span></span>
- <span data-ttu-id="0095d-778">Registrazione</span><span class="sxs-lookup"><span data-stu-id="0095d-778">Registration</span></span>
- <span data-ttu-id="0095d-779">Entrate</span><span class="sxs-lookup"><span data-stu-id="0095d-779">Revenue</span></span>
- <span data-ttu-id="0095d-780">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="0095d-780">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="0095d-781">Imposto</span><span class="sxs-lookup"><span data-stu-id="0095d-781">Imposto</span></span> 
- <span data-ttu-id="0095d-782">Identificação</span><span class="sxs-lookup"><span data-stu-id="0095d-782">Identificação</span></span> 
- <span data-ttu-id="0095d-783">Inscrição</span><span class="sxs-lookup"><span data-stu-id="0095d-783">Inscrição</span></span> 
- <span data-ttu-id="0095d-784">Receita</span><span class="sxs-lookup"><span data-stu-id="0095d-784">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="0095d-785">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="0095d-785">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-786">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-786">Format</span></span>

<span data-ttu-id="0095d-787">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="0095d-787">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-788">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-788">Pattern</span></span>
<span data-ttu-id="0095d-789">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="0095d-789">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="0095d-790">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-790">Two digits</span></span> 
- <span data-ttu-id="0095d-791">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-791">A period</span></span> 
- <span data-ttu-id="0095d-792">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-792">Three digits</span></span> 
- <span data-ttu-id="0095d-793">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-793">A period</span></span> 
- <span data-ttu-id="0095d-794">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="0095d-794">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="0095d-795">Una barra</span><span class="sxs-lookup"><span data-stu-id="0095d-795">A forward slash</span></span> 
- <span data-ttu-id="0095d-796">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="0095d-796">Four-digit branch number</span></span> 
- <span data-ttu-id="0095d-797">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-797">A hyphen</span></span> 
- <span data-ttu-id="0095d-798">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-798">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-799">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-799">Checksum</span></span>

<span data-ttu-id="0095d-800">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-801">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-801">Definition</span></span>

<span data-ttu-id="0095d-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-803">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-803">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-804">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="0095d-804">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="0095d-805">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-805">The checksum passes.</span></span>

<span data-ttu-id="0095d-806">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-807">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-807">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-808">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-808">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-809">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-809">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="0095d-810">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="0095d-810">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="0095d-811">CNPJ</span><span class="sxs-lookup"><span data-stu-id="0095d-811">CNPJ</span></span> 
- <span data-ttu-id="0095d-812">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="0095d-812">CNPJ/MF</span></span> 
- <span data-ttu-id="0095d-813">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="0095d-813">CNPJ-MF</span></span> 
- <span data-ttu-id="0095d-814">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="0095d-814">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="0095d-815">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="0095d-815">Taxpayers Registry</span></span> 
- <span data-ttu-id="0095d-816">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="0095d-816">Legal entity</span></span> 
- <span data-ttu-id="0095d-817">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="0095d-817">Legal entities</span></span> 
- <span data-ttu-id="0095d-818">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="0095d-818">Registration Status</span></span> 
- <span data-ttu-id="0095d-819">Business</span><span class="sxs-lookup"><span data-stu-id="0095d-819">Business</span></span> 
- <span data-ttu-id="0095d-820">Company</span><span class="sxs-lookup"><span data-stu-id="0095d-820">Company</span></span>
- <span data-ttu-id="0095d-821">CNPJ</span><span class="sxs-lookup"><span data-stu-id="0095d-821">CNPJ</span></span> 
- <span data-ttu-id="0095d-822">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="0095d-822">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="0095d-823">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="0095d-823">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="0095d-824">CGC</span><span class="sxs-lookup"><span data-stu-id="0095d-824">CGC</span></span> 
- <span data-ttu-id="0095d-825">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="0095d-825">Pessoa jurídica</span></span> 
- <span data-ttu-id="0095d-826">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="0095d-826">Pessoas jurídicas</span></span> 
- <span data-ttu-id="0095d-827">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="0095d-827">Situação cadastral</span></span> 
- <span data-ttu-id="0095d-828">Inscrição</span><span class="sxs-lookup"><span data-stu-id="0095d-828">Inscrição</span></span> 
- <span data-ttu-id="0095d-829">Empresa</span><span class="sxs-lookup"><span data-stu-id="0095d-829">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="0095d-830">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="0095d-830">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-831">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-831">Format</span></span>

<span data-ttu-id="0095d-832">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-832">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="0095d-833">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-833">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-834">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-834">Pattern</span></span>

<span data-ttu-id="0095d-835">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="0095d-835">Registro Geral (old format):</span></span>
- <span data-ttu-id="0095d-836">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-836">Two digits</span></span> 
- <span data-ttu-id="0095d-837">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-837">A period</span></span> 
- <span data-ttu-id="0095d-838">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-838">Three digits</span></span> 
- <span data-ttu-id="0095d-839">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-839">A period</span></span> 
- <span data-ttu-id="0095d-840">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-840">Three digits</span></span> 
- <span data-ttu-id="0095d-841">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-841">A hyphen</span></span> 
- <span data-ttu-id="0095d-842">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-842">One digit which is a check digit</span></span>

<span data-ttu-id="0095d-843">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="0095d-843">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="0095d-844">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-844">10 digits</span></span> 
- <span data-ttu-id="0095d-845">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-845">A hyphen</span></span> 
- <span data-ttu-id="0095d-846">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-846">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-847">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-847">Checksum</span></span>

<span data-ttu-id="0095d-848">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-848">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-849">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-849">Definition</span></span>

<span data-ttu-id="0095d-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-850">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-851">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-851">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-852">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="0095d-852">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="0095d-853">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-853">The checksum passes.</span></span>

<span data-ttu-id="0095d-854">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-854">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-855">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-855">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-856">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-857">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-857">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="0095d-858">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="0095d-858">Keyword_brazil_rg</span></span>

<span data-ttu-id="0095d-859">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-859">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="0095d-860">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="0095d-860">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-861">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-861">Format</span></span>

<span data-ttu-id="0095d-862">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-862">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-863">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-863">Pattern</span></span>

<span data-ttu-id="0095d-864">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="0095d-864">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="0095d-865">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="0095d-865">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="0095d-866">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-866">Five digits</span></span> 
- <span data-ttu-id="0095d-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-867">A hyphen</span></span> 
- <span data-ttu-id="0095d-868">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="0095d-868">Three digits OR</span></span>
- <span data-ttu-id="0095d-869">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="0095d-869">A zero "0"</span></span> 
- <span data-ttu-id="0095d-870">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-870">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-871">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-871">Checksum</span></span>

<span data-ttu-id="0095d-872">No</span><span class="sxs-lookup"><span data-stu-id="0095d-872">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-873">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-873">Definition</span></span>

<span data-ttu-id="0095d-874">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-874">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-875">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-875">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-876">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-876">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="0095d-877">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-877">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="0095d-878">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-878">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-879">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-879">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-880">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-880">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-881">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-881">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="0095d-882">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="0095d-882">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="0095d-883">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="0095d-883">canada savings bonds</span></span>
- <span data-ttu-id="0095d-884">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="0095d-884">canada revenue agency</span></span>
- <span data-ttu-id="0095d-885">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="0095d-885">canadian financial institution</span></span>
- <span data-ttu-id="0095d-886">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="0095d-886">direct deposit form</span></span>
- <span data-ttu-id="0095d-887">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="0095d-887">canadian citizen</span></span>
- <span data-ttu-id="0095d-888">legal representative</span><span class="sxs-lookup"><span data-stu-id="0095d-888">legal representative</span></span>
- <span data-ttu-id="0095d-889">notary public</span><span class="sxs-lookup"><span data-stu-id="0095d-889">notary public</span></span>
- <span data-ttu-id="0095d-890">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="0095d-890">commissioner for oaths</span></span>
- <span data-ttu-id="0095d-891">child care benefit</span><span class="sxs-lookup"><span data-stu-id="0095d-891">child care benefit</span></span>
- <span data-ttu-id="0095d-892">universal child care</span><span class="sxs-lookup"><span data-stu-id="0095d-892">universal child care</span></span>
- <span data-ttu-id="0095d-893">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="0095d-893">canada child tax benefit</span></span>
- <span data-ttu-id="0095d-894">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="0095d-894">income tax benefit</span></span>
- <span data-ttu-id="0095d-895">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="0095d-895">harmonized sales tax</span></span>
- <span data-ttu-id="0095d-896">social insurance number</span><span class="sxs-lookup"><span data-stu-id="0095d-896">social insurance number</span></span>
- <span data-ttu-id="0095d-897">income tax refund</span><span class="sxs-lookup"><span data-stu-id="0095d-897">income tax refund</span></span>
- <span data-ttu-id="0095d-898">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="0095d-898">child tax benefit</span></span>
- <span data-ttu-id="0095d-899">territorial payments</span><span class="sxs-lookup"><span data-stu-id="0095d-899">territorial payments</span></span>
- <span data-ttu-id="0095d-900">institution number</span><span class="sxs-lookup"><span data-stu-id="0095d-900">institution number</span></span>
- <span data-ttu-id="0095d-901">deposit request</span><span class="sxs-lookup"><span data-stu-id="0095d-901">deposit request</span></span>
- <span data-ttu-id="0095d-902">banking information</span><span class="sxs-lookup"><span data-stu-id="0095d-902">banking information</span></span>
- <span data-ttu-id="0095d-903">direct deposit</span><span class="sxs-lookup"><span data-stu-id="0095d-903">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="0095d-904">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-904">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-905">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-905">Format</span></span>

<span data-ttu-id="0095d-906">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="0095d-906">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-907">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-907">Pattern</span></span>

<span data-ttu-id="0095d-908">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="0095d-908">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-909">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-909">Checksum</span></span>

<span data-ttu-id="0095d-910">No</span><span class="sxs-lookup"><span data-stu-id="0095d-910">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-911">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-911">Definition</span></span>

<span data-ttu-id="0095d-912">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-913">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-913">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-914">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="0095d-914">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="0095d-915">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-915">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-916">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-916">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="0095d-917">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="0095d-917">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="0095d-918">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="0095d-918">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="0095d-919">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="0095d-919">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="0095d-920">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="0095d-920">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="0095d-921">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-921">DL</span></span>
- <span data-ttu-id="0095d-922">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-922">DLS</span></span>
- <span data-ttu-id="0095d-923">CDL</span><span class="sxs-lookup"><span data-stu-id="0095d-923">CDL</span></span>
- <span data-ttu-id="0095d-924">CDLS</span><span class="sxs-lookup"><span data-stu-id="0095d-924">CDLS</span></span>
- <span data-ttu-id="0095d-925">DriverLic</span><span class="sxs-lookup"><span data-stu-id="0095d-925">DriverLic</span></span>
- <span data-ttu-id="0095d-926">DriverLics</span><span class="sxs-lookup"><span data-stu-id="0095d-926">DriverLics</span></span>
- <span data-ttu-id="0095d-927">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-927">DriverLicense</span></span>
- <span data-ttu-id="0095d-928">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-928">DriverLicenses</span></span>
- <span data-ttu-id="0095d-929">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-929">DriverLicence</span></span>
- <span data-ttu-id="0095d-930">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-930">DriverLicences</span></span>
- <span data-ttu-id="0095d-931">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-931">Driver Lic</span></span>
- <span data-ttu-id="0095d-932">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-932">Driver Lics</span></span>
- <span data-ttu-id="0095d-933">Driver License</span><span class="sxs-lookup"><span data-stu-id="0095d-933">Driver License</span></span>
- <span data-ttu-id="0095d-934">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-934">Driver Licenses</span></span>
- <span data-ttu-id="0095d-935">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-935">Driver Licence</span></span>
- <span data-ttu-id="0095d-936">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-936">Driver Licences</span></span>
- <span data-ttu-id="0095d-937">DriversLic</span><span class="sxs-lookup"><span data-stu-id="0095d-937">DriversLic</span></span>
- <span data-ttu-id="0095d-938">DriversLics</span><span class="sxs-lookup"><span data-stu-id="0095d-938">DriversLics</span></span>
- <span data-ttu-id="0095d-939">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-939">DriversLicence</span></span>
- <span data-ttu-id="0095d-940">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-940">DriversLicences</span></span>
- <span data-ttu-id="0095d-941">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-941">DriversLicense</span></span>
- <span data-ttu-id="0095d-942">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-942">DriversLicenses</span></span>
- <span data-ttu-id="0095d-943">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-943">Drivers Lic</span></span>
- <span data-ttu-id="0095d-944">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-944">Drivers Lics</span></span>
- <span data-ttu-id="0095d-945">Drivers License</span><span class="sxs-lookup"><span data-stu-id="0095d-945">Drivers License</span></span>
- <span data-ttu-id="0095d-946">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-946">Drivers Licenses</span></span>
- <span data-ttu-id="0095d-947">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-947">Drivers Licence</span></span>
- <span data-ttu-id="0095d-948">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-948">Drivers Licences</span></span>
- <span data-ttu-id="0095d-949">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-949">Driver'Lic</span></span>
- <span data-ttu-id="0095d-950">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-950">Driver'Lics</span></span>
- <span data-ttu-id="0095d-951">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-951">Driver'License</span></span>
- <span data-ttu-id="0095d-952">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-952">Driver'Licenses</span></span>
- <span data-ttu-id="0095d-953">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-953">Driver'Licence</span></span>
- <span data-ttu-id="0095d-954">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-954">Driver'Licences</span></span>
- <span data-ttu-id="0095d-955">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-955">Driver' Lic</span></span>
- <span data-ttu-id="0095d-956">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-956">Driver' Lics</span></span>
- <span data-ttu-id="0095d-957">Driver' License</span><span class="sxs-lookup"><span data-stu-id="0095d-957">Driver' License</span></span>
- <span data-ttu-id="0095d-958">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-958">Driver' Licenses</span></span>
- <span data-ttu-id="0095d-959">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-959">Driver' Licence</span></span>
- <span data-ttu-id="0095d-960">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-960">Driver' Licences</span></span>
- <span data-ttu-id="0095d-961">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="0095d-961">Driver'sLic</span></span>
- <span data-ttu-id="0095d-962">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="0095d-962">Driver'sLics</span></span>
- <span data-ttu-id="0095d-963">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-963">Driver'sLicense</span></span>
- <span data-ttu-id="0095d-964">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-964">Driver'sLicenses</span></span>
- <span data-ttu-id="0095d-965">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="0095d-965">Driver'sLicence</span></span>
- <span data-ttu-id="0095d-966">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="0095d-966">Driver'sLicences</span></span>
- <span data-ttu-id="0095d-967">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-967">Driver's Lic</span></span>
- <span data-ttu-id="0095d-968">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-968">Driver's Lics</span></span>
- <span data-ttu-id="0095d-969">Driver's License</span><span class="sxs-lookup"><span data-stu-id="0095d-969">Driver's License</span></span>
- <span data-ttu-id="0095d-970">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-970">Driver's Licenses</span></span>
- <span data-ttu-id="0095d-971">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-971">Driver's Licence</span></span>
- <span data-ttu-id="0095d-972">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-972">Driver's Licences</span></span>
- <span data-ttu-id="0095d-973">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="0095d-973">Permis de Conduire</span></span>
- <span data-ttu-id="0095d-974">id</span><span class="sxs-lookup"><span data-stu-id="0095d-974">id</span></span>
- <span data-ttu-id="0095d-975">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-975">ids</span></span>
- <span data-ttu-id="0095d-976">idcard number</span><span class="sxs-lookup"><span data-stu-id="0095d-976">idcard number</span></span>
- <span data-ttu-id="0095d-977">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-977">idcard numbers</span></span>
- <span data-ttu-id="0095d-978">idcard #</span><span class="sxs-lookup"><span data-stu-id="0095d-978">idcard #</span></span>
- <span data-ttu-id="0095d-979">idcard #s</span><span class="sxs-lookup"><span data-stu-id="0095d-979">idcard #s</span></span>
- <span data-ttu-id="0095d-980">idcard card</span><span class="sxs-lookup"><span data-stu-id="0095d-980">idcard card</span></span>
- <span data-ttu-id="0095d-981">idcard cards</span><span class="sxs-lookup"><span data-stu-id="0095d-981">idcard cards</span></span>
- <span data-ttu-id="0095d-982">IDcard</span><span class="sxs-lookup"><span data-stu-id="0095d-982">idcard</span></span>
- <span data-ttu-id="0095d-983">identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-983">identification number</span></span>
- <span data-ttu-id="0095d-984">identification numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-984">identification numbers</span></span>
- <span data-ttu-id="0095d-985">identification #</span><span class="sxs-lookup"><span data-stu-id="0095d-985">identification #</span></span>
- <span data-ttu-id="0095d-986">identification #s</span><span class="sxs-lookup"><span data-stu-id="0095d-986">identification #s</span></span>
- <span data-ttu-id="0095d-987">identification card</span><span class="sxs-lookup"><span data-stu-id="0095d-987">identification card</span></span>
- <span data-ttu-id="0095d-988">identification cards</span><span class="sxs-lookup"><span data-stu-id="0095d-988">identification cards</span></span>
- <span data-ttu-id="0095d-989">identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-989">identification</span></span> 
- <span data-ttu-id="0095d-990">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-990">DL#</span></span>
- <span data-ttu-id="0095d-991">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-991">DLS#</span></span> 
- <span data-ttu-id="0095d-992">CDL</span><span class="sxs-lookup"><span data-stu-id="0095d-992">CDL#</span></span> 
- <span data-ttu-id="0095d-993">CDLS</span><span class="sxs-lookup"><span data-stu-id="0095d-993">CDLS#</span></span> 
- <span data-ttu-id="0095d-994">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-994">DriverLic#</span></span> 
- <span data-ttu-id="0095d-995">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-995">DriverLics#</span></span> 
- <span data-ttu-id="0095d-996">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-996">DriverLicense#</span></span> 
- <span data-ttu-id="0095d-997">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-997">DriverLicenses#</span></span> 
- <span data-ttu-id="0095d-998">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-998">DriverLicence#</span></span> 
- <span data-ttu-id="0095d-999">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-999">DriverLicences#</span></span> 
- <span data-ttu-id="0095d-1000">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-1000">Driver Lic#</span></span>
- <span data-ttu-id="0095d-1001">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-1001">Driver Lics#</span></span> 
- <span data-ttu-id="0095d-1002">Driver License#</span><span class="sxs-lookup"><span data-stu-id="0095d-1002">Driver License#</span></span> 
- <span data-ttu-id="0095d-1003">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-1003">Driver Licenses#</span></span> 
- <span data-ttu-id="0095d-1004">Driver License#</span><span class="sxs-lookup"><span data-stu-id="0095d-1004">Driver License#</span></span> 
- <span data-ttu-id="0095d-1005">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-1005">Driver Licences#</span></span> 
- <span data-ttu-id="0095d-1006">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-1006">DriversLic#</span></span> 
- <span data-ttu-id="0095d-1007">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-1007">DriversLics#</span></span> 
- <span data-ttu-id="0095d-1008">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-1008">DriversLicense#</span></span> 
- <span data-ttu-id="0095d-1009">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-1009">DriversLicenses#</span></span> 
- <span data-ttu-id="0095d-1010">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-1010">DriversLicence#</span></span> 
- <span data-ttu-id="0095d-1011">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-1011">DriversLicences#</span></span> 
- <span data-ttu-id="0095d-1012">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-1012">Drivers Lic#</span></span> 
- <span data-ttu-id="0095d-1013">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-1013">Drivers Lics#</span></span> 
- <span data-ttu-id="0095d-1014">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="0095d-1014">Drivers License#</span></span> 
- <span data-ttu-id="0095d-1015">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-1015">Drivers Licenses#</span></span> 
- <span data-ttu-id="0095d-1016">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-1016">Drivers Licence#</span></span> 
- <span data-ttu-id="0095d-1017">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-1017">Drivers Licences#</span></span> 
- <span data-ttu-id="0095d-1018">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="0095d-1018">Driver'Lic#</span></span> 
- <span data-ttu-id="0095d-1019">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-1019">Driver'Lics#</span></span> 
- <span data-ttu-id="0095d-1020">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-1020">Driver'License#</span></span> 
- <span data-ttu-id="0095d-1021">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-1021">Driver'Licenses#</span></span> 
- <span data-ttu-id="0095d-1022">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="0095d-1022">Driver'Licence#</span></span> 
- <span data-ttu-id="0095d-1023">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="0095d-1023">Driver'Licences#</span></span> 
- <span data-ttu-id="0095d-1024">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-1024">Driver' Lic#</span></span> 
- <span data-ttu-id="0095d-1025">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-1025">Driver' Lics#</span></span> 
- <span data-ttu-id="0095d-1026">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="0095d-1026">Driver' License#</span></span> 
- <span data-ttu-id="0095d-1027">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-1027">Driver' Licenses#</span></span> 
- <span data-ttu-id="0095d-1028">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-1028">Driver' Licence#</span></span> 
- <span data-ttu-id="0095d-1029">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-1029">Driver' Licences#</span></span> 
- <span data-ttu-id="0095d-1030">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-1030">Driver'sLic#</span></span> 
- <span data-ttu-id="0095d-1031">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-1031">Driver'sLics#</span></span> 
- <span data-ttu-id="0095d-1032">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-1032">Driver'sLicense#</span></span> 
- <span data-ttu-id="0095d-1033">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-1033">Driver'sLicenses#</span></span> 
- <span data-ttu-id="0095d-1034">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="0095d-1034">Driver'sLicence#</span></span> 
- <span data-ttu-id="0095d-1035">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="0095d-1035">Driver'sLicences#</span></span> 
- <span data-ttu-id="0095d-1036">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-1036">Driver's Lic#</span></span> 
- <span data-ttu-id="0095d-1037">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-1037">Driver's Lics#</span></span> 
- <span data-ttu-id="0095d-1038">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="0095d-1038">Driver's License#</span></span> 
- <span data-ttu-id="0095d-1039">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-1039">Driver's Licenses#</span></span> 
- <span data-ttu-id="0095d-1040">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="0095d-1040">Driver's Licence#</span></span> 
- <span data-ttu-id="0095d-1041">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="0095d-1041">Driver's Licences#</span></span> 
- <span data-ttu-id="0095d-1042">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="0095d-1042">Permis de Conduire#</span></span> 
- <span data-ttu-id="0095d-1043">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1043">id#</span></span> 
- <span data-ttu-id="0095d-1044">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1044">ids#</span></span> 
- <span data-ttu-id="0095d-1045">idcard card#</span><span class="sxs-lookup"><span data-stu-id="0095d-1045">idcard card#</span></span> 
- <span data-ttu-id="0095d-1046">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="0095d-1046">idcard cards#</span></span> 
- <span data-ttu-id="0095d-1047">IDcard #</span><span class="sxs-lookup"><span data-stu-id="0095d-1047">idcard#</span></span> 
- <span data-ttu-id="0095d-1048">identification card#</span><span class="sxs-lookup"><span data-stu-id="0095d-1048">identification card#</span></span> 
- <span data-ttu-id="0095d-1049">identification cards#</span><span class="sxs-lookup"><span data-stu-id="0095d-1049">identification cards#</span></span> 
- <span data-ttu-id="0095d-1050">identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-1050">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="0095d-1051">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="0095d-1051">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1052">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1052">Format</span></span>

<span data-ttu-id="0095d-1053">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1053">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1054">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1054">Pattern</span></span>

<span data-ttu-id="0095d-1055">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1055">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1056">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1056">Checksum</span></span>

<span data-ttu-id="0095d-1057">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1057">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1058">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1058">Definition</span></span>

<span data-ttu-id="0095d-1059">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1059">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1060">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1060">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1061">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-1061">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1062">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1062">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="0095d-1063">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="0095d-1063">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="0095d-1064">personal health number</span><span class="sxs-lookup"><span data-stu-id="0095d-1064">personal health number</span></span>
- <span data-ttu-id="0095d-1065">patient information</span><span class="sxs-lookup"><span data-stu-id="0095d-1065">patient information</span></span>
- <span data-ttu-id="0095d-1066">health services</span><span class="sxs-lookup"><span data-stu-id="0095d-1066">health services</span></span>
- <span data-ttu-id="0095d-1067">speciality services</span><span class="sxs-lookup"><span data-stu-id="0095d-1067">speciality services</span></span>
- <span data-ttu-id="0095d-1068">automobile accident</span><span class="sxs-lookup"><span data-stu-id="0095d-1068">automobile accident</span></span>
- <span data-ttu-id="0095d-1069">patient hospital</span><span class="sxs-lookup"><span data-stu-id="0095d-1069">patient hospital</span></span>
- <span data-ttu-id="0095d-1070">psichiatra</span><span class="sxs-lookup"><span data-stu-id="0095d-1070">psychiatrist</span></span>
- <span data-ttu-id="0095d-1071">workers compensation</span><span class="sxs-lookup"><span data-stu-id="0095d-1071">workers compensation</span></span>
- <span data-ttu-id="0095d-1072">Disability</span><span class="sxs-lookup"><span data-stu-id="0095d-1072">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="0095d-1073">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-1073">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1074">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1074">Format</span></span>

<span data-ttu-id="0095d-1075">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1075">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1076">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1076">Pattern</span></span>

<span data-ttu-id="0095d-1077">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1077">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1078">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1078">Checksum</span></span>

<span data-ttu-id="0095d-1079">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1079">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1080">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1080">Definition</span></span>

<span data-ttu-id="0095d-1081">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1081">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1082">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1082">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1083">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-1083">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1084">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1084">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="0095d-1085">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="0095d-1085">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="0095d-1086">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="0095d-1086">canadian citizenship</span></span>
- <span data-ttu-id="0095d-1087">canadian passport</span><span class="sxs-lookup"><span data-stu-id="0095d-1087">canadian passport</span></span>
- <span data-ttu-id="0095d-1088">passport application</span><span class="sxs-lookup"><span data-stu-id="0095d-1088">passport application</span></span>
- <span data-ttu-id="0095d-1089">passport photos</span><span class="sxs-lookup"><span data-stu-id="0095d-1089">passport photos</span></span>
- <span data-ttu-id="0095d-1090">certified translator</span><span class="sxs-lookup"><span data-stu-id="0095d-1090">certified translator</span></span>
- <span data-ttu-id="0095d-1091">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="0095d-1091">canadian citizens</span></span>
- <span data-ttu-id="0095d-1092">processing times</span><span class="sxs-lookup"><span data-stu-id="0095d-1092">processing times</span></span>
- <span data-ttu-id="0095d-1093">renewal application</span><span class="sxs-lookup"><span data-stu-id="0095d-1093">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="0095d-1094">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-1094">Keyword_passport</span></span>

- <span data-ttu-id="0095d-1095">Passport Number</span><span class="sxs-lookup"><span data-stu-id="0095d-1095">Passport Number</span></span>
- <span data-ttu-id="0095d-1096">Passport No</span><span class="sxs-lookup"><span data-stu-id="0095d-1096">Passport No</span></span>
- <span data-ttu-id="0095d-1097">Passport#</span><span class="sxs-lookup"><span data-stu-id="0095d-1097">Passport #</span></span>
- <span data-ttu-id="0095d-1098">Passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-1098">Passport#</span></span>
- <span data-ttu-id="0095d-1099">PassportID</span><span class="sxs-lookup"><span data-stu-id="0095d-1099">PassportID</span></span>
- <span data-ttu-id="0095d-1100">Passportno</span><span class="sxs-lookup"><span data-stu-id="0095d-1100">Passportno</span></span>
- <span data-ttu-id="0095d-1101">passportnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-1101">passportnumber</span></span>
- <span data-ttu-id="0095d-1102">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-1102">パスポート</span></span>
- <span data-ttu-id="0095d-1103">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-1103">パスポート番号</span></span>
- <span data-ttu-id="0095d-1104">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-1104">パスポートのNum</span></span>
- <span data-ttu-id="0095d-1105">パスポート #</span><span class="sxs-lookup"><span data-stu-id="0095d-1105">パスポート＃</span></span>
- <span data-ttu-id="0095d-1106">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-1106">Numéro de passeport</span></span>
- <span data-ttu-id="0095d-1107">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="0095d-1107">Passeport n °</span></span>
- <span data-ttu-id="0095d-1108">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="0095d-1108">Passeport Non</span></span>
- <span data-ttu-id="0095d-1109">Passeport#</span><span class="sxs-lookup"><span data-stu-id="0095d-1109">Passeport #</span></span>
- <span data-ttu-id="0095d-1110">Passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-1110">Passeport#</span></span>
- <span data-ttu-id="0095d-1111">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="0095d-1111">PasseportNon</span></span>
- <span data-ttu-id="0095d-1112">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="0095d-1112">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="0095d-1113">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="0095d-1113">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1114">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1114">Format</span></span>

<span data-ttu-id="0095d-1115">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1115">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1116">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1116">Pattern</span></span>

<span data-ttu-id="0095d-1117">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1117">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1118">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1118">Checksum</span></span>

<span data-ttu-id="0095d-1119">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1119">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1120">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1120">Definition</span></span>

<span data-ttu-id="0095d-1121">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-1122">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="0095d-1122">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1123">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1123">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="0095d-1124">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="0095d-1124">Keyword_canada_phin</span></span>

- <span data-ttu-id="0095d-1125">social insurance number</span><span class="sxs-lookup"><span data-stu-id="0095d-1125">social insurance number</span></span>
- <span data-ttu-id="0095d-1126">health information act</span><span class="sxs-lookup"><span data-stu-id="0095d-1126">health information act</span></span>
- <span data-ttu-id="0095d-1127">income tax information</span><span class="sxs-lookup"><span data-stu-id="0095d-1127">income tax information</span></span>
- <span data-ttu-id="0095d-1128">manitoba health</span><span class="sxs-lookup"><span data-stu-id="0095d-1128">manitoba health</span></span>
- <span data-ttu-id="0095d-1129">health registration</span><span class="sxs-lookup"><span data-stu-id="0095d-1129">health registration</span></span>
- <span data-ttu-id="0095d-1130">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="0095d-1130">prescription purchases</span></span>
- <span data-ttu-id="0095d-1131">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="0095d-1131">benefit eligibility</span></span>
- <span data-ttu-id="0095d-1132">personal health</span><span class="sxs-lookup"><span data-stu-id="0095d-1132">personal health</span></span>
- <span data-ttu-id="0095d-1133">power of attorney</span><span class="sxs-lookup"><span data-stu-id="0095d-1133">power of attorney</span></span>
- <span data-ttu-id="0095d-1134">registration number</span><span class="sxs-lookup"><span data-stu-id="0095d-1134">registration number</span></span>
- <span data-ttu-id="0095d-1135">personal health number</span><span class="sxs-lookup"><span data-stu-id="0095d-1135">personal health number</span></span>
- <span data-ttu-id="0095d-1136">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="0095d-1136">practitioner referral</span></span>
- <span data-ttu-id="0095d-1137">wellness professional</span><span class="sxs-lookup"><span data-stu-id="0095d-1137">wellness professional</span></span>
- <span data-ttu-id="0095d-1138">patient referral</span><span class="sxs-lookup"><span data-stu-id="0095d-1138">patient referral</span></span>
- <span data-ttu-id="0095d-1139">health and wellness</span><span class="sxs-lookup"><span data-stu-id="0095d-1139">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="0095d-1140">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="0095d-1140">Keyword_canada_provinces</span></span>

- <span data-ttu-id="0095d-1141">Nunavut</span><span class="sxs-lookup"><span data-stu-id="0095d-1141">Nunavut</span></span>
- <span data-ttu-id="0095d-1142">Quebec</span><span class="sxs-lookup"><span data-stu-id="0095d-1142">Quebec</span></span>
- <span data-ttu-id="0095d-1143">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="0095d-1143">Northwest Territories</span></span>
- <span data-ttu-id="0095d-1144">Ontario</span><span class="sxs-lookup"><span data-stu-id="0095d-1144">Ontario</span></span>
- <span data-ttu-id="0095d-1145">British Columbia</span><span class="sxs-lookup"><span data-stu-id="0095d-1145">British Columbia</span></span>
- <span data-ttu-id="0095d-1146">Filippa</span><span class="sxs-lookup"><span data-stu-id="0095d-1146">Alberta</span></span>
- <span data-ttu-id="0095d-1147">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="0095d-1147">Saskatchewan</span></span>
- <span data-ttu-id="0095d-1148">Manitoba</span><span class="sxs-lookup"><span data-stu-id="0095d-1148">Manitoba</span></span>
- <span data-ttu-id="0095d-1149">Yukon</span><span class="sxs-lookup"><span data-stu-id="0095d-1149">Yukon</span></span>
- <span data-ttu-id="0095d-1150">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="0095d-1150">Newfoundland and Labrador</span></span>
- <span data-ttu-id="0095d-1151">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="0095d-1151">New Brunswick</span></span>
- <span data-ttu-id="0095d-1152">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="0095d-1152">Nova Scotia</span></span>
- <span data-ttu-id="0095d-1153">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="0095d-1153">Prince Edward Island</span></span>
- <span data-ttu-id="0095d-1154">Canada</span><span class="sxs-lookup"><span data-stu-id="0095d-1154">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="0095d-1155">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-1155">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1156">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1156">Format</span></span>

<span data-ttu-id="0095d-1157">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="0095d-1157">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1158">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1158">Pattern</span></span>

<span data-ttu-id="0095d-1159">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-1159">Formatted:</span></span>
- <span data-ttu-id="0095d-1160">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1160">Three digits</span></span> 
- <span data-ttu-id="0095d-1161">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="0095d-1161">A hyphen or space</span></span> 
- <span data-ttu-id="0095d-1162">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1162">Three digits</span></span> 
- <span data-ttu-id="0095d-1163">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="0095d-1163">A hyphen or space</span></span> 
- <span data-ttu-id="0095d-1164">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1164">Three digits</span></span>

<span data-ttu-id="0095d-1165">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1165">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1166">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1166">Checksum</span></span>

<span data-ttu-id="0095d-1167">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1167">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1168">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1168">Definition</span></span>

<span data-ttu-id="0095d-1169">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1169">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1170">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1170">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1171">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="0095d-1171">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="0095d-1172">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="0095d-1172">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="0095d-1173">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="0095d-1173">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="0095d-1174">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-1174">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="0095d-1175">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1175">The checksum passes.</span></span>

<span data-ttu-id="0095d-1176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1177">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1177">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1178">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="0095d-1178">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="0095d-1179">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1179">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1180">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1180">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="0095d-1181">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="0095d-1181">Keyword_sin</span></span>

- <span data-ttu-id="0095d-1182">sin</span><span class="sxs-lookup"><span data-stu-id="0095d-1182">sin</span></span> 
- <span data-ttu-id="0095d-1183">social insurance</span><span class="sxs-lookup"><span data-stu-id="0095d-1183">social insurance</span></span> 
- <span data-ttu-id="0095d-1184">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-1184">numero d'assurance sociale</span></span> 
- <span data-ttu-id="0095d-1185">peccati</span><span class="sxs-lookup"><span data-stu-id="0095d-1185">sins</span></span> 
- <span data-ttu-id="0095d-1186">SSN</span><span class="sxs-lookup"><span data-stu-id="0095d-1186">ssn</span></span> 
- <span data-ttu-id="0095d-1187">SNSS</span><span class="sxs-lookup"><span data-stu-id="0095d-1187">ssns</span></span> 
- <span data-ttu-id="0095d-1188">social security</span><span class="sxs-lookup"><span data-stu-id="0095d-1188">social security</span></span> 
- <span data-ttu-id="0095d-1189">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="0095d-1189">numero d'assurance social</span></span> 
- <span data-ttu-id="0095d-1190">national identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-1190">national identification number</span></span> 
- <span data-ttu-id="0095d-1191">national id</span><span class="sxs-lookup"><span data-stu-id="0095d-1191">national id</span></span> 
- <span data-ttu-id="0095d-1192">sin</span><span class="sxs-lookup"><span data-stu-id="0095d-1192">sin#</span></span> 
- <span data-ttu-id="0095d-1193">soc ins</span><span class="sxs-lookup"><span data-stu-id="0095d-1193">soc ins</span></span> 
- <span data-ttu-id="0095d-1194">social ins</span><span class="sxs-lookup"><span data-stu-id="0095d-1194">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="0095d-1195">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="0095d-1195">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="0095d-1196">driver's license</span><span class="sxs-lookup"><span data-stu-id="0095d-1196">driver's license</span></span> 
- <span data-ttu-id="0095d-1197">drivers license</span><span class="sxs-lookup"><span data-stu-id="0095d-1197">drivers license</span></span> 
- <span data-ttu-id="0095d-1198">driver's licence</span><span class="sxs-lookup"><span data-stu-id="0095d-1198">driver's licence</span></span> 
- <span data-ttu-id="0095d-1199">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0095d-1199">drivers licence</span></span> 
- <span data-ttu-id="0095d-1200">DOB</span><span class="sxs-lookup"><span data-stu-id="0095d-1200">DOB</span></span> 
- <span data-ttu-id="0095d-1201">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-1201">Birthdate</span></span> 
- <span data-ttu-id="0095d-1202">Compleanno</span><span class="sxs-lookup"><span data-stu-id="0095d-1202">Birthday</span></span> 
- <span data-ttu-id="0095d-1203">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="0095d-1203">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="0095d-1204">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-1204">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1205">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1205">Format</span></span>

<span data-ttu-id="0095d-1206">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="0095d-1206">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1207">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1207">Pattern</span></span>

<span data-ttu-id="0095d-1208">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="0095d-1208">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="0095d-1209">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1209">1-2 digits</span></span> 
- <span data-ttu-id="0095d-1210">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-1210">A period</span></span> 
- <span data-ttu-id="0095d-1211">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1211">Three digits</span></span> 
- <span data-ttu-id="0095d-1212">Un punto </span><span class="sxs-lookup"><span data-stu-id="0095d-1212">A period</span></span> 
- <span data-ttu-id="0095d-1213">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1213">Three digits</span></span> 
- <span data-ttu-id="0095d-1214">Un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-1214">A dash</span></span> 
- <span data-ttu-id="0095d-1215">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1215">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1216">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1216">Checksum</span></span>

<span data-ttu-id="0095d-1217">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1217">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1218">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1218">Definition</span></span>

<span data-ttu-id="0095d-1219">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1219">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1220">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1220">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1221">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-1221">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="0095d-1222">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1222">The checksum passes.</span></span>

<span data-ttu-id="0095d-1223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1224">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1224">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1225">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1225">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1226">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1226">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="0095d-1227">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-1227">Keyword_chile_id_card</span></span>

- <span data-ttu-id="0095d-1228">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="0095d-1228">National Identification Number</span></span> 
- <span data-ttu-id="0095d-1229">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-1229">Identity card</span></span> 
- <span data-ttu-id="0095d-1230">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1230">ID</span></span> 
- <span data-ttu-id="0095d-1231">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-1231">Identification</span></span> 
- <span data-ttu-id="0095d-1232">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="0095d-1232">Rol Único Nacional</span></span> 
- <span data-ttu-id="0095d-1233">Correre</span><span class="sxs-lookup"><span data-stu-id="0095d-1233">RUN</span></span> 
- <span data-ttu-id="0095d-1234">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="0095d-1234">Rol Único Tributario</span></span> 
- <span data-ttu-id="0095d-1235">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="0095d-1235">RUT</span></span> 
- <span data-ttu-id="0095d-1236">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="0095d-1236">Cédula de Identidad</span></span> 
- <span data-ttu-id="0095d-1237">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="0095d-1237">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="0095d-1238">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="0095d-1238">Tarjeta de identificación</span></span> 
- <span data-ttu-id="0095d-1239">Identificación</span><span class="sxs-lookup"><span data-stu-id="0095d-1239">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="0095d-1240">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="0095d-1240">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1241">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1241">Format</span></span>

<span data-ttu-id="0095d-1242">18 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1242">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1243">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1243">Pattern</span></span>

<span data-ttu-id="0095d-1244">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-1244">18 digits:</span></span>
- <span data-ttu-id="0095d-1245">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="0095d-1245">Six digits which are an address code</span></span> 
- <span data-ttu-id="0095d-1246">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="0095d-1246">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="0095d-1247">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="0095d-1247">Three digits which are an order code</span></span> 
- <span data-ttu-id="0095d-1248">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1248">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1249">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1249">Checksum</span></span>

<span data-ttu-id="0095d-1250">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1250">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1251">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1251">Definition</span></span>

<span data-ttu-id="0095d-1252">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1252">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1253">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1253">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1254">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-1254">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="0095d-1255">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1255">The checksum passes.</span></span>

<span data-ttu-id="0095d-1256">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1256">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1257">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1257">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1258">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1258">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1259">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1259">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="0095d-1260">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="0095d-1260">Keyword_china_resident_id</span></span>

- <span data-ttu-id="0095d-1261">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="0095d-1261">Resident Identity Card</span></span> 
- <span data-ttu-id="0095d-1262">RPC</span><span class="sxs-lookup"><span data-stu-id="0095d-1262">PRC</span></span> 
- <span data-ttu-id="0095d-1263">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="0095d-1263">National Identification Card</span></span> 
- <span data-ttu-id="0095d-1264">身份证</span><span class="sxs-lookup"><span data-stu-id="0095d-1264">身份证</span></span> 
- <span data-ttu-id="0095d-1265">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="0095d-1265">居民 身份证</span></span> 
- <span data-ttu-id="0095d-1266">居民身份证</span><span class="sxs-lookup"><span data-stu-id="0095d-1266">居民身份证</span></span> 
- <span data-ttu-id="0095d-1267">鉴定</span><span class="sxs-lookup"><span data-stu-id="0095d-1267">鉴定</span></span> 
- <span data-ttu-id="0095d-1268">身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-1268">身分證</span></span> 
- <span data-ttu-id="0095d-1269">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-1269">居民 身份證</span></span>
- <span data-ttu-id="0095d-1270">鑑定</span><span class="sxs-lookup"><span data-stu-id="0095d-1270">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="0095d-1271">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="0095d-1271">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1272">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1272">Format</span></span>

<span data-ttu-id="0095d-1273">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="0095d-1273">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1274">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1274">Pattern</span></span>

<span data-ttu-id="0095d-1275">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="0095d-1275">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1276">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1276">Checksum</span></span>

<span data-ttu-id="0095d-1277">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="0095d-1277">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1278">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1278">Definition</span></span>

<span data-ttu-id="0095d-1279">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1279">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1280">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1280">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1281">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-1281">One of the following is true:</span></span>
    - <span data-ttu-id="0095d-1282">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="0095d-1282">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="0095d-1283">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="0095d-1283">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="0095d-1284">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-1284">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="0095d-1285">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1285">The checksum passes.</span></span>

<span data-ttu-id="0095d-1286">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1286">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1287">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1287">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1288">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1288">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1289">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1289">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="0095d-1290">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="0095d-1290">Keyword_cc_verification</span></span>

- <span data-ttu-id="0095d-1291">card verification</span><span class="sxs-lookup"><span data-stu-id="0095d-1291">card verification</span></span>
- <span data-ttu-id="0095d-1292">card identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-1292">card identification number</span></span>
- <span data-ttu-id="0095d-1293">CVN</span><span class="sxs-lookup"><span data-stu-id="0095d-1293">cvn</span></span>
- <span data-ttu-id="0095d-1294">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1294">cid</span></span>
- <span data-ttu-id="0095d-1295">CVC2</span><span class="sxs-lookup"><span data-stu-id="0095d-1295">cvc2</span></span>
- <span data-ttu-id="0095d-1296">CVV2</span><span class="sxs-lookup"><span data-stu-id="0095d-1296">cvv2</span></span>
- <span data-ttu-id="0095d-1297">pin block</span><span class="sxs-lookup"><span data-stu-id="0095d-1297">pin block</span></span>
- <span data-ttu-id="0095d-1298">security code</span><span class="sxs-lookup"><span data-stu-id="0095d-1298">security code</span></span>
- <span data-ttu-id="0095d-1299">security number</span><span class="sxs-lookup"><span data-stu-id="0095d-1299">security number</span></span>
- <span data-ttu-id="0095d-1300">security no</span><span class="sxs-lookup"><span data-stu-id="0095d-1300">security no</span></span>
- <span data-ttu-id="0095d-1301">issue number</span><span class="sxs-lookup"><span data-stu-id="0095d-1301">issue number</span></span>
- <span data-ttu-id="0095d-1302">issue no</span><span class="sxs-lookup"><span data-stu-id="0095d-1302">issue no</span></span>
- <span data-ttu-id="0095d-1303">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="0095d-1303">cryptogramme</span></span>
- <span data-ttu-id="0095d-1304">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="0095d-1304">numéro de sécurité</span></span>
- <span data-ttu-id="0095d-1305">numero de securite</span><span class="sxs-lookup"><span data-stu-id="0095d-1305">numero de securite</span></span>
- <span data-ttu-id="0095d-1306">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1306">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="0095d-1307">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1307">kreditkartenprufnummer</span></span>
- <span data-ttu-id="0095d-1308">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="0095d-1308">prüfziffer</span></span>
- <span data-ttu-id="0095d-1309">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="0095d-1309">prufziffer</span></span>
- <span data-ttu-id="0095d-1310">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="0095d-1310">sicherheits Kode</span></span>
- <span data-ttu-id="0095d-1311">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="0095d-1311">sicherheitscode</span></span>
- <span data-ttu-id="0095d-1312">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1312">sicherheitsnummer</span></span>
- <span data-ttu-id="0095d-1313">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1313">verfalldatum</span></span>
- <span data-ttu-id="0095d-1314">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="0095d-1314">codice di verifica</span></span>
- <span data-ttu-id="0095d-1315">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1315">cod.</span></span> <span data-ttu-id="0095d-1316">sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1316">sicurezza</span></span>
- <span data-ttu-id="0095d-1317">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1317">cod sicurezza</span></span>
- <span data-ttu-id="0095d-1318">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0095d-1318">n autorizzazione</span></span>
- <span data-ttu-id="0095d-1319">Código</span><span class="sxs-lookup"><span data-stu-id="0095d-1319">código</span></span>
- <span data-ttu-id="0095d-1320">Codigo</span><span class="sxs-lookup"><span data-stu-id="0095d-1320">codigo</span></span>
- <span data-ttu-id="0095d-1321">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1321">cod.</span></span> <span data-ttu-id="0095d-1322">SEG</span><span class="sxs-lookup"><span data-stu-id="0095d-1322">seg</span></span>
- <span data-ttu-id="0095d-1323">cod seg</span><span class="sxs-lookup"><span data-stu-id="0095d-1323">cod seg</span></span>
- <span data-ttu-id="0095d-1324">código de segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1324">código de segurança</span></span>
- <span data-ttu-id="0095d-1325">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1325">codigo de seguranca</span></span>
- <span data-ttu-id="0095d-1326">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1326">codigo de segurança</span></span>
- <span data-ttu-id="0095d-1327">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1327">código de seguranca</span></span>
- <span data-ttu-id="0095d-1328">cód.</span><span class="sxs-lookup"><span data-stu-id="0095d-1328">cód.</span></span> <span data-ttu-id="0095d-1329">Segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1329">segurança</span></span>
- <span data-ttu-id="0095d-1330">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1330">cod.</span></span> <span data-ttu-id="0095d-1331">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1331">seguranca cod.</span></span> <span data-ttu-id="0095d-1332">Segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1332">segurança</span></span>
- <span data-ttu-id="0095d-1333">cód.</span><span class="sxs-lookup"><span data-stu-id="0095d-1333">cód.</span></span> <span data-ttu-id="0095d-1334">seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1334">seguranca</span></span>
- <span data-ttu-id="0095d-1335">cód segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1335">cód segurança</span></span>
- <span data-ttu-id="0095d-1336">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1336">cod seguranca cod segurança</span></span>
- <span data-ttu-id="0095d-1337">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1337">cód seguranca</span></span>
- <span data-ttu-id="0095d-1338">número de verificação</span><span class="sxs-lookup"><span data-stu-id="0095d-1338">número de verificação</span></span>
- <span data-ttu-id="0095d-1339">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="0095d-1339">numero de verificacao</span></span>
- <span data-ttu-id="0095d-1340">Ablauf</span><span class="sxs-lookup"><span data-stu-id="0095d-1340">ablauf</span></span>
- <span data-ttu-id="0095d-1341">gültig bis</span><span class="sxs-lookup"><span data-stu-id="0095d-1341">gültig bis</span></span>
- <span data-ttu-id="0095d-1342">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1342">gültigkeitsdatum</span></span>
- <span data-ttu-id="0095d-1343">gultig bis</span><span class="sxs-lookup"><span data-stu-id="0095d-1343">gultig bis</span></span>
- <span data-ttu-id="0095d-1344">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1344">gultigkeitsdatum</span></span>
- <span data-ttu-id="0095d-1345">scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1345">scadenza</span></span>
- <span data-ttu-id="0095d-1346">data scad</span><span class="sxs-lookup"><span data-stu-id="0095d-1346">data scad</span></span>
- <span data-ttu-id="0095d-1347">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="0095d-1347">fecha de expiracion</span></span>
- <span data-ttu-id="0095d-1348">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="0095d-1348">fecha de venc</span></span>
- <span data-ttu-id="0095d-1349">vencimiento</span><span class="sxs-lookup"><span data-stu-id="0095d-1349">vencimiento</span></span>
- <span data-ttu-id="0095d-1350">válido hasta</span><span class="sxs-lookup"><span data-stu-id="0095d-1350">válido hasta</span></span>
- <span data-ttu-id="0095d-1351">valido hasta</span><span class="sxs-lookup"><span data-stu-id="0095d-1351">valido hasta</span></span>
- <span data-ttu-id="0095d-1352">VTO</span><span class="sxs-lookup"><span data-stu-id="0095d-1352">vto</span></span>
- <span data-ttu-id="0095d-1353">data de expiração</span><span class="sxs-lookup"><span data-stu-id="0095d-1353">data de expiração</span></span>
- <span data-ttu-id="0095d-1354">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="0095d-1354">data de expiracao</span></span>
- <span data-ttu-id="0095d-1355">data em que expira</span><span class="sxs-lookup"><span data-stu-id="0095d-1355">data em que expira</span></span>
- <span data-ttu-id="0095d-1356">validade</span><span class="sxs-lookup"><span data-stu-id="0095d-1356">validade</span></span>
- <span data-ttu-id="0095d-1357">Valor</span><span class="sxs-lookup"><span data-stu-id="0095d-1357">valor</span></span>
- <span data-ttu-id="0095d-1358">vencimento</span><span class="sxs-lookup"><span data-stu-id="0095d-1358">vencimento</span></span>
- <span data-ttu-id="0095d-1359">Venc</span><span class="sxs-lookup"><span data-stu-id="0095d-1359">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="0095d-1360">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="0095d-1360">Keyword_cc_name</span></span>

- <span data-ttu-id="0095d-1361">Amex</span><span class="sxs-lookup"><span data-stu-id="0095d-1361">amex</span></span>
- <span data-ttu-id="0095d-1362">american express</span><span class="sxs-lookup"><span data-stu-id="0095d-1362">american express</span></span>
- <span data-ttu-id="0095d-1363">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="0095d-1363">americanexpress</span></span>
- <span data-ttu-id="0095d-1364">Esempio</span><span class="sxs-lookup"><span data-stu-id="0095d-1364">Visa</span></span>
- <span data-ttu-id="0095d-1365">Mastercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1365">mastercard</span></span>
- <span data-ttu-id="0095d-1366">master card</span><span class="sxs-lookup"><span data-stu-id="0095d-1366">master card</span></span>
- <span data-ttu-id="0095d-1367">MC</span><span class="sxs-lookup"><span data-stu-id="0095d-1367">mc</span></span> 
- <span data-ttu-id="0095d-1368">Mastercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1368">mastercards</span></span>
- <span data-ttu-id="0095d-1369">master cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1369">master cards</span></span>
- <span data-ttu-id="0095d-1370">diner's Club</span><span class="sxs-lookup"><span data-stu-id="0095d-1370">diner's Club</span></span>
- <span data-ttu-id="0095d-1371">diners club</span><span class="sxs-lookup"><span data-stu-id="0095d-1371">diners club</span></span>
- <span data-ttu-id="0095d-1372">DinersClub</span><span class="sxs-lookup"><span data-stu-id="0095d-1372">dinersclub</span></span>
- <span data-ttu-id="0095d-1373">discover card</span><span class="sxs-lookup"><span data-stu-id="0095d-1373">discover card</span></span>
- <span data-ttu-id="0095d-1374">discovercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1374">discovercard</span></span>
- <span data-ttu-id="0095d-1375">discover cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1375">discover cards</span></span>
- <span data-ttu-id="0095d-1376">JCB</span><span class="sxs-lookup"><span data-stu-id="0095d-1376">JCB</span></span>
- <span data-ttu-id="0095d-1377">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="0095d-1377">japanese card bureau</span></span>
- <span data-ttu-id="0095d-1378">carte blanche</span><span class="sxs-lookup"><span data-stu-id="0095d-1378">carte blanche</span></span>
- <span data-ttu-id="0095d-1379">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="0095d-1379">carteblanche</span></span>
- <span data-ttu-id="0095d-1380">credit card</span><span class="sxs-lookup"><span data-stu-id="0095d-1380">credit card</span></span>
- <span data-ttu-id="0095d-1381">CC</span><span class="sxs-lookup"><span data-stu-id="0095d-1381">cc#</span></span>
- <span data-ttu-id="0095d-1382">CC #:</span><span class="sxs-lookup"><span data-stu-id="0095d-1382">cc#:</span></span>
- <span data-ttu-id="0095d-1383">expiration date</span><span class="sxs-lookup"><span data-stu-id="0095d-1383">expiration date</span></span>
- <span data-ttu-id="0095d-1384">exp date</span><span class="sxs-lookup"><span data-stu-id="0095d-1384">exp date</span></span>
- <span data-ttu-id="0095d-1385">expiry date</span><span class="sxs-lookup"><span data-stu-id="0095d-1385">expiry date</span></span>
- <span data-ttu-id="0095d-1386">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="0095d-1386">date d’expiration</span></span>
- <span data-ttu-id="0095d-1387">date d'exp</span><span class="sxs-lookup"><span data-stu-id="0095d-1387">date d'exp</span></span>
- <span data-ttu-id="0095d-1388">date expiration</span><span class="sxs-lookup"><span data-stu-id="0095d-1388">date expiration</span></span>
- <span data-ttu-id="0095d-1389">bank card</span><span class="sxs-lookup"><span data-stu-id="0095d-1389">bank card</span></span>
- <span data-ttu-id="0095d-1390">Bankcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1390">bankcard</span></span>
- <span data-ttu-id="0095d-1391">card number</span><span class="sxs-lookup"><span data-stu-id="0095d-1391">card number</span></span>
- <span data-ttu-id="0095d-1392">card num</span><span class="sxs-lookup"><span data-stu-id="0095d-1392">card num</span></span>
- <span data-ttu-id="0095d-1393">CardNumber</span><span class="sxs-lookup"><span data-stu-id="0095d-1393">cardnumber</span></span>
- <span data-ttu-id="0095d-1394">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1394">cardnumbers</span></span>
- <span data-ttu-id="0095d-1395">card numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1395">card numbers</span></span>
- <span data-ttu-id="0095d-1396">CreditCard</span><span class="sxs-lookup"><span data-stu-id="0095d-1396">creditcard</span></span>
- <span data-ttu-id="0095d-1397">credit cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1397">credit cards</span></span>
- <span data-ttu-id="0095d-1398">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="0095d-1398">creditcards</span></span>
- <span data-ttu-id="0095d-1399">Ccn</span><span class="sxs-lookup"><span data-stu-id="0095d-1399">ccn</span></span>
- <span data-ttu-id="0095d-1400">card holder</span><span class="sxs-lookup"><span data-stu-id="0095d-1400">card holder</span></span>
- <span data-ttu-id="0095d-1401">titolare</span><span class="sxs-lookup"><span data-stu-id="0095d-1401">cardholder</span></span>
- <span data-ttu-id="0095d-1402">card holders</span><span class="sxs-lookup"><span data-stu-id="0095d-1402">card holders</span></span>
- <span data-ttu-id="0095d-1403">titolari</span><span class="sxs-lookup"><span data-stu-id="0095d-1403">cardholders</span></span>
- <span data-ttu-id="0095d-1404">check card</span><span class="sxs-lookup"><span data-stu-id="0095d-1404">check card</span></span>
- <span data-ttu-id="0095d-1405">checkcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1405">checkcard</span></span>
- <span data-ttu-id="0095d-1406">check cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1406">check cards</span></span>
- <span data-ttu-id="0095d-1407">checkcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1407">checkcards</span></span>
- <span data-ttu-id="0095d-1408">debit card</span><span class="sxs-lookup"><span data-stu-id="0095d-1408">debit card</span></span>
- <span data-ttu-id="0095d-1409">debitcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1409">debitcard</span></span>
- <span data-ttu-id="0095d-1410">debit cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1410">debit cards</span></span>
- <span data-ttu-id="0095d-1411">debitcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1411">debitcards</span></span>
- <span data-ttu-id="0095d-1412">atm card</span><span class="sxs-lookup"><span data-stu-id="0095d-1412">atm card</span></span>
- <span data-ttu-id="0095d-1413">atmcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1413">atmcard</span></span>
- <span data-ttu-id="0095d-1414">atm cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1414">atm cards</span></span>
- <span data-ttu-id="0095d-1415">atmcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1415">atmcards</span></span>
- <span data-ttu-id="0095d-1416">Enroute</span><span class="sxs-lookup"><span data-stu-id="0095d-1416">enroute</span></span>
- <span data-ttu-id="0095d-1417">en route</span><span class="sxs-lookup"><span data-stu-id="0095d-1417">en route</span></span>
- <span data-ttu-id="0095d-1418">card type</span><span class="sxs-lookup"><span data-stu-id="0095d-1418">card type</span></span>
- <span data-ttu-id="0095d-1419">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="0095d-1419">carte bancaire</span></span>
- <span data-ttu-id="0095d-1420">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="0095d-1420">carte de crédit</span></span>
- <span data-ttu-id="0095d-1421">carte de credit</span><span class="sxs-lookup"><span data-stu-id="0095d-1421">carte de credit</span></span>
- <span data-ttu-id="0095d-1422">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1422">numéro de carte</span></span>
- <span data-ttu-id="0095d-1423">numero de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1423">numero de carte</span></span>
- <span data-ttu-id="0095d-1424">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1424">nº de la carte</span></span>
- <span data-ttu-id="0095d-1425">nº de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1425">nº de carte</span></span>
- <span data-ttu-id="0095d-1426">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="0095d-1426">kreditkarte</span></span>
- <span data-ttu-id="0095d-1427">Karte</span><span class="sxs-lookup"><span data-stu-id="0095d-1427">karte</span></span>
- <span data-ttu-id="0095d-1428">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="0095d-1428">karteninhaber</span></span>
- <span data-ttu-id="0095d-1429">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="0095d-1429">karteninhabers</span></span>
- <span data-ttu-id="0095d-1430">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="0095d-1430">kreditkarteninhaber</span></span>
- <span data-ttu-id="0095d-1431">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="0095d-1431">kreditkarteninstitut</span></span>
- <span data-ttu-id="0095d-1432">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="0095d-1432">kreditkartentyp</span></span>
- <span data-ttu-id="0095d-1433">eigentümername</span><span class="sxs-lookup"><span data-stu-id="0095d-1433">eigentümername</span></span>
- <span data-ttu-id="0095d-1434">kartennr</span><span class="sxs-lookup"><span data-stu-id="0095d-1434">kartennr</span></span> 
- <span data-ttu-id="0095d-1435">kartennummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1435">kartennummer</span></span>
- <span data-ttu-id="0095d-1436">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1436">kreditkartennummer</span></span>
- <span data-ttu-id="0095d-1437">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1437">kreditkarten-nummer</span></span>
- <span data-ttu-id="0095d-1438">carta di credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1438">carta di credito</span></span>
- <span data-ttu-id="0095d-1439">carta credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1439">carta credito</span></span>
- <span data-ttu-id="0095d-1440">carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1440">carta</span></span>
- <span data-ttu-id="0095d-1441">n carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1441">n carta</span></span>
- <span data-ttu-id="0095d-1442">Nr.</span><span class="sxs-lookup"><span data-stu-id="0095d-1442">nr.</span></span> <span data-ttu-id="0095d-1443">carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1443">carta</span></span>
- <span data-ttu-id="0095d-1444">nr carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1444">nr carta</span></span>
- <span data-ttu-id="0095d-1445">numero carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1445">numero carta</span></span>
- <span data-ttu-id="0095d-1446">numero della carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1446">numero della carta</span></span>
- <span data-ttu-id="0095d-1447">numero di carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1447">numero di carta</span></span>
- <span data-ttu-id="0095d-1448">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1448">tarjeta credito</span></span>
- <span data-ttu-id="0095d-1449">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1449">tarjeta de credito</span></span>
- <span data-ttu-id="0095d-1450">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1450">tarjeta crédito</span></span>
- <span data-ttu-id="0095d-1451">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1451">tarjeta de crédito</span></span>
- <span data-ttu-id="0095d-1452">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="0095d-1452">tarjeta de atm</span></span>
- <span data-ttu-id="0095d-1453">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="0095d-1453">tarjeta atm</span></span>
- <span data-ttu-id="0095d-1454">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1454">tarjeta debito</span></span>
- <span data-ttu-id="0095d-1455">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1455">tarjeta de debito</span></span>
- <span data-ttu-id="0095d-1456">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1456">tarjeta débito</span></span>
- <span data-ttu-id="0095d-1457">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1457">tarjeta de débito</span></span>
- <span data-ttu-id="0095d-1458">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1458">nº de tarjeta</span></span>
- <span data-ttu-id="0095d-1459">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1459">no.</span></span> <span data-ttu-id="0095d-1460">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1460">de tarjeta</span></span>
- <span data-ttu-id="0095d-1461">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1461">no de tarjeta</span></span>
- <span data-ttu-id="0095d-1462">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1462">numero de tarjeta</span></span>
- <span data-ttu-id="0095d-1463">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1463">número de tarjeta</span></span>
- <span data-ttu-id="0095d-1464">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="0095d-1464">tarjeta no</span></span>
- <span data-ttu-id="0095d-1465">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="0095d-1465">tarjetahabiente</span></span>
- <span data-ttu-id="0095d-1466">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1466">cartão de crédito</span></span>
- <span data-ttu-id="0095d-1467">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1467">cartão de credito</span></span>
- <span data-ttu-id="0095d-1468">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1468">cartao de crédito</span></span>
- <span data-ttu-id="0095d-1469">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1469">cartao de credito</span></span>
- <span data-ttu-id="0095d-1470">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1470">cartão de débito</span></span>
- <span data-ttu-id="0095d-1471">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1471">cartao de débito</span></span>
- <span data-ttu-id="0095d-1472">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1472">cartão de debito</span></span>
- <span data-ttu-id="0095d-1473">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1473">cartao de debito</span></span>
- <span data-ttu-id="0095d-1474">débito automático</span><span class="sxs-lookup"><span data-stu-id="0095d-1474">débito automático</span></span>
- <span data-ttu-id="0095d-1475">debito automatico</span><span class="sxs-lookup"><span data-stu-id="0095d-1475">debito automatico</span></span>
- <span data-ttu-id="0095d-1476">número do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1476">número do cartão</span></span>
- <span data-ttu-id="0095d-1477">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1477">numero do cartão</span></span> 
- <span data-ttu-id="0095d-1478">número do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1478">número do cartao</span></span>
- <span data-ttu-id="0095d-1479">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1479">numero do cartao</span></span>
- <span data-ttu-id="0095d-1480">número de cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1480">número de cartão</span></span>
- <span data-ttu-id="0095d-1481">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1481">numero de cartão</span></span>
- <span data-ttu-id="0095d-1482">número de cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1482">número de cartao</span></span>
- <span data-ttu-id="0095d-1483">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1483">numero de cartao</span></span>
- <span data-ttu-id="0095d-1484">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1484">nº do cartão</span></span>
- <span data-ttu-id="0095d-1485">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1485">nº do cartao</span></span>
- <span data-ttu-id="0095d-1486">n º.</span><span class="sxs-lookup"><span data-stu-id="0095d-1486">nº.</span></span> <span data-ttu-id="0095d-1487">do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1487">do cartão</span></span>
- <span data-ttu-id="0095d-1488">no do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1488">no do cartão</span></span>
- <span data-ttu-id="0095d-1489">no do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1489">no do cartao</span></span>
- <span data-ttu-id="0095d-1490">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1490">no.</span></span> <span data-ttu-id="0095d-1491">do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1491">do cartão</span></span>
- <span data-ttu-id="0095d-1492">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1492">no.</span></span> <span data-ttu-id="0095d-1493">do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1493">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="0095d-1494">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="0095d-1494">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1495">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1495">Format</span></span>

<span data-ttu-id="0095d-1496">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1496">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1497">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1497">Pattern</span></span>

<span data-ttu-id="0095d-1498">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-1498">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1499">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1499">Checksum</span></span>

<span data-ttu-id="0095d-1500">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1500">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1501">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1501">Definition</span></span>

<span data-ttu-id="0095d-1502">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1502">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1503">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1503">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1504">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-1504">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-1505">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1505">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="0095d-1506">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-1506">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="0095d-1507">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="0095d-1507">Croatian identity card</span></span>
- <span data-ttu-id="0095d-1508">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="0095d-1508">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="0095d-1509">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="0095d-1509">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1510">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1510">Format</span></span>

<span data-ttu-id="0095d-1511">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1511">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1512">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1512">Pattern</span></span>

<span data-ttu-id="0095d-1513">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-1513">11 digits:</span></span>
- <span data-ttu-id="0095d-1514">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1514">10 digits</span></span> 
- <span data-ttu-id="0095d-1515">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="0095d-1515">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1516">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1516">Checksum</span></span>

<span data-ttu-id="0095d-1517">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1518">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1518">Definition</span></span>

<span data-ttu-id="0095d-1519">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1520">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1520">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1521">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-1521">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="0095d-1522">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1522">The checksum passes.</span></span>

<span data-ttu-id="0095d-1523">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1523">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1524">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1524">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1525">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1525">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1526">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1526">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="0095d-1527">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="0095d-1527">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="0095d-1528">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="0095d-1528">Personal Identification Number</span></span>
- <span data-ttu-id="0095d-1529">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="0095d-1529">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="0095d-1530">OIB</span><span class="sxs-lookup"><span data-stu-id="0095d-1530">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="0095d-1531">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="0095d-1531">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1532">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1532">Format</span></span>

<span data-ttu-id="0095d-1533">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="0095d-1533">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1534">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1534">Pattern</span></span>

<span data-ttu-id="0095d-1535">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="0095d-1535">Nine digits (old format):</span></span>
- <span data-ttu-id="0095d-1536">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1536">Nine digits</span></span>

<span data-ttu-id="0095d-1537">O</span><span class="sxs-lookup"><span data-stu-id="0095d-1537">OR</span></span>

- <span data-ttu-id="0095d-1538">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-1538">Six digits that represent date of birth</span></span>
- <span data-ttu-id="0095d-1539">Una barra</span><span class="sxs-lookup"><span data-stu-id="0095d-1539">A forward slash</span></span>
- <span data-ttu-id="0095d-1540">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1540">Three digits</span></span>

<span data-ttu-id="0095d-1541">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="0095d-1541">10 digits (new format):</span></span>
- <span data-ttu-id="0095d-1542">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1542">10 digits</span></span>

<span data-ttu-id="0095d-1543">O</span><span class="sxs-lookup"><span data-stu-id="0095d-1543">OR</span></span>

- <span data-ttu-id="0095d-1544">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-1544">Six digits that represent date of birth</span></span>
- <span data-ttu-id="0095d-1545">Una barra</span><span class="sxs-lookup"><span data-stu-id="0095d-1545">A forward slash</span></span> 
- <span data-ttu-id="0095d-1546">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1546">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1547">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1547">Checksum</span></span>

<span data-ttu-id="0095d-1548">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1549">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1549">Definition</span></span>

<span data-ttu-id="0095d-1550">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-1551">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-1551">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="0095d-1552">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1552">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="0095d-1553">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1553">Keywords</span></span>

- <span data-ttu-id="0095d-1554">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="0095d-1554">czech personal identity number</span></span>
- <span data-ttu-id="0095d-1555">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="0095d-1555">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="0095d-1556">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="0095d-1556">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1557">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1557">Format</span></span>

<span data-ttu-id="0095d-1558">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-1558">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1559">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1559">Pattern</span></span>

<span data-ttu-id="0095d-1560">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-1560">10 digits:</span></span>
- <span data-ttu-id="0095d-1561">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-1561">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="0095d-1562">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-1562">A hyphen</span></span> 
- <span data-ttu-id="0095d-1563">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1563">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1564">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1564">Checksum</span></span>

<span data-ttu-id="0095d-1565">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1565">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1566">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1566">Definition</span></span>

<span data-ttu-id="0095d-1567">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-1568">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-1568">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="0095d-1569">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1569">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-1570">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1570">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="0095d-1571">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="0095d-1571">Keyword_denmark_id</span></span>

- <span data-ttu-id="0095d-1572">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="0095d-1572">Personal Identification Number</span></span>
- <span data-ttu-id="0095d-1573">CPR</span><span class="sxs-lookup"><span data-stu-id="0095d-1573">CPR</span></span>
- <span data-ttu-id="0095d-1574">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="0095d-1574">Det Centrale Personregister</span></span>
- <span data-ttu-id="0095d-1575">Personnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1575">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="0095d-1576">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="0095d-1576">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1577">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1577">Format</span></span>

<span data-ttu-id="0095d-1578">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1578">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1579">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1579">Pattern</span></span>

<span data-ttu-id="0095d-1580">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-1580">Pattern must include all of the following:</span></span>
- <span data-ttu-id="0095d-1581">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="0095d-1581">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="0095d-1582">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="0095d-1582">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="0095d-1583">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1583">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1584">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1584">Checksum</span></span>

<span data-ttu-id="0095d-1585">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1586">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1586">Definition</span></span>

<span data-ttu-id="0095d-1587">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1587">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1588">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1588">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1589">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1589">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-1590">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1590">Keywords</span></span>

<span data-ttu-id="0095d-1591">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0095d-1591">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="0095d-1592">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1592">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1593">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1593">Format</span></span>

<span data-ttu-id="0095d-1594">16 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1594">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1595">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1595">Pattern</span></span>

<span data-ttu-id="0095d-1596">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="0095d-1596">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1597">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1597">Checksum</span></span>

<span data-ttu-id="0095d-1598">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1598">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1599">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1599">Definition</span></span>

<span data-ttu-id="0095d-1600">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1600">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1601">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1601">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1602">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-1602">At least one of the following is true:</span></span>
    - <span data-ttu-id="0095d-1603">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-1603">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="0095d-1604">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="0095d-1604">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="0095d-1605">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="0095d-1605">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="0095d-1606">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="0095d-1606">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="0095d-1607">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-1607">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="0095d-1608">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1608">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1609">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1609">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="0095d-1610">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="0095d-1610">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="0095d-1611">account number</span><span class="sxs-lookup"><span data-stu-id="0095d-1611">account number</span></span> 
- <span data-ttu-id="0095d-1612">card number</span><span class="sxs-lookup"><span data-stu-id="0095d-1612">card number</span></span> 
- <span data-ttu-id="0095d-1613">card no.</span><span class="sxs-lookup"><span data-stu-id="0095d-1613">card no.</span></span> 
- <span data-ttu-id="0095d-1614">security number</span><span class="sxs-lookup"><span data-stu-id="0095d-1614">security number</span></span> 
- <span data-ttu-id="0095d-1615">CC</span><span class="sxs-lookup"><span data-stu-id="0095d-1615">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="0095d-1616">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="0095d-1616">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="0095d-1617">acct nbr</span><span class="sxs-lookup"><span data-stu-id="0095d-1617">acct nbr</span></span> 
- <span data-ttu-id="0095d-1618">acct num</span><span class="sxs-lookup"><span data-stu-id="0095d-1618">acct num</span></span> 
- <span data-ttu-id="0095d-1619">acct no</span><span class="sxs-lookup"><span data-stu-id="0095d-1619">acct no</span></span> 
- <span data-ttu-id="0095d-1620">american express</span><span class="sxs-lookup"><span data-stu-id="0095d-1620">american express</span></span> 
- <span data-ttu-id="0095d-1621">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="0095d-1621">americanexpress</span></span> 
- <span data-ttu-id="0095d-1622">americano espresso</span><span class="sxs-lookup"><span data-stu-id="0095d-1622">americano espresso</span></span> 
- <span data-ttu-id="0095d-1623">Amex</span><span class="sxs-lookup"><span data-stu-id="0095d-1623">amex</span></span> 
- <span data-ttu-id="0095d-1624">atm card</span><span class="sxs-lookup"><span data-stu-id="0095d-1624">atm card</span></span> 
- <span data-ttu-id="0095d-1625">atm cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1625">atm cards</span></span> 
- <span data-ttu-id="0095d-1626">atm kaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1626">atm kaart</span></span> 
- <span data-ttu-id="0095d-1627">atmcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1627">atmcard</span></span> 
- <span data-ttu-id="0095d-1628">atmcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1628">atmcards</span></span> 
- <span data-ttu-id="0095d-1629">atmkaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1629">atmkaart</span></span> 
- <span data-ttu-id="0095d-1630">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="0095d-1630">atmkaarten</span></span> 
- <span data-ttu-id="0095d-1631">Bancontact</span><span class="sxs-lookup"><span data-stu-id="0095d-1631">bancontact</span></span> 
- <span data-ttu-id="0095d-1632">bank card</span><span class="sxs-lookup"><span data-stu-id="0095d-1632">bank card</span></span> 
- <span data-ttu-id="0095d-1633">bankkaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1633">bankkaart</span></span> 
- <span data-ttu-id="0095d-1634">card holder</span><span class="sxs-lookup"><span data-stu-id="0095d-1634">card holder</span></span> 
- <span data-ttu-id="0095d-1635">card holders</span><span class="sxs-lookup"><span data-stu-id="0095d-1635">card holders</span></span> 
- <span data-ttu-id="0095d-1636">card num</span><span class="sxs-lookup"><span data-stu-id="0095d-1636">card num</span></span> 
- <span data-ttu-id="0095d-1637">card number</span><span class="sxs-lookup"><span data-stu-id="0095d-1637">card number</span></span> 
- <span data-ttu-id="0095d-1638">card numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1638">card numbers</span></span> 
- <span data-ttu-id="0095d-1639">card type</span><span class="sxs-lookup"><span data-stu-id="0095d-1639">card type</span></span> 
- <span data-ttu-id="0095d-1640">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="0095d-1640">cardano numerico</span></span> 
- <span data-ttu-id="0095d-1641">titolare</span><span class="sxs-lookup"><span data-stu-id="0095d-1641">cardholder</span></span> 
- <span data-ttu-id="0095d-1642">titolari</span><span class="sxs-lookup"><span data-stu-id="0095d-1642">cardholders</span></span> 
- <span data-ttu-id="0095d-1643">CardNumber</span><span class="sxs-lookup"><span data-stu-id="0095d-1643">cardnumber</span></span> 
- <span data-ttu-id="0095d-1644">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1644">cardnumbers</span></span> 
- <span data-ttu-id="0095d-1645">carta bianca</span><span class="sxs-lookup"><span data-stu-id="0095d-1645">carta bianca</span></span> 
- <span data-ttu-id="0095d-1646">carta credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1646">carta credito</span></span> 
- <span data-ttu-id="0095d-1647">carta di credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1647">carta di credito</span></span> 
- <span data-ttu-id="0095d-1648">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1648">cartao de credito</span></span> 
- <span data-ttu-id="0095d-1649">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1649">cartao de crédito</span></span> 
- <span data-ttu-id="0095d-1650">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1650">cartao de debito</span></span> 
- <span data-ttu-id="0095d-1651">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1651">cartao de débito</span></span> 
- <span data-ttu-id="0095d-1652">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="0095d-1652">carte bancaire</span></span> 
- <span data-ttu-id="0095d-1653">carte blanche</span><span class="sxs-lookup"><span data-stu-id="0095d-1653">carte blanche</span></span> 
- <span data-ttu-id="0095d-1654">carte bleue</span><span class="sxs-lookup"><span data-stu-id="0095d-1654">carte bleue</span></span> 
- <span data-ttu-id="0095d-1655">carte de credit</span><span class="sxs-lookup"><span data-stu-id="0095d-1655">carte de credit</span></span> 
- <span data-ttu-id="0095d-1656">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="0095d-1656">carte de crédit</span></span> 
- <span data-ttu-id="0095d-1657">carte di credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1657">carte di credito</span></span> 
- <span data-ttu-id="0095d-1658">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="0095d-1658">carteblanche</span></span> 
- <span data-ttu-id="0095d-1659">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1659">cartão de credito</span></span> 
- <span data-ttu-id="0095d-1660">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="0095d-1660">cartão de crédito</span></span> 
- <span data-ttu-id="0095d-1661">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1661">cartão de debito</span></span> 
- <span data-ttu-id="0095d-1662">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="0095d-1662">cartão de débito</span></span> 
- <span data-ttu-id="0095d-1663">CB</span><span class="sxs-lookup"><span data-stu-id="0095d-1663">cb</span></span> 
- <span data-ttu-id="0095d-1664">Ccn</span><span class="sxs-lookup"><span data-stu-id="0095d-1664">ccn</span></span> 
- <span data-ttu-id="0095d-1665">check card</span><span class="sxs-lookup"><span data-stu-id="0095d-1665">check card</span></span> 
- <span data-ttu-id="0095d-1666">check cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1666">check cards</span></span> 
- <span data-ttu-id="0095d-1667">checkcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1667">checkcard</span></span>
- <span data-ttu-id="0095d-1668">checkcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1668">checkcards</span></span> 
- <span data-ttu-id="0095d-1669">chequekaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1669">chequekaart</span></span> 
- <span data-ttu-id="0095d-1670">Cirrus</span><span class="sxs-lookup"><span data-stu-id="0095d-1670">cirrus</span></span> 
- <span data-ttu-id="0095d-1671">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="0095d-1671">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="0095d-1672">controlekaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1672">controlekaart</span></span> 
- <span data-ttu-id="0095d-1673">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="0095d-1673">controlekaarten</span></span> 
- <span data-ttu-id="0095d-1674">credit card</span><span class="sxs-lookup"><span data-stu-id="0095d-1674">credit card</span></span> 
- <span data-ttu-id="0095d-1675">credit cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1675">credit cards</span></span> 
- <span data-ttu-id="0095d-1676">CreditCard</span><span class="sxs-lookup"><span data-stu-id="0095d-1676">creditcard</span></span> 
- <span data-ttu-id="0095d-1677">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="0095d-1677">creditcards</span></span> 
- <span data-ttu-id="0095d-1678">debetkaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1678">debetkaart</span></span> 
- <span data-ttu-id="0095d-1679">carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1679">debetkaarten</span></span> 
- <span data-ttu-id="0095d-1680">debit card</span><span class="sxs-lookup"><span data-stu-id="0095d-1680">debit card</span></span> 
- <span data-ttu-id="0095d-1681">debit cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1681">debit cards</span></span> 
- <span data-ttu-id="0095d-1682">debitcard</span><span class="sxs-lookup"><span data-stu-id="0095d-1682">debitcard</span></span> 
- <span data-ttu-id="0095d-1683">debitcards</span><span class="sxs-lookup"><span data-stu-id="0095d-1683">debitcards</span></span> 
- <span data-ttu-id="0095d-1684">debito automatico</span><span class="sxs-lookup"><span data-stu-id="0095d-1684">debito automatico</span></span> 
- <span data-ttu-id="0095d-1685">diners club</span><span class="sxs-lookup"><span data-stu-id="0095d-1685">diners club</span></span> 
- <span data-ttu-id="0095d-1686">DinersClub</span><span class="sxs-lookup"><span data-stu-id="0095d-1686">dinersclub</span></span> 
- <span data-ttu-id="0095d-1687">individuare</span><span class="sxs-lookup"><span data-stu-id="0095d-1687">discover</span></span> 
- <span data-ttu-id="0095d-1688">discover card</span><span class="sxs-lookup"><span data-stu-id="0095d-1688">discover card</span></span> 
- <span data-ttu-id="0095d-1689">discover cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1689">discover cards</span></span> 
- <span data-ttu-id="0095d-1690">discovercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1690">discovercard</span></span> 
- <span data-ttu-id="0095d-1691">discovercards</span><span class="sxs-lookup"><span data-stu-id="0095d-1691">discovercards</span></span> 
- <span data-ttu-id="0095d-1692">débito automático</span><span class="sxs-lookup"><span data-stu-id="0095d-1692">débito automático</span></span>
- <span data-ttu-id="0095d-1693">EDC</span><span class="sxs-lookup"><span data-stu-id="0095d-1693">edc</span></span> 
- <span data-ttu-id="0095d-1694">eigentümername</span><span class="sxs-lookup"><span data-stu-id="0095d-1694">eigentümername</span></span> 
- <span data-ttu-id="0095d-1695">european debit card</span><span class="sxs-lookup"><span data-stu-id="0095d-1695">european debit card</span></span> 
- <span data-ttu-id="0095d-1696">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1696">hoofdkaart</span></span> 
- <span data-ttu-id="0095d-1697">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="0095d-1697">hoofdkaarten</span></span> 
- <span data-ttu-id="0095d-1698">in viaggio</span><span class="sxs-lookup"><span data-stu-id="0095d-1698">in viaggio</span></span> 
- <span data-ttu-id="0095d-1699">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="0095d-1699">japanese card bureau</span></span> 
- <span data-ttu-id="0095d-1700">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="0095d-1700">japanse kaartdienst</span></span> 
- <span data-ttu-id="0095d-1701">JCB</span><span class="sxs-lookup"><span data-stu-id="0095d-1701">jcb</span></span> 
- <span data-ttu-id="0095d-1702">kaart</span><span class="sxs-lookup"><span data-stu-id="0095d-1702">kaart</span></span> 
- <span data-ttu-id="0095d-1703">kaart num</span><span class="sxs-lookup"><span data-stu-id="0095d-1703">kaart num</span></span> 
- <span data-ttu-id="0095d-1704">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="0095d-1704">kaartaantal</span></span> 
- <span data-ttu-id="0095d-1705">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="0095d-1705">kaartaantallen</span></span> 
- <span data-ttu-id="0095d-1706">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="0095d-1706">kaarthouder</span></span> 
- <span data-ttu-id="0095d-1707">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="0095d-1707">kaarthouders</span></span> 
- <span data-ttu-id="0095d-1708">Karte</span><span class="sxs-lookup"><span data-stu-id="0095d-1708">karte</span></span>  
- <span data-ttu-id="0095d-1709">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="0095d-1709">karteninhaber</span></span> 
- <span data-ttu-id="0095d-1710">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="0095d-1710">karteninhabers</span></span>
- <span data-ttu-id="0095d-1711">kartennr</span><span class="sxs-lookup"><span data-stu-id="0095d-1711">kartennr</span></span> 
- <span data-ttu-id="0095d-1712">kartennummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1712">kartennummer</span></span> 
- <span data-ttu-id="0095d-1713">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="0095d-1713">kreditkarte</span></span> 
- <span data-ttu-id="0095d-1714">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1714">kreditkarten-nummer</span></span> 
- <span data-ttu-id="0095d-1715">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="0095d-1715">kreditkarteninhaber</span></span> 
- <span data-ttu-id="0095d-1716">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="0095d-1716">kreditkarteninstitut</span></span> 
- <span data-ttu-id="0095d-1717">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1717">kreditkartennummer</span></span> 
- <span data-ttu-id="0095d-1718">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="0095d-1718">kreditkartentyp</span></span> 
- <span data-ttu-id="0095d-1719">Maestro</span><span class="sxs-lookup"><span data-stu-id="0095d-1719">maestro</span></span> 
- <span data-ttu-id="0095d-1720">master card</span><span class="sxs-lookup"><span data-stu-id="0095d-1720">master card</span></span> 
- <span data-ttu-id="0095d-1721">master cards</span><span class="sxs-lookup"><span data-stu-id="0095d-1721">master cards</span></span> 
- <span data-ttu-id="0095d-1722">Mastercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1722">mastercard</span></span> 
- <span data-ttu-id="0095d-1723">Mastercard</span><span class="sxs-lookup"><span data-stu-id="0095d-1723">mastercards</span></span> 
- <span data-ttu-id="0095d-1724">MC</span><span class="sxs-lookup"><span data-stu-id="0095d-1724">mc</span></span> 
- <span data-ttu-id="0095d-1725">mister cash</span><span class="sxs-lookup"><span data-stu-id="0095d-1725">mister cash</span></span> 
- <span data-ttu-id="0095d-1726">n carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1726">n carta</span></span> 
- <span data-ttu-id="0095d-1727">carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1727">carta</span></span> 
- <span data-ttu-id="0095d-1728">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1728">no de tarjeta</span></span> 
- <span data-ttu-id="0095d-1729">no do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1729">no do cartao</span></span> 
- <span data-ttu-id="0095d-1730">no do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1730">no do cartão</span></span> 
- <span data-ttu-id="0095d-1731">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1731">no.</span></span> <span data-ttu-id="0095d-1732">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1732">de tarjeta</span></span> 
- <span data-ttu-id="0095d-1733">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1733">no.</span></span> <span data-ttu-id="0095d-1734">do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1734">do cartao</span></span> 
- <span data-ttu-id="0095d-1735">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1735">no.</span></span> <span data-ttu-id="0095d-1736">do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1736">do cartão</span></span> 
- <span data-ttu-id="0095d-1737">nr carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1737">nr carta</span></span> 
- <span data-ttu-id="0095d-1738">Nr.</span><span class="sxs-lookup"><span data-stu-id="0095d-1738">nr.</span></span> <span data-ttu-id="0095d-1739">carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1739">carta</span></span> 
- <span data-ttu-id="0095d-1740">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1740">numeri di scheda</span></span> 
- <span data-ttu-id="0095d-1741">numero carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1741">numero carta</span></span> 
- <span data-ttu-id="0095d-1742">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1742">numero de cartao</span></span> 
- <span data-ttu-id="0095d-1743">numero de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1743">numero de carte</span></span> 
- <span data-ttu-id="0095d-1744">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1744">numero de cartão</span></span> 
- <span data-ttu-id="0095d-1745">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1745">numero de tarjeta</span></span>
- <span data-ttu-id="0095d-1746">numero della carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1746">numero della carta</span></span> 
- <span data-ttu-id="0095d-1747">numero di carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1747">numero di carta</span></span> 
- <span data-ttu-id="0095d-1748">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1748">numero di scheda</span></span> 
- <span data-ttu-id="0095d-1749">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1749">numero do cartao</span></span> 
- <span data-ttu-id="0095d-1750">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1750">numero do cartão</span></span> 
- <span data-ttu-id="0095d-1751">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1751">numéro de carte</span></span> 
- <span data-ttu-id="0095d-1752">nº carta</span><span class="sxs-lookup"><span data-stu-id="0095d-1752">nº carta</span></span> 
- <span data-ttu-id="0095d-1753">nº de carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1753">nº de carte</span></span> 
- <span data-ttu-id="0095d-1754">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="0095d-1754">nº de la carte</span></span> 
- <span data-ttu-id="0095d-1755">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1755">nº de tarjeta</span></span> 
- <span data-ttu-id="0095d-1756">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1756">nº do cartao</span></span> 
- <span data-ttu-id="0095d-1757">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1757">nº do cartão</span></span> 
- <span data-ttu-id="0095d-1758">n º.</span><span class="sxs-lookup"><span data-stu-id="0095d-1758">nº.</span></span> <span data-ttu-id="0095d-1759">do cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1759">do cartão</span></span> 
- <span data-ttu-id="0095d-1760">número de cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1760">número de cartao</span></span> 
- <span data-ttu-id="0095d-1761">número de cartão</span><span class="sxs-lookup"><span data-stu-id="0095d-1761">número de cartão</span></span> 
- <span data-ttu-id="0095d-1762">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="0095d-1762">número de tarjeta</span></span> 
- <span data-ttu-id="0095d-1763">número do cartao</span><span class="sxs-lookup"><span data-stu-id="0095d-1763">número do cartao</span></span> 
- <span data-ttu-id="0095d-1764">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="0095d-1764">scheda dell'assegno</span></span> 
- <span data-ttu-id="0095d-1765">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="0095d-1765">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="0095d-1766">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="0095d-1766">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="0095d-1767">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="0095d-1767">scheda della banca</span></span> 
- <span data-ttu-id="0095d-1768">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1768">scheda di controllo</span></span> 
- <span data-ttu-id="0095d-1769">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1769">scheda di debito</span></span> 
- <span data-ttu-id="0095d-1770">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="0095d-1770">scheda matrice</span></span> 
- <span data-ttu-id="0095d-1771">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="0095d-1771">schede dell'atmosfera</span></span> 
- <span data-ttu-id="0095d-1772">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1772">schede di controllo</span></span> 
- <span data-ttu-id="0095d-1773">schede di debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1773">schede di debito</span></span> 
- <span data-ttu-id="0095d-1774">schede matrici</span><span class="sxs-lookup"><span data-stu-id="0095d-1774">schede matrici</span></span> 
- <span data-ttu-id="0095d-1775">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1775">scoprono la scheda</span></span> 
- <span data-ttu-id="0095d-1776">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="0095d-1776">scoprono le schede</span></span> 
- <span data-ttu-id="0095d-1777">solo</span><span class="sxs-lookup"><span data-stu-id="0095d-1777">solo</span></span> 
- <span data-ttu-id="0095d-1778">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1778">supporti di scheda</span></span> 
- <span data-ttu-id="0095d-1779">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1779">supporto di scheda</span></span> 
- <span data-ttu-id="0095d-1780">opzione</span><span class="sxs-lookup"><span data-stu-id="0095d-1780">switch</span></span> 
- <span data-ttu-id="0095d-1781">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="0095d-1781">tarjeta atm</span></span> 
- <span data-ttu-id="0095d-1782">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1782">tarjeta credito</span></span> 
- <span data-ttu-id="0095d-1783">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="0095d-1783">tarjeta de atm</span></span> 
- <span data-ttu-id="0095d-1784">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="0095d-1784">tarjeta de credito</span></span> 
- <span data-ttu-id="0095d-1785">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1785">tarjeta de debito</span></span> 
- <span data-ttu-id="0095d-1786">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="0095d-1786">tarjeta debito</span></span> 
- <span data-ttu-id="0095d-1787">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="0095d-1787">tarjeta no</span></span>
- <span data-ttu-id="0095d-1788">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="0095d-1788">tarjetahabiente</span></span> 
- <span data-ttu-id="0095d-1789">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1789">tipo della scheda</span></span> 
- <span data-ttu-id="0095d-1790">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="0095d-1790">ufficio giapponese della</span></span> 
- <span data-ttu-id="0095d-1791">scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1791">scheda</span></span> 
- <span data-ttu-id="0095d-1792">v pay</span><span class="sxs-lookup"><span data-stu-id="0095d-1792">v pay</span></span> 
- <span data-ttu-id="0095d-1793">v-pay</span><span class="sxs-lookup"><span data-stu-id="0095d-1793">v-pay</span></span> 
- <span data-ttu-id="0095d-1794">esempio</span><span class="sxs-lookup"><span data-stu-id="0095d-1794">visa</span></span> 
- <span data-ttu-id="0095d-1795">visa plus</span><span class="sxs-lookup"><span data-stu-id="0095d-1795">visa plus</span></span> 
- <span data-ttu-id="0095d-1796">visa electron</span><span class="sxs-lookup"><span data-stu-id="0095d-1796">visa electron</span></span> 
- <span data-ttu-id="0095d-1797">visto</span><span class="sxs-lookup"><span data-stu-id="0095d-1797">visto</span></span> 
- <span data-ttu-id="0095d-1798">Visum</span><span class="sxs-lookup"><span data-stu-id="0095d-1798">visum</span></span> 
- <span data-ttu-id="0095d-1799">vpay</span><span class="sxs-lookup"><span data-stu-id="0095d-1799">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="0095d-1800">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="0095d-1800">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="0095d-1801">card identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-1801">card identification number</span></span>
- <span data-ttu-id="0095d-1802">card verification</span><span class="sxs-lookup"><span data-stu-id="0095d-1802">card verification</span></span> 
- <span data-ttu-id="0095d-1803">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="0095d-1803">cardi la verifica</span></span> 
- <span data-ttu-id="0095d-1804">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1804">cid</span></span> 
- <span data-ttu-id="0095d-1805">cod seg</span><span class="sxs-lookup"><span data-stu-id="0095d-1805">cod seg</span></span> 
- <span data-ttu-id="0095d-1806">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1806">cod seguranca</span></span> 
- <span data-ttu-id="0095d-1807">cod segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1807">cod segurança</span></span> 
- <span data-ttu-id="0095d-1808">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1808">cod sicurezza</span></span> 
- <span data-ttu-id="0095d-1809">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1809">cod.</span></span> <span data-ttu-id="0095d-1810">SEG</span><span class="sxs-lookup"><span data-stu-id="0095d-1810">seg</span></span> 
- <span data-ttu-id="0095d-1811">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1811">cod.</span></span> <span data-ttu-id="0095d-1812">seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1812">seguranca</span></span> 
- <span data-ttu-id="0095d-1813">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1813">cod.</span></span> <span data-ttu-id="0095d-1814">Segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1814">segurança</span></span> 
- <span data-ttu-id="0095d-1815">Cod.</span><span class="sxs-lookup"><span data-stu-id="0095d-1815">cod.</span></span> <span data-ttu-id="0095d-1816">sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1816">sicurezza</span></span> 
- <span data-ttu-id="0095d-1817">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1817">codice di sicurezza</span></span> 
- <span data-ttu-id="0095d-1818">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="0095d-1818">codice di verifica</span></span> 
- <span data-ttu-id="0095d-1819">Codigo</span><span class="sxs-lookup"><span data-stu-id="0095d-1819">codigo</span></span> 
- <span data-ttu-id="0095d-1820">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1820">codigo de seguranca</span></span> 
- <span data-ttu-id="0095d-1821">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1821">codigo de segurança</span></span> 
- <span data-ttu-id="0095d-1822">crittogramma</span><span class="sxs-lookup"><span data-stu-id="0095d-1822">crittogramma</span></span> 
- <span data-ttu-id="0095d-1823">crittogramma</span><span class="sxs-lookup"><span data-stu-id="0095d-1823">cryptogram</span></span> 
- <span data-ttu-id="0095d-1824">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="0095d-1824">cryptogramme</span></span> 
- <span data-ttu-id="0095d-1825">CV2</span><span class="sxs-lookup"><span data-stu-id="0095d-1825">cv2</span></span> 
- <span data-ttu-id="0095d-1826">CVC</span><span class="sxs-lookup"><span data-stu-id="0095d-1826">cvc</span></span> 
- <span data-ttu-id="0095d-1827">CVC2</span><span class="sxs-lookup"><span data-stu-id="0095d-1827">cvc2</span></span> 
- <span data-ttu-id="0095d-1828">CVN</span><span class="sxs-lookup"><span data-stu-id="0095d-1828">cvn</span></span> 
- <span data-ttu-id="0095d-1829">CVV</span><span class="sxs-lookup"><span data-stu-id="0095d-1829">cvv</span></span> 
- <span data-ttu-id="0095d-1830">CVV2</span><span class="sxs-lookup"><span data-stu-id="0095d-1830">cvv2</span></span> 
- <span data-ttu-id="0095d-1831">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1831">cód seguranca</span></span> 
- <span data-ttu-id="0095d-1832">cód segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1832">cód segurança</span></span> 
- <span data-ttu-id="0095d-1833">cód.</span><span class="sxs-lookup"><span data-stu-id="0095d-1833">cód.</span></span> <span data-ttu-id="0095d-1834">seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1834">seguranca</span></span> 
- <span data-ttu-id="0095d-1835">cód.</span><span class="sxs-lookup"><span data-stu-id="0095d-1835">cód.</span></span> <span data-ttu-id="0095d-1836">Segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1836">segurança</span></span> 
- <span data-ttu-id="0095d-1837">Código</span><span class="sxs-lookup"><span data-stu-id="0095d-1837">código</span></span> 
- <span data-ttu-id="0095d-1838">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="0095d-1838">código de seguranca</span></span> 
- <span data-ttu-id="0095d-1839">código de segurança</span><span class="sxs-lookup"><span data-stu-id="0095d-1839">código de segurança</span></span> 
- <span data-ttu-id="0095d-1840">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="0095d-1840">de kaart controle</span></span> 
- <span data-ttu-id="0095d-1841">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="0095d-1841">geeft nr uit</span></span> 
- <span data-ttu-id="0095d-1842">issue no</span><span class="sxs-lookup"><span data-stu-id="0095d-1842">issue no</span></span> 
- <span data-ttu-id="0095d-1843">issue number</span><span class="sxs-lookup"><span data-stu-id="0095d-1843">issue number</span></span> 
- <span data-ttu-id="0095d-1844">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1844">kaartidentificatienummer</span></span> 
- <span data-ttu-id="0095d-1845">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1845">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="0095d-1846">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1846">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="0095d-1847">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="0095d-1847">kwestieaantal</span></span> 
- <span data-ttu-id="0095d-1848">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1848">no.</span></span> <span data-ttu-id="0095d-1849">Dell'Edizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1849">dell'edizione</span></span> 
- <span data-ttu-id="0095d-1850">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-1850">no.</span></span> <span data-ttu-id="0095d-1851">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1851">di sicurezza</span></span> 
- <span data-ttu-id="0095d-1852">numero de securite</span><span class="sxs-lookup"><span data-stu-id="0095d-1852">numero de securite</span></span> 
- <span data-ttu-id="0095d-1853">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="0095d-1853">numero de verificacao</span></span> 
- <span data-ttu-id="0095d-1854">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1854">numero dell'edizione</span></span> 
- <span data-ttu-id="0095d-1855">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="0095d-1855">numero di identificazione della</span></span> 
- <span data-ttu-id="0095d-1856">scheda</span><span class="sxs-lookup"><span data-stu-id="0095d-1856">scheda</span></span> 
- <span data-ttu-id="0095d-1857">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0095d-1857">numero di sicurezza</span></span> 
- <span data-ttu-id="0095d-1858">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="0095d-1858">numero van veiligheid</span></span> 
- <span data-ttu-id="0095d-1859">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="0095d-1859">numéro de sécurité</span></span> 
- <span data-ttu-id="0095d-1860">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0095d-1860">nº autorizzazione</span></span> 
- <span data-ttu-id="0095d-1861">número de verificação</span><span class="sxs-lookup"><span data-stu-id="0095d-1861">número de verificação</span></span> 
- <span data-ttu-id="0095d-1862">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="0095d-1862">perno il blocco</span></span> 
- <span data-ttu-id="0095d-1863">pin block</span><span class="sxs-lookup"><span data-stu-id="0095d-1863">pin block</span></span> 
- <span data-ttu-id="0095d-1864">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="0095d-1864">prufziffer</span></span> 
- <span data-ttu-id="0095d-1865">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="0095d-1865">prüfziffer</span></span> 
- <span data-ttu-id="0095d-1866">security code</span><span class="sxs-lookup"><span data-stu-id="0095d-1866">security code</span></span> 
- <span data-ttu-id="0095d-1867">security no</span><span class="sxs-lookup"><span data-stu-id="0095d-1867">security no</span></span> 
- <span data-ttu-id="0095d-1868">security number</span><span class="sxs-lookup"><span data-stu-id="0095d-1868">security number</span></span> 
- <span data-ttu-id="0095d-1869">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="0095d-1869">sicherheits kode</span></span> 
- <span data-ttu-id="0095d-1870">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="0095d-1870">sicherheitscode</span></span> 
- <span data-ttu-id="0095d-1871">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1871">sicherheitsnummer</span></span> 
- <span data-ttu-id="0095d-1872">speldblok</span><span class="sxs-lookup"><span data-stu-id="0095d-1872">speldblok</span></span> 
- <span data-ttu-id="0095d-1873">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="0095d-1873">veiligheid nr</span></span> 
- <span data-ttu-id="0095d-1874">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="0095d-1874">veiligheidsaantal</span></span> 
- <span data-ttu-id="0095d-1875">Veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="0095d-1875">veiligheidscode</span></span> 
- <span data-ttu-id="0095d-1876">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1876">veiligheidsnummer</span></span> 
- <span data-ttu-id="0095d-1877">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1877">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="0095d-1878">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="0095d-1878">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="0095d-1879">Ablauf</span><span class="sxs-lookup"><span data-stu-id="0095d-1879">ablauf</span></span> 
- <span data-ttu-id="0095d-1880">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="0095d-1880">data de expiracao</span></span> 
- <span data-ttu-id="0095d-1881">data de expiração</span><span class="sxs-lookup"><span data-stu-id="0095d-1881">data de expiração</span></span> 
- <span data-ttu-id="0095d-1882">data del exp</span><span class="sxs-lookup"><span data-stu-id="0095d-1882">data del exp</span></span> 
- <span data-ttu-id="0095d-1883">data di exp</span><span class="sxs-lookup"><span data-stu-id="0095d-1883">data di exp</span></span> 
- <span data-ttu-id="0095d-1884">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1884">data di scadenza</span></span> 
- <span data-ttu-id="0095d-1885">data em que expira</span><span class="sxs-lookup"><span data-stu-id="0095d-1885">data em que expira</span></span> 
- <span data-ttu-id="0095d-1886">data scad</span><span class="sxs-lookup"><span data-stu-id="0095d-1886">data scad</span></span> 
- <span data-ttu-id="0095d-1887">data scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1887">data scadenza</span></span> 
- <span data-ttu-id="0095d-1888">date de validité</span><span class="sxs-lookup"><span data-stu-id="0095d-1888">date de validité</span></span> 
- <span data-ttu-id="0095d-1889">datum afloop</span><span class="sxs-lookup"><span data-stu-id="0095d-1889">datum afloop</span></span> 
- <span data-ttu-id="0095d-1890">datum van exp</span><span class="sxs-lookup"><span data-stu-id="0095d-1890">datum van exp</span></span> 
- <span data-ttu-id="0095d-1891">de afloop</span><span class="sxs-lookup"><span data-stu-id="0095d-1891">de afloop</span></span> 
- <span data-ttu-id="0095d-1892">espira</span><span class="sxs-lookup"><span data-stu-id="0095d-1892">espira</span></span> 
- <span data-ttu-id="0095d-1893">espira</span><span class="sxs-lookup"><span data-stu-id="0095d-1893">espira</span></span> 
- <span data-ttu-id="0095d-1894">exp date</span><span class="sxs-lookup"><span data-stu-id="0095d-1894">exp date</span></span> 
- <span data-ttu-id="0095d-1895">exp datum</span><span class="sxs-lookup"><span data-stu-id="0095d-1895">exp datum</span></span> 
- <span data-ttu-id="0095d-1896">scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1896">expiration</span></span> 
- <span data-ttu-id="0095d-1897">scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1897">expire</span></span> 
- <span data-ttu-id="0095d-1898">scade</span><span class="sxs-lookup"><span data-stu-id="0095d-1898">expires</span></span> 
- <span data-ttu-id="0095d-1899">scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1899">expiry</span></span> 
- <span data-ttu-id="0095d-1900">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="0095d-1900">fecha de expiracion</span></span> 
- <span data-ttu-id="0095d-1901">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="0095d-1901">fecha de venc</span></span> 
- <span data-ttu-id="0095d-1902">gultig bis</span><span class="sxs-lookup"><span data-stu-id="0095d-1902">gultig bis</span></span> 
- <span data-ttu-id="0095d-1903">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1903">gultigkeitsdatum</span></span> 
- <span data-ttu-id="0095d-1904">gültig bis</span><span class="sxs-lookup"><span data-stu-id="0095d-1904">gültig bis</span></span> 
- <span data-ttu-id="0095d-1905">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1905">gültigkeitsdatum</span></span> 
- <span data-ttu-id="0095d-1906">la scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1906">la scadenza</span></span> 
- <span data-ttu-id="0095d-1907">scadenza</span><span class="sxs-lookup"><span data-stu-id="0095d-1907">scadenza</span></span> 
- <span data-ttu-id="0095d-1908">valable</span><span class="sxs-lookup"><span data-stu-id="0095d-1908">valable</span></span> 
- <span data-ttu-id="0095d-1909">validade</span><span class="sxs-lookup"><span data-stu-id="0095d-1909">validade</span></span> 
- <span data-ttu-id="0095d-1910">valido hasta</span><span class="sxs-lookup"><span data-stu-id="0095d-1910">valido hasta</span></span> 
- <span data-ttu-id="0095d-1911">Valor</span><span class="sxs-lookup"><span data-stu-id="0095d-1911">valor</span></span> 
- <span data-ttu-id="0095d-1912">venc</span><span class="sxs-lookup"><span data-stu-id="0095d-1912">venc</span></span> 
- <span data-ttu-id="0095d-1913">vencimento</span><span class="sxs-lookup"><span data-stu-id="0095d-1913">vencimento</span></span> 
- <span data-ttu-id="0095d-1914">vencimiento</span><span class="sxs-lookup"><span data-stu-id="0095d-1914">vencimiento</span></span> 
- <span data-ttu-id="0095d-1915">verloopt</span><span class="sxs-lookup"><span data-stu-id="0095d-1915">verloopt</span></span> 
- <span data-ttu-id="0095d-1916">vervaldag</span><span class="sxs-lookup"><span data-stu-id="0095d-1916">vervaldag</span></span> 
- <span data-ttu-id="0095d-1917">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="0095d-1917">vervaldatum</span></span> 
- <span data-ttu-id="0095d-1918">VTO</span><span class="sxs-lookup"><span data-stu-id="0095d-1918">vto</span></span> 
- <span data-ttu-id="0095d-1919">válido hasta</span><span class="sxs-lookup"><span data-stu-id="0095d-1919">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="0095d-1920">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="0095d-1920">EU Driver's License Number</span></span>

<span data-ttu-id="0095d-1921">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="0095d-1921">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="0095d-1922">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="0095d-1922">EU National Identification Number</span></span>

<span data-ttu-id="0095d-1923">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="0095d-1923">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="0095d-1924">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="0095d-1924">EU Passport Number</span></span>

<span data-ttu-id="0095d-1925">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="0095d-1925">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="0095d-1926">Codice di preVidenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="0095d-1926">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="0095d-1927">Per ulteriori informazioni, vedere [codice di PrevideNza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="0095d-1927">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="0095d-1928">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="0095d-1928">EU Tax Identification Number</span></span>

<span data-ttu-id="0095d-1929">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="0095d-1929">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="0095d-1930">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="0095d-1930">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1931">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1931">Format</span></span>

<span data-ttu-id="0095d-1932">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1932">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1933">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1933">Pattern</span></span>

<span data-ttu-id="0095d-1934">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-1934">Pattern must include all of the following:</span></span>
- <span data-ttu-id="0095d-1935">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-1935">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="0095d-1936">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="0095d-1936">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="0095d-1937">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1937">Three-digit personal identification number</span></span> 
- <span data-ttu-id="0095d-1938">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-1938">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1939">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1939">Checksum</span></span>

<span data-ttu-id="0095d-1940">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-1940">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1941">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1941">Definition</span></span>

<span data-ttu-id="0095d-1942">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1942">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1943">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1943">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1944">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-1944">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="0095d-1945">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-1945">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-1946">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1946">Keywords</span></span>

- <span data-ttu-id="0095d-1947">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="0095d-1947">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="0095d-1948">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="0095d-1948">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="0095d-1949">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="0095d-1949">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="0095d-1950">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="0095d-1950">Personbeteckning</span></span>
- <span data-ttu-id="0095d-1951">Personnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-1951">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="0095d-1952">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-1952">Finland Passport Number</span></span>

<span data-ttu-id="0095d-1953">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1953">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-1954">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-1954">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="0095d-1955"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="0095d-1955"></span></span>
<span data-ttu-id="0095d-1956">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="0095d-1956">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="0095d-1957">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-1957">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1958">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1958">Format</span></span>

<span data-ttu-id="0095d-1959">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1959">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1960">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1960">Pattern</span></span>

<span data-ttu-id="0095d-1961">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="0095d-1961">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1962">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1962">Checksum</span></span>

<span data-ttu-id="0095d-1963">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1963">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1964">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1964">Definition</span></span>

<span data-ttu-id="0095d-1965">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1965">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1966">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1966">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-1967">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-1967">At least one of the following is true:</span></span>
- <span data-ttu-id="0095d-1968">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-1968">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="0095d-1969">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-1969">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-1970">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1970">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="0095d-1971">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="0095d-1971">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="0095d-1972">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0095d-1972">drivers licence</span></span>
- <span data-ttu-id="0095d-1973">drivers license</span><span class="sxs-lookup"><span data-stu-id="0095d-1973">drivers license</span></span>
- <span data-ttu-id="0095d-1974">driving licence</span><span class="sxs-lookup"><span data-stu-id="0095d-1974">driving licence</span></span>
- <span data-ttu-id="0095d-1975">driving license</span><span class="sxs-lookup"><span data-stu-id="0095d-1975">driving license</span></span>
- <span data-ttu-id="0095d-1976">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="0095d-1976">permis de conduire</span></span>
- <span data-ttu-id="0095d-1977">licence number</span><span class="sxs-lookup"><span data-stu-id="0095d-1977">licence number</span></span>
- <span data-ttu-id="0095d-1978">license number</span><span class="sxs-lookup"><span data-stu-id="0095d-1978">license number</span></span>
- <span data-ttu-id="0095d-1979">licence numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1979">licence numbers</span></span>
- <span data-ttu-id="0095d-1980">license numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-1980">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="0095d-1981">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="0095d-1981">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1982">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1982">Format</span></span>

<span data-ttu-id="0095d-1983">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1983">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1984">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1984">Pattern</span></span>

<span data-ttu-id="0095d-1985">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1985">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-1986">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-1986">Checksum</span></span>

<span data-ttu-id="0095d-1987">No</span><span class="sxs-lookup"><span data-stu-id="0095d-1987">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-1988">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-1988">Definition</span></span>

<span data-ttu-id="0095d-1989">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-1989">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-1990">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-1990">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-1991">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-1991">Keywords</span></span>

<span data-ttu-id="0095d-1992">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0095d-1992">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="0095d-1993">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-1993">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-1994">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-1994">Format</span></span>

<span data-ttu-id="0095d-1995">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-1995">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-1996">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-1996">Pattern</span></span>

<span data-ttu-id="0095d-1997">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="0095d-1997">Nine digits and letters:</span></span>
- <span data-ttu-id="0095d-1998">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-1998">Two digits</span></span> 
- <span data-ttu-id="0095d-1999">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-1999">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2000">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2000">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2001">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2001">Checksum</span></span>

<span data-ttu-id="0095d-2002">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2002">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2003">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2003">Definition</span></span>

<span data-ttu-id="0095d-2004">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2005">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2005">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2006">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-2006">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2007">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2007">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="0095d-2008">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-2008">Keyword_passport</span></span>

- <span data-ttu-id="0095d-2009">Passport Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2009">Passport Number</span></span>
- <span data-ttu-id="0095d-2010">Passport No</span><span class="sxs-lookup"><span data-stu-id="0095d-2010">Passport No</span></span>
- <span data-ttu-id="0095d-2011">Passport#</span><span class="sxs-lookup"><span data-stu-id="0095d-2011">Passport #</span></span>
- <span data-ttu-id="0095d-2012">Passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-2012">Passport#</span></span>
- <span data-ttu-id="0095d-2013">PassportID</span><span class="sxs-lookup"><span data-stu-id="0095d-2013">PassportID</span></span>
- <span data-ttu-id="0095d-2014">Passportno</span><span class="sxs-lookup"><span data-stu-id="0095d-2014">Passportno</span></span>
- <span data-ttu-id="0095d-2015">passportnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-2015">passportnumber</span></span>
- <span data-ttu-id="0095d-2016">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-2016">パスポート</span></span>
- <span data-ttu-id="0095d-2017">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2017">パスポート番号</span></span>
- <span data-ttu-id="0095d-2018">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-2018">パスポートのNum</span></span>
- <span data-ttu-id="0095d-2019">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="0095d-2019">パスポート ＃</span></span> 
- <span data-ttu-id="0095d-2020">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-2020">Numéro de passeport</span></span>
- <span data-ttu-id="0095d-2021">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="0095d-2021">Passeport n °</span></span>
- <span data-ttu-id="0095d-2022">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="0095d-2022">Passeport Non</span></span>
- <span data-ttu-id="0095d-2023">Passeport#</span><span class="sxs-lookup"><span data-stu-id="0095d-2023">Passeport #</span></span>
- <span data-ttu-id="0095d-2024">Passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-2024">Passeport#</span></span>
- <span data-ttu-id="0095d-2025">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="0095d-2025">PasseportNon</span></span>
- <span data-ttu-id="0095d-2026">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="0095d-2026">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="0095d-2027">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="0095d-2027">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2028">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2028">Format</span></span>

<span data-ttu-id="0095d-2029">15 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2029">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2030">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2030">Pattern</span></span>

<span data-ttu-id="0095d-2031">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="0095d-2031">Must match one of two patterns:</span></span>
- <span data-ttu-id="0095d-2032">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2032">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="0095d-2033">oppure</span><span class="sxs-lookup"><span data-stu-id="0095d-2033">or</span></span>
- <span data-ttu-id="0095d-2034">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2034">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2035">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2035">Checksum</span></span>

<span data-ttu-id="0095d-2036">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2036">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2037">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2037">Definition</span></span>

<span data-ttu-id="0095d-2038">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2038">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2039">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2039">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2040">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="0095d-2040">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="0095d-2041">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2041">The checksum passes.</span></span>

<span data-ttu-id="0095d-2042">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2042">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2043">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2043">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2044">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="0095d-2044">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="0095d-2045">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2045">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2046">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2046">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="0095d-2047">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="0095d-2047">Keyword_fr_insee</span></span>

- <span data-ttu-id="0095d-2048">INSEE</span><span class="sxs-lookup"><span data-stu-id="0095d-2048">insee</span></span>
- <span data-ttu-id="0095d-2049">securité sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-2049">securité sociale</span></span>
- <span data-ttu-id="0095d-2050">securite sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-2050">securite sociale</span></span>
- <span data-ttu-id="0095d-2051">national id</span><span class="sxs-lookup"><span data-stu-id="0095d-2051">national id</span></span>
- <span data-ttu-id="0095d-2052">national identification</span><span class="sxs-lookup"><span data-stu-id="0095d-2052">national identification</span></span>
- <span data-ttu-id="0095d-2053">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="0095d-2053">numéro d'identité</span></span>
- <span data-ttu-id="0095d-2054">no d'identité</span><span class="sxs-lookup"><span data-stu-id="0095d-2054">no d'identité</span></span>
- <span data-ttu-id="0095d-2055">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2055">no.</span></span> <span data-ttu-id="0095d-2056">d'identité</span><span class="sxs-lookup"><span data-stu-id="0095d-2056">d'identité</span></span>
- <span data-ttu-id="0095d-2057">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="0095d-2057">numero d'identite</span></span>
- <span data-ttu-id="0095d-2058">no d'identite</span><span class="sxs-lookup"><span data-stu-id="0095d-2058">no d'identite</span></span>
- <span data-ttu-id="0095d-2059">No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2059">no.</span></span> <span data-ttu-id="0095d-2060">d'identite</span><span class="sxs-lookup"><span data-stu-id="0095d-2060">d'identite</span></span>
- <span data-ttu-id="0095d-2061">social security number</span><span class="sxs-lookup"><span data-stu-id="0095d-2061">social security number</span></span>
- <span data-ttu-id="0095d-2062">social security code</span><span class="sxs-lookup"><span data-stu-id="0095d-2062">social security code</span></span>
- <span data-ttu-id="0095d-2063">social insurance number</span><span class="sxs-lookup"><span data-stu-id="0095d-2063">social insurance number</span></span>
- <span data-ttu-id="0095d-2064">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="0095d-2064">le numéro d'identification nationale</span></span>
- <span data-ttu-id="0095d-2065">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="0095d-2065">d'identité nationale</span></span>
- <span data-ttu-id="0095d-2066">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-2066">numéro de sécurité sociale</span></span>
- <span data-ttu-id="0095d-2067">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-2067">le code de la sécurité sociale</span></span>
- <span data-ttu-id="0095d-2068">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="0095d-2068">numéro d'assurance sociale</span></span>
- <span data-ttu-id="0095d-2069">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="0095d-2069">numéro de sécu</span></span>
- <span data-ttu-id="0095d-2070">code sécu</span><span class="sxs-lookup"><span data-stu-id="0095d-2070">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="0095d-2071">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-2071">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2072">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2072">Format</span></span>

<span data-ttu-id="0095d-2073">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-2073">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2074">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2074">Pattern</span></span>

<span data-ttu-id="0095d-2075">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="0095d-2075">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="0095d-2076">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="0095d-2076">A digit or letter</span></span> 
- <span data-ttu-id="0095d-2077">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2077">Two digits</span></span> 
- <span data-ttu-id="0095d-2078">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-2078">Six digits or letters</span></span> 
- <span data-ttu-id="0095d-2079">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-2079">A digit</span></span> 
- <span data-ttu-id="0095d-2080">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="0095d-2080">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2081">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2081">Checksum</span></span>

<span data-ttu-id="0095d-2082">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2083">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2083">Definition</span></span>

<span data-ttu-id="0095d-2084">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2084">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2085">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2085">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2086">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-2086">At least one of the following is true:</span></span>
    - <span data-ttu-id="0095d-2087">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2087">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="0095d-2088">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="0095d-2088">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="0095d-2089">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-2089">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="0095d-2090">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2090">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2091">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2091">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="0095d-2092">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2092">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="0095d-2093">Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2093">Führerschein</span></span>
- <span data-ttu-id="0095d-2094">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2094">Fuhrerschein</span></span>
- <span data-ttu-id="0095d-2095">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2095">Fuehrerschein</span></span>
- <span data-ttu-id="0095d-2096">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2096">Führerscheinnummer</span></span>
- <span data-ttu-id="0095d-2097">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2097">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="0095d-2098">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2098">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="0095d-2099">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="0095d-2099">Führerschein-</span></span> 
- <span data-ttu-id="0095d-2100">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="0095d-2100">Fuhrerschein-</span></span> 
- <span data-ttu-id="0095d-2101">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="0095d-2101">Fuehrerschein-</span></span> 
- <span data-ttu-id="0095d-2102">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2102">FührerscheinnummerNr</span></span>
- <span data-ttu-id="0095d-2103">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2103">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="0095d-2104">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2104">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="0095d-2105">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2105">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="0095d-2106">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2106">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="0095d-2107">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2107">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="0095d-2108">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2108">Führerschein- Nr</span></span>
- <span data-ttu-id="0095d-2109">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2109">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="0095d-2110">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2110">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="0095d-2111">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2111">Führerschein- Klasse</span></span> 
- <span data-ttu-id="0095d-2112">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2112">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="0095d-2113">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2113">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="0095d-2114">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2114">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="0095d-2115">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2115">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="0095d-2116">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="0095d-2116">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="0095d-2117">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2117">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="0095d-2118">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2118">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="0095d-2119">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2119">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="0095d-2120">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2120">Führerschein- Nr</span></span> 
- <span data-ttu-id="0095d-2121">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2121">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="0095d-2122">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2122">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="0095d-2123">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2123">Führerschein- Klasse</span></span> 
- <span data-ttu-id="0095d-2124">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2124">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="0095d-2125">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2125">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="0095d-2126">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-2126">DL</span></span> 
- <span data-ttu-id="0095d-2127">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-2127">DLS</span></span>
- <span data-ttu-id="0095d-2128">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2128">Driv Lic</span></span> 
- <span data-ttu-id="0095d-2129">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="0095d-2129">Driv Licen</span></span> 
- <span data-ttu-id="0095d-2130">Driv License</span><span class="sxs-lookup"><span data-stu-id="0095d-2130">Driv License</span></span>
- <span data-ttu-id="0095d-2131">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2131">Driv Licenses</span></span> 
- <span data-ttu-id="0095d-2132">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2132">Driv Licence</span></span> 
- <span data-ttu-id="0095d-2133">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-2133">Driv Licences</span></span> 
- <span data-ttu-id="0095d-2134">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2134">Driv Lic</span></span> 
- <span data-ttu-id="0095d-2135">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="0095d-2135">Driver Licen</span></span> 
- <span data-ttu-id="0095d-2136">Driver License</span><span class="sxs-lookup"><span data-stu-id="0095d-2136">Driver License</span></span> 
- <span data-ttu-id="0095d-2137">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2137">Driver Licenses</span></span> 
- <span data-ttu-id="0095d-2138">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2138">Driver Licence</span></span> 
- <span data-ttu-id="0095d-2139">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-2139">Driver Licences</span></span> 
- <span data-ttu-id="0095d-2140">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2140">Drivers Lic</span></span> 
- <span data-ttu-id="0095d-2141">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="0095d-2141">Drivers Licen</span></span> 
- <span data-ttu-id="0095d-2142">Drivers License</span><span class="sxs-lookup"><span data-stu-id="0095d-2142">Drivers License</span></span> 
- <span data-ttu-id="0095d-2143">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2143">Drivers Licenses</span></span> 
- <span data-ttu-id="0095d-2144">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2144">Drivers Licence</span></span> 
- <span data-ttu-id="0095d-2145">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-2145">Drivers Licences</span></span> 
- <span data-ttu-id="0095d-2146">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2146">Driver's Lic</span></span> 
- <span data-ttu-id="0095d-2147">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="0095d-2147">Driver's Licen</span></span> 
- <span data-ttu-id="0095d-2148">Driver's License</span><span class="sxs-lookup"><span data-stu-id="0095d-2148">Driver's License</span></span> 
- <span data-ttu-id="0095d-2149">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2149">Driver's Licenses</span></span> 
- <span data-ttu-id="0095d-2150">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2150">Driver's Licence</span></span> 
- <span data-ttu-id="0095d-2151">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-2151">Driver's Licences</span></span> 
- <span data-ttu-id="0095d-2152">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2152">Driving Lic</span></span> 
- <span data-ttu-id="0095d-2153">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="0095d-2153">Driving Licen</span></span> 
- <span data-ttu-id="0095d-2154">Driving License</span><span class="sxs-lookup"><span data-stu-id="0095d-2154">Driving License</span></span> 
- <span data-ttu-id="0095d-2155">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2155">Driving Licenses</span></span> 
- <span data-ttu-id="0095d-2156">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2156">Driving Licence</span></span> 
- <span data-ttu-id="0095d-2157">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="0095d-2157">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="0095d-2158">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="0095d-2158">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="0095d-2159">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2159">Nr-Führerschein</span></span> 
- <span data-ttu-id="0095d-2160">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2160">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2161">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2161">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="0095d-2162">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2162">No-Führerschein</span></span> 
- <span data-ttu-id="0095d-2163">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2163">No-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2164">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2164">No-Fuehrerschein</span></span> 
- <span data-ttu-id="0095d-2165">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2165">N-Führerschein</span></span> 
- <span data-ttu-id="0095d-2166">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2166">N-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2167">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2167">N-Fuehrerschein</span></span>
- <span data-ttu-id="0095d-2168">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2168">Nr-Führerschein</span></span> 
- <span data-ttu-id="0095d-2169">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2169">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2170">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2170">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="0095d-2171">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2171">No-Führerschein</span></span> 
- <span data-ttu-id="0095d-2172">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2172">No-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2173">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2173">No-Fuehrerschein</span></span> 
- <span data-ttu-id="0095d-2174">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2174">N-Führerschein</span></span> 
- <span data-ttu-id="0095d-2175">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2175">N-Fuhrerschein</span></span> 
- <span data-ttu-id="0095d-2176">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="0095d-2176">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="0095d-2177">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="0095d-2177">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="0095d-2178">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-2178">ausstellungsdatum</span></span>
- <span data-ttu-id="0095d-2179">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="0095d-2179">ausstellungsort</span></span>
- <span data-ttu-id="0095d-2180">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="0095d-2180">ausstellende behöde</span></span>
- <span data-ttu-id="0095d-2181">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="0095d-2181">ausstellende behorde</span></span>
- <span data-ttu-id="0095d-2182">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="0095d-2182">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="0095d-2183">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-2183">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2184">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2184">Format</span></span>

<span data-ttu-id="0095d-2185">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-2185">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2186">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2186">Pattern</span></span>

<span data-ttu-id="0095d-2187">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-2187">Pattern must include all of the following:</span></span>
- <span data-ttu-id="0095d-2188">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="0095d-2188">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="0095d-2189">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2189">Three digits</span></span> 
- <span data-ttu-id="0095d-2190">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="0095d-2190">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="0095d-2191">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-2191">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2192">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2192">Checksum</span></span>

<span data-ttu-id="0095d-2193">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2194">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2194">Definition</span></span>

<span data-ttu-id="0095d-2195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2196">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2196">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2197">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="0095d-2197">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="0095d-2198">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2198">The checksum passes.</span></span>

<span data-ttu-id="0095d-2199">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2199">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2200">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2200">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2201">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="0095d-2201">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="0095d-2202">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2202">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2203">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="0095d-2204">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-2204">Keyword_german_passport</span></span>

- <span data-ttu-id="0095d-2205">Reisepass</span><span class="sxs-lookup"><span data-stu-id="0095d-2205">reisepass</span></span>
- <span data-ttu-id="0095d-2206">reisepasse</span><span class="sxs-lookup"><span data-stu-id="0095d-2206">reisepasse</span></span>
- <span data-ttu-id="0095d-2207">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2207">reisepassnummer</span></span>
- <span data-ttu-id="0095d-2208">passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-2208">passport</span></span>
- <span data-ttu-id="0095d-2209">passaporti</span><span class="sxs-lookup"><span data-stu-id="0095d-2209">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="0095d-2210">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="0095d-2210">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="0095d-2211">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-2211">geburtsdatum</span></span>
- <span data-ttu-id="0095d-2212">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="0095d-2212">ausstellungsdatum</span></span>
- <span data-ttu-id="0095d-2213">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="0095d-2213">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="0095d-2214">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2214">Keyword_german_passport_number</span></span>

<span data-ttu-id="0095d-2215">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="0095d-2215">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="0095d-2216">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="0095d-2216">Keyword_german_passport1</span></span>

<span data-ttu-id="0095d-2217">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="0095d-2217">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="0095d-2218">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="0095d-2218">Keyword_german_passport2</span></span>

<span data-ttu-id="0095d-2219">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="0095d-2219">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="0095d-2220">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2220">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2221">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2221">Format</span></span>

<span data-ttu-id="0095d-2222">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2222">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="0095d-2223">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2223">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2224">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2224">Pattern</span></span>

<span data-ttu-id="0095d-2225">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="0095d-2225">Since 1 November 2010:</span></span>
- <span data-ttu-id="0095d-2226">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2226">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2227">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2227">Eight digits</span></span>

<span data-ttu-id="0095d-2228">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="0095d-2228">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="0095d-2229">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2229">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2230">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2230">Checksum</span></span>

<span data-ttu-id="0095d-2231">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2232">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2232">Definition</span></span>

<span data-ttu-id="0095d-2233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2233">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2234">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2234">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2235">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-2235">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2236">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="0095d-2237">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-2237">Keyword_germany_id_card</span></span>

- <span data-ttu-id="0095d-2238">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2238">Identity Card</span></span>
- <span data-ttu-id="0095d-2239">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-2239">ID</span></span>
- <span data-ttu-id="0095d-2240">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-2240">Identification</span></span>
- <span data-ttu-id="0095d-2241">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="0095d-2241">Personalausweis</span></span>
- <span data-ttu-id="0095d-2242">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2242">Identifizierungsnummer</span></span>
- <span data-ttu-id="0095d-2243">Ausweis</span><span class="sxs-lookup"><span data-stu-id="0095d-2243">Ausweis</span></span>
- <span data-ttu-id="0095d-2244">Identifikation</span><span class="sxs-lookup"><span data-stu-id="0095d-2244">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="0095d-2245">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="0095d-2245">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2246">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2246">Format</span></span>

<span data-ttu-id="0095d-2247">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-2247">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2248">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2248">Pattern</span></span>

<span data-ttu-id="0095d-2249">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="0095d-2249">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="0095d-2250">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="0095d-2250">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="0095d-2251">Un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-2251">A dash</span></span> 
- <span data-ttu-id="0095d-2252">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2252">Six digits</span></span>

<span data-ttu-id="0095d-2253">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="0095d-2253">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="0095d-2254">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="0095d-2254">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="0095d-2255">Un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-2255">A dash</span></span> 
- <span data-ttu-id="0095d-2256">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2256">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2257">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2257">Checksum</span></span>

<span data-ttu-id="0095d-2258">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2258">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2259">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2259">Definition</span></span>

<span data-ttu-id="0095d-2260">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2261">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2261">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2262">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-2262">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2263">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2263">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="0095d-2264">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-2264">Keyword_greece_id_card</span></span>

- <span data-ttu-id="0095d-2265">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="0095d-2265">Greek identity Card</span></span>
- <span data-ttu-id="0095d-2266">Tautotita</span><span class="sxs-lookup"><span data-stu-id="0095d-2266">Tautotita</span></span>
- <span data-ttu-id="0095d-2267">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="0095d-2267">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="0095d-2268">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="0095d-2268">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="0095d-2269">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="0095d-2269">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2270">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2270">Format</span></span>

<span data-ttu-id="0095d-2271">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="0095d-2271">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2272">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2272">Pattern</span></span>

<span data-ttu-id="0095d-2273">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="0095d-2273">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="0095d-2274">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2274">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2275">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2275">Six digits</span></span> 
- <span data-ttu-id="0095d-2276">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="0095d-2276">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2277">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2277">Checksum</span></span>

<span data-ttu-id="0095d-2278">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2278">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2279">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2279">Definition</span></span>

<span data-ttu-id="0095d-2280">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2281">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2281">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2282">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-2282">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="0095d-2283">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2283">The checksum passes.</span></span>

<span data-ttu-id="0095d-2284">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2284">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2285">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2285">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2286">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2286">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2287">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2287">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="0095d-2288">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-2288">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="0095d-2289">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="0095d-2289">hong kong identity card</span></span>
- <span data-ttu-id="0095d-2290">HKIDC</span><span class="sxs-lookup"><span data-stu-id="0095d-2290">HKIDC</span></span>
- <span data-ttu-id="0095d-2291">id card</span><span class="sxs-lookup"><span data-stu-id="0095d-2291">id card</span></span>
- <span data-ttu-id="0095d-2292">carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2292">identity card</span></span>
- <span data-ttu-id="0095d-2293">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="0095d-2293">hk identity card</span></span>
- <span data-ttu-id="0095d-2294">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="0095d-2294">hong kong id</span></span>
- <span data-ttu-id="0095d-2295">香港身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2295">香港身份證</span></span>
- <span data-ttu-id="0095d-2296">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2296">香港永久性居民身份證</span></span>
- <span data-ttu-id="0095d-2297">身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2297">身份證</span></span>
- <span data-ttu-id="0095d-2298">身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2298">身份証</span></span>
- <span data-ttu-id="0095d-2299">身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2299">身分證</span></span>
- <span data-ttu-id="0095d-2300">身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2300">身分証</span></span>
- <span data-ttu-id="0095d-2301">香港身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2301">香港身份証</span></span>
- <span data-ttu-id="0095d-2302">香港身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2302">香港身分證</span></span>
- <span data-ttu-id="0095d-2303">香港身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2303">香港身分証</span></span>
- <span data-ttu-id="0095d-2304">香港身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2304">香港身份證</span></span>
- <span data-ttu-id="0095d-2305">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2305">香港居民身份證</span></span>
- <span data-ttu-id="0095d-2306">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2306">香港居民身份証</span></span>
- <span data-ttu-id="0095d-2307">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2307">香港居民身分證</span></span>
- <span data-ttu-id="0095d-2308">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2308">香港居民身分証</span></span>
- <span data-ttu-id="0095d-2309">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2309">香港永久性居民身份証</span></span>
- <span data-ttu-id="0095d-2310">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2310">香港永久性居民身分證</span></span>
- <span data-ttu-id="0095d-2311">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2311">香港永久性居民身分証</span></span>
- <span data-ttu-id="0095d-2312">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2312">香港永久性居民身份證</span></span>
- <span data-ttu-id="0095d-2313">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2313">香港非永久性居民身份證</span></span>
- <span data-ttu-id="0095d-2314">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2314">香港非永久性居民身份証</span></span>
- <span data-ttu-id="0095d-2315">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2315">香港非永久性居民身分證</span></span>
- <span data-ttu-id="0095d-2316">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2316">香港非永久性居民身分証</span></span>
- <span data-ttu-id="0095d-2317">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2317">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="0095d-2318">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2318">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="0095d-2319">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2319">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="0095d-2320">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2320">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="0095d-2321">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-2321">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="0095d-2322">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="0095d-2322">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="0095d-2323">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-2323">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="0095d-2324">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="0095d-2324">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="0095d-2325">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="0095d-2325">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2326">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2326">Format</span></span>

<span data-ttu-id="0095d-2327">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2327">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2328">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2328">Pattern</span></span>

<span data-ttu-id="0095d-2329">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2329">10 letters or digits:</span></span>
- <span data-ttu-id="0095d-2330">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2330">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2331">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2331">Four digits</span></span> 
- <span data-ttu-id="0095d-2332">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="0095d-2332">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2333">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2333">Checksum</span></span>

<span data-ttu-id="0095d-2334">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2335">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2335">Definition</span></span>

<span data-ttu-id="0095d-2336">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2337">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2337">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2338">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2338">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="0095d-2339">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2339">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2340">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2340">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="0095d-2341">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2341">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="0095d-2342">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2342">Permanent Account Number</span></span> 
- <span data-ttu-id="0095d-2343">PAN</span><span class="sxs-lookup"><span data-stu-id="0095d-2343">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="0095d-2344">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="0095d-2344">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2345">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2345">Format</span></span>

<span data-ttu-id="0095d-2346">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="0095d-2346">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2347">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2347">Pattern</span></span>

<span data-ttu-id="0095d-2348">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2348">12 digits:</span></span>
- <span data-ttu-id="0095d-2349">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2349">Four digits</span></span> 
- <span data-ttu-id="0095d-2350">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="0095d-2350">An optional space or dash</span></span> 
- <span data-ttu-id="0095d-2351">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2351">Four digits</span></span> 
- <span data-ttu-id="0095d-2352">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="0095d-2352">An optional space or dash</span></span> 
- <span data-ttu-id="0095d-2353">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-2353">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2354">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2354">Checksum</span></span>

<span data-ttu-id="0095d-2355">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2355">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2356">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2356">Definition</span></span>

<span data-ttu-id="0095d-2357">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2357">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-2358">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="0095d-2358">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="0095d-2359">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2359">The checksum passes.</span></span>
<span data-ttu-id="0095d-2360">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-2361">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2361">The checksum passes.</span></span>
<span data-ttu-id="0095d-2362"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="0095d-2362"></span></span>

### <a name="keywords"></a><span data-ttu-id="0095d-2363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2363">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="0095d-2364">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="0095d-2364">Keyword_india_aadhar</span></span>
- <span data-ttu-id="0095d-2365">Aadhar</span><span class="sxs-lookup"><span data-stu-id="0095d-2365">Aadhar</span></span>
- <span data-ttu-id="0095d-2366">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="0095d-2366">Aadhaar</span></span>
- <span data-ttu-id="0095d-2367">UID</span><span class="sxs-lookup"><span data-stu-id="0095d-2367">UID</span></span>
- <span data-ttu-id="0095d-2368">आधार</span><span class="sxs-lookup"><span data-stu-id="0095d-2368">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="0095d-2369">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="0095d-2369">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2370">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2370">Format</span></span>

<span data-ttu-id="0095d-2371">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="0095d-2371">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2372">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2372">Pattern</span></span>

<span data-ttu-id="0095d-2373">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2373">16 digits:</span></span>
- <span data-ttu-id="0095d-2374">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="0095d-2374">Two-digit province code</span></span> 
- <span data-ttu-id="0095d-2375">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="0095d-2375">A period (optional)</span></span> 
- <span data-ttu-id="0095d-2376">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="0095d-2376">Two-digit regency or city code</span></span> 
- <span data-ttu-id="0095d-2377">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="0095d-2377">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="0095d-2378">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="0095d-2378">A period (optional)</span></span> 
- <span data-ttu-id="0095d-2379">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-2379">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="0095d-2380">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="0095d-2380">A period (optional)</span></span> 
- <span data-ttu-id="0095d-2381">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2381">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2382">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2382">Checksum</span></span>

<span data-ttu-id="0095d-2383">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2383">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2384">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2384">Definition</span></span>

<span data-ttu-id="0095d-2385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2386">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2386">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2387">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-2387">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="0095d-2388">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2388">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2389">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2389">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2390">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2390">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="0095d-2391">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="0095d-2391">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="0095d-2392">KTP</span><span class="sxs-lookup"><span data-stu-id="0095d-2392">KTP</span></span>
- <span data-ttu-id="0095d-2393">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="0095d-2393">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="0095d-2394">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="0095d-2394">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="0095d-2395">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="0095d-2395">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2396">Format</span></span>

<span data-ttu-id="0095d-2397">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="0095d-2397">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2398">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2398">Pattern</span></span>

<span data-ttu-id="0095d-2399">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-2399">Pattern must include all of the following:</span></span>

- <span data-ttu-id="0095d-2400">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-2400">Two-letter country code</span></span>
- <span data-ttu-id="0095d-2401">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2401">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="0095d-2402">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="0095d-2402">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="0095d-2403">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2403">1-3 letters or digits</span></span>

<span data-ttu-id="0095d-2404">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="0095d-2404">The format for each country is slightly different.</span></span> <span data-ttu-id="0095d-2405">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="0095d-2405">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="0095d-2406">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="0095d-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2407">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2407">Checksum</span></span>

<span data-ttu-id="0095d-2408">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2408">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2409">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2409">Definition</span></span>

<span data-ttu-id="0095d-2410">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2410">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2411">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2411">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2412">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2412">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2413">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2413">Keywords</span></span>

<span data-ttu-id="0095d-2414">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0095d-2414">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="0095d-2415">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="0095d-2415">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2416">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2416">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="0095d-2417">IPv4</span><span class="sxs-lookup"><span data-stu-id="0095d-2417">IPv4:</span></span>
<span data-ttu-id="0095d-2418">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="0095d-2418">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="0095d-2419">IPv6</span><span class="sxs-lookup"><span data-stu-id="0095d-2419">IPv6:</span></span>
<span data-ttu-id="0095d-2420">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="0095d-2420">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2421">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2421">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2422">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2422">Checksum</span></span>

<span data-ttu-id="0095d-2423">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2424">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2424">Definition</span></span>

<span data-ttu-id="0095d-2425">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2425">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2426">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2426">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2427">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="0095d-2427">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="0095d-2428">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2428">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2429">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2429">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2430">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="0095d-2430">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="0095d-2431">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2431">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2432">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2432">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2433">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="0095d-2433">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2434">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2434">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="0095d-2435">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="0095d-2435">Keyword_ipaddress</span></span>

- <span data-ttu-id="0095d-2436">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2436">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="0095d-2437">ip address</span><span class="sxs-lookup"><span data-stu-id="0095d-2437">ip address</span></span> 
- <span data-ttu-id="0095d-2438">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="0095d-2438">ip addresses</span></span>
- <span data-ttu-id="0095d-2439">internet protocol</span><span class="sxs-lookup"><span data-stu-id="0095d-2439">internet protocol</span></span>
- <span data-ttu-id="0095d-2440">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="0095d-2440">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="0095d-2441">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="0095d-2441">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2442">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2442">Format</span></span>

<span data-ttu-id="0095d-2443">Dizionario</span><span class="sxs-lookup"><span data-stu-id="0095d-2443">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2444">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2444">Pattern</span></span>

<span data-ttu-id="0095d-2445">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2445">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2446">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2446">Checksum</span></span>

<span data-ttu-id="0095d-2447">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2447">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2448">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2448">Definition</span></span>

<span data-ttu-id="0095d-2449">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2449">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2450">Viene trovata una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="0095d-2450">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="0095d-2451">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2451">Keywords</span></span>

<span data-ttu-id="0095d-2452">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_cm, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="0095d-2452">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="0095d-2453">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="0095d-2453">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="0095d-2454">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="0095d-2454">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2455">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2455">Format</span></span>

<span data-ttu-id="0095d-2456">Dizionario</span><span class="sxs-lookup"><span data-stu-id="0095d-2456">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2457">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2457">Pattern</span></span>

<span data-ttu-id="0095d-2458">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2458">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2459">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2459">Checksum</span></span>

<span data-ttu-id="0095d-2460">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2460">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2461">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2461">Definition</span></span>

<span data-ttu-id="0095d-2462">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2462">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2463">Viene trovata una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="0095d-2463">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2464">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2464">Keywords</span></span>

<span data-ttu-id="0095d-2465">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_cm, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="0095d-2465">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="0095d-2466">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="0095d-2466">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="0095d-2467">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="0095d-2467">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2468">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2468">Format</span></span>

<span data-ttu-id="0095d-2469">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="0095d-2469">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="0095d-2470">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="0095d-2470">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="0095d-2471">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="0095d-2471">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="0095d-2472">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-2472">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2473">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2473">Pattern</span></span>

<span data-ttu-id="0095d-2474">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="0095d-2474">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="0095d-2475">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2475">Seven digits</span></span> 
- <span data-ttu-id="0095d-2476">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2476">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="0095d-2477">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="0095d-2477">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="0095d-2478">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2478">Seven digits</span></span> 
- <span data-ttu-id="0095d-2479">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="0095d-2479">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="0095d-2480">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2480">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2481">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2481">Checksum</span></span>

<span data-ttu-id="0095d-2482">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2482">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2483">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2483">Definition</span></span>

<span data-ttu-id="0095d-2484">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2485">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2485">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2486">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-2486">One of the following is true:</span></span>
    - <span data-ttu-id="0095d-2487">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="0095d-2487">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="0095d-2488">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-2488">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="0095d-2489">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2489">The checksum passes.</span></span>

<span data-ttu-id="0095d-2490">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2490">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2491">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2491">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2492">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2492">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2493">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2493">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="0095d-2494">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="0095d-2494">Keyword_ireland_pps</span></span>

- <span data-ttu-id="0095d-2495">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="0095d-2495">Personal Public Service Number</span></span> 
- <span data-ttu-id="0095d-2496">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="0095d-2496">PPS Number</span></span> 
- <span data-ttu-id="0095d-2497">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="0095d-2497">PPS Num</span></span> 
- <span data-ttu-id="0095d-2498">N° PPS</span><span class="sxs-lookup"><span data-stu-id="0095d-2498">PPS No.</span></span> 
- <span data-ttu-id="0095d-2499">PPS #</span><span class="sxs-lookup"><span data-stu-id="0095d-2499">PPS #</span></span> 
- <span data-ttu-id="0095d-2500">PPS</span><span class="sxs-lookup"><span data-stu-id="0095d-2500">PPS#</span></span> 
- <span data-ttu-id="0095d-2501">PPSN</span><span class="sxs-lookup"><span data-stu-id="0095d-2501">PPSN</span></span> 
- <span data-ttu-id="0095d-2502">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="0095d-2502">Public Services Card</span></span> 
- <span data-ttu-id="0095d-2503">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="0095d-2503">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="0095d-2504">Uimh.</span><span class="sxs-lookup"><span data-stu-id="0095d-2504">Uimh.</span></span> <span data-ttu-id="0095d-2505">PSP</span><span class="sxs-lookup"><span data-stu-id="0095d-2505">PSP</span></span> 
- <span data-ttu-id="0095d-2506">PSP</span><span class="sxs-lookup"><span data-stu-id="0095d-2506">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="0095d-2507">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="0095d-2507">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2508">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2508">Format</span></span>

<span data-ttu-id="0095d-2509">13 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2509">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2510">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2510">Pattern</span></span>

<span data-ttu-id="0095d-2511">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-2511">Formatted:</span></span>
- <span data-ttu-id="0095d-2512">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2512">Two digits</span></span> 
- <span data-ttu-id="0095d-2513">Un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-2513">A dash</span></span> 
- <span data-ttu-id="0095d-2514">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2514">Three digits</span></span> 
- <span data-ttu-id="0095d-2515">Un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-2515">A dash</span></span> 
- <span data-ttu-id="0095d-2516">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2516">Eight digits</span></span>

<span data-ttu-id="0095d-2517">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-2517">Unformatted:</span></span>
- <span data-ttu-id="0095d-2518">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2518">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2519">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2519">Checksum</span></span>

<span data-ttu-id="0095d-2520">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2520">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2521">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2521">Definition</span></span>

<span data-ttu-id="0095d-2522">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2523">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2523">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2524">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2524">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2525">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2525">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="0095d-2526">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2526">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="0095d-2527">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2527">Bank Account Number</span></span> 
- <span data-ttu-id="0095d-2528">Bank Account</span><span class="sxs-lookup"><span data-stu-id="0095d-2528">Bank Account</span></span> 
- <span data-ttu-id="0095d-2529">Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2529">Account Number</span></span> 
- <span data-ttu-id="0095d-2530">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="0095d-2530">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="0095d-2531">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="0095d-2531">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2532">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2532">Format</span></span>

<span data-ttu-id="0095d-2533">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2534">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2534">Pattern</span></span>

<span data-ttu-id="0095d-2535">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2536">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2536">Checksum</span></span>

<span data-ttu-id="0095d-2537">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2537">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2538">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2538">Definition</span></span>

<span data-ttu-id="0095d-2539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2540">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2540">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2541">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="0095d-2541">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="0095d-2542">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2542">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2543">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2543">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="0095d-2544">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="0095d-2544">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="0095d-2545">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="0095d-2545">מספר זהות</span></span> 
- <span data-ttu-id="0095d-2546">National ID Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2546">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="0095d-2547">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-2547">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2548">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2548">Format</span></span>

<span data-ttu-id="0095d-2549">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2549">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2550">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2550">Pattern</span></span>

- <span data-ttu-id="0095d-2551">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2551">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="0095d-2552">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2552">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2553">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2553">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-2554">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="0095d-2554">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="0095d-2555">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2555">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2556">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2556">Checksum</span></span>

<span data-ttu-id="0095d-2557">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2557">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2558">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2558">Definition</span></span>

<span data-ttu-id="0095d-2559">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2559">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2560">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2560">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2561">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2561">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2562">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2562">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="0095d-2563">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2563">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="0095d-2564">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-2564">numero di patente di guida</span></span> 
- <span data-ttu-id="0095d-2565">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-2565">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="0095d-2566">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="0095d-2566">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2567">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2567">Format</span></span>

<span data-ttu-id="0095d-2568">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2568">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2569">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2569">Pattern</span></span>

<span data-ttu-id="0095d-2570">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="0095d-2570">Bank account number:</span></span>
- <span data-ttu-id="0095d-2571">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2571">Seven or eight digits</span></span>
- <span data-ttu-id="0095d-2572">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="0095d-2572">Bank account branch code:</span></span>
- <span data-ttu-id="0095d-2573">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2573">Four digits</span></span> 
- <span data-ttu-id="0095d-2574">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2574">A space or dash (optional)</span></span> 
- <span data-ttu-id="0095d-2575">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2575">Three digits</span></span>

<span data-ttu-id="0095d-2576">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2576">Checksum</span></span>

<span data-ttu-id="0095d-2577">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2577">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2578">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2578">Definition</span></span>

<span data-ttu-id="0095d-2579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2580">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2580">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2581">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="0095d-2581">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="0095d-2582">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-2582">One of the following is true:</span></span>
- <span data-ttu-id="0095d-2583">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2583">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2584">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="0095d-2584">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="0095d-2585">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2586">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2586">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2587">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="0095d-2587">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2588">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2588">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="0095d-2589">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="0095d-2589">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="0095d-2590">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2590">Checking Account Number</span></span> 
- <span data-ttu-id="0095d-2591">Checking Account</span><span class="sxs-lookup"><span data-stu-id="0095d-2591">Checking Account</span></span> 
- <span data-ttu-id="0095d-2592">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-2592">Checking Account #</span></span> 
- <span data-ttu-id="0095d-2593">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2593">Checking Acct Number</span></span> 
- <span data-ttu-id="0095d-2594">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-2594">Checking Acct #</span></span> 
- <span data-ttu-id="0095d-2595">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2595">Checking Acct No.</span></span> 
- <span data-ttu-id="0095d-2596">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2596">Checking Account No.</span></span> 
- <span data-ttu-id="0095d-2597">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2597">Bank Account Number</span></span> 
- <span data-ttu-id="0095d-2598">Bank Account</span><span class="sxs-lookup"><span data-stu-id="0095d-2598">Bank Account</span></span> 
- <span data-ttu-id="0095d-2599">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-2599">Bank Account #</span></span> 
- <span data-ttu-id="0095d-2600">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2600">Bank Acct Number</span></span> 
- <span data-ttu-id="0095d-2601">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-2601">Bank Acct #</span></span> 
- <span data-ttu-id="0095d-2602">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2602">Bank Acct No.</span></span> 
- <span data-ttu-id="0095d-2603">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2603">Bank Account No.</span></span> 
- <span data-ttu-id="0095d-2604">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2604">Savings Account Number</span></span> 
- <span data-ttu-id="0095d-2605">Savings Account</span><span class="sxs-lookup"><span data-stu-id="0095d-2605">Savings Account</span></span> 
- <span data-ttu-id="0095d-2606">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-2606">Savings Account #</span></span> 
- <span data-ttu-id="0095d-2607">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2607">Savings Acct Number</span></span> 
- <span data-ttu-id="0095d-2608">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-2608">Savings Acct #</span></span> 
- <span data-ttu-id="0095d-2609">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2609">Savings Acct No.</span></span> 
- <span data-ttu-id="0095d-2610">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2610">Savings Account No.</span></span> 
- <span data-ttu-id="0095d-2611">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2611">Debit Account Number</span></span> 
- <span data-ttu-id="0095d-2612">Debit Account</span><span class="sxs-lookup"><span data-stu-id="0095d-2612">Debit Account</span></span> 
- <span data-ttu-id="0095d-2613">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-2613">Debit Account #</span></span> 
- <span data-ttu-id="0095d-2614">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2614">Debit Acct Number</span></span> 
- <span data-ttu-id="0095d-2615">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-2615">Debit Acct #</span></span> 
- <span data-ttu-id="0095d-2616">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2616">Debit Acct No.</span></span> 
- <span data-ttu-id="0095d-2617">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2617">Debit Account No.</span></span> 
- <span data-ttu-id="0095d-2618">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="0095d-2618">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="0095d-2619">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="0095d-2619">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="0095d-2620">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="0095d-2620">＃勘定の確認</span></span> 
- <span data-ttu-id="0095d-2621">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="0095d-2621">勘定番号の確認</span></span> 
- <span data-ttu-id="0095d-2622">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="0095d-2622">口座番号の確認</span></span> 
- <span data-ttu-id="0095d-2623">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2623">銀行口座番号</span></span> 
- <span data-ttu-id="0095d-2624">銀行口座</span><span class="sxs-lookup"><span data-stu-id="0095d-2624">銀行口座</span></span> 
- <span data-ttu-id="0095d-2625">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2625">銀行口座＃</span></span> 
- <span data-ttu-id="0095d-2626">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2626">銀行の勘定番号</span></span> 
- <span data-ttu-id="0095d-2627">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="0095d-2627">銀行のacct＃</span></span> 
- <span data-ttu-id="0095d-2628">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="0095d-2628">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="0095d-2629">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2629">銀行口座番号</span></span>
- <span data-ttu-id="0095d-2630">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2630">普通預金口座番号</span></span> 
- <span data-ttu-id="0095d-2631">預金口座</span><span class="sxs-lookup"><span data-stu-id="0095d-2631">預金口座</span></span> 
- <span data-ttu-id="0095d-2632">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2632">貯蓄口座＃</span></span> 
- <span data-ttu-id="0095d-2633">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="0095d-2633">貯蓄勘定の数</span></span> 
- <span data-ttu-id="0095d-2634">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2634">貯蓄勘定＃</span></span> 
- <span data-ttu-id="0095d-2635">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2635">貯蓄勘定番号</span></span> 
- <span data-ttu-id="0095d-2636">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2636">普通預金口座番号</span></span> 
- <span data-ttu-id="0095d-2637">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2637">引き落とし口座番号</span></span> 
- <span data-ttu-id="0095d-2638">口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2638">口座番号</span></span> 
- <span data-ttu-id="0095d-2639">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2639">口座番号＃</span></span> 
- <span data-ttu-id="0095d-2640">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2640">デビットのacct番号</span></span> 
- <span data-ttu-id="0095d-2641">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2641">デビット勘定＃</span></span> 
- <span data-ttu-id="0095d-2642">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2642">デビットACCTの番号</span></span> 
- <span data-ttu-id="0095d-2643">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2643">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="0095d-2644">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="0095d-2644">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="0095d-2645">Otemachi</span><span class="sxs-lookup"><span data-stu-id="0095d-2645">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="0095d-2646">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-2646">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2647">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2647">Format</span></span>

<span data-ttu-id="0095d-2648">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2648">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2649">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2649">Pattern</span></span>

<span data-ttu-id="0095d-2650">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2650">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2651">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2651">Checksum</span></span>

<span data-ttu-id="0095d-2652">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2652">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2653">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2653">Definition</span></span>

<span data-ttu-id="0095d-2654">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2654">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2655">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2655">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2656">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2656">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2657">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2657">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="0095d-2658">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2658">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="0095d-2659">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-2659">dl#</span></span> 
- <span data-ttu-id="0095d-2660">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-2660">DL＃</span></span> 
- <span data-ttu-id="0095d-2661">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-2661">dls#</span></span> 
- <span data-ttu-id="0095d-2662">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-2662">DLS＃</span></span> 
- <span data-ttu-id="0095d-2663">driver license</span><span class="sxs-lookup"><span data-stu-id="0095d-2663">driver license</span></span> 
- <span data-ttu-id="0095d-2664">driver licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2664">driver licenses</span></span> 
- <span data-ttu-id="0095d-2665">drivers license</span><span class="sxs-lookup"><span data-stu-id="0095d-2665">drivers license</span></span> 
- <span data-ttu-id="0095d-2666">driver's license</span><span class="sxs-lookup"><span data-stu-id="0095d-2666">driver's license</span></span> 
- <span data-ttu-id="0095d-2667">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2667">drivers licenses</span></span> 
- <span data-ttu-id="0095d-2668">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-2668">driver's licenses</span></span> 
- <span data-ttu-id="0095d-2669">driving licence</span><span class="sxs-lookup"><span data-stu-id="0095d-2669">driving licence</span></span> 
- <span data-ttu-id="0095d-2670">driver'lic</span><span class="sxs-lookup"><span data-stu-id="0095d-2670">lic#</span></span> 
- <span data-ttu-id="0095d-2671">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="0095d-2671">LIC＃</span></span> 
- <span data-ttu-id="0095d-2672">driver'lics</span><span class="sxs-lookup"><span data-stu-id="0095d-2672">lics#</span></span> 
- <span data-ttu-id="0095d-2673">state id</span><span class="sxs-lookup"><span data-stu-id="0095d-2673">state id</span></span> 
- <span data-ttu-id="0095d-2674">state identification</span><span class="sxs-lookup"><span data-stu-id="0095d-2674">state identification</span></span> 
- <span data-ttu-id="0095d-2675">state identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-2675">state identification number</span></span> 
- <span data-ttu-id="0095d-2676">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="0095d-2676">低所得国＃</span></span> 
- <span data-ttu-id="0095d-2677">免許証</span><span class="sxs-lookup"><span data-stu-id="0095d-2677">免許証</span></span> 
- <span data-ttu-id="0095d-2678">状態ID</span><span class="sxs-lookup"><span data-stu-id="0095d-2678">状態ID</span></span>
- <span data-ttu-id="0095d-2679">状態の識別</span><span class="sxs-lookup"><span data-stu-id="0095d-2679">状態の識別</span></span> 
- <span data-ttu-id="0095d-2680">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2680">状態の識別番号</span></span> 
- <span data-ttu-id="0095d-2681">運転免許</span><span class="sxs-lookup"><span data-stu-id="0095d-2681">運転免許</span></span> 
- <span data-ttu-id="0095d-2682">運転免許証</span><span class="sxs-lookup"><span data-stu-id="0095d-2682">運転免許証</span></span> 
- <span data-ttu-id="0095d-2683">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2683">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="0095d-2684">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-2684">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2685">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2685">Format</span></span>

<span data-ttu-id="0095d-2686">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2686">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2687">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2687">Pattern</span></span>

<span data-ttu-id="0095d-2688">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2688">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2689">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2689">Checksum</span></span>

<span data-ttu-id="0095d-2690">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2690">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2691">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2691">Definition</span></span>

<span data-ttu-id="0095d-2692">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2692">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2693">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2693">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2694">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-2694">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2695">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2695">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="0095d-2696">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-2696">Keyword_jp_passport</span></span>

- <span data-ttu-id="0095d-2697">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-2697">パスポート</span></span> 
- <span data-ttu-id="0095d-2698">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2698">パスポート番号</span></span> 
- <span data-ttu-id="0095d-2699">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-2699">パスポートのNum</span></span> 
- <span data-ttu-id="0095d-2700">パスポート #</span><span class="sxs-lookup"><span data-stu-id="0095d-2700">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="0095d-2701">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="0095d-2701">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2702">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2702">Format</span></span>

<span data-ttu-id="0095d-2703">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2703">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2704">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2704">Pattern</span></span>

<span data-ttu-id="0095d-2705">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2705">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2706">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2706">Checksum</span></span>

<span data-ttu-id="0095d-2707">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2707">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2708">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2708">Definition</span></span>

<span data-ttu-id="0095d-2709">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2709">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2710">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2710">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2711">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2711">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2712">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2712">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="0095d-2713">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2713">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="0095d-2714">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2714">Resident Registration Number</span></span>
- <span data-ttu-id="0095d-2715">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2715">Resident Register Number</span></span> 
- <span data-ttu-id="0095d-2716">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2716">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="0095d-2717">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2717">Resident Registration No.</span></span> 
- <span data-ttu-id="0095d-2718">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2718">Resident Register No.</span></span> 
- <span data-ttu-id="0095d-2719">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2719">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="0095d-2720">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2720">Basic Resident Register No.</span></span> 
- <span data-ttu-id="0095d-2721">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="0095d-2721">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="0095d-2722">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2722">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="0095d-2723">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="0095d-2723">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="0095d-2724">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2724">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="0095d-2725">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="0095d-2725">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2726">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2726">Format</span></span>

<span data-ttu-id="0095d-2727">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2727">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2728">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2728">Pattern</span></span>

<span data-ttu-id="0095d-2729">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2729">7-12 digits:</span></span>
- <span data-ttu-id="0095d-2730">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2730">Four digits</span></span> 
- <span data-ttu-id="0095d-2731">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="0095d-2731">A hyphen (optional)</span></span> 
- <span data-ttu-id="0095d-2732">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="0095d-2732">Six digits OR</span></span>
- <span data-ttu-id="0095d-2733">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2733">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2734">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2734">Checksum</span></span>

<span data-ttu-id="0095d-2735">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2736">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2736">Definition</span></span>

<span data-ttu-id="0095d-2737">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2737">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2738">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2738">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2739">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="0095d-2739">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="0095d-2740">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2740">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2741">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2741">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2742">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="0095d-2742">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2743">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2743">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="0095d-2744">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="0095d-2744">Keyword_jp_sin</span></span>

- <span data-ttu-id="0095d-2745">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="0095d-2745">Social Insurance No.</span></span> 
- <span data-ttu-id="0095d-2746">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="0095d-2746">Social Insurance Num</span></span> 
- <span data-ttu-id="0095d-2747">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="0095d-2747">Social Insurance Number</span></span> 
- <span data-ttu-id="0095d-2748">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="0095d-2748">社会保険のテンキー</span></span> 
- <span data-ttu-id="0095d-2749">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2749">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="0095d-2750">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="0095d-2750">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2751">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2751">Format</span></span>

<span data-ttu-id="0095d-2752">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2752">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2753">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2753">Pattern</span></span>

<span data-ttu-id="0095d-2754">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2754">12 letters and digits:</span></span>
- <span data-ttu-id="0095d-2755">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2755">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="0095d-2756">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2756">Eight digits</span></span> 
- <span data-ttu-id="0095d-2757">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-2757">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2758">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2758">Checksum</span></span>

<span data-ttu-id="0095d-2759">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2759">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2760">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2760">Definition</span></span>

<span data-ttu-id="0095d-2761">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2761">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2762">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2762">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2763">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2763">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2764">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2764">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="0095d-2765">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2765">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="0095d-2766">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="0095d-2766">Residence card number</span></span>
- <span data-ttu-id="0095d-2767">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="0095d-2767">Residence card no</span></span>
- <span data-ttu-id="0095d-2768">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="0095d-2768">Residence card #</span></span>
- <span data-ttu-id="0095d-2769">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="0095d-2769">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="0095d-2770">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2770">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2771">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2771">Format</span></span>

<span data-ttu-id="0095d-2772">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="0095d-2772">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2773">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2773">Pattern</span></span>

<span data-ttu-id="0095d-2774">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2774">12 digits:</span></span>
- <span data-ttu-id="0095d-2775">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-2775">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="0095d-2776">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2776">A dash (optional)</span></span> 
- <span data-ttu-id="0095d-2777">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="0095d-2777">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="0095d-2778">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2778">A dash (optional)</span></span> 
- <span data-ttu-id="0095d-2779">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="0095d-2779">Three random digits</span></span> 
- <span data-ttu-id="0095d-2780">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="0095d-2780">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2781">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2781">Checksum</span></span>

<span data-ttu-id="0095d-2782">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2782">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2783">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2783">Definition</span></span>

<span data-ttu-id="0095d-2784">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2785">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2785">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2786">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2786">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2787">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2787">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="0095d-2788">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2788">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="0095d-2789">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="0095d-2789">digital application card</span></span>
- <span data-ttu-id="0095d-2790">i/c</span><span class="sxs-lookup"><span data-stu-id="0095d-2790">i/c</span></span>
- <span data-ttu-id="0095d-2791">i/c no</span><span class="sxs-lookup"><span data-stu-id="0095d-2791">i/c no</span></span>
- <span data-ttu-id="0095d-2792">IC</span><span class="sxs-lookup"><span data-stu-id="0095d-2792">ic</span></span>
- <span data-ttu-id="0095d-2793">IC No</span><span class="sxs-lookup"><span data-stu-id="0095d-2793">ic no</span></span>
- <span data-ttu-id="0095d-2794">id card</span><span class="sxs-lookup"><span data-stu-id="0095d-2794">id card</span></span>
- <span data-ttu-id="0095d-2795">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-2795">identification Card</span></span>
- <span data-ttu-id="0095d-2796">carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2796">identity card</span></span>
- <span data-ttu-id="0095d-2797">k/p</span><span class="sxs-lookup"><span data-stu-id="0095d-2797">k/p</span></span>
- <span data-ttu-id="0095d-2798">k/p no</span><span class="sxs-lookup"><span data-stu-id="0095d-2798">k/p no</span></span>
- <span data-ttu-id="0095d-2799">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="0095d-2799">kad akuan diri</span></span>
- <span data-ttu-id="0095d-2800">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="0095d-2800">kad aplikasi digital</span></span>
- <span data-ttu-id="0095d-2801">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="0095d-2801">kad pengenalan malaysia</span></span>
- <span data-ttu-id="0095d-2802">KP</span><span class="sxs-lookup"><span data-stu-id="0095d-2802">kp</span></span>
- <span data-ttu-id="0095d-2803">KP No</span><span class="sxs-lookup"><span data-stu-id="0095d-2803">kp no</span></span>
- <span data-ttu-id="0095d-2804">MyKad</span><span class="sxs-lookup"><span data-stu-id="0095d-2804">mykad</span></span>
- <span data-ttu-id="0095d-2805">MYKAS</span><span class="sxs-lookup"><span data-stu-id="0095d-2805">mykas</span></span>
- <span data-ttu-id="0095d-2806">mykid</span><span class="sxs-lookup"><span data-stu-id="0095d-2806">mykid</span></span>
- <span data-ttu-id="0095d-2807">mypr</span><span class="sxs-lookup"><span data-stu-id="0095d-2807">mypr</span></span>
- <span data-ttu-id="0095d-2808">mytentera</span><span class="sxs-lookup"><span data-stu-id="0095d-2808">mytentera</span></span>
- <span data-ttu-id="0095d-2809">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="0095d-2809">malaysia identity card</span></span>
- <span data-ttu-id="0095d-2810">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="0095d-2810">malaysian identity card</span></span>
- <span data-ttu-id="0095d-2811">NRIC</span><span class="sxs-lookup"><span data-stu-id="0095d-2811">nric</span></span>
- <span data-ttu-id="0095d-2812">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="0095d-2812">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="0095d-2813">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="0095d-2813">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2814">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2814">Format</span></span>

<span data-ttu-id="0095d-2815">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="0095d-2815">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2816">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2816">Pattern</span></span>

<span data-ttu-id="0095d-2817">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2817">8-9 digits:</span></span>
- <span data-ttu-id="0095d-2818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2818">Three digits</span></span> 
- <span data-ttu-id="0095d-2819">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2819">A space (optional)</span></span> 
- <span data-ttu-id="0095d-2820">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2820">Three digits</span></span> 
- <span data-ttu-id="0095d-2821">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-2821">A space (optional)</span></span> 
- <span data-ttu-id="0095d-2822">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2822">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2823">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2823">Checksum</span></span>

<span data-ttu-id="0095d-2824">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2825">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2825">Definition</span></span>

<span data-ttu-id="0095d-2826">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2826">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2827">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2827">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2828">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="0095d-2828">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="0095d-2829">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="0095d-2829">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="0095d-2830">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2830">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2831">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2831">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="0095d-2832">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="0095d-2832">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="0095d-2833">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="0095d-2833">Citizen service number</span></span> 
- <span data-ttu-id="0095d-2834">BSN</span><span class="sxs-lookup"><span data-stu-id="0095d-2834">BSN</span></span> 
- <span data-ttu-id="0095d-2835">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2835">Burgerservicenummer</span></span> 
- <span data-ttu-id="0095d-2836">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2836">Sofinummer</span></span> 
- <span data-ttu-id="0095d-2837">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2837">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="0095d-2838">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2838">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="0095d-2839">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="0095d-2839">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2840">Format</span></span>

<span data-ttu-id="0095d-2841">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2841">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2842">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2842">Pattern</span></span>

<span data-ttu-id="0095d-2843">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2843">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2844">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2844">Checksum</span></span>

<span data-ttu-id="0095d-2845">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2845">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2846">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2846">Definition</span></span>

<span data-ttu-id="0095d-2847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2848">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2848">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2849">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="0095d-2849">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="0095d-2850">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2850">The checksum passes.</span></span>

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

<span data-ttu-id="0095d-2851">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2851">Keywords</span></span>

<span data-ttu-id="0095d-2852">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="0095d-2852">Keyword_nz_terms</span></span>

- <span data-ttu-id="0095d-2853">NHI</span><span class="sxs-lookup"><span data-stu-id="0095d-2853">NHI</span></span> 
- <span data-ttu-id="0095d-2854">New Zealand</span><span class="sxs-lookup"><span data-stu-id="0095d-2854">New Zealand</span></span> 
- <span data-ttu-id="0095d-2855">Integrità</span><span class="sxs-lookup"><span data-stu-id="0095d-2855">Health</span></span> 
- <span data-ttu-id="0095d-2856">trattamento</span><span class="sxs-lookup"><span data-stu-id="0095d-2856">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="0095d-2857">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="0095d-2857">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2858">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2858">Format</span></span>

<span data-ttu-id="0095d-2859">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2859">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2860">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2860">Pattern</span></span>

<span data-ttu-id="0095d-2861">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2861">11 digits:</span></span>
- <span data-ttu-id="0095d-2862">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-2862">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="0095d-2863">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="0095d-2863">Three-digit individual number</span></span> 
- <span data-ttu-id="0095d-2864">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="0095d-2864">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2865">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2865">Checksum</span></span>

<span data-ttu-id="0095d-2866">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2866">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2867">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2867">Definition</span></span>

<span data-ttu-id="0095d-2868">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2868">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2869">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2869">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2870">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2870">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="0095d-2871">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2871">The checksum passes.</span></span>
- <span data-ttu-id="0095d-2872">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2873">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2873">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2874">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2874">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2875">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2875">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="0095d-2876">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2876">Keyword_norway_id_number</span></span>

- <span data-ttu-id="0095d-2877">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="0095d-2877">Personal identification number</span></span>
- <span data-ttu-id="0095d-2878">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="0095d-2878">Norwegian ID Number</span></span>
- <span data-ttu-id="0095d-2879">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="0095d-2879">ID Number</span></span>
- <span data-ttu-id="0095d-2880">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-2880">Identification</span></span>
- <span data-ttu-id="0095d-2881">Personnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2881">Personnummer</span></span>
- <span data-ttu-id="0095d-2882">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="0095d-2882">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="0095d-2883">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="0095d-2883">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2884">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2884">Format</span></span>

<span data-ttu-id="0095d-2885">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="0095d-2885">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2886">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2886">Pattern</span></span>

<span data-ttu-id="0095d-2887">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-2887">12 digits:</span></span>
- <span data-ttu-id="0095d-2888">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2888">Four digits</span></span> 
- <span data-ttu-id="0095d-2889">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-2889">A hyphen</span></span> 
- <span data-ttu-id="0095d-2890">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2890">Seven digits</span></span> 
- <span data-ttu-id="0095d-2891">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-2891">A hyphen</span></span> 
- <span data-ttu-id="0095d-2892">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-2892">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2893">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2893">Checksum</span></span>

<span data-ttu-id="0095d-2894">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2894">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2895">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2895">Definition</span></span>

<span data-ttu-id="0095d-2896">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2896">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2897">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2897">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2898">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-2898">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2899">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2899">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="0095d-2900">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="0095d-2900">Keyword_philippines_id</span></span>

- <span data-ttu-id="0095d-2901">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="0095d-2901">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="0095d-2902">UMID</span><span class="sxs-lookup"><span data-stu-id="0095d-2902">UMID</span></span> 
- <span data-ttu-id="0095d-2903">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-2903">Identity Card</span></span> 
- <span data-ttu-id="0095d-2904">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="0095d-2904">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="0095d-2905">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="0095d-2905">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2906">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2906">Format</span></span>

<span data-ttu-id="0095d-2907">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2907">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2908">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2908">Pattern</span></span>

<span data-ttu-id="0095d-2909">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2909">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2910">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2910">Checksum</span></span>

<span data-ttu-id="0095d-2911">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2912">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2912">Definition</span></span>

<span data-ttu-id="0095d-2913">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2913">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="0095d-2914">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2914">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="0095d-2915">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2915">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2916">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2916">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="0095d-2917">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2917">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="0095d-2918">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="0095d-2918">Dowód osobisty</span></span>
- <span data-ttu-id="0095d-2919">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="0095d-2919">Numer dowodu osobistego</span></span>
- <span data-ttu-id="0095d-2920">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="0095d-2920">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="0095d-2921">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="0095d-2921">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="0095d-2922">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="0095d-2922">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="0095d-2923">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="0095d-2923">Dowód Tożsamości</span></span>
- <span data-ttu-id="0095d-2924">Dow.</span><span class="sxs-lookup"><span data-stu-id="0095d-2924">dow.</span></span> <span data-ttu-id="0095d-2925">OS.</span><span class="sxs-lookup"><span data-stu-id="0095d-2925">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="0095d-2926">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="0095d-2926">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2927">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2927">Format</span></span>

<span data-ttu-id="0095d-2928">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2928">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2929">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2929">Pattern</span></span>

<span data-ttu-id="0095d-2930">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2930">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2931">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2931">Checksum</span></span>

<span data-ttu-id="0095d-2932">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2932">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2933">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2933">Definition</span></span>

<span data-ttu-id="0095d-2934">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2934">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2935">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2935">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2936">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2936">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="0095d-2937">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2937">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2938">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2938">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="0095d-2939">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2939">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="0095d-2940">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="0095d-2940">Nr PESEL</span></span>
- <span data-ttu-id="0095d-2941">PESEL</span><span class="sxs-lookup"><span data-stu-id="0095d-2941">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="0095d-2942">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="0095d-2942">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2943">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2943">Format</span></span>

<span data-ttu-id="0095d-2944">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2944">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2945">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2945">Pattern</span></span>

<span data-ttu-id="0095d-2946">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2946">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2947">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2947">Checksum</span></span>

<span data-ttu-id="0095d-2948">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-2948">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2949">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2949">Definition</span></span>

<span data-ttu-id="0095d-2950">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2950">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2951">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2951">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2952">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-2952">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="0095d-2953">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-2953">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2954">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2954">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="0095d-2955">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="0095d-2955">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="0095d-2956">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="0095d-2956">Numer paszportu</span></span>
- <span data-ttu-id="0095d-2957">Nr.</span><span class="sxs-lookup"><span data-stu-id="0095d-2957">Nr.</span></span> <span data-ttu-id="0095d-2958">Paszportu</span><span class="sxs-lookup"><span data-stu-id="0095d-2958">Paszportu</span></span>
- <span data-ttu-id="0095d-2959">Paszport</span><span class="sxs-lookup"><span data-stu-id="0095d-2959">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="0095d-2960">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="0095d-2960">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2961">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2961">Format</span></span>

<span data-ttu-id="0095d-2962">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2962">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2963">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2963">Pattern</span></span>

<span data-ttu-id="0095d-2964">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2964">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2965">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2965">Checksum</span></span>

<span data-ttu-id="0095d-2966">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2966">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2967">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2967">Definition</span></span>

<span data-ttu-id="0095d-2968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2969">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2969">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2970">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="0095d-2970">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-2971">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2971">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="0095d-2972">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="0095d-2972">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="0095d-2973">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="0095d-2973">Citizen Card</span></span>
- <span data-ttu-id="0095d-2974">Carta ID</span><span class="sxs-lookup"><span data-stu-id="0095d-2974">National ID Card</span></span>
- <span data-ttu-id="0095d-2975">CC</span><span class="sxs-lookup"><span data-stu-id="0095d-2975">CC</span></span>
- <span data-ttu-id="0095d-2976">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="0095d-2976">Cartão de Cidadão</span></span>
- <span data-ttu-id="0095d-2977">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="0095d-2977">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="0095d-2978">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-2978">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2979">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2979">Format</span></span>

<span data-ttu-id="0095d-2980">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-2980">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2981">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2981">Pattern</span></span>

<span data-ttu-id="0095d-2982">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-2982">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-2983">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-2983">Checksum</span></span>

<span data-ttu-id="0095d-2984">No</span><span class="sxs-lookup"><span data-stu-id="0095d-2984">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-2985">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-2985">Definition</span></span>

<span data-ttu-id="0095d-2986">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-2987">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-2987">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-2988">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-2988">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-2989">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-2989">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="0095d-2990">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="0095d-2990">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="0095d-2991">Identification Card</span><span class="sxs-lookup"><span data-stu-id="0095d-2991">Identification Card</span></span> 
- <span data-ttu-id="0095d-2992">I card number</span><span class="sxs-lookup"><span data-stu-id="0095d-2992">I card number</span></span> 
- <span data-ttu-id="0095d-2993">ID number</span><span class="sxs-lookup"><span data-stu-id="0095d-2993">ID number</span></span> 
- <span data-ttu-id="0095d-2994">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="0095d-2994">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="0095d-2995">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="0095d-2995">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-2996">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-2996">Format</span></span>

<span data-ttu-id="0095d-2997">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="0095d-2997">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-2998">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-2998">Pattern</span></span>

- <span data-ttu-id="0095d-2999">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="0095d-2999">Nine letters and digits:</span></span>
- <span data-ttu-id="0095d-3000">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="0095d-3000">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-3001">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3001">Seven digits</span></span> 
- <span data-ttu-id="0095d-3002">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="0095d-3002">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3003">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3003">Checksum</span></span>

<span data-ttu-id="0095d-3004">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3004">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3005">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3005">Definition</span></span>

<span data-ttu-id="0095d-3006">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3006">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3007">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3007">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3008">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="0095d-3008">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="0095d-3009">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3009">The checksum passes.</span></span>

<span data-ttu-id="0095d-3010">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3010">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3011">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3011">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3012">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3012">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3013">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3013">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="0095d-3014">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="0095d-3014">Keyword_singapore_nric</span></span>

- <span data-ttu-id="0095d-3015">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-3015">National Registration Identity Card</span></span> 
- <span data-ttu-id="0095d-3016">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-3016">Identity Card Number</span></span> 
- <span data-ttu-id="0095d-3017">NRIC</span><span class="sxs-lookup"><span data-stu-id="0095d-3017">NRIC</span></span> 
- <span data-ttu-id="0095d-3018">IC</span><span class="sxs-lookup"><span data-stu-id="0095d-3018">IC</span></span> 
- <span data-ttu-id="0095d-3019">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="0095d-3019">Foreign Identification Number</span></span> 
- <span data-ttu-id="0095d-3020">FIN</span><span class="sxs-lookup"><span data-stu-id="0095d-3020">FIN</span></span> 
- <span data-ttu-id="0095d-3021">身份证</span><span class="sxs-lookup"><span data-stu-id="0095d-3021">身份证</span></span> 
- <span data-ttu-id="0095d-3022">身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-3022">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="0095d-3023">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="0095d-3023">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3024">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3024">Format</span></span>

<span data-ttu-id="0095d-3025">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="0095d-3025">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3026">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3026">Pattern</span></span>

<span data-ttu-id="0095d-3027">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3027">13 digits:</span></span>
- <span data-ttu-id="0095d-3028">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-3028">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="0095d-3029">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3029">Four digits</span></span> 
- <span data-ttu-id="0095d-3030">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="0095d-3030">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="0095d-3031">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="0095d-3031">The digit "8" or "9"</span></span> 
- <span data-ttu-id="0095d-3032">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3032">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3033">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3033">Checksum</span></span>

<span data-ttu-id="0095d-3034">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3034">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3035">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3035">Definition</span></span>

<span data-ttu-id="0095d-3036">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3036">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3037">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3037">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3038">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-3038">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="0095d-3039">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3039">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3040">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3040">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="0095d-3041">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="0095d-3041">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="0095d-3042">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-3042">Identity card</span></span>
- <span data-ttu-id="0095d-3043">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3043">ID</span></span>
- <span data-ttu-id="0095d-3044">Identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-3044">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="0095d-3045">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="0095d-3045">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3046">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3046">Format</span></span>

<span data-ttu-id="0095d-3047">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="0095d-3047">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3048">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3048">Pattern</span></span>

<span data-ttu-id="0095d-3049">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3049">13 digits:</span></span>
- <span data-ttu-id="0095d-3050">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-3050">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="0095d-3051">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0095d-3051">A hyphen</span></span> 
- <span data-ttu-id="0095d-3052">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="0095d-3052">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="0095d-3053">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="0095d-3053">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="0095d-3054">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="0095d-3054">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="0095d-3055">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3055">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3056">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3056">Checksum</span></span>

<span data-ttu-id="0095d-3057">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3057">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3058">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3058">Definition</span></span>

<span data-ttu-id="0095d-3059">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3059">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3060">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3060">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3061">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-3061">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="0095d-3062">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3062">The checksum passes.</span></span>

<span data-ttu-id="0095d-3063">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3063">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3064">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3064">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3065">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3065">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3066">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3066">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="0095d-3067">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="0095d-3067">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="0095d-3068">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="0095d-3068">National ID card</span></span> 
- <span data-ttu-id="0095d-3069">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="0095d-3069">Citizen's Registration Number</span></span> 
- <span data-ttu-id="0095d-3070">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="0095d-3070">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="0095d-3071">RRN</span><span class="sxs-lookup"><span data-stu-id="0095d-3071">RRN</span></span> 
- <span data-ttu-id="0095d-3072">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="0095d-3072">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="0095d-3073">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="0095d-3073">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3074">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3074">Format</span></span>

<span data-ttu-id="0095d-3075">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3075">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3076">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3076">Pattern</span></span>

<span data-ttu-id="0095d-3077">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3077">11-12 digits:</span></span>
- <span data-ttu-id="0095d-3078">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3078">Two digits</span></span> 
- <span data-ttu-id="0095d-3079">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="0095d-3079">A forward slash (optional)</span></span> 
- <span data-ttu-id="0095d-3080">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3080">7-8 digits</span></span> 
- <span data-ttu-id="0095d-3081">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="0095d-3081">A forward slash (optional)</span></span> 
- <span data-ttu-id="0095d-3082">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3082">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3083">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3083">Checksum</span></span>

<span data-ttu-id="0095d-3084">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3084">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3085">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3085">Definition</span></span>

<span data-ttu-id="0095d-3086">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3086">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3087">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3087">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3088">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3088">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3089">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3089">Keywords</span></span>

<span data-ttu-id="0095d-3090">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0095d-3090">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="0095d-3091">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0095d-3091">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3092">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3092">Format</span></span>

<span data-ttu-id="0095d-3093">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="0095d-3093">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3094">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3094">Pattern</span></span>

- <span data-ttu-id="0095d-3095">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="0095d-3095">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="0095d-3096">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="0095d-3096">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="0095d-3097">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="0095d-3097">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="0095d-3098">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-3098">An equal sign (=)</span></span>
- <span data-ttu-id="0095d-3099">Qualsiasi carattere non costituito da un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), un simbolo (@), una virgoletta ("), un punto e virgola (;), una parentesi graffa sinistra ([) o una parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="0095d-3099">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="0095d-3100">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="0095d-3100">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="0095d-3101">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="0095d-3101">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3102">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3102">Checksum</span></span>

<span data-ttu-id="0095d-3103">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3103">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3104">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3104">Definition</span></span>

<span data-ttu-id="0095d-3105">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3106">L'espressione regolare CEP_Regex_SQLServerConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3106">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3107">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="0095d-3107">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="0095d-3108">L'espressione regolare CEP_PasswordPlaceHolder non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3108">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3109">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3109">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3110">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="0095d-3111">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="0095d-3111">CEP_GlobalFilter</span></span>

- <span data-ttu-id="0095d-3112">some-password</span><span class="sxs-lookup"><span data-stu-id="0095d-3112">some-password</span></span>
- <span data-ttu-id="0095d-3113">somepassword</span><span class="sxs-lookup"><span data-stu-id="0095d-3113">somepassword</span></span>
- <span data-ttu-id="0095d-3114">secretPassword</span><span class="sxs-lookup"><span data-stu-id="0095d-3114">secretPassword</span></span>
- <span data-ttu-id="0095d-3115">esempio</span><span class="sxs-lookup"><span data-stu-id="0095d-3115">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="0095d-3116">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="0095d-3116">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="0095d-3117">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-3117">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-3118">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="0095d-3118">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="0095d-3119">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="0095d-3119">Password or pwd followed by:</span></span>
    - <span data-ttu-id="0095d-3120">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="0095d-3120">Equal sign (=)</span></span>
    - <span data-ttu-id="0095d-3121">Valore minore di (<)</span><span class="sxs-lookup"><span data-stu-id="0095d-3121">Less than symbol (<)</span></span>
    - <span data-ttu-id="0095d-3122">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="0095d-3122">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="0095d-3123">Simbolo maggiore di (>)</span><span class="sxs-lookup"><span data-stu-id="0095d-3123">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="0095d-3124">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="0095d-3124">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="0095d-3125">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0095d-3125">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="0095d-3126">contoso</span><span class="sxs-lookup"><span data-stu-id="0095d-3126">contoso</span></span>
- <span data-ttu-id="0095d-3127">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="0095d-3127">fabrikam</span></span>
- <span data-ttu-id="0095d-3128">Northwind</span><span class="sxs-lookup"><span data-stu-id="0095d-3128">northwind</span></span>
- <span data-ttu-id="0095d-3129">sandbox</span><span class="sxs-lookup"><span data-stu-id="0095d-3129">sandbox</span></span>
- <span data-ttu-id="0095d-3130">OneBox</span><span class="sxs-lookup"><span data-stu-id="0095d-3130">onebox</span></span>
- <span data-ttu-id="0095d-3131">localhost</span><span class="sxs-lookup"><span data-stu-id="0095d-3131">localhost</span></span>
- <span data-ttu-id="0095d-3132">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="0095d-3132">127.0.0.1</span></span>
- <span data-ttu-id="0095d-3133">testacs. <!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="0095d-3133">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="0095d-3134">s-int.<!--no-hyperlink-->NET</span><span class="sxs-lookup"><span data-stu-id="0095d-3134">s-int.<!--no-hyperlink-->net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="0095d-3135">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-3135">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3136">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3136">Format</span></span>

<span data-ttu-id="0095d-3137">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="0095d-3137">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3138">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3138">Pattern</span></span>

<span data-ttu-id="0095d-3139">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="0095d-3139">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="0095d-3140">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="0095d-3140">2-4 digits (optional)</span></span> 
- <span data-ttu-id="0095d-3141">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="0095d-3141">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="0095d-3142">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="0095d-3142">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="0095d-3143">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3143">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3144">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3144">Checksum</span></span>

<span data-ttu-id="0095d-3145">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3145">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3146">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3146">Definition</span></span>

<span data-ttu-id="0095d-3147">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3147">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3148">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3148">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3149">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3149">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3150">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3150">Keywords</span></span>

<span data-ttu-id="0095d-3151">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3151">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="0095d-3152">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3152">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3153">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3153">Format</span></span>

<span data-ttu-id="0095d-3154">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3154">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3155">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3155">Pattern</span></span>

<span data-ttu-id="0095d-3156">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-3156">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3157">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3157">Checksum</span></span>

<span data-ttu-id="0095d-3158">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3158">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3159">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3159">Definition</span></span>

<span data-ttu-id="0095d-3160">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3160">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3161">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3161">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3162">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-3162">One of the following is true:</span></span>
    - <span data-ttu-id="0095d-3163">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-3163">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="0095d-3164">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-3164">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3165">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3165">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="0095d-3166">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-3166">Keyword_sweden_passport</span></span>

- <span data-ttu-id="0095d-3167">visa requirements</span><span class="sxs-lookup"><span data-stu-id="0095d-3167">visa requirements</span></span> 
- <span data-ttu-id="0095d-3168">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="0095d-3168">Alien Registration Card</span></span> 
- <span data-ttu-id="0095d-3169">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="0095d-3169">Schengen visas</span></span> 
- <span data-ttu-id="0095d-3170">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="0095d-3170">Schengen visa</span></span> 
- <span data-ttu-id="0095d-3171">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="0095d-3171">Visa Processing</span></span> 
- <span data-ttu-id="0095d-3172">Visa Type</span><span class="sxs-lookup"><span data-stu-id="0095d-3172">Visa Type</span></span> 
- <span data-ttu-id="0095d-3173">Single Entry</span><span class="sxs-lookup"><span data-stu-id="0095d-3173">Single Entry</span></span> 
- <span data-ttu-id="0095d-3174">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="0095d-3174">Multiple Entry</span></span> 
- <span data-ttu-id="0095d-3175">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="0095d-3175">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="0095d-3176">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-3176">Keyword_passport</span></span>

- <span data-ttu-id="0095d-3177">Passport Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3177">Passport Number</span></span> 
- <span data-ttu-id="0095d-3178">Passport No</span><span class="sxs-lookup"><span data-stu-id="0095d-3178">Passport No</span></span> 
- <span data-ttu-id="0095d-3179">Passport#</span><span class="sxs-lookup"><span data-stu-id="0095d-3179">Passport #</span></span> 
- <span data-ttu-id="0095d-3180">Passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3180">Passport#</span></span> 
- <span data-ttu-id="0095d-3181">PassportID</span><span class="sxs-lookup"><span data-stu-id="0095d-3181">PassportID</span></span> 
- <span data-ttu-id="0095d-3182">Passportno</span><span class="sxs-lookup"><span data-stu-id="0095d-3182">Passportno</span></span> 
- <span data-ttu-id="0095d-3183">passportnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-3183">passportnumber</span></span> 
- <span data-ttu-id="0095d-3184">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-3184">パスポート</span></span> 
- <span data-ttu-id="0095d-3185">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-3185">パスポート番号</span></span> 
- <span data-ttu-id="0095d-3186">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-3186">パスポートのNum</span></span> 
- <span data-ttu-id="0095d-3187">パスポート #</span><span class="sxs-lookup"><span data-stu-id="0095d-3187">パスポート＃</span></span> 
- <span data-ttu-id="0095d-3188">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-3188">Numéro de passeport</span></span> 
- <span data-ttu-id="0095d-3189">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="0095d-3189">Passeport n °</span></span> 
- <span data-ttu-id="0095d-3190">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="0095d-3190">Passeport Non</span></span> 
- <span data-ttu-id="0095d-3191">Passeport#</span><span class="sxs-lookup"><span data-stu-id="0095d-3191">Passeport #</span></span> 
- <span data-ttu-id="0095d-3192">Passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-3192">Passeport#</span></span> 
- <span data-ttu-id="0095d-3193">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="0095d-3193">PasseportNon</span></span> 
- <span data-ttu-id="0095d-3194">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="0095d-3194">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="0095d-3195">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="0095d-3195">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3196">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3196">Format</span></span>

<span data-ttu-id="0095d-3197">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3197">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3198">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3198">Pattern</span></span>

<span data-ttu-id="0095d-3199">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3199">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="0095d-3200">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-3200">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-3201">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="0095d-3201">An optional space</span></span> 
- <span data-ttu-id="0095d-3202">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="0095d-3202">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="0095d-3203">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="0095d-3203">An optional space</span></span> 
- <span data-ttu-id="0095d-3204">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="0095d-3204">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3205">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3205">Checksum</span></span>

<span data-ttu-id="0095d-3206">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3206">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3207">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3207">Definition</span></span>

<span data-ttu-id="0095d-3208">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3208">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3209">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3209">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3210">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="0095d-3210">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3211">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3211">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="0095d-3212">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="0095d-3212">Keyword_swift</span></span>

- <span data-ttu-id="0095d-3213">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="0095d-3213">international organization for standardization 9362</span></span> 
- <span data-ttu-id="0095d-3214">iso 9362</span><span class="sxs-lookup"><span data-stu-id="0095d-3214">iso 9362</span></span> 
- <span data-ttu-id="0095d-3215">iso9362</span><span class="sxs-lookup"><span data-stu-id="0095d-3215">iso9362</span></span> 
- <span data-ttu-id="0095d-3216">Swift\#</span><span class="sxs-lookup"><span data-stu-id="0095d-3216">swift\#</span></span> 
- <span data-ttu-id="0095d-3217">swiftcode</span><span class="sxs-lookup"><span data-stu-id="0095d-3217">swiftcode</span></span> 
- <span data-ttu-id="0095d-3218">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-3218">swiftnumber</span></span> 
- <span data-ttu-id="0095d-3219">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-3219">swiftroutingnumber</span></span> 
- <span data-ttu-id="0095d-3220">swift code</span><span class="sxs-lookup"><span data-stu-id="0095d-3220">swift code</span></span> 
- <span data-ttu-id="0095d-3221">swift number #</span><span class="sxs-lookup"><span data-stu-id="0095d-3221">swift number #</span></span> 
- <span data-ttu-id="0095d-3222">swift routing number</span><span class="sxs-lookup"><span data-stu-id="0095d-3222">swift routing number</span></span> 
- <span data-ttu-id="0095d-3223">bic number</span><span class="sxs-lookup"><span data-stu-id="0095d-3223">bic number</span></span> 
- <span data-ttu-id="0095d-3224">bic code</span><span class="sxs-lookup"><span data-stu-id="0095d-3224">bic code</span></span> 
- <span data-ttu-id="0095d-3225">BIC\#</span><span class="sxs-lookup"><span data-stu-id="0095d-3225">bic \#</span></span> 
- <span data-ttu-id="0095d-3226">BIC\#</span><span class="sxs-lookup"><span data-stu-id="0095d-3226">bic\#</span></span> 
- <span data-ttu-id="0095d-3227">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="0095d-3227">bank identifier code</span></span> 
- <span data-ttu-id="0095d-3228">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="0095d-3228">標準化9362</span></span> 
- <span data-ttu-id="0095d-3229">迅速 #</span><span class="sxs-lookup"><span data-stu-id="0095d-3229">迅速＃</span></span> 
- <span data-ttu-id="0095d-3230">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="0095d-3230">SWIFTコード</span></span> 
- <span data-ttu-id="0095d-3231">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="0095d-3231">SWIFT番号</span></span> 
- <span data-ttu-id="0095d-3232">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="0095d-3232">迅速なルーティング番号</span></span> 
- <span data-ttu-id="0095d-3233">BIC番号</span><span class="sxs-lookup"><span data-stu-id="0095d-3233">BIC番号</span></span> 
- <span data-ttu-id="0095d-3234">BICコード</span><span class="sxs-lookup"><span data-stu-id="0095d-3234">BICコード</span></span> 
- <span data-ttu-id="0095d-3235">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="0095d-3235">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="0095d-3236">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="0095d-3236">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="0095d-3237">rapide\#</span><span class="sxs-lookup"><span data-stu-id="0095d-3237">rapide \#</span></span> 
- <span data-ttu-id="0095d-3238">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="0095d-3238">code SWIFT</span></span> 
- <span data-ttu-id="0095d-3239">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="0095d-3239">le numéro de swift</span></span> 
- <span data-ttu-id="0095d-3240">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="0095d-3240">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="0095d-3241">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="0095d-3241">le numéro BIC</span></span> 
- <span data-ttu-id="0095d-3242">\#BIC</span><span class="sxs-lookup"><span data-stu-id="0095d-3242">\# BIC</span></span> 
- <span data-ttu-id="0095d-3243">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="0095d-3243">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="0095d-3244">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3244">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3245">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3245">Format</span></span>

<span data-ttu-id="0095d-3246">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3246">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3247">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3247">Pattern</span></span>

<span data-ttu-id="0095d-3248">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3248">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="0095d-3249">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-3249">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="0095d-3250">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="0095d-3250">The digit "1" or "2"</span></span> 
- <span data-ttu-id="0095d-3251">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3251">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3252">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3252">Checksum</span></span>

<span data-ttu-id="0095d-3253">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3253">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3254">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3254">Definition</span></span>

<span data-ttu-id="0095d-3255">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3255">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3256">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3256">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3257">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="0095d-3257">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="0095d-3258">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3258">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3259">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3259">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="0095d-3260">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="0095d-3260">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="0095d-3261">身份證字號</span><span class="sxs-lookup"><span data-stu-id="0095d-3261">身份證字號</span></span> 
- <span data-ttu-id="0095d-3262">身份證</span><span class="sxs-lookup"><span data-stu-id="0095d-3262">身份證</span></span> 
- <span data-ttu-id="0095d-3263">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="0095d-3263">身份證號碼</span></span> 
- <span data-ttu-id="0095d-3264">身份證號</span><span class="sxs-lookup"><span data-stu-id="0095d-3264">身份證號</span></span> 
- <span data-ttu-id="0095d-3265">身分證字號</span><span class="sxs-lookup"><span data-stu-id="0095d-3265">身分證字號</span></span> 
- <span data-ttu-id="0095d-3266">身分證</span><span class="sxs-lookup"><span data-stu-id="0095d-3266">身分證</span></span> 
- <span data-ttu-id="0095d-3267">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="0095d-3267">身分證號碼</span></span> 
- <span data-ttu-id="0095d-3268">身份證號</span><span class="sxs-lookup"><span data-stu-id="0095d-3268">身份證號</span></span> 
- <span data-ttu-id="0095d-3269">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="0095d-3269">身分證統一編號</span></span> 
- <span data-ttu-id="0095d-3270">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="0095d-3270">國民身分證統一編號</span></span> 
- <span data-ttu-id="0095d-3271">簽名</span><span class="sxs-lookup"><span data-stu-id="0095d-3271">簽名</span></span> 
- <span data-ttu-id="0095d-3272">蓋章</span><span class="sxs-lookup"><span data-stu-id="0095d-3272">蓋章</span></span> 
- <span data-ttu-id="0095d-3273">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="0095d-3273">簽名或蓋章</span></span> 
- <span data-ttu-id="0095d-3274">簽章</span><span class="sxs-lookup"><span data-stu-id="0095d-3274">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="0095d-3275">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3275">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3276">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3276">Format</span></span>

- <span data-ttu-id="0095d-3277">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3277">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="0095d-3278">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3278">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3279">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3279">Pattern</span></span>
<span data-ttu-id="0095d-3280">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="0095d-3280">Biometric passport number:</span></span>
- <span data-ttu-id="0095d-3281">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="0095d-3281">The digit "3"</span></span> 
- <span data-ttu-id="0095d-3282">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3282">Eight digits</span></span>

<span data-ttu-id="0095d-3283">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="0095d-3283">Non-biometric passport number:</span></span>
- <span data-ttu-id="0095d-3284">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3284">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3285">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3285">Checksum</span></span>

<span data-ttu-id="0095d-3286">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3287">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3287">Definition</span></span>

<span data-ttu-id="0095d-3288">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3289">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3289">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3290">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-3290">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3291">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3291">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="0095d-3292">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-3292">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="0095d-3293">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="0095d-3293">ROC passport number</span></span> 
- <span data-ttu-id="0095d-3294">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3294">Passport number</span></span> 
- <span data-ttu-id="0095d-3295">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3295">Passport no</span></span> 
- <span data-ttu-id="0095d-3296">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="0095d-3296">Passport Num</span></span> 
- <span data-ttu-id="0095d-3297">Passport #</span><span class="sxs-lookup"><span data-stu-id="0095d-3297">Passport #</span></span> 
- <span data-ttu-id="0095d-3298">护照</span><span class="sxs-lookup"><span data-stu-id="0095d-3298">护照</span></span> 
- <span data-ttu-id="0095d-3299">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="0095d-3299">中華民國護照</span></span> 
- <span data-ttu-id="0095d-3300">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="0095d-3300">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="0095d-3301">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="0095d-3301">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3302">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3302">Format</span></span>

<span data-ttu-id="0095d-3303">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3303">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3304">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3304">Pattern</span></span>

<span data-ttu-id="0095d-3305">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3305">10 letters and digits:</span></span>
- <span data-ttu-id="0095d-3306">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-3306">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="0095d-3307">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3307">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3308">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3308">Checksum</span></span>

<span data-ttu-id="0095d-3309">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3309">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3310">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3310">Definition</span></span>

<span data-ttu-id="0095d-3311">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3311">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3312">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3312">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3313">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="0095d-3313">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3314">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3314">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="0095d-3315">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="0095d-3315">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="0095d-3316">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="0095d-3316">Resident Certificate</span></span> 
- <span data-ttu-id="0095d-3317">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="0095d-3317">Resident Cert</span></span> 
- <span data-ttu-id="0095d-3318">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="0095d-3318">Resident Cert.</span></span> 
- <span data-ttu-id="0095d-3319">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="0095d-3319">Identification card</span></span> 
- <span data-ttu-id="0095d-3320">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="0095d-3320">Alien Resident Certificate</span></span> 
- <span data-ttu-id="0095d-3321">ARCO</span><span class="sxs-lookup"><span data-stu-id="0095d-3321">ARC</span></span> 
- <span data-ttu-id="0095d-3322">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="0095d-3322">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="0095d-3323">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="0095d-3323">TARC</span></span> 
- <span data-ttu-id="0095d-3324">居留證</span><span class="sxs-lookup"><span data-stu-id="0095d-3324">居留證</span></span> 
- <span data-ttu-id="0095d-3325">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="0095d-3325">外僑居留證</span></span> 
- <span data-ttu-id="0095d-3326">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="0095d-3326">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="0095d-3327">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="0095d-3327">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3328">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3328">Format</span></span>

<span data-ttu-id="0095d-3329">13 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3329">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3330">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3330">Pattern</span></span>

<span data-ttu-id="0095d-3331">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3331">13 digits:</span></span>
- <span data-ttu-id="0095d-3332">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="0095d-3332">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="0095d-3333">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3333">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3334">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3334">Checksum</span></span>

<span data-ttu-id="0095d-3335">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3335">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3336">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3336">Definition</span></span>

<span data-ttu-id="0095d-3337">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3337">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3338">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3338">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3339">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="0095d-3339">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="0095d-3340">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3340">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3341">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3341">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3342">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3342">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="0095d-3343">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="0095d-3343">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="0095d-3344">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="0095d-3344">ID Number</span></span>
- <span data-ttu-id="0095d-3345">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="0095d-3345">Identification Number</span></span>
- <span data-ttu-id="0095d-3346">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="0095d-3346">บัตรประชาชน</span></span>
- <span data-ttu-id="0095d-3347">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="0095d-3347">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="0095d-3348">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="0095d-3348">บัตรประชาชน</span></span>
- <span data-ttu-id="0095d-3349">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="0095d-3349">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="0095d-3350">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="0095d-3350">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3351">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3351">Format</span></span>

<span data-ttu-id="0095d-3352">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3352">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3353">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3353">Pattern</span></span>

<span data-ttu-id="0095d-3354">11 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3354">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3355">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3355">Checksum</span></span>

<span data-ttu-id="0095d-3356">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3356">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3357">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3357">Definition</span></span>

<span data-ttu-id="0095d-3358">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3358">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3359">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3359">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3360">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="0095d-3360">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="0095d-3361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3362">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3362">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3363">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="0095d-3364">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="0095d-3364">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="0095d-3365">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="0095d-3365">TC Kimlik No</span></span>
- <span data-ttu-id="0095d-3366">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="0095d-3366">TC Kimlik numarası</span></span>
- <span data-ttu-id="0095d-3367">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="0095d-3367">Vatandaşlık numarası</span></span>
- <span data-ttu-id="0095d-3368">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="0095d-3368">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="0095d-p141">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3371">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3371">Format</span></span>

<span data-ttu-id="0095d-3372">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="0095d-3372">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3373">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3373">Pattern</span></span>

<span data-ttu-id="0095d-3374">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3374">18 letters and digits:</span></span>
- <span data-ttu-id="0095d-3375">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="0095d-3375">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="0095d-3376">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-3376">One digit</span></span> 
- <span data-ttu-id="0095d-3377">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-3377">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="0095d-3378">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="0095d-3378">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="0095d-3379">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3379">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3380">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3380">Checksum</span></span>

<span data-ttu-id="0095d-3381">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3382">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3382">Definition</span></span>

<span data-ttu-id="0095d-3383">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3383">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3384">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3384">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3385">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-3385">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="0095d-3386">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3386">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3387">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="0095d-3388">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="0095d-3388">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="0095d-3389">DVLA</span><span class="sxs-lookup"><span data-stu-id="0095d-3389">DVLA</span></span> 
- <span data-ttu-id="0095d-3390">light vans</span><span class="sxs-lookup"><span data-stu-id="0095d-3390">light vans</span></span> 
- <span data-ttu-id="0095d-3391">quadbikes</span><span class="sxs-lookup"><span data-stu-id="0095d-3391">quadbikes</span></span> 
- <span data-ttu-id="0095d-3392">motor cars</span><span class="sxs-lookup"><span data-stu-id="0095d-3392">motor cars</span></span> 
- <span data-ttu-id="0095d-3393">125cc</span><span class="sxs-lookup"><span data-stu-id="0095d-3393">125cc</span></span> 
- <span data-ttu-id="0095d-3394">sidecar</span><span class="sxs-lookup"><span data-stu-id="0095d-3394">sidecar</span></span> 
- <span data-ttu-id="0095d-3395">tricicli</span><span class="sxs-lookup"><span data-stu-id="0095d-3395">tricycles</span></span> 
- <span data-ttu-id="0095d-3396">moto</span><span class="sxs-lookup"><span data-stu-id="0095d-3396">motorcycles</span></span> 
- <span data-ttu-id="0095d-3397">photocard licence</span><span class="sxs-lookup"><span data-stu-id="0095d-3397">photocard licence</span></span> 
- <span data-ttu-id="0095d-3398">learner drivers</span><span class="sxs-lookup"><span data-stu-id="0095d-3398">learner drivers</span></span> 
- <span data-ttu-id="0095d-3399">licence holder</span><span class="sxs-lookup"><span data-stu-id="0095d-3399">licence holder</span></span> 
- <span data-ttu-id="0095d-3400">licence holders</span><span class="sxs-lookup"><span data-stu-id="0095d-3400">licence holders</span></span> 
- <span data-ttu-id="0095d-3401">driving licences</span><span class="sxs-lookup"><span data-stu-id="0095d-3401">driving licences</span></span> 
- <span data-ttu-id="0095d-3402">driving licence</span><span class="sxs-lookup"><span data-stu-id="0095d-3402">driving licence</span></span> 
- <span data-ttu-id="0095d-3403">dual control car</span><span class="sxs-lookup"><span data-stu-id="0095d-3403">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="0095d-p142">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="0095d-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3406">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3406">Format</span></span>

<span data-ttu-id="0095d-3407">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3407">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3408">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3408">Pattern</span></span>

<span data-ttu-id="0095d-3409">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="0095d-3409">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3410">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3410">Checksum</span></span>

<span data-ttu-id="0095d-3411">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3411">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3412">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3412">Definition</span></span>

<span data-ttu-id="0095d-3413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3414">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3414">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3415">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="0095d-3415">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3416">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3416">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="0095d-3417">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="0095d-3417">Keyword_uk_electoral</span></span>

- <span data-ttu-id="0095d-3418">council nomination</span><span class="sxs-lookup"><span data-stu-id="0095d-3418">council nomination</span></span> 
- <span data-ttu-id="0095d-3419">nomination form</span><span class="sxs-lookup"><span data-stu-id="0095d-3419">nomination form</span></span> 
- <span data-ttu-id="0095d-3420">electoral register</span><span class="sxs-lookup"><span data-stu-id="0095d-3420">electoral register</span></span> 
- <span data-ttu-id="0095d-3421">electoral roll</span><span class="sxs-lookup"><span data-stu-id="0095d-3421">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="0095d-p143">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="0095d-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3424">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3424">Format</span></span>

<span data-ttu-id="0095d-3425">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="0095d-3425">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3426">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3426">Pattern</span></span>

<span data-ttu-id="0095d-3427">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="0095d-3427">10-17 digits:</span></span>
- <span data-ttu-id="0095d-3428">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3428">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="0095d-3429">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="0095d-3429">A space</span></span> 
- <span data-ttu-id="0095d-3430">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3430">Three digits</span></span> 
- <span data-ttu-id="0095d-3431">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="0095d-3431">A space</span></span> 
- <span data-ttu-id="0095d-3432">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3432">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3433">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3433">Checksum</span></span>

<span data-ttu-id="0095d-3434">Sì</span><span class="sxs-lookup"><span data-stu-id="0095d-3434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3435">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3435">Definition</span></span>

<span data-ttu-id="0095d-3436">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3437">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3437">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3438">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-3438">One of the following is true:</span></span>
    - <span data-ttu-id="0095d-3439">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="0095d-3439">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="0095d-3440">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="0095d-3440">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="0095d-3441">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="0095d-3441">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="0095d-3442">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0095d-3442">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3443">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="0095d-3444">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="0095d-3444">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="0095d-3445">national health service</span><span class="sxs-lookup"><span data-stu-id="0095d-3445">national health service</span></span> 
- <span data-ttu-id="0095d-3446">NHS</span><span class="sxs-lookup"><span data-stu-id="0095d-3446">nhs</span></span> 
- <span data-ttu-id="0095d-3447">health services authority</span><span class="sxs-lookup"><span data-stu-id="0095d-3447">health services authority</span></span> 
- <span data-ttu-id="0095d-3448">health authority</span><span class="sxs-lookup"><span data-stu-id="0095d-3448">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="0095d-3449">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="0095d-3449">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="0095d-3450">patient id</span><span class="sxs-lookup"><span data-stu-id="0095d-3450">patient id</span></span> 
- <span data-ttu-id="0095d-3451">patient identification</span><span class="sxs-lookup"><span data-stu-id="0095d-3451">patient identification</span></span> 
- <span data-ttu-id="0095d-3452">patient no</span><span class="sxs-lookup"><span data-stu-id="0095d-3452">patient no</span></span> 
- <span data-ttu-id="0095d-3453">patient number</span><span class="sxs-lookup"><span data-stu-id="0095d-3453">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="0095d-3454">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="0095d-3454">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="0095d-3455">GP</span><span class="sxs-lookup"><span data-stu-id="0095d-3455">GP</span></span> 
- <span data-ttu-id="0095d-3456">DOB</span><span class="sxs-lookup"><span data-stu-id="0095d-3456">DOB</span></span> 
- <span data-ttu-id="0095d-3457">D. O. B</span><span class="sxs-lookup"><span data-stu-id="0095d-3457">D.O.B</span></span> 
- <span data-ttu-id="0095d-3458">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="0095d-3458">Date of Birth</span></span> 
- <span data-ttu-id="0095d-3459">Birth Date</span><span class="sxs-lookup"><span data-stu-id="0095d-3459">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="0095d-p144">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="0095d-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3462">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3462">Format</span></span>

<span data-ttu-id="0095d-3463">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="0095d-3463">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3464">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3464">Pattern</span></span>

<span data-ttu-id="0095d-3465">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="0095d-3465">Two possible patterns:</span></span>

- <span data-ttu-id="0095d-3466">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-3466">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="0095d-3467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3467">Six digits</span></span>
- <span data-ttu-id="0095d-3468">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0095d-3468">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="0095d-3469">O</span><span class="sxs-lookup"><span data-stu-id="0095d-3469">OR</span></span>

- <span data-ttu-id="0095d-3470">Due lettere</span><span class="sxs-lookup"><span data-stu-id="0095d-3470">Two letters</span></span>
- <span data-ttu-id="0095d-3471">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3471">A space or dash</span></span>
- <span data-ttu-id="0095d-3472">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3472">Two digits</span></span>
- <span data-ttu-id="0095d-3473">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3473">A space or dash</span></span>
- <span data-ttu-id="0095d-3474">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3474">Two digits</span></span>
- <span data-ttu-id="0095d-3475">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3475">A space or dash</span></span>
- <span data-ttu-id="0095d-3476">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3476">Two digits</span></span>
- <span data-ttu-id="0095d-3477">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3477">A space or dash</span></span>
- <span data-ttu-id="0095d-3478">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="0095d-3478">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3479">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3479">Checksum</span></span>

<span data-ttu-id="0095d-3480">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3480">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3481">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3481">Definition</span></span>

<span data-ttu-id="0095d-3482">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3482">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3483">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3483">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3484">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="0095d-3484">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="0095d-3485">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3485">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3486">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3486">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3487">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="0095d-3487">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3488">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3488">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="0095d-3489">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="0095d-3489">Keyword_uk_nino</span></span>

- <span data-ttu-id="0095d-3490">national insurance number</span><span class="sxs-lookup"><span data-stu-id="0095d-3490">national insurance number</span></span> 
- <span data-ttu-id="0095d-3491">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="0095d-3491">national insurance contributions</span></span> 
- <span data-ttu-id="0095d-3492">protection act</span><span class="sxs-lookup"><span data-stu-id="0095d-3492">protection act</span></span> 
- <span data-ttu-id="0095d-3493">Insurance</span><span class="sxs-lookup"><span data-stu-id="0095d-3493">insurance</span></span> 
- <span data-ttu-id="0095d-3494">social security number</span><span class="sxs-lookup"><span data-stu-id="0095d-3494">social security number</span></span> 
- <span data-ttu-id="0095d-3495">insurance application</span><span class="sxs-lookup"><span data-stu-id="0095d-3495">insurance application</span></span> 
- <span data-ttu-id="0095d-3496">medical application</span><span class="sxs-lookup"><span data-stu-id="0095d-3496">medical application</span></span> 
- <span data-ttu-id="0095d-3497">social insurance</span><span class="sxs-lookup"><span data-stu-id="0095d-3497">social insurance</span></span> 
- <span data-ttu-id="0095d-3498">medical attention</span><span class="sxs-lookup"><span data-stu-id="0095d-3498">medical attention</span></span> 
- <span data-ttu-id="0095d-3499">social security</span><span class="sxs-lookup"><span data-stu-id="0095d-3499">social security</span></span> 
- <span data-ttu-id="0095d-3500">great britain</span><span class="sxs-lookup"><span data-stu-id="0095d-3500">great britain</span></span> 
- <span data-ttu-id="0095d-3501">Insurance</span><span class="sxs-lookup"><span data-stu-id="0095d-3501">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="0095d-p145">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3504">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3504">Format</span></span>

<span data-ttu-id="0095d-3505">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3505">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3506">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3506">Pattern</span></span>

<span data-ttu-id="0095d-3507">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-3507">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3508">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3508">Checksum</span></span>

<span data-ttu-id="0095d-3509">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3509">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3510">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3510">Definition</span></span>

<span data-ttu-id="0095d-3511">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3511">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3512">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3512">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3513">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="0095d-3513">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3514">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3514">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="0095d-3515">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="0095d-3515">Keyword_passport</span></span>

- <span data-ttu-id="0095d-3516">Passport Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3516">Passport Number</span></span> 
- <span data-ttu-id="0095d-3517">Passport No</span><span class="sxs-lookup"><span data-stu-id="0095d-3517">Passport No</span></span> 
- <span data-ttu-id="0095d-3518">Passport#</span><span class="sxs-lookup"><span data-stu-id="0095d-3518">Passport #</span></span> 
- <span data-ttu-id="0095d-3519">Passaporto</span><span class="sxs-lookup"><span data-stu-id="0095d-3519">Passport#</span></span> 
- <span data-ttu-id="0095d-3520">PassportID</span><span class="sxs-lookup"><span data-stu-id="0095d-3520">PassportID</span></span> 
- <span data-ttu-id="0095d-3521">Passportno</span><span class="sxs-lookup"><span data-stu-id="0095d-3521">Passportno</span></span> 
- <span data-ttu-id="0095d-3522">passportnumber</span><span class="sxs-lookup"><span data-stu-id="0095d-3522">passportnumber</span></span> 
- <span data-ttu-id="0095d-3523">パスポート</span><span class="sxs-lookup"><span data-stu-id="0095d-3523">パスポート</span></span> 
- <span data-ttu-id="0095d-3524">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="0095d-3524">パスポート番号</span></span> 
- <span data-ttu-id="0095d-3525">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="0095d-3525">パスポートのNum</span></span> 
- <span data-ttu-id="0095d-3526">パスポート #</span><span class="sxs-lookup"><span data-stu-id="0095d-3526">パスポート＃</span></span> 
- <span data-ttu-id="0095d-3527">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-3527">Numéro de passeport</span></span> 
- <span data-ttu-id="0095d-3528">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="0095d-3528">Passeport n °</span></span> 
- <span data-ttu-id="0095d-3529">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="0095d-3529">Passeport Non</span></span> 
- <span data-ttu-id="0095d-3530">Passeport#</span><span class="sxs-lookup"><span data-stu-id="0095d-3530">Passeport #</span></span> 
- <span data-ttu-id="0095d-3531">Passeport</span><span class="sxs-lookup"><span data-stu-id="0095d-3531">Passeport#</span></span> 
- <span data-ttu-id="0095d-3532">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="0095d-3532">PasseportNon</span></span> 
- <span data-ttu-id="0095d-3533">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="0095d-3533">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="0095d-3534">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="0095d-3534">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3535">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3535">Format</span></span>

<span data-ttu-id="0095d-3536">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3536">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3537">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3537">Pattern</span></span>

<span data-ttu-id="0095d-3538">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="0095d-3538">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3539">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3539">Checksum</span></span>

<span data-ttu-id="0095d-3540">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3540">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3541">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3541">Definition</span></span>

<span data-ttu-id="0095d-3542">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3542">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3543">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3543">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3544">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="0095d-3544">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0095d-3545">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3545">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="0095d-3546">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="0095d-3546">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="0095d-3547">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3547">Checking Account Number</span></span> 
- <span data-ttu-id="0095d-3548">Checking Account</span><span class="sxs-lookup"><span data-stu-id="0095d-3548">Checking Account</span></span> 
- <span data-ttu-id="0095d-3549">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-3549">Checking Account #</span></span> 
- <span data-ttu-id="0095d-3550">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3550">Checking Acct Number</span></span> 
- <span data-ttu-id="0095d-3551">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-3551">Checking Acct #</span></span> 
- <span data-ttu-id="0095d-3552">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3552">Checking Acct No.</span></span> 
- <span data-ttu-id="0095d-3553">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3553">Checking Account No.</span></span> 
- <span data-ttu-id="0095d-3554">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3554">Bank Account Number</span></span> 
- <span data-ttu-id="0095d-3555">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-3555">Bank Account #</span></span> 
- <span data-ttu-id="0095d-3556">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3556">Bank Acct Number</span></span> 
- <span data-ttu-id="0095d-3557">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-3557">Bank Acct #</span></span> 
- <span data-ttu-id="0095d-3558">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3558">Bank Acct No.</span></span> 
- <span data-ttu-id="0095d-3559">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3559">Bank Account No.</span></span> 
- <span data-ttu-id="0095d-3560">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3560">Savings Account Number</span></span> 
- <span data-ttu-id="0095d-3561">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="0095d-3561">Savings Account.</span></span> 
- <span data-ttu-id="0095d-3562">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-3562">Savings Account #</span></span> 
- <span data-ttu-id="0095d-3563">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3563">Savings Acct Number</span></span> 
- <span data-ttu-id="0095d-3564">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-3564">Savings Acct #</span></span> 
- <span data-ttu-id="0095d-3565">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3565">Savings Acct No.</span></span> 
- <span data-ttu-id="0095d-3566">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3566">Savings Account No.</span></span> 
- <span data-ttu-id="0095d-3567">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3567">Debit Account Number</span></span> 
- <span data-ttu-id="0095d-3568">Debit Account</span><span class="sxs-lookup"><span data-stu-id="0095d-3568">Debit Account</span></span> 
- <span data-ttu-id="0095d-3569">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="0095d-3569">Debit Account #</span></span> 
- <span data-ttu-id="0095d-3570">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="0095d-3570">Debit Acct Number</span></span> 
- <span data-ttu-id="0095d-3571">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="0095d-3571">Debit Acct #</span></span> 
- <span data-ttu-id="0095d-3572">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3572">Debit Acct No.</span></span> 
- <span data-ttu-id="0095d-3573">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="0095d-3573">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="0095d-3574">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0095d-3574">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3575">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3575">Format</span></span>

<span data-ttu-id="0095d-3576">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="0095d-3576">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3577">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3577">Pattern</span></span>

<span data-ttu-id="0095d-3578">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="0095d-3578">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="0095d-3579">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="0095d-3579">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="0095d-3580">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="0095d-3580">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3581">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3581">Checksum</span></span>

<span data-ttu-id="0095d-3582">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3582">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3583">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3583">Definition</span></span>

<span data-ttu-id="0095d-3584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3585">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3585">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3586">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="0095d-3586">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="0095d-3587">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-3587">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="0095d-3588">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3588">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3589">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3589">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3590">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="0095d-3590">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="0095d-3591">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="0095d-3591">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="0095d-3592">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="0095d-3592">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3593">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3593">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="0095d-3594">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="0095d-3594">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="0095d-3595">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-3595">DL</span></span> 
- <span data-ttu-id="0095d-3596">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-3596">DLS</span></span> 
- <span data-ttu-id="0095d-3597">CDL</span><span class="sxs-lookup"><span data-stu-id="0095d-3597">CDL</span></span> 
- <span data-ttu-id="0095d-3598">CDLS</span><span class="sxs-lookup"><span data-stu-id="0095d-3598">CDLS</span></span> 
- <span data-ttu-id="0095d-3599">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3599">ID</span></span> 
- <span data-ttu-id="0095d-3600">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3600">IDs</span></span> 
- <span data-ttu-id="0095d-3601">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-3601">DL#</span></span> 
- <span data-ttu-id="0095d-3602">DLS</span><span class="sxs-lookup"><span data-stu-id="0095d-3602">DLS#</span></span> 
- <span data-ttu-id="0095d-3603">CDL</span><span class="sxs-lookup"><span data-stu-id="0095d-3603">CDL#</span></span> 
- <span data-ttu-id="0095d-3604">CDLS</span><span class="sxs-lookup"><span data-stu-id="0095d-3604">CDLS#</span></span> 
- <span data-ttu-id="0095d-3605">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3605">ID#</span></span>
- <span data-ttu-id="0095d-3606">ID</span><span class="sxs-lookup"><span data-stu-id="0095d-3606">IDs#</span></span> 
- <span data-ttu-id="0095d-3607">ID number</span><span class="sxs-lookup"><span data-stu-id="0095d-3607">ID number</span></span> 
- <span data-ttu-id="0095d-3608">ID numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-3608">ID numbers</span></span> 
- <span data-ttu-id="0095d-3609">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="0095d-3609">LIC</span></span> 
- <span data-ttu-id="0095d-3610">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="0095d-3610">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="0095d-3611">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="0095d-3611">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="0095d-3612">DriverLic</span><span class="sxs-lookup"><span data-stu-id="0095d-3612">DriverLic</span></span> 
- <span data-ttu-id="0095d-3613">DriverLics</span><span class="sxs-lookup"><span data-stu-id="0095d-3613">DriverLics</span></span> 
- <span data-ttu-id="0095d-3614">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-3614">DriverLicense</span></span> 
- <span data-ttu-id="0095d-3615">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3615">DriverLicenses</span></span> 
- <span data-ttu-id="0095d-3616">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-3616">Driver Lic</span></span> 
- <span data-ttu-id="0095d-3617">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-3617">Driver Lics</span></span> 
- <span data-ttu-id="0095d-3618">Driver License</span><span class="sxs-lookup"><span data-stu-id="0095d-3618">Driver License</span></span> 
- <span data-ttu-id="0095d-3619">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3619">Driver Licenses</span></span> 
- <span data-ttu-id="0095d-3620">DriversLic</span><span class="sxs-lookup"><span data-stu-id="0095d-3620">DriversLic</span></span> 
- <span data-ttu-id="0095d-3621">DriversLics</span><span class="sxs-lookup"><span data-stu-id="0095d-3621">DriversLics</span></span> 
- <span data-ttu-id="0095d-3622">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="0095d-3622">DriversLicense</span></span> 
- <span data-ttu-id="0095d-3623">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3623">DriversLicenses</span></span> 
- <span data-ttu-id="0095d-3624">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-3624">Drivers Lic</span></span> 
- <span data-ttu-id="0095d-3625">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-3625">Drivers Lics</span></span> 
- <span data-ttu-id="0095d-3626">Drivers License</span><span class="sxs-lookup"><span data-stu-id="0095d-3626">Drivers License</span></span> 
- <span data-ttu-id="0095d-3627">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3627">Drivers Licenses</span></span> 
- <span data-ttu-id="0095d-3628">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-3628">Driver'Lic</span></span> 
- <span data-ttu-id="0095d-3629">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-3629">Driver'Lics</span></span> 
- <span data-ttu-id="0095d-3630">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-3630">Driver'License</span></span> 
- <span data-ttu-id="0095d-3631">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3631">Driver'Licenses</span></span> 
- <span data-ttu-id="0095d-3632">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-3632">Driver' Lic</span></span> 
- <span data-ttu-id="0095d-3633">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-3633">Driver' Lics</span></span> 
- <span data-ttu-id="0095d-3634">Driver' License</span><span class="sxs-lookup"><span data-stu-id="0095d-3634">Driver' License</span></span> 
- <span data-ttu-id="0095d-3635">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3635">Driver' Licenses</span></span>
- <span data-ttu-id="0095d-3636">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="0095d-3636">Driver'sLic</span></span> 
- <span data-ttu-id="0095d-3637">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="0095d-3637">Driver'sLics</span></span> 
- <span data-ttu-id="0095d-3638">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-3638">Driver'sLicense</span></span> 
- <span data-ttu-id="0095d-3639">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3639">Driver'sLicenses</span></span> 
- <span data-ttu-id="0095d-3640">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="0095d-3640">Driver's Lic</span></span> 
- <span data-ttu-id="0095d-3641">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="0095d-3641">Driver's Lics</span></span> 
- <span data-ttu-id="0095d-3642">Driver's License</span><span class="sxs-lookup"><span data-stu-id="0095d-3642">Driver's License</span></span> 
- <span data-ttu-id="0095d-3643">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3643">Driver's Licenses</span></span> 
- <span data-ttu-id="0095d-3644">identification number</span><span class="sxs-lookup"><span data-stu-id="0095d-3644">identification number</span></span> 
- <span data-ttu-id="0095d-3645">identification numbers</span><span class="sxs-lookup"><span data-stu-id="0095d-3645">identification numbers</span></span> 
- <span data-ttu-id="0095d-3646">identification#</span><span class="sxs-lookup"><span data-stu-id="0095d-3646">identification #</span></span> 
- <span data-ttu-id="0095d-3647">id card</span><span class="sxs-lookup"><span data-stu-id="0095d-3647">id card</span></span> 
- <span data-ttu-id="0095d-3648">id cards</span><span class="sxs-lookup"><span data-stu-id="0095d-3648">id cards</span></span> 
- <span data-ttu-id="0095d-3649">identification card</span><span class="sxs-lookup"><span data-stu-id="0095d-3649">identification card</span></span> 
- <span data-ttu-id="0095d-3650">identification cards</span><span class="sxs-lookup"><span data-stu-id="0095d-3650">identification cards</span></span> 
- <span data-ttu-id="0095d-3651">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-3651">DriverLic#</span></span> 
- <span data-ttu-id="0095d-3652">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-3652">DriverLics#</span></span> 
- <span data-ttu-id="0095d-3653">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-3653">DriverLicense#</span></span> 
- <span data-ttu-id="0095d-3654">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-3654">DriverLicenses#</span></span> 
- <span data-ttu-id="0095d-3655">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-3655">Driver Lic#</span></span> 
- <span data-ttu-id="0095d-3656">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-3656">Driver Lics#</span></span> 
- <span data-ttu-id="0095d-3657">Driver License#</span><span class="sxs-lookup"><span data-stu-id="0095d-3657">Driver License#</span></span> 
- <span data-ttu-id="0095d-3658">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-3658">Driver Licenses#</span></span> 
- <span data-ttu-id="0095d-3659">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-3659">DriversLic#</span></span> 
- <span data-ttu-id="0095d-3660">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-3660">DriversLics#</span></span> 
- <span data-ttu-id="0095d-3661">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="0095d-3661">DriversLicense#</span></span> 
- <span data-ttu-id="0095d-3662">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-3662">DriversLicenses#</span></span> 
- <span data-ttu-id="0095d-3663">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-3663">Drivers Lic#</span></span> 
- <span data-ttu-id="0095d-3664">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-3664">Drivers Lics#</span></span> 
- <span data-ttu-id="0095d-3665">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="0095d-3665">Drivers License#</span></span> 
- <span data-ttu-id="0095d-3666">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-3666">Drivers Licenses#</span></span> 
- <span data-ttu-id="0095d-3667">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="0095d-3667">Driver'Lic#</span></span> 
- <span data-ttu-id="0095d-3668">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="0095d-3668">Driver'Lics#</span></span> 
- <span data-ttu-id="0095d-3669">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="0095d-3669">Driver'License#</span></span> 
- <span data-ttu-id="0095d-3670">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="0095d-3670">Driver'Licenses#</span></span> 
- <span data-ttu-id="0095d-3671">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-3671">Driver' Lic#</span></span> 
- <span data-ttu-id="0095d-3672">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-3672">Driver' Lics#</span></span> 
- <span data-ttu-id="0095d-3673">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="0095d-3673">Driver' License#</span></span> 
- <span data-ttu-id="0095d-3674">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-3674">Driver' Licenses#</span></span> 
- <span data-ttu-id="0095d-3675">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="0095d-3675">Driver'sLic#</span></span> 
- <span data-ttu-id="0095d-3676">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="0095d-3676">Driver'sLics#</span></span> 
- <span data-ttu-id="0095d-3677">Secondola</span><span class="sxs-lookup"><span data-stu-id="0095d-3677">Driver'sLicense#</span></span> 
- <span data-ttu-id="0095d-3678">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="0095d-3678">Driver'sLicenses#</span></span> 
- <span data-ttu-id="0095d-3679">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="0095d-3679">Driver's Lic#</span></span> 
- <span data-ttu-id="0095d-3680">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="0095d-3680">Driver's Lics#</span></span> 
- <span data-ttu-id="0095d-3681">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="0095d-3681">Driver's License#</span></span> 
- <span data-ttu-id="0095d-3682">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="0095d-3682">Driver's Licenses#</span></span> 
- <span data-ttu-id="0095d-3683">id card#</span><span class="sxs-lookup"><span data-stu-id="0095d-3683">id card#</span></span> 
- <span data-ttu-id="0095d-3684">id cards#</span><span class="sxs-lookup"><span data-stu-id="0095d-3684">id cards#</span></span> 
- <span data-ttu-id="0095d-3685">identification card#</span><span class="sxs-lookup"><span data-stu-id="0095d-3685">identification card#</span></span> 
- <span data-ttu-id="0095d-3686">identification cards#</span><span class="sxs-lookup"><span data-stu-id="0095d-3686">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="0095d-3687">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="0095d-3687">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="0095d-3688">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="0095d-3688">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="0095d-3689">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="0095d-3689">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="0095d-3690">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="0095d-3690">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3691">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3691">Format</span></span>

<span data-ttu-id="0095d-3692">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0095d-3692">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3693">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3693">Pattern</span></span>

<span data-ttu-id="0095d-3694">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-3694">Formatted:</span></span>
- <span data-ttu-id="0095d-3695">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="0095d-3695">The digit "9"</span></span> 
- <span data-ttu-id="0095d-3696">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3696">Two digits</span></span> 
- <span data-ttu-id="0095d-3697">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3697">A space or dash</span></span> 
- <span data-ttu-id="0095d-3698">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="0095d-3698">A "7" or "8"</span></span> 
- <span data-ttu-id="0095d-3699">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0095d-3699">A digit</span></span> 
- <span data-ttu-id="0095d-3700">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="0095d-3700">A space, or dash</span></span> 
- <span data-ttu-id="0095d-3701">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3701">Four digits</span></span>

<span data-ttu-id="0095d-3702">Formattato</span><span class="sxs-lookup"><span data-stu-id="0095d-3702">Unformatted:</span></span>
- <span data-ttu-id="0095d-3703">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="0095d-3703">The digit "9"</span></span> 
- <span data-ttu-id="0095d-3704">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3704">Two digits</span></span> 
- <span data-ttu-id="0095d-3705">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="0095d-3705">A "7" or "8"</span></span> 
- <span data-ttu-id="0095d-3706">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="0095d-3706">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3707">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3707">Checksum</span></span>

<span data-ttu-id="0095d-3708">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3708">No</span></span>

### <a name="definition"></a><span data-ttu-id="0095d-3709">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3709">Definition</span></span>

<span data-ttu-id="0095d-3710">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3710">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3711">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3711">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3712">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-3712">At least one of the following is true:</span></span>
    - <span data-ttu-id="0095d-3713">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="0095d-3713">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="0095d-3714">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-3714">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="0095d-3715">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-3715">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="0095d-3716">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="0095d-3716">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="0095d-3717">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3717">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3718">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3718">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3719">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0095d-3719">At least one of the following is true:</span></span>
    - <span data-ttu-id="0095d-3720">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="0095d-3720">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="0095d-3721">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-3721">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="0095d-3722">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="0095d-3722">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3723">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3723">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="0095d-3724">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="0095d-3724">Keyword_itin</span></span>

- <span data-ttu-id="0095d-3725">contribuente</span><span class="sxs-lookup"><span data-stu-id="0095d-3725">taxpayer</span></span> 
- <span data-ttu-id="0095d-3726">tax id</span><span class="sxs-lookup"><span data-stu-id="0095d-3726">tax id</span></span> 
- <span data-ttu-id="0095d-3727">tax identification</span><span class="sxs-lookup"><span data-stu-id="0095d-3727">tax identification</span></span> 
- <span data-ttu-id="0095d-3728">Itin</span><span class="sxs-lookup"><span data-stu-id="0095d-3728">itin</span></span> 
- <span data-ttu-id="0095d-3729">SSN</span><span class="sxs-lookup"><span data-stu-id="0095d-3729">ssn</span></span> 
- <span data-ttu-id="0095d-3730">latta</span><span class="sxs-lookup"><span data-stu-id="0095d-3730">tin</span></span> 
- <span data-ttu-id="0095d-3731">social security</span><span class="sxs-lookup"><span data-stu-id="0095d-3731">social security</span></span> 
- <span data-ttu-id="0095d-3732">tax payer</span><span class="sxs-lookup"><span data-stu-id="0095d-3732">tax payer</span></span> 
- <span data-ttu-id="0095d-3733">itins</span><span class="sxs-lookup"><span data-stu-id="0095d-3733">itins</span></span> 
- <span data-ttu-id="0095d-3734">taxid</span><span class="sxs-lookup"><span data-stu-id="0095d-3734">taxid</span></span> 
- <span data-ttu-id="0095d-3735">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="0095d-3735">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="0095d-3736">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="0095d-3736">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="0095d-3737">License</span><span class="sxs-lookup"><span data-stu-id="0095d-3737">License</span></span> 
- <span data-ttu-id="0095d-3738">DL</span><span class="sxs-lookup"><span data-stu-id="0095d-3738">DL</span></span> 
- <span data-ttu-id="0095d-3739">DOB</span><span class="sxs-lookup"><span data-stu-id="0095d-3739">DOB</span></span> 
- <span data-ttu-id="0095d-3740">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="0095d-3740">Birthdate</span></span> 
- <span data-ttu-id="0095d-3741">Compleanno</span><span class="sxs-lookup"><span data-stu-id="0095d-3741">Birthday</span></span> 
- <span data-ttu-id="0095d-3742">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="0095d-3742">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="0095d-3743">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="0095d-3743">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="0095d-3744">Formato</span><span class="sxs-lookup"><span data-stu-id="0095d-3744">Format</span></span>

<span data-ttu-id="0095d-3745">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="0095d-3745">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="0095d-3746">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="0095d-3746">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="0095d-3747">Modello</span><span class="sxs-lookup"><span data-stu-id="0095d-3747">Pattern</span></span>

<span data-ttu-id="0095d-3748">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="0095d-3748">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="0095d-3749">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="0095d-3749">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="0095d-3750">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="0095d-3750">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="0095d-3751">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="0095d-3751">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="0095d-3752">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="0095d-3752">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="0095d-3753">Checksum</span><span class="sxs-lookup"><span data-stu-id="0095d-3753">Checksum</span></span>

<span data-ttu-id="0095d-3754">No</span><span class="sxs-lookup"><span data-stu-id="0095d-3754">No</span></span>


### <a name="definition"></a><span data-ttu-id="0095d-3755">Definizione</span><span class="sxs-lookup"><span data-stu-id="0095d-3755">Definition</span></span>

<span data-ttu-id="0095d-3756">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3757">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3757">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3758">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="0095d-3758">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="0095d-3759">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3759">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3760">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3760">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3761">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="0095d-3761">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="0095d-3762">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3762">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3763">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3763">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3764">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="0095d-3764">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="0095d-3765">La funzione Func_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3765">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="0095d-3766">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0095d-3766">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="0095d-3767">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3767">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="0095d-3768">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="0095d-3768">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="0095d-3769">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="0095d-3769">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="0095d-3770">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0095d-3770">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="0095d-3771">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="0095d-3771">Keyword_ssn</span></span>

- <span data-ttu-id="0095d-3772">Social Security</span><span class="sxs-lookup"><span data-stu-id="0095d-3772">Social Security</span></span> 
- <span data-ttu-id="0095d-3773">Social Security#</span><span class="sxs-lookup"><span data-stu-id="0095d-3773">Social Security#</span></span> 
- <span data-ttu-id="0095d-3774">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="0095d-3774">Soc Sec</span></span> 
- <span data-ttu-id="0095d-3775">SSN</span><span class="sxs-lookup"><span data-stu-id="0095d-3775">SSN</span></span> 
- <span data-ttu-id="0095d-3776">SNSS</span><span class="sxs-lookup"><span data-stu-id="0095d-3776">SSNS</span></span> 
- <span data-ttu-id="0095d-3777">SSN</span><span class="sxs-lookup"><span data-stu-id="0095d-3777">SSN#</span></span> 
- <span data-ttu-id="0095d-3778">SS</span><span class="sxs-lookup"><span data-stu-id="0095d-3778">SS#</span></span> 
- <span data-ttu-id="0095d-3779">SSID</span><span class="sxs-lookup"><span data-stu-id="0095d-3779">SSID</span></span> 
   

